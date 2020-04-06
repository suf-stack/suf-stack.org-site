<template>
  <div>
    <section class="section">
      <div class="container">
        <h1 class="title">What is the SUF Stack?</h1>
        <h2 class="subtitle">by <a href="https://bradito.me/">Brad Ito</a></h2>
        <p>
          I've been building web apps since the turn of the century, and jumped between many languages
          and frameworks over time - never quite happy with the trade-offs between users, creators, and
          deployment infrastructure.  I came up with this architecture about two years ago and have
          used it to build several production webapps, finding that the mix of technologies are now
          complementing each other without a need for trade-offs.
        </p>
        
        <p>
          This site is about sharing the SUF Stack architecture with other creators to help enable
          them to create great things.
        </p>
        
        <h2 class="subtitle">Some History and Context</h2>
        
        <p>
          The first websites were hand-coded HTML files hosted on individual web servers.  For creators
          of those sites, it often meant lots of markup repetition and other inefficiencies.  For users
          of such sites, the content would tend to get stale and lose relevance.  For the system administrators
          in charge of the infrastructure, there would be a worry about keeping the sites online, especially
          when there would be a surge in users for a popular site.
        </p>
        
        <p>
          Next came the first generation of web applications.  These provided dyamic content via server-side
          code, and unlocked the web as a vehicle for eCommerce, search engines, and more.  Users were
          delighted by the new functionality, and would tolerate the sometimes slow loading times.  Creators
          were empowered by their new capabilities and eagerly dove into a raft of new languages and frameworks.
          However the infrastructure demands became complex and error-prone.
        </p>
        
        <p>
          Single-page apps emerged next, offering much richer experiences for users by leveraging
          browser capabilities to react quickly to user inputs, and unlock emerging web standards.
          However, for creators this created the need for different languages and technologies for the
          frontend and backend, resulting in diverging skills and split teams.  Infrastructure needs,
          which had only started to simplify via public cloud providers, became complex balances
          between versioned deployments of the frontend and backend, and the unique scaling needs of each.
        </p>
        
        <p>
          The next set of web application architectures solve specific weaknesses.  Universal apps
          which render content both on the server and in the browser aid in search discoverability and speed
          but suffer from complex deployments.  Static site generators sacrifice dynamic backends to
          optimize for distributed and cached infrastructure, and fast page speeds for the user.  The Jamstack
          adds more dynamic content to static sites, but still suffers from a lack of a backend with priviledged
          code.
        </p>
        
        <h2 class="subtitle">Serverless</h2>
        
        <p>
          A SUF-Stack App should be optimized for its deployment on the cloud.  This means optimizing
          costs to only pay for the compute which one is using.  And it should mean worry free server provisioning
          and maintenance.
        </p>
        
        <p>
          We've been using the 
          <a href="https://serverless.com/" rel="nofollow noopener" target="_blank">Serverless Framework</a>.
          It configures deployment of apps to deploy as HTTP endpoints that call function-as-a-service (FaaS)
          code on a variety of cloud providers.  It also provides a rich ecosystem of plugins and tools
          which one can leverage to expand its capabilities.  In the AWS context, it actually configures
          AWS CloudFormation, and can thus be extended to configure pretty much anything on AWS.
        </p>
        
        <p>
          The starter template deploys to AWS Lambda, behind AWS API Gateway.  It also deploys static
          assets on S3 (using content-based hashes in names to bust caches) and leverages CloudFront
          to both serve content close to users and
          to only send HTTP requests which need a dynamic evaluation to the backend in Lambda.
          CloudFront is configured to use HTTP/2 for faster transport, and to take advantage of compression
          to further reduce bandwidth usage.
          Furthermore, logging is written to AWS CloudWatch in JSON, for parsing in
          CloudWatch Insights dashboards.
        </p>
        
        <p>
          FaaS-based HTTP endpoints have a known issue of taking longer to serve requests
          if the function has not been called for a while.  To solve this cold-start problem, and to
          provide better uptime monitoring, we configure an AWS Route 53 HealthCheck to repeatedly query
          the backend from a variety of global locations which keeps the lambda function warm.
          We also deploy the application as a single function to simplify routing and so that there is
          only a single function to keep warm.
        </p>
        
        <b-message title="Known Limitations" :closable="false">
          <p>
            - Web requests must not take longer than a few seconds (30 seconds for AWS).
            This is also a good practice for human-facing user experience, and you should consider
            a different backend infrastructure to run long-running processes.
          </p>
          <p>
            - The bundled application should not be too large (250MB for AWS).  Which means that your
            application code should just be code.  Data should be stored in something like a database.
            And images and video should be stored elsewhere and linked in to the application.
            I'd recommend a service like <a href="https://cloudinary.com/">cloudinary</a> for images
            and video.
          </p>
          <p>
            - Streaming HTTP services like web sockets and WebRTC will require, a different, more
            specialized, deployment.
          </p>
        </b-message>
        
        <h2 class="subtitle">Universal</h2>
        
        <p>
          A SUF-Stack app should be optimized for its users.  This means being a universal application
          where the first page has HTML generated on the server, for the fastest possible render,
          and where subsequent pages are generated on the browser, leveraging the techniques
          from single-page apps.  Being universal helps with automated parsing of your web pages, as
          for search engines and other web spiders.
        </p>
        
        <p>
          In addition, web application code should be delivered with long cache times to speed
          up later visits to the web application, with those bundles named automatically with
          hashes of their content so as to do cache busting in a natural manner.
        </p>
        
        <p>
          The starter template uses
          <a href="https://nuxtjs.org/">Nuxt.js</a> to orchestrate <a href="https://webpack.js.org/">webpack</a>
          to build universal applications.  This means that you just need to focus on writing your app
          and Nuxt.js will take care of wiring it up into a universal app, without you having to worry
          about how to make that happen.  There are some subtleties about making relative URL resolution
          consistent which the starter template takes care of for you.
        </p>
        
        <p>
          Another great feature that Nuxt.js exposes from webpack is the
          <a href="https://nuxtjs.org/api/configuration-build/#analyze">analyze</a> build option
          which lets one visualize how many bytes your code and library dependencies are using.
          One should use this to guide optimizing your web app size to speed things up for your users.
          There is also a great <a href="https://github.com/nuxt-community/awesome-nuxt">variety</a>
          of Nuxt.js modules which one can use.
        </p>
        
        <b-message title="Known Limitations" :closable="false">
          <p>
            Some UX-related packages only work in the browser, and may need to be loaded
            via the Vue <a href="https://vuejs.org/v2/api/#mounted">mounted</a> hook
          </p>
          <p>
            Some bugs may be harder to trace when your app is in universal mode.  You may need
            to temporarily <a href="https://nuxtjs.org/api/configuration-mode">change</a>
            your app to a single-page-app to debug.
          </p>
          <p>
            Universal apps run code every time that a page is requested.  This lets a web application
            show different content to different viewers, but it is not as efficient as a static page.
            If you are only rendering static content, you don't need to build a web app, and should
            use a <a href="https://www.staticgen.com/">static site generator</a>.
          </p>
        </b-message>
        
        <h2 class="subtitle">Full Stack</h2>
        
        <p>
          A SUF-Stack app should be optimized for developers.  That is, it should minimize the
          number of languages needed to write the full application to just Javascript (or Typescript).
        </p>
        
        <p>
          It should have a clearly defined frontend using a mature framework, so that one
          can count on finding answers to common problems.  There should also be features such
          as hot-reloading during development and a robust set of options for CSS and UX component
          frameworks.
        </p>
        
        <p>
          A major differentiator between a SUF-Stack web app and a Jamstack app is the use of a
          proper backend in SUF.  This means either Express.js or Koa.js or similar backend designed
          to be run server-side, with access to secret credentials, and priviledged code.  It's often
          simpler and easier to just write your own backend API routes using Node.js code, especially when interacting
          with databases and external APIs.
        </p>
        
        <p>
          The starter template puts backend code into its own folder, and optimizes the development experience
          for it.  The backend is deployed as part of the same serverless function as the frontend
          but with priviledged values (secrets) available to it via environment variables.  One can develop
          the frontend and backend for a given feature in the same code base, and ensure that they are always
          deployed in sync.  For development, the frontend and the backend execute locally for a
          fully functional local development environment.
        </p>
        
        <b-message title="Known Limitations" :closable="false">
          <p>
            Not all developers or applications need a backend.  For those situations, it may not be
            necessary to use the SUF-Stack.
          </p>
        </b-message>
        
        <h2 class="subtitle">Next Steps</h2>
        
        <p>
          If the SUF-stack sounds like what you need, then you can
          <nuxt-link to="/get-started">get started</nuxt-link> today!
        </p>
      </div>
    </section>
  </div>
</template>
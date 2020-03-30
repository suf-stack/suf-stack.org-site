<template>
  <div>
    <section class="section">
      <div class="container">
        <h1 class="title">What is SUF Stack?</h1>
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
        
        <h2 class="subtitle">Some History</h2>
        
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
      </div>
    </section>
  </div>
</template>
<template>
  <div class="home-page">
    <section>
      <b-carousel
        :animated="'slide'"
        :autplay="true"
        :pause-hover="true"
        :pause-info="false"
        :repeat="true"
        :interval="5000"
      >
        <b-carousel-item>
          <section class="hero is-medium">
            <div class="hero-body has-text-centered item-1">
              <h1 class="is-size-1-desktop is-size-3-touch has-text-weight-semibold">
                Serverless
              </h1>
              <h3 class="is-size-4">Deploy without worrying about servers</h3>
            </div>
          </section>
        </b-carousel-item>
        <b-carousel-item>
          <section class="hero is-medium">
            <div class="hero-body has-text-centered item-2">
              <h1 class="is-size-1-desktop is-size-3-touch has-text-weight-semibold">
                Universal
              </h1>
              <h3 class="is-size-4">Optimize rendering for users and search engines</h3>
            </div>
          </section>
        </b-carousel-item>
        <b-carousel-item>
          <section class="hero is-medium">
            <div class="hero-body has-text-centered item-3">
              <h1 class="is-size-1-desktop is-size-3-touch has-text-weight-semibold">
                Full Stack
              </h1>
              <h3 class="is-size-4">Develop frontend and backend together</h3>
            </div>
          </section>
        </b-carousel-item>
      </b-carousel>
    </section>
    <section class="section">
      <div class="container">
        <h1 class="title">Serverless + Universal + Full Stack = SUF</h1>
        <p>
          The SUF-Stack is an opinionated way to build web apps without compromise.
          It's a new <em>architecture</em> (not a framework)
          which combines several modern technologies in a way which is both powerful and easy to use.
        </p>
        <p>
          To get you started, we have created a few free and open source
          <nuxt-link to="/get-started">templates</nuxt-link>.
          Contributors are welcome!
        </p>
        
        <hr />
        
        <h3 class="subtitle">
          Technology Choices:
        </h3>
        <div class="content">
          <table>
            <thead>
              <tr>
                <th>Cloud Provider</th>
                <th>Frontend</th>
                <th>Backend</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td class="nowrap">
                  <a href="https://aws.amazon.com/lambda/" target="_blank">AWS Lambda</a>
                  <b-icon title="implemented" icon="checkbox-marked-circle-outline"></b-icon>
                </td>
                <td class="nowrap">
                  <a href="https://nuxtjs.org/" target="_blank">Nuxt.js</a> /
                  <a href="https://vuejs.org/" target="_blank">Vue.js</a>
                  <b-icon title="implemented" icon="checkbox-marked-circle-outline"></b-icon>
                </td>
                <td class="nowrap">
                  <a href="https://koajs.com/" target="_blank">Koa.js</a>
                  <b-icon title="implemented" icon="checkbox-marked-circle-outline"></b-icon>
                </td>
              </tr>
              <tr>
                <td class="nowrap">
                  <a href="https://azure.microsoft.com/en-us/services/functions/" target="_blank">Azure Functions</a>
                </td>
                <td class="nowrap">
                  <a href="https://nextjs.org/" target="_blank" rel="nofollow">Next.js</a> /
                  <a href="https://reactjs.org/" target="_blank" rel="nofollow">React.js</a>
                </td>
                <td class="nowrap">
                  <a href="https://expressjs.com/" target="_blank">Express.js</a>
                </td>
              </tr>
              <tr>
                <td>
                  <a href="https://serverless.com/framework/docs/providers/" target="_blank">
                    see Serverless Framework providers
                  </a>
                </td>
                <td>
                  Other?
                </td>
                <td>
                  Fastify, Feathers, Hapi, etc
                </td>
              </tr>
            </tbody>
          </table>
          <p>
            * not all technologies yet implemented in templates.
          </p>
          <p>
            Also built upon:
            <a href="https://serverless.com/framework/docs/" target="_blank">Serverless Framework</a>,
            <a href="https://webpack.js.org/" target="_blank">Webpack.js</a>
          </p>
        </div>
      </div>
    </section>
    <section class="section has-background-info">
      <div class="container">
        <div class="tile is-ancestor">
          <div class="tile is-parent">
            <article class="tile is-child box">
              <b-icon
                icon="cloud-outline"
                size="is-large">
              </b-icon>
              <h1 class="title">
                <nuxt-link to="/about">
                  Serverless
                </nuxt-link>
              </h1>
              <div class="content">
                <p>
                  Optimize for the cloud.
                </p>
                <p>
                  Deploy your app without worrying about maintaining or scaling servers.
                </p>
              </div>
            </article>
          </div>
          <div class="tile is-parent">
            <article class="tile is-child box">
              <b-icon
                icon="vector-difference"
                size="is-large">
              </b-icon>
              <h1 class="title">
                <nuxt-link to="/about">
                  Universal
                </nuxt-link>
              </h1>
              <div class="content">
                <p>
                  Optimize for users.
                </p>
                <p>
                  Ensure your content is optimized for speed and the semantic web (and SEO)
                </p>
              </div>
            </article>
          </div>
          <div class="tile is-parent">
            <article class="tile is-child box">
              <b-icon
                icon="language-javascript"
                size="is-large">
              </b-icon>
              <h1 class="title">
                <nuxt-link to="/about">
                  Full Stack
                </nuxt-link>
              </h1>
              <div class="content">
                <p>
                  Optimize for developers.
                </p>
                <p>
                  Use a "real" frontend and backend, written and deployed together seamlessly
                </p>
              </div>
            </article>
          </div>
        </div>
      </div>
    </section>
    <section class="section">
      <div class="container">
        <p class="is-size-3 has-text-centered">
          <nuxt-link to="/about">Read more</nuxt-link>
          about the SUF Stack...
        </p>
      </div>
    </section>
  </div>
</template>

<script>

export default {
  head: {
    title: 'SUF-Stack',
    titleTemplate: '%s',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'SUF-Stack - Modern web app architecture. Serverless, Universal, Full Stack'
      }
    ],
  }
}
</script>

<style lang="scss">
.home-page {
  font-size: 1.25rem;
  
  .item-1 {
    color: black;
    background-color: #74dbef;
  }
  .item-2 {
    color: #eff0f4;
    background-color: #0074e4;
  }
  .item-3 {
    color: #eff0f4;
    background-color: #264e86;
  }
}
</style>

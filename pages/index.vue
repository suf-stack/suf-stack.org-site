<template>
  <div class="home-page">
    <section>
      <b-carousel
        :animated="'slide'"
        :autplay="true"
        :pause-hover="true"
        :pause-info="false"
        :repeat="true"
        :interval="2300"
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
          Build web applications without compromise with the
          SUF Stack.
          This new architecture combines several modern technologies in a way which is both powerful and easy to use.
        </p>
        <p>
          To get you started, we have created a few free and open source
          <nuxt-link to="/get-started">templates</nuxt-link>.
          Contributors are welcome!
        </p>
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
              <h1 class="title">Serverless</h1>
              <div class="content">
                <p>
                  Deploy your app without worrying about maintaining or scaling servers.
                </p>
                <p>
                  Pay only for the actual usage of your app.
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
              <h1 class="title">Universal</h1>
              <div class="content">
                <p>
                  Give users the fastest possible page renders
                </p>
                <p>
                  Ensure your content is optimized for the semantic web (and SEO)
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
              <h1 class="title">Full Stack</h1>
              <div class="content">
                <p>
                  Use a "real" frontend and backend, written and deployed together seamlessly
                </p>
                <p>
                  Organize teams around features, not technical limitations
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
    titleTemplate: '%s'
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

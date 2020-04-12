<template>
  <div class="default-layout">
    <b-navbar
      :fixed-top="true"
      :spaced="true"
    >
        <template slot="brand">
            <b-navbar-item tag="router-link" to="/">
                <img
                  alt="SUF"
                  src="https://res.cloudinary.com/dn7sohze7/image/upload/c_scale,f_auto,q_auto,w_52/v1586668370/suf-stack/favicon.svg"
                >
            </b-navbar-item>
        </template>
        <template slot="end">
            <b-navbar-item tag="router-link" to="/about">
                About SUF-Stack
            </b-navbar-item>
            <b-navbar-item tag="router-link" to="/get-started">
                Get Started
            </b-navbar-item>
        </template>
    </b-navbar>
    <nuxt />
    <footer class="footer">
      <div class="content">
        <p>
          <strong>SUF Stack</strong> by <a href="https://bradito.me/">Brad Ito</a>.
        </p>
      </div>
    </footer>
  </div>
</template>

<script>
import SufStackLogo from '~/components/SufStackLogo.vue'

export default {
  head: {
    titleTemplate: '%s - SUF-Stack'
  },
  components: {
    'suf-stack-logo': SufStackLogo
  }
}
</script>

<style lang="scss">
.default-layout {
  .navbar {
    background-color: $theme-background;
    color: $theme-primary;
  }
  .section .container {
    max-width: 769px;
    margin: 0 auto;
    p {
      margin-bottom: 25px;
    }
  }
}
</style>

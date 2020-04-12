<template>
  <div class="get-started-page">
    <section class="section">
      <div class="container">
        <h1 class="title">Get Started with SUF-Stack!</h1>
        
        <h2 class="subtitle">Yeoman Generator</h2>
        <p>
          As an example of how to get started writing a SUF-Stack app we created
          a <a href="https://yeoman.io/">yeoman</a> generator:
          <a href="https://www.npmjs.com/package/generator-suf-stack-aws-koa-nuxt">generator-suf-stack-aws-koa-nuxt</a>.
        </p>
        <p>
          To use it:
        </p>
        <vue-code-highlight>
          npm install -g yo
          npm install -g generator-suf-stack-aws-koa-nuxt
          mkdir *appname*
          cd *appname*
          yo suf-stack-aws-koa-nuxt
        </vue-code-highlight>
        
        <p>
          Note that this version uses AWS (Lambda, API Gateway, CloudFront) and is optimized to be used
          with a custom domain, and to serve content via S3.  Before using it, make sure to setup AWS credentials
          and to prepare an S3 bucket for your static assets.
        </p>
        
        <p>
          This yeoman generator also uses Koa.js for the backend, and Nuxt.js/Vue.js for the frontend.  For more
          details, read the <a href="https://www.npmjs.com/package/generator-suf-stack-aws-koa-nuxt">documentation</a>.
        </p>
        
        <hr />
        
        <h2 class="subtitle">create-app scaffolder</h2>
        
        <p>
          Coming Soon!  This will also provide more options for frontend and backend frameworks, and later
          deployment onto other cloud providers.
        </p>
      </div>
    </section>
  </div>
</template>

<script>
import { component as VueCodeHighlight } from 'vue-code-highlight'

export default {
  head: {
    title: 'Get Started',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'SUF-Stack - Serverless, Universal, Full Stack - Get Started'
      }
    ],
  },
  components:{
  VueCodeHighlight,
  }
}
</script>

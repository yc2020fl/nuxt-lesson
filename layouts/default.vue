<template>
<div>
  <!-- this Header is a references to Header in component -->
  <Header>
    <template #headerontop>
      Artworks and its Relationship to...
    </template>
    <template #headersecond>
      Female Images
    </template>
  </Header>


  <div class='head'>
    <div id="nav">
      <nuxt-link to="/">Home</nuxt-link> |
      <nuxt-link to="/artists">Artists</nuxt-link> |
      <nuxt-link to="/Showcase">Portrayed</nuxt-link> |
      <nuxt-link to="/Statistics">Statistics</nuxt-link> |
      <nuxt-link to="/Blog">Blog</nuxt-link> |
      <nuxt-link to="/about">About</nuxt-link>

      <Nuxt />
    </div>
  </div>

  <footer>{{ footer }}</footer>


</div>
</template>


<script >
import Header from "~/components/Header"




export default {
  name: 'default',

  components: {
    Header
  },

  //SEO; metavue, the content of the footer is also use in html
  data() {
    return {
      footer: '| This Site is for Informational Purpose Only |'
    }
  },



  head() {
    return {
      footer: this.footer,
      title: 'Artworks of Female Artists',
      htmlAttrs: {
        lang: 'en',
        amp: true
      },
      // bodyAttrs: {
      //   class: ['xl-lg-sm responsive', 'pink']
      // },

      meta: [{
          charset: 'utf-8'
        },
        {
          name: 'viewport',
          content: 'width=device-width, initial-scale=1'
        },
        {
          hid: 'description',
          name: 'description',
          content: ''
        },
        {
          name: 'format-detection',
          content: 'telephone=no'
        }
      ],
      link: [{
        rel: 'icon',
        type: 'image/x-icon',
        href: '/favicon.ico'
      }]
    }
  }




}
</script>


<style lang="scss">
#nav {
    text-align: center;

    a {
        font-weight: bold;
        color: #2c3e50;

        &.router-link-exact-active {
            color: #74401c;
        }
    }
}

nuxt-link {
    background-color: #d7b6c9;
}

footer {
    text-align: center;
    font-size: 1.2em;
    background-color: #042030;
    color: #a5a6b1;
    padding: 1em;
}
</style>

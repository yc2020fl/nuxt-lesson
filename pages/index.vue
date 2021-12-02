<template>

<!-- keep the style from previous lesson 6, items in female artists and paintings are listed in script -->
<div>


<!-- this header is not <header>, it is a name that I choose to apply style, go check header.vue -->
<!-- this has been moved -->
<!--took out the header in each file, and import it to the defaut.vue file inside .nuxt/layouts/default.vue  -->
<!-- see Blog.vue -->
  <!-- <Header>
    <template #headerontop>
  Artworks and its Relationship to...
  </template>
  <template #headersecond>
  Female Images
  </template>
  </Header> -->


  <main class="main">
    <div class="row mt-5 mb-5">
      <div class="col-xl-4 col-lg-4 col-sm-4 col-12  p-2 mt-2">
        <h2 class="bg-light">Females Artists</h2>
        <ul>
          <li v-for="item in femaleArtists" :key="item.message">
            {{ item.message }}
          </li>
        </ul>

        <!-- did v-b-tooltip.hover here, it is easier than the previous lesson of repeative of data-toggle, etc -->
        <!-- did v-for in script for all the data as a list here -->
        <a href="artists.html" v-b-tooltip.hover class="btn btn-light btn-sm active"  title="Learn More about Artists" >See More</a>
      </div>

      <div class="home-painting">
      <div class="col-xl-8 col-lg-8 col-sm-8 col-12 p-2 mt-2">
        <h2 class="bg-light">Paintings</h2>
        <ul>
          <li v-for="item in paintings" :key="item.message">
            {{ item.message }}
          </li>
        </ul>
        <a href="showcase.html" v-b-tooltip.hover class="btn btn-light btn-sm active" title="See More Paintings">See More</a>

      </div>
    </div>

    </div>
  </main>

</div>
</template>

<script>

export default {


  name: 'Home',


  data() {
    return {
      femaleArtists: [{
          message: 'Berthe Morisot '
        },
        {
          message: 'Adélaïde Labille-Guiard'
        },
        {
          message: 'Rosa Bonheur'
        },
        {
          message: 'Mary Cassatt '
        }
      ],
      paintings: [{
          message: 'A Woman Seated at a Bench on the Avenue du Bois | 1885'
        },
        {
          message: 'The Horse Fair | 1852–55'
        },
        {
          message: 'Madame Élisabeth de France (1764–1794) | ca. 1787 '
        },
        {
          message: 'Lydia Crocheting in the Garden at Marly | 1880'
        }
      ]
    }
  },

//start of vue-meta
  head: {
    title: 'Artitist and their Art Works',
    titleTemplate: '%s | Home',
    htmlAttrs: {
      lang: 'en',

    },

    meta: [
      { charset: 'utf-8' },
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      { hid: 'description', name: 'description', content: 'list some artists and their works, with link to the MET museum' },
      { name: 'format-detection', content: 'telephone=no' }
    ],
    link: [
      { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }
    ]
  }

}



</script>



<style media="screen">
.main {
  padding: 1em;
  background-color: #d7b6c9;
}

/* .home-painting {
  background-color: #2b4c39;
  border-radius:5%;
} */

</style>

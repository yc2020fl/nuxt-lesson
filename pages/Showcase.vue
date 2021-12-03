<!-- Parent -->


<template>
<div>

  <h2> Paris Salon Kind of Room</h2>

  <main>
    <div class="row mt-5 mb-5">


      <!-- a list of the female artists names from script, kpt the same style of list-group of the white bg -->
      <!-- take this part out, because do not need repeating names -->
      <!-- <div class="col-xl-12 col-lg-12 col-sm-12 col-12 bg-success p-2 mt-2">
        <h2 class="bg-warning">Females Artists</h2>

        <ul class="list-group">
          <li class="list-group-item" v-for="item in femaleArtists" :key="item.message">
            {{ item.message }}
          </li>
        </ul>
      </div> -->


      <div id="Showcase">
        <!-- <div class=" col-xl-3 col-lg-4 col-sm-6 col-12 bg-danger p-2 mt-5"> -->

        <!-- the mock up are from post.vue, and also the styles -->
        <section v-if="posts">
          <div class="image">
            <div class="imageShow">
              <!--  pull the mock up from post.vue -->
              <post v-for="post in posts" v-bind:post="post" v-bind:key="post.id">
              </post>


            </div>
          </div>
        </section>
      </div>

    </div>



  </main>
</div>
</template>



<script>
import Post from '../components/Post';



export default {
  name: 'Showcase',

  components: {
    Post
  },



  data() {
    return {


      //did not use since Lesosn 8
      // femaleArtists: [{
      //     message: 'Berthe Morisot '
      //   },
      //   {
      //     message: 'Adélaïde Labille-Guiard'
      //   },
      //   {
      //     message: 'Rosa Bonheur'
      //   },
      //   {
      //     message: 'Mary Cassatt '
      //   }
      // ],




      posts: [{
          id: 1,
          name: 'Berthe Morisot',
          painting: 'Young Woman Knitting',
          year: 'ca. 1883',
          link: 'https://www.metmuseum.org/art/collection/search/437159',
          image: 'https://collectionapi.metmuseum.org/api/collection/v1/iiif/437159/796162/main-image',
          alt: 'Young Woman Knitting'
        },
        {
          id: 2,
          name: ' Berthe Morisot',
          painting: ' A Woman Seated at a Bench on the Avenue du Bois',
          year: ' 1885',
          link: 'https://www.metmuseum.org/art/collection/search/337864',
          image: 'https://collectionapi.metmuseum.org/api/collection/v1/iiif/337864/756828/main-image'
        },
        {
          id: 3,
          name: 'Adélaïde Labille-Guiard',
          painting: ' Self-Portrait with Two Pupils, Marie Gabrielle Capet (1761–1818) and Marie Marguerite Carreaux de Rosemond (died 1788)',
          year: '1785 ',
          link: ' https://www.metmuseum.org/art/collection/search/436840',
          image: 'https://collectionapi.metmuseum.org/api/collection/v1/iiif/436840/1425691/main-image'
        },
        {
          id: 4,
          name: 'Adélaïde Labille-Guiard ',
          painting: ' Madame Élisabeth de France (1764–1794)',
          year: 'ca.1787 ',
          link: ' https://www.metmuseum.org/art/collection/search/439405',
          image: ' https://collectionapi.metmuseum.org/api/collection/v1/iiif/439405/795077/main-image'
        },


        {
          id: 5,
          name: 'Rosa Bonheur',
          painting: ' The Horse Fair',
          year: '1852–55 ',
          link: ' https://www.metmuseum.org/art/collection/search/435702',
          image: 'https://collectionapi.metmuseum.org/api/collection/v1/iiif/435702/796396/main-image'
        },

        {
          id: 6,
          name: 'Mary Cassatt',
          painting: ' Lydia Crocheting in the Garden at Marly',
          year: '1880',
          link: 'https://www.metmuseum.org/art/collection/search/10393',
          image: 'https://images.metmuseum.org/CRDImages/ad/mobile-large/DP165250.jpg'
        },

        {
          id: 7,
          name: 'Mary Cassatt ',
          painting: ' Lilacs in a Window (Vase de Lilas a la Fenetre)',
          year: 'ca. 1880-83',
          link: 'https://www.metmuseum.org/art/collection/search/13758',
          image: 'https://images.metmuseum.org/CRDImages/ad/mobile-large/DT254478.jpg'
        }

      ]

    }
  },

  //start of vue-meta
  head: {
    title: 'Artworks of Impressionism Female Artists ',
    titleTemplate: '%s | Paris Salon',
    htmlAttrs: {
      lang: 'en',

    },

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
        content: 'an art gallery-like of paintings of female artists in the impressionism era'
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
</script>



<!-- all the styles in this page, is of the images, so it is inside nuxt09/components/Post.vue -->

<template>
<div>

  <!--took out the header in each file, and import it to the defaut.vue file inside .nuxt/layouts/default.vue  -->
  <!-- <Header>
    <template #headerontop>
  Artworks and its Relationship to...
  </template>
  <template #headersecond>
  Female Images
  </template>
  </Header> -->

  <!-- left and right -->
  <div class="color">
    <div class="row">
      <div class="col-xl-4 col-lg-5 col-sm-6 col-12 p-5">

        <!-- some articles places at the left side -->
        <ul class="bg-light p-5">
          <!-- v-on:click applies the clickMixin to this <p> -->
          <p v-on:click="makeRed" :class="{'red': !isRed}">Through Their Lens ✨ ✨</p>
          <li><a v-bind:href="bloglink1">From 1971: Why Have There Been No Great Women Artists?</a></li>

          <li> <a v-bind:href="bloglink2">Alice Neel: They Are Their Own Gifts, 1978 | From the Vaults</a> </li>
          <li> <a v-bind:href="bloglink3">10 Inspiring Stories of Women at The Met</a> </li>
          <li> <a v-bind:href="bloglink4">Art That Looks at What Women See</a> </li>



        </ul>
      </div>




      <!-- accordion via v-for, title and decsription all together -->
      <div class="col-xl-8 col-lg-7 col-sm-6 col-12 bg-light p-2">
        <div>
          <h2 class="bg-dark text-light text-uppercase">Exhibits/Books/... </h2>

          <div class="card ">
            <div class="card-header">
              <h5 class="mb-5">
                <button class="btn btn-dark mt-5" type="button" v-on:click="show = !show">Click to See the Exhibts, Books, and More!</button>

              </h5>
            </div>

            <!-- list out each item related to art, use v-for for all the data, and did v-if show: true for accordion ,
v-if show: false means the accordion item shows automatically-->
            <div class="m-3" v-for="accordion in accordions" :key="accordion.title">
              <p class="bookTitle" v-if="show"> {{accordion.title}} </p>
              <p v-if="show"> {{accordion.text}}</p>
              <img v-if="show" v-bind:src="accordion.image"></br>
              <a class="text-dark bg-light m-5" v-if="show" v-bind:href="accordion.link" target="_blank">Learn More</a>
            </div>

          </div>

        </div>
      </div>
    </div>
  </div>

  <!-- first book under accordion -->

</div>
</template>

<script>
//took out Header, and import it to .nuxt/layouts/default.vue
// import Header from '../components/Header';
import clickMixin from '../mixins/clickMixin';
export default {


  //trigger the clickMixin event, with the frame around it, with this export, and the above import #71
  mixins: [clickMixin],


  name: 'Blog',


  //took out Header, and import it to .nuxt/layouts/default.vue
  // components: {
  //   Header
  // },
  data() {


    return {

      bloglink1: 'https://www.artnews.com/art-news/retrospective/why-have-there-been-no-great-women-artists-4201/',
      bloglink2: 'https://youtu.be/MQtSDLOg05c',
      bloglink3: 'https://www.metmuseum.org/blogs/collection-insights/2021/womens-history-month-stories',
      bloglink4: 'https://www.nytimes.com/2021/09/21/arts/women-artists.html',




      // to show the title and descrpition and images while show is true,
      //while show  is false, the automatic is not showing
      show: true,
      accordions: [{
          title: ' Public Parks, Private Gardens: Paris to Provence ',
          text: ' "This catalogue accompanies The Metropolitan Museum of Art exhibition. ..."',
          link: 'https://store.metmuseum.org/public-parks-private-gardens-paris-to-provence-80040790',
          image: 'https://store.metmuseum.org/media/catalog/product/8/0-12712-28570/public-parks-private-gardens-paris-to-provence.jpg?quality=80&bg-color=255,255,255&fit=bounds&height=448&width=448&canvas=448:448'
        },
        {
          title: ' Art = Discovering Infinite Connections in Art History',
          text: ' "Featuring more than 800 artworks from the collection of The Metropolitan Museum of Art, ..." ',
          link: ' https://store.metmuseum.org/art-equals-discovering-infinite-connections-in-art-history-80047004',
          image: 'https://store.metmuseum.org/media/catalog/product/a/r/art_equals_discovering_infinite_connections_in_art_history_80047004_02.jpg'
        },

      ]



    }
  },

  head: {
    title: 'Impressionism articles and other resouces',
    titleTemplate: '%s | Blog',
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
        content: 'A list of the materials in relates to female artists and their works in the past'
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

<style lang="css" scoped>
.row {
  padding: 1em;
}


img {
width: 10em;
border-radius: 15%;
margin: 1em;
}

.bookTitle {
 font-weight: bolder;
}

div {
background-color: #d7b6c9;
}

.color {
  padding: 1em;
}

a {
  font-weight: bold;

  color: #74401c;
}

p {
  font-weight: bolder;

  color: #74401c;
}

</style>

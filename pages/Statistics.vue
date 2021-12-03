<template >
<div class>


  <section class="container" v-if="list">
    <paintingsAPI v-for="item of list" :key="item.id" :item="item" />
  </section>




</div> <!-- /.row -->
</template>

<script>
import axios from 'axios'
import PaintingsAPI from '~/components/PaintingsAPI.vue'

export default {
  components: {
    PaintingsAPI
  },

  data() {
    return {
      art: null,
      list: null,
      response: null,
      loading: true,
      errored: false
    }
  },

  methods: {



    getPainting: function() {

      var art = this;

      axios.get('https://collectionapi.metmuseum.org/public/collection/v1/search?dateBegin=1770&dateEnd=1890&q=impressionism')

        // getData =>
        //     let objectIDs = data.objectIDs.length;
        //   for (let i = 0; i < data.objectIDs.length; i++) {
        //     everyObjectID = results.objectIDs[i]
        //   }
        // )

        // .then((apiData) => {
        //   console.log(apiData);
        //   apiList.list = collection.map(function(a) {
        //     return a.data
        //     console.log(a.data)
        //   })
        // })

        .then(function(response) {

          // var array = results;

          //even with out the above codes, .get of IDs, and .then(function(response)), the code below will still works,
          //with promise.all because each ID is explicitly listed
          Promise.all([
              // axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/${everyObjectID}'),
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/435877'),
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/437993'),
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/438015'),
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/436951'),
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/306163'),
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/766682'),
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/436004'),
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/437435'),
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/435867'),
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/438818'),
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/435963'),
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/436524'),
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/334312')
            ])

            .then((collection) => {
              console.log(collection);
              art.list = collection.map(function(c) {
                return c.data
                console.log(c.data)
              })
            })
        }) //.then(function(response))


        //start of .catch
        .catch(function(error) {
          console.log(error)
          this.errored = true
        })
        .finally(() => this.loading = false)
    } //

  }, //closing for method

  mounted: function() {
    this.getPainting();
  },


  //start of vue-meta
  head: {
    title: 'Use of the MET Museum API',
    titleTemplate: '%s | Statistic',
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
        content: 'THE MET API, list all the paintings from the Impressionism era in THET MET'
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


} //closing for export default
</script>

<style lang="css" scoped>
.container {
  margin: auto;
  display: flex;
  justify-content: center;
  align-items: stretch;
  text-align: center;
  flex-wrap: wrap;
}

</style>

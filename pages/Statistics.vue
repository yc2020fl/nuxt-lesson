<template >
<div class="row">
  <div class="column">

    <section class="container" v-if="list">
      <card v-for="item of list" :key="item.id" :item="item" />
    </section>



  </div> <!-- /.column -->
</div> <!-- /.row -->
</template>

<script>
import axios from 'axios'
import Card from '~/components/Card.vue'

export default {
  components: {
    Card
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
      axios
        .get('https://collectionapi.metmuseum.org/public/collection/v1/search?dateBegin=1770&dateEnd=1890&q=impressionism',
        )
        .then(function(response) {

          var array = results;
          for (let i = 0; i < results.objectIDs.length; i++) {
            let everyObjectID = results.objectIDs[i]
          };

          //even with out the above codes, .get of IDs, and .then(function(response)), the code below will still works,
          //with promise.all because each ID is explicitly listed
          Promise.all([
              axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/${everyObjectID}')
              // axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/435877')
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
        content: 'THE MET API'
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


</style>

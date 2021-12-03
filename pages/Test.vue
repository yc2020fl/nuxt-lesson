<!--

<script>

mounted () {


      axios.get('https://collectionapi.metmuseum.org/public/collection/v1/search?dateBegin=1770&dateEnd=1890&q=impressionism')
.then(
  responseA =>
    Promise.all([
      responseA,
      axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/435877'),
      axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/437993')
    ])
)
.then(
  ([responseA,responseB, responseC]) => {
  console.log(responseA,responseB, responseC);

})
.catch(error => {
  console.log(error)
  this.errored = true
})
.finally(() => this.loading = false)



  }

</script>


 -->














<!-- working code with hard corded codes -->

 // <script>
// import axios from 'axios'
// import Card from '~/components/Card.vue'
//
// export default {
//   components: {
//     Card
//   },
//
//   data() {
//     return{
// 		art: null,
//     list: null,
//     loading: true,
//     errored: false
//   }
// 	},
//
//   methods: {
//
// 	getPainting: function() {
//   			var art = this;
//
//   			axios
//         .get('https://collectionapi.metmuseum.org/public/collection/v1/search?dateBegin=1770&dateEnd=1890&q=impressionism')
//
//         .then(function(response) {
//
// //even with out the above codes, .get of IDs, and .then(function(response)), the code below will still works,
// with promise.all because each ID is explicitly listed within promise.all
//           Promise.all([
//
//             axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/435877'),
//             axios.get('https://collectionapi.metmuseum.org/public/collection/v1/objects/437993')
//
//
//
//
//           ])
//
//
//           .then((collection) =>
//           { console.log(collection);
//             art.list=collection.map(function(c) {
//               return c.data
//             })
//
//
//
//       })
//
//   			})
//
//
//
// //
//
// //start of .catch
//         .catch(function (error) {
//           console.log(error)
//                          this.errored = true
//         })
//         .finally(() => this.loading = false)
//   		 }//
//
//
//   	},//closing for method
//
//
//   	mounted: function() {
//   		this.getPainting();
//   	},
//
//
//
//
//     //start of vue-meta
//       head: {
//         title: 'Use of the MET Museum API',
//         titleTemplate: '%s | Statistic',
//         htmlAttrs: {
//           lang: 'en',
//
//         },
//
//         meta: [
//           { charset: 'utf-8' },
//           { name: 'viewport', content: 'width=device-width, initial-scale=1' },
//           { hid: 'description', name: 'description', content: 'THE MET API' },
//           { name: 'format-detection', content: 'telephone=no' }
//         ],
//         link: [
//           { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }
//         ]
//       }
//
//
//   } //closing for export default
//
//
//
//
//
//
//
//
// </script>

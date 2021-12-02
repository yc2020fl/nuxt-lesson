<template>
 <article class="card">

   <p class="card__copy">{{ item.accessionYear}}</p>
   <p class="card__copy">{{ item.title}}</p>
	 <img :src="item.primaryImageSmall" :alt="item.title" class="card__img">



 </article>
</template>

<script>
export default {
	props: {
    item: null,

		// item: {
    //   objectIDs: String
    // }
	}
}
</script>


<style lang="scss">
.card {
	margin: 1rem;
	border: 1px solid #000;
	padding: 1.5rem;
	max-width: 200px;
	min-height: 200px;
	&__img {
		display: block;
		margin-bottom: 1rem;
	}
	&__title {
		font-size: 1rem;
		margin-bottom: .25rem;
	}
	&__copy {
		font-size: .875rem;
	}
}
</style>

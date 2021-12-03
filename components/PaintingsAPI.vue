<template>
<article class="paintingsAPI">
  <div class="frame">
    <p class="paintingsAPI__title">{{ item.title}}</p>
    <p class="paintingsAPI__copy">Author: {{ item.artistDisplayName}}</p>
    <p class="paintingsAPI__copy">{{ item.accessionYear}}</p>
    <p class="paintingsAPI__copy">Department: {{ item.department}}</p>
    <img class="paintingsAPI__img" v-on:click="makeRed" :class="{'red': !isRed}" :src="item.primaryImageSmall" :alt="item.title">
    <a class="paintingsAPI__copy" v-bind:href="item.objectURL" target="_blank">Click Me</a>
  </div>


</article>
</template>

<script>
import clickMixin from '../mixins/clickMixin';

export default {
  //use the same mixins as the showcase page, after click of a image, show border, click again border gone
  mixins: [clickMixin],

  props: {
    item: null
  }
}
</script>


<style lang="scss">
.paintingsAPI {
    margin: 1em;
    padding: 1.5em;
    max-width: 200px;
    min-height: 200px;
    border-top: 1em solid #042030;
    border-bottom: 1em double #042030;
    border-radius: 2%;

    &__img {
        display: block;
        margin-bottom: 1em;
        width: 100%;
    }
    &__title {
        font-size: 1em;
        margin-bottom: 0.25em;
    }
    &__copy {
        font-size: 1em;
    }

    div .frame {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(15rem, 1fr));
        grid-gap: 1em;
        padding: 0.5em;
        background: #d7b6c9;
        margin: 0.4em;
    }
}
</style>

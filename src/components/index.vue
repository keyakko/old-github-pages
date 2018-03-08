<template>
  <div class="main">
    <div class="jumbo">
      <div class="wrapper">
       <h2>yakko.me(開発中)</h2>
       <p>開発中なのでボロがたくさん</p>
      </div>
    </div>
    <div class="lists">
      <list v-for="list in archive" :title="list.title" :desc="list.wrapup" :post_date="list.date" :next_path="'/article/' + list.title + '/'" />
    </div>
  </div>
</template>

<script>
import List from './list'
export default {
  name: 'main',
  components: {
    List,
  },
  data () {
    return {
    }
  },
  props: [
    'archive',
  ]
}
</script>

<style lang="scss">
  
  /*basecolor*/
  $basewhite: #ffffff;
  $baseblack: #555555;
  $baseblue: #4B9494;
  $basered: #F77D7D;
  
  .main {
    .jumbo {
      background-color: $baseblue;
      color: $basewhite;
      padding: 30px 50px;
      .wrapper {
        max-width: 1100px;
        margin: 0 auto;
        h2 {
          margin: 0;
          font-size: 1.8em;
          line-height: 2.3em;
        }
      }
    }
  }
</style>

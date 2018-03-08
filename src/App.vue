<template>
  <div id="app">
    <template-header />
    <router-view :archive="archive" />
    <template-footer />
  </div>
</template>

<script>
import TemplateHeader from './components/template-header'
import TemplateFooter from './components/template-footer'
import axios from 'axios'
export default {
  name: 'App',
  components: {
    TemplateHeader,
    TemplateFooter,
  },
  data () {
    return {
      archive: [],
    }
  },
  mounted () {
    this.get_lists()
  },
  methods: {
    async get_lists () {
      var j_data;
      await axios.get('http://localhost/posts/list.json')
      .then(function(response) {
        j_data = response.data;
      });
      this.$data.archive = j_data;
    }
  }
}
//const store = new Vuex.Store({
//  state: {
//    
//  },
//})
</script>

<style lang="scss">
  /*basecolor*/
  $basewhite: #ffffff;
  $baseblack: #555555;
  $baseblue: #4B9494;
  $basered: #F77D7D;

  @charset 'UTF-8';
  @import 'normalize.css';
  body {
    font-family: "Shin Go Light", "Quicksand","游ゴシック体","Yu Gothic",YuGothic,"ヒラギノ角ゴシック Pro","Hiragino Kaku Gothic Pro","メイリオ",Meiryo,Osaka,"ＭＳ Ｐゴシック","MS PGothic",sans-serif;
  }
</style>

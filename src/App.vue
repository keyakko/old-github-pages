<template>
  <div id="app">
    <template-header />
    <router-view/>
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
  created () {
    this.get_lists()
  },
  methods: {
    get_lists () {
      console.log('hoge');
      axios.get('/posts/list.json')
      .then(function(response) {
        console.table(response);
        return response;
      });
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
  @charset 'UTF-8';
  @import 'normalize.css';
  body {
    font-family: "Shin Go Light", "Quicksand","游ゴシック体","Yu Gothic",YuGothic,"ヒラギノ角ゴシック Pro","Hiragino Kaku Gothic Pro","メイリオ",Meiryo,Osaka,"ＭＳ Ｐゴシック","MS PGothic",sans-serif;
  }
</style>

<template>
  <div class="list">
    <router-link :to="next_path">
      <h3>{{title}}</h3>
      <div class="meta">{{post_date}}</div>
      <p>{{desc}}</p>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'list',
  props: [
    'title',
    'desc',
    'next_path',
    'post_date'
  ]
}
</script>

<style lang="scss" scoped>
  /*basecolor*/
  $basewhite: #ffffff;
  $baseblack: #555555;
  $baseblue: #4B9494;
  $basered: #F77D7D;
  
  .list {
    width: 80vw;
    margin: 20px auto;
    max-width: 800px;
    a {
      display: block;
      width: 100%;
      box-sizing: border-box;
      padding: 10px 20px;
      border: 1px solid #aaa;
      border-radius: 10px;
      color: $baseblack;
      text-decoration: none;
      &:hover {
        text-decoration: underline;
      }
    }
  }
</style>

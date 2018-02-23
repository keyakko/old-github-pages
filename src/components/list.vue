<template>
  <div class="list">
    <router-link :to="next_path">
      <h3>{{title}}</h3>
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
  ]
}
</script>

<style lang="scss" scoped>
  $baseblack: #555;
  .list {
    width: 80vw;
    margin: 20px auto;
    border: 1px solid #aaa;
    border-radius: 10px;
    padding: 10px 20px;
    max-width: 800px;
    a {
      color: $baseblack;
      text-decoration: none;
      &:hover {
        text-decoration: underline;
      }
    }
  }
</style>

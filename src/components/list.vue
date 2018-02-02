<template>
  <div class="list">
    <router-link>
      <h3>{{title}}</h3>
      <p>{{desc}}</p>
      
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'list',
}
</script>

<style lang="scss" scoped>
  .wrapper {
    margin: 0 auto;
    width: 900px;
  }
</style>

<template>
  <div class="main">
    <div class="lists">
      <list v-for="list in archive" :title="list.title" :desc="list.wrapup" :next_path="'/article/' + list.title + '/'" />
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

<style>
  
</style>

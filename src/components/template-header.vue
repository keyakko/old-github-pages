<template>
  <div class="header">
    <header>
      <div class="wrapper">
        <h1 class="title">keyakko weblog</h1>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: 'template-header',
  data () {
    return {
      
    }
  }
}
</script>

<style lang='scss' scoped>
  $pc-wrap: 1100px;
  .header {
    width: 100%;
    header {
      width: 100%;
      color: white;
      background-color: #333;
      padding: 10px 0;
      .wrapper {
        width: 400px;
        margin: 0 auto;
        h1 {
          font-size: 1em;
          font-weight: normal;
          text-align: center;
          margin: 0;
          line-height: 1.5em;
        }
      }
    }
  }
</style>

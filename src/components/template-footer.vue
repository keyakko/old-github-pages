<template>
  <div class="footer">
    <footer>
      <div class="wrapper">
        <p class="copyright">&copy; 2018 keyakko weblog.</p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'template-footer',
  data () {
    return {
      
    }
  }
}
</script>

<style lang='scss' scoped>
  $pc-wrap: 1100px;
  .footer {
    width: 100%;
    margin-top: 200px;
    footer {
      width: 100%;
      color: white;
      background-color: #333;
      padding: 10px 0;
      .wrapper {
        width: 400px;
        margin: 0 auto;
        p {
          font-size: 0.7em;
          font-weight: normal;
          text-align: center;
          margin: 0;
          line-height: 1.5em;
        }
      }
    }
  }
</style>

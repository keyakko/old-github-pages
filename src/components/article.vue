<template>
  <div class="main">
    <article v-if="true">
      <div class="info">
        <p class="title">hogehoge</p>
        <div class="meta">
          <p class="date">100000000</p>
        </div>
      </div>
      <div class="wrapper">
        {{post}}
      </div>
    </article>

    <div class="notfound" v-else>
      <p>404 Not found</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'article',
  data () {
    return {
      post: 'post'
    }
  }
}
</script>

<style lang="scss" scoped>
  article {
    .info {
      background-color: #0fdca5;
      color: white;
      padding: 30px 20px;
      .title {
        margin: 0;
        font-size: 2em;
        text-align: center;
        padding: 0.5em 0;
      }
      .meta {
        .date {
          margin: 0 0 1em;
          text-align: center;
        }
      }
    }
    .wrapper {
      margin: 30px auto 50px;
      width: 90vw;
      max-width: 900px;
    }
  }
</style>

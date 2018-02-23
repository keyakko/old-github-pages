<template>
  <div class="main">
    <article v-if="true">
      <div class="info">
        <p class="title">{{post_title}}</p>
        <div class="meta">
          <p class="date">{{post_date}}</p>
        </div>
      </div>
      <div class="wrapper">
        <vue-markdown :source="post_description"></vue-markdown>
      </div>
    </article>

    <div class="notfound" v-else>
      <p>Not found</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import VueMarkdown from 'vue-markdown'
export default {
  name: 'article',
  components: {
    VueMarkdown
  },
  data () {
    return {
      exist: false,
      post_title: '',
      post_date: '',
      post_description: '',
    }
  },
  props: [
    'archive'
  ],
  mounted() {
    this.load_post()
  },
  beforeUpdate() {
  },
  watch: {
    archive: async function() {
      var search_lt = this.$route.params.title;
      var data = '';
      for(var i = 0; i < this.$props.archive.length; i++) {
        if (this.$props.archive[i].title == search_lt) {
          this.$data.exist = true;
          this.$data.post_title = this.$props.archive[i].title;
          this.$data.post_date = this.$props.archive[i].date;
          await axios.get('/posts/' + this.$props.archive[i].file + '.md')
          .then(function(response) {
            data = response.data;
          });
          this.$data.post_description = data;
          break;
        }
      }
      console.table(this.$prop.archive);
      console.table(this.$data);
    }
  },
  methods: {
    async load_post() {
      var search_lt = this.$route.params.title;
      var data = '';
      for(var i = 0; i < this.$props.archive.length; i++) {
        if (this.$props.archive[i].title == search_lt) {
          this.$data.exist = true;
          this.$data.post_title = this.$props.archive[i].title;
          this.$data.post_date = this.$props.archive[i].date;
          await axios.get('http://localhost/posts/' + this.$props.archive[i].file + '.md')
          .then(function(response) {
            data = response.data;
          });
          this.$data.post_description = data;
          break;
        }
      }
      console.table(this.$prop.archive);
      console.table(this.$data);
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

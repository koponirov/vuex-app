<template>
  <div id="app">
    <post-form/>
    <h1>{{ postsCount }}</h1>
    <div class="post" v-for="post in validPosts" :key="post.id">
      <h2>{{ post.title }}</h2>
      <p>{{ post.body }}</p>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';
import PostForm from "@/components/PostForm";
export default {
  name: 'App',
  components: {
    PostForm
  },
  computed: mapGetters(['validPosts','postsCount']),
  methods: mapActions(['fetchPosts']),
  mounted() {
    this.fetchPosts(100);
  }

};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 60px auto;
  width: 600px;

  .post {
    border: 1px solid #cccccc;
    border-radius: 5px;
    margin-bottom: 1rem;
  }
}
</style>

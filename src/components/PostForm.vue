<template>
  <form @submit.prevent="createPost">
    <input type="text" placeholder="title" v-model="title">
    <input type="text" placeholder="body" v-model="body">
    <button type="submit">Create  post</button>
    <hr/>
  </form>
</template>

<script>
export default {
  name: "PostForm",
  data() {
    return {
      title: '',
      body: ''
    }
  },
  methods: {
    createPost() {

    }
  }
}
</script>

<style scoped>
  input {
    display: block;
    width: 100%;
    border: 1px solid #cccccc;
    border-radius: 2px;
    padding: 10px;
    margin-bottom: 10px;
  }
</style>

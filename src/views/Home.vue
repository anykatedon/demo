<template>
  <div class="row"></div>
</template>

<script>
import PostService from "../PostService";
const postService = new PostService();

export default {
  name: "Home",
  data() {
    return {
      posts: []
    };
  },
  created() {
    postService
      .getAllPosts()
      .then(res => {
        this.posts = res.data;
        // eslint-disable-next-line
        console.log(this.posts);
      })
      .catch(err => {
        // eslint-disable-next-line
        console.error(err);
      });
  }
};
</script>

<style>
</style>
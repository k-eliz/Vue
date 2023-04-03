<template>
  <div class="app">
    <PostForm @create="createPost" />
    <PostList v-bind:posts="posts" />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";
import PostItem from "@/components/PostItem.vue";

export default {
  components: {
    PostForm,
    PostList,
    PostItem,
  },
  data() {
    return {
      posts: [
        { id: 1, title: "JavaS1", body: "body1" },
        { id: 2, title: "JavaS2", body: "body2" },
        { id: 3, title: "JavaS3", body: "body3" },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  display: flex;
  flex-direction: column;
  gap: 15px;
  padding: 20px;
}
</style>

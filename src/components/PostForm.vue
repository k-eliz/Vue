<template>
  <form @submit.prevent>
    <h4>Create post</h4>
    <input
      v-model="post.title"
      class="input"
      type="text"
      placeholder="Введите че-нить"
    />
    <input
      v-model="post.body"
      class="input"
      type="text"
      placeholder="Введите че-нить2"
    />
    <my-button
      style="align-self: flex-end; margin-top: 15px"
      @click="createPost"
      >create</my-button
    >
  </form>
</template>

<script>
import MyButton from "./UI/MyButton.vue";
export default {
  components: {
    MyButton,
  },
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost(event) {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}
.input {
  width: 100%;
  border: 1 px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}
</style>

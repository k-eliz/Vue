<template>
  <div class="app">
      <form>
        <h4>Create post</h4>
        <input v-bind:value="title" @input="inputTitle" class="input" type="text" placeholder="Название">
        <input v-bind:value="body" class="input" type="text" placeholder="Описание">
        <button class="btn" @click="createPost">Create</button>

      </form>
   <div class="post" v-for="post in posts">
    <div><strong>{{ post.title }}</strong></div>
    <div><strong>Описание</strong>{{ post.body }}</div>
   </div>
  </div>
</template>

<script>
import { eventNames } from 'process';

export default{
  data(){
    return {
      posts:[
        {id:1, title:"JavaScript", body:"Описание поста"},
        {id:2, title:"JavaScript", body:"Описание поста2"},
        {id:3, title:"JavaScript", body:"Описание поста3"},
      ],
      title:"",
      body:"",
    }
  },
  methods:{
   createPost(){

   },
   inputTitle(event){
    this.title = event.target.value;
   }
  }

}

</script>

<style >
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app{
  padding: 20px;
}
.post{
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}

form{
  display: flex;
  flex-direction: column;
}

.input{
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.btn{
  align-self: flex-end;
  margin-top: 15px;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}


</style>
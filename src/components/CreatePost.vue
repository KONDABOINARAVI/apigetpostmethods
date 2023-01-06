<template>
    <div>
      <form @submit.prevent="createPost">
        <div>
          <label for="userId">UserID:  </label>
          <input type="text" id="userId" v-model="postData.userId">
        </div>
        <br/>
        <div>
          <label for="title">Title: </label>
          <input type="text" id="title" v-model="postData.title">
        </div>
        <br/>
        <div>
          <label for="body">Body:  </label>
          <input type="text" id="body" v-model="postData.body">
        </div>
        <br/>
        <button>Create Post</button>
      </form>
    </div> 
  </template>
  
  <script>
  import axios from 'axios'
  
  export default {
    data() {
      return {
        postData: {
          userId: '',
          title:  '',
          body:   ''
        }
      }
    },
    methods: {
        createPost() {
          axios
            .post('https://jsonplaceholder.typicode.com/posts', this.postData)
            .then((response) => console.log(response))
      }
    }
  }
  </script>
<style scoped>
</style>
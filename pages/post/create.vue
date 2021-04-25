<template>
 <div class="page mt-5 text-center">
    <form @submit.prevent="post">
      <p><input type="text" v-model="title" placeholder="title" name="title"/></p>
      <p><input type="text" v-model="body" placeholder="body" name="body"/></p>
      <div class="login-btn">
        <button type="submit">提案</button>
      </div>
    </form>
 </div>
</template>

<script>
import axios from 'axios'

export default {
 data () {
   return {
    valid: false,
     title: [],
     body: []
   }
 },
 methods: {
  post() {
    axios.post('http://917f02cb43ed.ngrok.io/api/', {
      Title: this.title,
      Body: this.body
    })
      .then(function (response) {
        console.log(response);
      })
      .catch(function (error) {
        console.log(error);
      });
    this.$router.push('/')
  }
 }
}
</script>
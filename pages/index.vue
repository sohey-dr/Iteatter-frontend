<template>
 <div class="page">
   <ul>
     <li v-for="post in posts" :key="post.ID">
        {{ post.Title }}
     </li>
   </ul>
 </div>
</template>

<script>
import axios from 'axios'

export default {
 data () {
   return {
     posts: [],
   }
 },
 mounted () {
   axios.get('http://917f02cb43ed.ngrok.io/api/')
     .then((response) => this.posts = response.data)
 }
}
</script>

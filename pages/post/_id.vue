<template>
 <div class="page">
   {{ posts.Title }}
   
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
   axios.get('http://917f02cb43ed.ngrok.io/api/' + this.$route.params.id)
     .then((response) => this.posts = response.data)
 }
}
</script>
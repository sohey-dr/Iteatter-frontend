<template>
 <div class="page mt-5 text-center">
   <h3>{{ post.Title }}</h3>
   <p>{{ post.Body }}</p>
 </div>
</template>

<script>
import axios from 'axios'

export default {
 data () {
   return {
     post: [],
   }
 },
 mounted () {
   axios.get('http://917f02cb43ed.ngrok.io/api/' + this.$route.params.id)
     .then((response) => this.post = response.data)
 }
}
</script>
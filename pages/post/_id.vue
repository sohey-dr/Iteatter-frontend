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
   axios.get(process.env.BACK_URL + this.$route.params.id)
     .then((response) => this.post = response.data)
 }
}
</script>
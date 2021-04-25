<template>
 <div class="page mt-3">
    <div class="text-center mb-5" v-for="post in posts" :key="post.ID">
      <nuxt-link :to="`/post/${post.ID}`">{{ post.Title }}</nuxt-link>
    </div>
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
   axios.get(process.env.BACK_URL)
     .then((response) => this.posts = response.data)
 }
}
</script>

<style>
</style>

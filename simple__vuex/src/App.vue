<template>
  <div id="app">
    <PostForm/>
    <h1>{{postCount}}</h1>
    <div class="post" v-for="post in validPosts" :key="post.id">
      <h2>{{post.title}}</h2>
      <p>{{post.body}}</p>
    </div>
  </div>
</template>

<script>
import {mapGetters, mapActions} from 'vuex';
import PostForm from './components/PostForm'
export default {
  name: 'app',
  components: {PostForm},
  computed: mapGetters(['validPosts', 'postCount']),
  methods: mapActions(['fetchPosts']),
  async mounted() {
    // this.$store.dispatch('fetchPosts')
    this.fetchPosts();
  }
}
</script>

<style>
#app {
  margin: 60px auto;
  width: 400px;
  text-align: center;
  color: #333;
}

.post {
  border: 1px solid #999;
  border-radius: 2px;
  margin: 10px 0;
  padding: 5px;
}

</style>

<template>
  <div v-if="posts.length" class="container">
    <div class="row">
      <ul class="list-group-bank three-columns">
        <li v-for="post in posts" :key="post.id">
          <p>{{post.title}}</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>

export default {
  name: 'CountriesList',
  props: {
    posts: {
      type: Array,
      required: true,
    }
  }
};
</script>

<style scoped>

</style>

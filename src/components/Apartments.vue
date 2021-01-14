<template>
  <div class="list_header">
    <h2>Stays in Finland</h2>
    <span>{{ posts.length }} stays</span>
  </div>
  <ul class="posts_container">
    <li class="post_container_li" v-for="post in posts" v-bind:key="post.id">
      <PostItem
        :title="post.title"
        :src="post.photo"
        :superhost="post.superHost"
        :rating="post.rating"
        :apartmentType="post.type"
      />
    </li>
  </ul>
</template>

<script>
import PostItem from "../components/PostItem";

export default {
  name: "Apartments",
  components: {
    PostItem,
  },
  props: {
    posts: Array,
  },
};
</script>
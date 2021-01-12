<template>
  <div class="list_header">
    <h2>Stays in Finland</h2>
    <span>{{posts.length}} stays</span>
  </div>
  <ul class="posts_container">
    <li class="post_container_li" v-for="post in posts" v-bind:key="post.id">
      <PostItem :title="post.title" :img="post.img" :superhost="post.superhost" :rating="post.rating"/>
    </li>
  </ul>
  <Footer />
</template>

<script>
import PostItem from "./components/PostItem";
import Footer from "./components/Footer";

export default {
  name: "App",
  components: {
    PostItem,
    Footer,
  },
  data() {
    return {
      posts: [
        {
          id: 1,
          title: "Stylist apartment in center of the city",
          img: "../assets/hotel.jpeg",
          superhost:true,
          rating:4.2
        },
        {
          id: 2,
          title: "Cozy, peaceful and private room with...",
          img: "../assets/hotel.jpeg",
          superhost:false,
          rating:4.5
        },
        {
          id: 3,
          title: "Cozy, peaceful and private room with...",
          img: "../assets/hotel.jpeg",
          superhost:false,
          rating:4
        },
        {
          id: 4,
          title: "Cozy, peaceful and private room with...",
          img: "../assets/hotel.jpeg",
          superhost:true,
          rating:3.9
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 1150px;
  margin: 0 auto;
}
li{
  list-style-type: none;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.posts_container {
  display: grid;
  grid-template-columns: 33% 33% 33%;
  gap: 10px;
}
.post_container_li {
  width: 100%;
  height: auto;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.list_header {
  display: flex;
  justify-content: space-between;
  margin: 1rem 0;
}
</style>

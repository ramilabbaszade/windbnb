<template>
  <div class="post_image">
    <img :src="img" :alt="title" />
  </div>
  <div class="post_info_container">
    <div class="post_info">
      <div class="post_info-superhost" v-if="superhost">SUPER HOST</div>
      <div class="post_info-extra">Entire apartment . 2 beds</div>
      <div class="post_info-rating"> {{rating}}</div>
    </div>
    <div class="post_header">{{ title }}</div>
  </div>
</template>

<style >
.post_header {
  font-size: 16px;
  font-weight: bold;
  padding: 15px 0;
}
.post_image {
  width: 100%;
  height: 190px;
}
.post_image img {
  width: 100%;
  height: 100%;
  border-radius: 24px;
  object-fit: cover;
}
.post_info_container{
    padding: 10px 0;
}
.post_info {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.post_info-superhost {
  border: 1px solid black;
  border-radius: 15px;
  font-weight: bold;
  padding: 5px;
  font-size: 12px;
}
.post_info-extra {
  font-size: 14px;
  opacity: 0.7;
}
.post_info-rating {
  font-size: 14px;
}
</style>

<script>
export default {
  name: "PostItem",
  props: {
    title: String,
    img: String,
    superhost:Boolean,
    rating:Number
  },
};
</script>
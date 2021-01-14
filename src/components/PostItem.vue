<template>
  <div>
    <div class="post_image">
      <img :src="src" :alt="title" />
    </div>
    <div class="post_info_container">
      <div class="post_info">
        <div class="post_info-superhost" v-if="superhost">SUPER HOST</div>
        <div class="post_info-extra">{{ apartmentType }}</div>
        <div class="post_info-rating">
          <img
            src="../../public/assets/icons/star.png"
            alt="star"
            class="icon_png"
          />
          {{ rating }}
        </div>
      </div>
      <div class="post_header">{{ title }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PostItem",
  props: {
    title: String,
    src: String,
    superhost: Boolean,
    rating: Number,
    apartmentType: String,
  },
};
</script>


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
  border-radius: 5px;
  object-fit: cover;
}
.post_info_container {
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

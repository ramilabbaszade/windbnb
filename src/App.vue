<template>
  <Navigation :posts="posts" />
  <Apartments :posts="filterData"/>
  <Footer />
</template>

<script>
import Footer from "./components/Footer";
import Navigation from "./components/Navigation";
import appartamentsData from './apartmentsData.json';
import Apartments from './components/Apartments.vue';

export default {
  name: "App",
  components: {
    Footer,
    Navigation,
    Apartments,
  },
  data() {
    return {
      aisdeOpen: false,
      adult: 0,
      child: 0,
      appartamentsData,
      filterData: JSON.parse(JSON.stringify(appartamentsData)),
      citiesData: [],
      city: null,
    };
  },
  methods: {
    toggleAside() {
      this.aisdeOpen = !this.aisdeOpen;
    },
    adults(value) {
      this.adult = value;
    },
    childrens(value) {
      this.child = value;
    },
    filterGuests() {
      let temp = this.appartamentsData;
      if (this.city) {
        temp = temp
          .filter((el) => el.city === this.city)
          .filter((el) => el.maxGuests >= this.adult + this.child);
      } else {
        temp = this.appartamentsData
          .filter((el) => el.maxGuests >= this.adult + this.child);
      }
      console.log(this.city);
      this.filterData = temp;
      this.aisdeOpen = false;
    },
    filterCity(value) {
      if (value) {
        const [city] = value.split(' ');
        this.city = city;
      } else {
        this.city = null;
      }
    },
  },
  computed: {
    guests() {
      return this.adult + this.child;
    },
  },
  created() {
    const cities = [...new Set(appartamentsData.map((el) => el.city))];
    cities.forEach((el) => {
      this.citiesData = [...this.citiesData, `${el} ${appartamentsData.find((fel) => fel.city === el).country}`];
    });
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
li {
  list-style-type: none;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Montserrat", "Mulish", sans-serif;
}
.posts_container {
  display: grid;
  grid-template-columns: 25% 25% 25% 25%;
  column-gap: 2px;
}
.post_container_li {
  width: 100%;
  height: auto;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  overflow: hidden;
}
.list_header {
  display: flex;
  justify-content: space-between;
  margin: 1rem 0;
}
.icon_png {
  width: 14px;
}
</style>

<template>
  <div class="navigation" >
    <div class="navigation_logo">
      <img src="../../public/assets/icons/logo.png" alt="" />
    </div>
    <div class="navigation_search" @click="toggleFilter">
      <div class="navigation_search_city">Helsinki, Finland</div>
      <div class="navigation_search_addguests">Add guests</div>
      <div class="navigation_search_bar">
        <img
          src="../../public/assets/icons/search.png"
          alt="star"
          class="icon_png"
        />
      </div>
    </div>
  </div>
  <div class="backdrop" v-if="isFiltering">
    <div class="filter_container" >
      <div class="filterBar">
        <div @click="closeGuests" class="filterBar_item filterBar_location">Location</div>
        <div @click="openGuests" class="filterBar_item filterBar_guests">Guests</div>
        <button>Search</button>
      </div>
      <div class="filterOptions">
          <ul v-if="isGuests===false" class="filterOptions_location">
                  <li>Helsinki, Finland</li>
                  <li>Helsinki, Finland</li>
                  <li>Helsinki, Finland</li>
                  <li>Helsinki, Finland</li>
                  <li>Helsinki, Finland</li>
          </ul>
          <div v-if="isGuests===true" class="filterOptions_guests">
              <div class="filterOptions_guests_adults">
                  <h5>Adults</h5>
                  <small>Ages 13 or above</small>
                  <div class="filterOptions_guests_counter">
                      <span>-</span>  {{adults}} <span>+</span>
                  </div>
              </div>
              <div class="filterOptions_guests_children">
                  <h5>Children</h5>
                  <small>Ages 2-12</small>
                  <div class="filterOptions_guests_counter">
                      <span>-</span>  0 <span>+</span>
                  </div>
              </div>
          </div>
      </div>
    </div>
    <div @click="toggleFilter" class="backdrop_closer"></div>
  </div>
</template>

<script>
export default {
  name: "Navigation",
  props:{
      posts:Array
  },
  data() {
    return {
      isFiltering: false,
      isGuests: false,
      adults:0
    };
  },
  methods: {
    toggleFilter() {
      this.isFiltering = !this.isFiltering;
    },
    openGuests() {
      this.isGuests = true;
    },
    closeGuests() {
      this.isGuests = false;
    },
    incrementCount(){

    },
    decrementCount(){}
  },
};
</script>

<style scoped>
.navigation {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 0;
}
.navigation_search {
  display: flex;
  border-radius: 16px;
  box-shadow: 0px 1px 6px rgba(0, 0, 0, 0.1);
}
.navigation_search_addguests {
  font-family: "Mulish", sans-serif;
  opacity: 0.5;
  border-right: 3px solid #e9e9e9b9;
  border-left: 3px solid #e9e9e9b9;
  padding: 0.8rem;
}
.navigation_search_city {
  font-family: "Mulish", sans-serif;
  padding: 0.8rem;
}
.navigation_search_bar {
  font-family: "Mulish", sans-serif;
  padding: 0.8rem;
}

.backdrop {
  position: fixed;
  top: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  z-index: 97;
}
.backdrop_closer {
  height: 100%;
}
.filter_container {
  margin: 0 auto;
  height: 70%;
  background: white;
  padding: 1rem 2rem;
  z-index: 99;
}
.filterBar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.filterBar_item{
  text-align: center;
  width: 100%;
  border: 1px solid rgba(177, 177, 177, 0.589);
  border-radius: 10px;
  background: #f1f1f1;
  padding: .5rem 0;
}
input {
  width: 100%;
}
button {
  border: none;
  padding: 0.5rem 1rem;
  background: tomato;
  color: white;
  border-radius: 10px;
}
li {
  margin: 1rem 0;
}
span{
    border: 1px solid rgba(0, 0, 0, 0.445);
    padding: 0 5px;
}

.filterOptions_guests {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 1rem;
  margin: 2rem 0;
  text-align: center;
}
</style>
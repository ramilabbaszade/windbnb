<template>
    <div class="navigation">
      <div class="navigation_logo">
        <img src="../../public/assets/icons/logo.png" alt="">
      </div>
      <div class="navigation_search">
        <div class="navigation_search_city">Helsinki, Finland</div>
        <div class="navigation_search_addguests">Add guests</div>
        <div class="navigation_search_bar">
          <img src='../../public/assets/icons/search.png' alt="star" class="icon_png">
        </div>
      </div>
    </div>
</template>

<script>
export default {
    name:'Navigation',
    data(){
        return{
            toggleFilter:false
        }
    }
}
</script>

<style>
    .navigation{
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem 0;
    }
    .navigation_search{
        display: flex;
        border-radius: 16px;
        box-shadow: 0px 1px 6px rgba(0, 0, 0, 0.1);
    }
    .navigation_search_addguests{
        font-family: 'Mulish', sans-serif;
        opacity: .5;
        border-right: 3px solid #e9e9e9b9;
        border-left: 3px solid #e9e9e9b9;
        padding: .8rem;
    }
    .navigation_search_city{
        font-family: 'Mulish', sans-serif;
        padding: .8rem;
    }
    .navigation_search_bar{
        font-family: 'Mulish', sans-serif;
        padding: .8rem;
    }
</style>
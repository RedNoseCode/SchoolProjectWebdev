<template>
    <div class="background">
        <div id="nav">
            <router-link to="/dishes"><v-btn>Retter</v-btn></router-link> 
           
            <router-link to="/drinks"><v-btn>Drikke</v-btn></router-link> 
            
            <router-link to="/dessert"><v-btn>Dessert</v-btn></router-link>
        </div>
        <h1>Alle Retter</h1>
        <DishList />

    </div>
</template>

<script>
import DishList from '@/components/Dish/DishList.vue'
export default {
    name:"Dishes",
    components: {
        DishList
    }
}
</script>

<style lang="scss">
.background{
  background: url('../components/images/Frontpage/pizzabackground.jpg');
  height: 100%;
  /*width: 100%;*/
  background-position: center;
  background-size: cover;
}

#nav a{ 
  color: #ffffff;
  text-decoration: none;
  list-style-type: none;
  text-align: center;
  margin: 3px;
}
</style>

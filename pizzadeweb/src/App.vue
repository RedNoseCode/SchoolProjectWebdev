<template>
<nav >
<v-app>
  <div id="toolbar1">
    <v-toolbar dark
    padless>
      <router-link to="/"><nav><ul style="list-style: none;"><li><a>Customer</a></li></ul></nav></router-link>
      <router-link to="/admin"><nav><ul style="list-style: none;"><li><a>Admin</a></li></ul></nav></router-link>
      <v-spacer></v-spacer>

<v-toolbar-title id="titlePizza">Pizza de Web</v-toolbar-title>
 <v-spacer></v-spacer>

      <router-link to="/meny"><nav><ul style="list-style: none;"><li><a>Meny</a></li></ul></nav></router-link>
      <router-link to="/about"><nav><ul style="list-style: none;"><li><a>About</a></li></ul></nav></router-link>
      <router-link to="/"><nav><ul style="list-style: none;"><li><a>Home</a></li></ul></nav></router-link>
      
    </v-toolbar>
  </div> 
     
    <div>
      <router-view/>
      <router-link to="/meny"><h1></h1></router-link> 
      <router-link to="/about"></router-link> 
    </div>

  <v-footer 
    dark
    padless>
    <v-row
      justify="center">
  
      <v-card>
      <v-card-text>ABOUT</v-card-text>
  
      <v-card-text class="white--text pt-0">
      Lorem ipsum dolor sit amet consectetur m laudantium cum ipsa, hic i consectetur adipisicing elit.ipsum dolor sit amet consectetur m laudantium cum ipsa, hic i consectetur adipisicing elit. Nihil sint beatae accusamus necessitatibus, corrupti, numquam dolorum eveniet expedita officiis fugiat omnis ullam pariatur dicta explicabo minima iure aliquid quos assumenda?
      </v-card-text>
      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>PizzaDeWeb</strong>
      </v-card-text>
      </v-card>
    </v-row>
  </v-footer>
  


</v-app>

</nav>
</template>

<style lang="scss">
#titlePizza{
  color:#ffffff;
}
@media all and (min-width: 0.1px) and (max-width: 599.9px){#titlePizza{
  display:none;

}
 

}



#toolbar1 a{
  color: #ffffff;
  text-decoration: none;
  list-style-type: none;
  text-align: center;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffff;
}

#nav {
  padding-top:5px;
  min-height: 70px;
  

  a {
    font-weight: bold;
    

    &.router-link-exact-active {
      color: #ffff;
    }
  }

}


</style>

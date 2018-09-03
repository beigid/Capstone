<template>
  <div id="app">
    
     <div>
        <div  class="sidenav" :class="{shownav:isOpen}">
          <a href="javascript:void(0)" class="closebtn" id="closeNav" v-on:click='isOpen = !isOpen'>&times;</a>
         <router-link to="/about">About</router-link>
            <br><router-link to="/contact">Contact</router-link>
            <br><router-link to="/">Track Music</router-link>
        </div>
        
        <span style="font-size:35px;cursor:pointer; padding-left:10px; color:white;" id="openNav" v-on:click='isOpen = !isOpen'>&#9776;</span>
  </div>
    <router-view/>
 
  </div>
</template>


<script>
import Music from "./components/Music";

export default {
  name: "App",
   data() {
    return {
    isOpen: false,
    shownav: ""
    }
  },
  methods: {
    toggle: function() {
      this.isOpen = !this.isOpen;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#results li {
  padding-bottom: 30px;
  padding-top: 35px;
}

#openNav {
    position: absolute;
    top: 10px;
    left: 15px;
}

.sidenav {
  height: 100%;
  width: 0;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  background-color: #e9b2d9;
  overflow-x: hidden;
  transition: 0.5s;
  padding-top: 60px;
}

.sidenav a {
  padding: 8px 8px 8px 32px;
  text-decoration: none;
  font-size: 25px;
  color: #818181;
  display: block;
  transition: 0.3s;
}

.sidenav a:hover {
  color: #f1f1f1;
}

.sidenav .closebtn {
  position: absolute;
  top: 0;
  right: 25px;
  font-size: 36px;
  margin-left: 50px;
}
.shownav {
    width: 250px;
}

@media screen and (max-height: 450px) {
  .sidenav {
    padding-top: 15px;
  }
  .sidenav a {
    font-size: 18px;
  }
}
</style>
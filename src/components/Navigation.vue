<template>

<div>
  <div id="mySidenav" class="sidenav">
          <a href="javascript:void(0)" class="closebtn" onclick="closeNav()">&times;</a>
         <router-link to="/about">About</router-link>
    <br><router-link to="/contact">Contact</router-link>
        </div>
        
        <span style="font-size:35px;cursor:pointer; padding-left:10px; color:white;" id="openNav">&#9776;</span>
</div>
</template>

 <script>
        function openNav() {
            document.getElementById("mySidenav").style.width = "250px";
        }
        
        function closeNav() {
            document.getElementById("mySidenav").style.width = "0";
        }
   
        </script>

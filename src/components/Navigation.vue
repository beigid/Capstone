<template>

<div>
  <div id="mySidenav" class="sidenav">
          <a href="javascript:void(0)" class="closebtn" id="closeNav">&times;</a>
         <router-link to="/about">About</router-link>
    <br><router-link to="/contact">Contact</router-link>
        </div>
        
        <span style="font-size:35px;cursor:pointer; padding-left:10px; color:white;" id="openNav">&#9776;</span>
</div>
</template>

 <script>
         document.getElementById("openNav").addEventListener('click', function() {
            document.getElementById("mySidenav").style.width = "250px";
        });
        
        document.getElementById("closenNav").addEventListener('click', function() {
            document.getElementById("mySidenav").style.width = "0";
        });
   
        </script>

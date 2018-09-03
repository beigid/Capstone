<template>
  <div>
    <h1>Contact</h1>
    <p>To find out more, please check out the <a class="grow" href="https://affiliate.itunes.apple.com/resources/documentation/itunes-store-web-service-search-api/" title="iTunes API" target="_blank">iTunes API</a> page and try it out yourself!</p>
  </div>
</template>

<script>
export default {
  name: 'Contact' 
}
</script>
<style>

h1,
h2 {
  font-weight: normal;
  font-size:3em;
  color:white;
  font-family: 'PT Sans', sans-serif;

}

h1:hover {
  color:#5c63b8;
}

p {
  color:white;
}

a.grow{
  text-decoration:none;
  display:inline-block;
}

.grow { transition: all .2s ease-in-out; }
.grow:hover { transform: scale(1.1); }
</style>
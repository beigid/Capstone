<template>        
 <div class="Music">

    <h1 class="grow">iTunes Music Finder</h1>
    
<form v-on:submit.prevent="findmusic">
      <input type="text" id="myInput" v-model="artist" placeholder="Search Favorite Artist.." title="Type in a name" style="padding-bottom: 5px; padding-top: 3px;">
<input type="submit" value="Submit" class="buttonStyle"></p>
</form>

<div>
<ul id="results">
  <li v-for="result in results" class="styledList">
    <span><img v-bind:src="result.artworkUrl100"></span>
    <div><span><a v-bind:href="result.trackViewUrl" target="_blank">{{result.trackCensoredName}}</a></span> -
   <br><span><a v-bind:href="result.artistViewUrl" target="_blank">{{ result.artistName }}</a></span></div>
 
<div>
<audio controls preload="none">
 <source  v-bind:src="result.previewUrl" />
 </audio>
 </div>
   
   
  </li>
</ul>
</div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "Music",
  data() {
    return {
      results: [],
      errors: [],
      entity: "",
      atribute: "",
      artist: "",
      msg: "Itunes Search"
    };
  },
  methods: {
    findmusic: function() {
      axios
        .get("https://itunes.apple.com/search", {
          params: { term: this.artist, limit: "15" }
        })
        .then(response => {
          this.results = response.data.results;
        })
        .catch(error => {
          this.errors.push(error);
        });
    }
  
  }
};
</script> 

<style scoped>

h1,
h2 {
  font-weight: normal;
  font-size:4em;
  color:white;
  font-family: 'PT Sans', sans-serif;

}

h1:hover {
  color:#5c63b8;
}

.grow { transition: all .2s ease-in-out; }
.grow:hover { transform: scale(1.1); }

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: block;
  margin: 0 10px;
  border: 2px solid white;
}
a {
  color: #010a06;
}

li.styledList {
margin-left: 20%;
margin-right: 20%;
margin-bottom: 20px;
margin-top:20px;
background-color: rgba(246, 227, 244, 0.4);
border-radius:15px;
}

audio {
  width: 80%;
}

.buttonStyle {
display: inline-block;
    padding: 6px 12px;
    margin-bottom: 0;
    font-size: 14px;
    font-weight: 400;
    line-height: 1.42857143;
    text-align: center;
    white-space: nowrap;
    vertical-align: middle;
    -ms-touch-action: manipulation;
    touch-action: manipulation;
    cursor: pointer;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    background-image: none;
    border: 1px solid transparent;
    border-radius: 4px;
    color: #fff;
    background-color: #5c63b8;
    border-color: #5f63d8;
}

</style>
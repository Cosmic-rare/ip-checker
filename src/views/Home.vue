<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <div>
      <input id='bt' @click="getIp" type="button" value="Get IP!">
      <p>{{ ip }}</p>
    </div>
  </div>
</template>

<script>
import axios from "axios"
  export default {
  name: 'SearchIp',
  data () {
    return {
      ip: ''
    }
  },
  methods: {
    getIp() {
      axios.get('https://httpbin.org/get')
        .then((response) => {
          this.ip = response.data.origin;
        })
        .catch((e) => {
          alert(e);
        });
    }
  }
}
</script>

<style>
#bt {
	display: block;
	position: relative;
	width: 160px;
	padding: 0.8em;
	text-align: center;
	text-decoration: none;
	color: #fff;
	background: #41B883;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
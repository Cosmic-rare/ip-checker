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
  width: 100px;
  height: 30px;
  background-color: #41B883;
  color: #FFFFFF;
  text-align: center;
  text-decoration: none;
  line-height: 30px;
  border-radius: 5px;
  border: 3px solid #41B883;
}

#bt:hover {
  text-decoration: none;
  background-color: #FFFFFF;
  color: #41B883; 
}
</style>
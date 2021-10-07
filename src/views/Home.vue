<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <div>
      <input @click="getIp" type="button" value="Get IP!">
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
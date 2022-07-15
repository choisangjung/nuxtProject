<template>
    <div>
        <h1>Welcome to {{ myVue4 }}</h1> 
        <button @click="goHOME">go to {{home}}</button>
        <h1>{{data}}</h1>
    </div>
</template>
<script>

import axios from "axios";

export default {
  data() {
    return {
      myVue1 : "myVue1",
      myVue2 : "myVue2",
      myVue3 : "myVue3",
      myVue4 : "myVue4",
      myVue5 : "myVue5",
      home : "HOME",
      data : ""
    };
  },
  methods: {
    goHOME(){
    this.$router.push("/");
    },
    async fetchThing() {
      const response = await axios.get('http://localhost:3080/api/GETPRCOALIST')
      this.data = response.data;
    }
  },
  created() {
    this.fetchThing();
  }
}
</script>
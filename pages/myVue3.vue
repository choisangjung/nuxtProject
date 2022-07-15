<template>
    <div>
        <h1>POST API</h1>
        <button class="btn btnHome" @click="goHOME">HOME</button>
        <h1>({{connectData}})</h1>
    </div>
</template>
<script>

import axios from "axios";

export default {
  data() {
    return {
      connectData : ""
    };
  },
  methods: {
    goHOME(){
    this.$router.push("/");
    },
    async fetchThing() {
      const response = await axios.get('http://localhost:3080/api/TESTLIST2')
      this.connectData = response.data;
    }
  },
  created() {
    this.fetchThing();
  }
};
</script>

<style scoped>
.btn {
  text-decoration: none;
  padding: 20px 20px;
  font-size: 1.25rem;
  position: relative;
}

.btnHome {
  background: #000;
  color: #fff;
  border-radius: 30px;
  transition: transform 0.3s ease;
  box-shadow: 0 0 0 0 rgba(143, 64, 648, 0.5),10px -10px 25px 0 rgba(39, 200, 255, 0.5);
}

.btnHome:hover {
  cursor: pointer;
  transform: translateY(-0.25em);
}
</style>
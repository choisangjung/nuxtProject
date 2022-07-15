<template>
    <div>
        <h1>Welcome to {{ myVue5 }}</h1> 
        <v-btn class="btn btnHome" @click="goHOME">{{home}}</v-btn>
    </div>
</template>
<script>
export default {
  data() {
    return {
      myVue1 : "myVue1",
      myVue2 : "myVue2",
      myVue3 : "myVue3",
      myVue4 : "myVue4",
      myVue5 : "myVue5",
      home : "HOME"
    };
  },
  methods: {
    goHOME(){
    this.$router.push("/");
    },
  }
}
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
<template>
  <div>
    <h1>Nuxt.js</h1> 
    <button class="btnMyVue" @click="goMyVue1">go to {{myVue1}}</button>
    <button class="btnMyVue" @click="goMyVue2">go to {{myVue2}}</button>
    <button class="btnMyVue" @click="goMyVue3">go to {{myVue3}}</button>
    <button class="btnMyVue" @click="goMyVue4">go to {{myVue4}}</button>
    <button class="btnMyVue" @click="goMyVue5">go to {{myVue5}}</button>
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
    }
  },
  methods: {
    goMyVue1(){
      this.$router.push("/myVue1");
    },
    goMyVue2(){
      this.$router.push("/myVue2");
    },
    goMyVue3(){
      this.$router.push("/myVue3");
    },
    goMyVue4(){
      this.$router.push("/myVue4");
    },
    goMyVue5(){
      this.$router.push("/myVue5");
    },
  }
}
</script>

<style scoped>
  .btnMyVue {
    background : #000;
    color : #fff;
    border-radius: 30px;
    transition : transform 0.3s ease;
  }
</style>
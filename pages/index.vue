<template>
  <div>
    <h1>NUXT.js</h1><br><br>
    <div>
      <button class="btn btnMyVue" @click="goMyVue1">go to myVue1 </button>
      <button class="btn btnMyVue" @click="goMyVue2">go to myVue2 </button>
      <button class="btn btnMyVue" @click="goMyVue3">go to myVue3 </button>
      <button class="btn btnMyVue" @click="goMyVue4">go to myVue4 </button>
      <button class="btn btnMyVue" @click="goMyVue5">go to myVue5 </button>
      <button class="btn btnMyVue" @click="goMyVue6">go to myVue6 </button>
      <button class="btn btnMyVue" @click="goMyVue7">go to myVue7 </button>
    </div>
  </div>
</template>

<script>
export default {  
  methods: {
    goMyVue1() {
      this.$router.push("/myVue1");
    },
    goMyVue2() {
      this.$router.push("/myVue2");
    },
    goMyVue3() {
      this.$router.push("/myVue3");
    },
    goMyVue4() {
      this.$router.push("/myVue4");
    },
    goMyVue5() {
      this.$router.push("/myVue5");
    },
    goMyVue6() {
      this.$router.push("/myVue6");
    },
    goMyVue7() {
      this.$router.push("/myVue7");
    },
  },
};
</script>

<style scoped>
.btnMyVue {
  background: #000;
  color: #fff;
  border-radius: 30px;
  transition: transform 0.3s ease;
  box-shadow: 0 0 0 0 rgba(143, 64, 648, 0.5),10px -10px 25px 0 rgba(39, 200, 255, 0.5);
}

.btn {
  text-decoration: none;
  padding: 20px 20px;
  font-size: 1.25rem;
  position: relative;
}
.btn:hover {
  cursor: pointer;
  transform: translateY(-0.25em);
}
</style>
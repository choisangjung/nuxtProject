<template>
    <div>
        <h1>Welcome to {{ myVue5 }}</h1> 
        <button class="btn btnIndex">go to {{home}}</button>
        <v-btn @click="goHOME">go to {{home}}</v-btn>
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
    position: relative;
  }

  .btnIndex {
    overflow: hidden;
    color: #fff;
    border-radius: 30px;
    box-shadow: 0 0 0 0 rgba(143, 64, 648, 0.5), 0 0 0 0;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .btnIndex::after {
    content: "";
    width: 400px;
    height: 400px;
    position: absolute;
    top: -50px;
    left: -100px;
    background-color: #ff3cac;
    background-image: linear-gradient(
      225deg,
      #27d86c 0%,
      #26caf8 50%,
      #c625d0 100%
    );
    z-index: -1;
    transition: transform 0.5s ease;
  }

  .btnIndex:hover {
    transform : translate(0,-6px);
    box-shadow: 10px -10px 25px 0 rgba(143, 64, 248, 0.5) 10px -10px 25px 0 rgba(39, 200, 255, 0.5);
  }

  .btnIndex:hover::after {
    transform: rotate(150deg);
  }
</style>
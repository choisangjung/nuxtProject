<template>
    <div>
        <h1>Welcome to {{ myVue3 }}</h1>
        <button @click="goHOME">go to {{home}}</button>
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
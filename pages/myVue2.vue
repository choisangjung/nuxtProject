<template>
  <div>
    <div>
      <h1>Welcome to {{ title2 }}</h1> 
      <button @click="goHOME">go to {{home}}</button>
      <input type="text" v-model="input1" />
      <button type="button" @click="getData">GET</button>
      <button type="button" @click="setData">SET</button>
    </div>
    <div>
      <select class="form-control">
        <option :key="i" :value="d.v" v-for="(d, i) in options">
          {{ d.t }}
        </option>
      </select>
      <select class="form-control" v-model="region">
        <option :key="i" :value="d.v" v-for="(d, i) in options">
          {{ d.t }}
        </option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title1: "title1",
      title2: "title2",
      input1: "abcd",
      options: [
        { v: "S", t: "Seoul" },
        { v: "J", t: "Jeju" },
        { v: "B", t: "Busan" },
      ],
      region: "J",
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
    getData() {
      alert(this.input1);
    },
    setData() {
      this.input1 = "123123123123";
    },
  },
  beforeCreate() {
    console.log("beforeCreate");
  },
  created() {
    console.log("created");
  },
  beforeMount() {
    console.log("beforeMount");
  },
  mounted() {
    console.log("mounted");
  },
  beforeUpdate() {
    console.log("beforeUpdate");
  },
  updated() {
    console.log("updated");
  },
  beforeDestroy() {
    console.log("beforeDestroy");
  },
  destroyed() {
    console.log("destroyed");
  },
};
</script>

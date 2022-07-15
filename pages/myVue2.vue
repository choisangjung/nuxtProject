<template>
  <div>
    <div>
      <h1>GET,SET</h1> 
      <button class="btn btnHome" @click="goHOME">HOME</button><br><br>
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
      input1: "abcd",
      options: [
        { v: "S", t: "Seoul" },
        { v: "J", t: "Jeju" },
        { v: "B", t: "Busan" },
      ],
      region: "J",
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
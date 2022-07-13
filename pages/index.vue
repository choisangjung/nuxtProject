<template>
  <div>
    <div>
      <h1>Welcome to {{ title2 }}</h1>
      <input type="text" v-model="input1" />
      <button type="button" @click="getData">GET</button>
      <button type="button" @click="setData">SET</button>
    </div>
    <div>
      <ul>
        <li id="myVue" v-for="item in list" v-bind:key="item">
          {{item}}
        </li>
      </ul>
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
new Vue({
  el: '#myVue',
  data: {
    list : ['Seoul','Busan','Daegu']
  }
});
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
    };
  },
  methods: {
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

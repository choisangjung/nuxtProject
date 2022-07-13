<template>
  <div>
    <h1>Welcome to {{ myVue1 }}</h1> 
    <button @click="goHOME">go to {{home}}</button>
    <ul>
        <li v-for="item in list" v-bind:key="item">
        {{item}}
        </li>
    </ul>
</div>
</template>

<script>
export default{
  data() {
    return {
      list : ['mine','it','record'],
      myVue1 : "myVue1",
      myVue2 : "myVue2",
      myVue3 : "myVue3",
      myVue4 : "myVue4",
      myVue5 : "myVue5",
      home : "HOME"
    }
  },
  methods: {
  goHOME(){
    this.$router.push("/");
    }
  },
}
</script>

<template>
  <div>
    <h1>V-FOR</h1> 
    <button class="btn btnHome" @click="goHOME">HOME</button>
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
      list : ['mine','it','record']
    }
  },
  methods: {
  goHOME(){
    this.$router.push("/");
    }
  },
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
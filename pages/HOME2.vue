<template>
  <div>
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
    }
}
</script>

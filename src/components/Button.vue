
<script>
 import './Styles.vue';
 export default {
     props:{
         msg: {
             type: String,
             required: true
      }
    }
 }
</script>
<template>
      <button>{{msg}}</button>
</template>
<style>
</style>
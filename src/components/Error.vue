<template>
      <p 
      class="error"
      >{{ msg }}
    </p>
</template>
<script>
 export default {
 props:{
         msg: {
             type: String,
             required: true
      },
    }
 }
</script>
<style>
.error {
    color:beige;
    padding: 10px;
    font-weight: 800;
    background-color: red;
    text-transform: uppercase; 
    border-radius: 8px;
    text-align: center;
  }
  </style>
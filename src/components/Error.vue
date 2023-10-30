<template>
      <p 
      class="error"
      ><slot></slot>
    </p>
</template>
<script>
 export default {
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
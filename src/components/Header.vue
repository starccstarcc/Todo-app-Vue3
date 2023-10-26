<script>
 import Button from './Button.vue'
 export default {    
    props: {
      items: Object, 
    },
    emits: ['input'],
    components: {
        Button
    },
    methods:{
  addItem() {
    this.items.push({ id: Date.now(), task: this.currentValue, completed: false });
    this.currentValue='' 
  },
  handleSubmit(){
    this.addItem()
},
}    
 }
</script>
<template>
<form 
class="container" 
@submit.prevent="handleSubmit"
>
      <div class="header">
          <input 
          type="text" 
          v-model="currentValue" 
          />
  <Button 
  msg="Añadir" 
  class="primary"
  ></Button>
      </div>
     </form>
</template>
<style scoped>

.container  {
  background-color:white;
  border-radius: 2px;
  margin-bottom: 20px;
  padding: 13px;
  display: flex;
  box-shadow: 3px 3px 3px lightgray;
}

.header {
  width: 100%;
  display: flex;
    max-width: 100%;
    position: relative;
  }

.header input {
  display: block;
    padding: 1rem 2rem;
    width: 100%;
    background: whitesmoke;  
    border: none;
    color:black;
    text-align: left;
    text-decoration: none;
    font-size: 16px;
    outline:white;
    border-radius: 2px;
  }

.header button {
  display: block;
    height: 70%;
  
     position: absolute; 
    right:2%;
    transform: translateX(-10%);
    top: 17%;
  }

  @media (prefers-color-scheme: dark) {
      .header input{
        background-color:grey;
      }
      .container {
        background-color:dimgrey;
        box-shadow: 3px 3px 3px gray
      }
   } 

   @media (prefers-color-scheme: dark) {
      .header input{
        background-color:grey;
      }
      .container {
        background-color:dimgrey;
        box-shadow: 3px 3px 3px gray
      }
     
   } 
 
</style>


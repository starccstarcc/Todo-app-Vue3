<script>
 import Button from './Button.vue'
 import Error from './Error.vue'
 export default {    
    props: {
      items: Object,
    },
    emits: ['input'],
    components: {
        Button,
        Error
    },
    data() {
      return {
        newItem: '',
        inputError: false,
      };
    },
    methods:{
addItem() {
            if (this.newItem.trim() === '') {
                console.log(this.newItem.trim());
          this.inputError = true;
          setTimeout(() => {
            this.inputError = false;
          }, 900);
          return; 
        }
        this.items.push({ id: Date.now(), task: this.newItem, completed: false });
    this.newItem='' 
},
}    
 }
</script>
<template>
<div 
class="container" 
@submit.prevent="addItem"
>
      <div class="header">
          <input
        type="text"
        v-model="newItem"
        @keyup.enter="addItem"
      />
  <Button 
  msg="Añadir" 
  class="primary"
  @click="addItem"
  ></Button>
      </div>
     </div>
<Error v-if="inputError" msg="Ingrese una tarea por favor"></Error>
</template>
<style scoped>

.hola {
    background-color: aquamarine;
}
.none {
    background-color: blue;
}
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


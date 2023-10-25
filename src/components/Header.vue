<script>
 import './Styles.vue';
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



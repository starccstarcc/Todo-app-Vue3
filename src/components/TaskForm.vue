<template>
     <div class="container-form" >
         <div
         v-if="files.length"
         class="list" 
         v-for="item in files" 
         :key="item.id">
        <div 
 v-bind:class="{'no-text': item.completed === true,'text': item.completed === false}" >
    <button 
  v-bind:class="{'button-completed-true': item.completed ===true,
   'button-completed-false': item.completed === false}"
    @click="modifyItem(item)"
    >{{item.completed === true? "✔": "" }}
    </button>
            {{ item.task }}
            <hr class="lineFormDivisory">            
        </div>
</div>
<Button 
:disabled='!this.files.filter((objectToDelete) => objectToDelete.completed).length'
class='secondary'
@click="removeItem">Eliminar completados</Button>
      </div>
</template>
<script>
import Button from './Button.vue';

export default {
    props: {
        files: Object,
    },
    methods: {
        removeItem() {
            this.$emit('removeItem');
        },
        modifyItem(item) {
            const index = this.files.indexOf(item);
            if (index !== -1) {
                this.files[index].completed = !this.files[index].completed;
            }
        },
        handleSubmit() {
            this.addItem();
        },
    },
    components: { Button },
    
}

</script>
<style scoped>
.container-form {
  background-color:white;
  border-radius: 2px;
  margin-bottom: 20px;
  padding-bottom: 50px;
  width: 100%;
  box-shadow: 3px 3px 3px lightgray
}

.list {
  width: 100%;
    color:darkcyan;
    padding-top: 5px;
    padding-inline: 10px;
    position: relative;
  }
  
.no-text {
    text-decoration: line-through  lightseagreen 2px;
    color: rgb(162, 161, 161);  
    padding: 2px;
  }

.text {
  padding: 2px;
  }
.lineFormDivisory{
    margin-right: 40px;
}
  .container  {
  background-color:white;
  border-radius: 2px;
  margin-bottom: 1px;
  padding: 13px;
  display: flex;
  box-shadow: 3px 3px 3px lightgray;
}

@media (prefers-color-scheme: dark) {
      .input-bar input{
        background-color:grey;
      }
      .container {
        background-color:dimgrey;
        box-shadow: 3px 3px 3px gray
      }
   } 

   @media (prefers-color-scheme: dark) {
      .input-bar input{
        background-color:grey;
      }
      .container {
        background-color:dimgrey;
        box-shadow: 3px 3px 3px gray
      }
      .container-form {
        background-color:dimgrey;
        box-shadow: 3px 3px 3px gray
      }
   } 

</style>
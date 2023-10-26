<script>
import Button from './Button.vue';
export default {
    props: {
        items: Object,
    },
    methods: {
        removeItem() {
            this.$emit('removeItem');
        },
        modifyItem(item) {
            const index = this.items.indexOf(item);
            if (index !== -1) {
                this.items[index].completed = !this.items[index].completed;
            }
        },
        handleSubmit() {
            this.addItem();
        },
    },
    components: { Button },
}
</script>
<template>
     <div class="container-form">
         <div 
         class="list" 
         v-for="item in items" 
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
        </div>
<hr class="lineFormDivisory">            
</div>
<Button 
:disabled='!this.items.filter((objectToDelete) => objectToDelete.completed).length'
msg="Eliminar completados"
class='secondary'
@click="removeItem"/>
      </div>
</template>
<style scoped>
.container-form {
  background-color:white;
  border-radius: 2px;
  margin-bottom: 20px;
  padding-bottom: 10px;
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
  margin-bottom: 20px;
  padding: 13px;
  display: flex;
  box-shadow: 3px 3px 3px lightgray;
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
      .container-form {
        background-color:dimgrey;
        box-shadow: 3px 3px 3px gray
      }
   } 

</style>
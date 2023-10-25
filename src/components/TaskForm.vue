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
     <div class="containerL">
         <div 
         class="list" 
         v-for="item in items" 
         :key="item.id">
        <div 
 v-bind:class="{'no-text': item.completed === true,'text': item.completed === false}" >
    <button 
  v-bind:class="{'button-completed-true': !item.completed ===true,
   'button-completed-false': item.completed === false}"
    @click="modifyItem(item)"
    >{{item.completed === true? "✔": "" }}
    </button>
            {{ item.task }}
        </div>
<hr>            
          </div>
          <Button 
          :disabled='!this.items.filter((objectToDelete) => objectToDelete.completed).length'
          msg="Eliminar completados"
          class='secondary'
          @click="removeItem"/>
      </div>
</template>
<style>
</style>
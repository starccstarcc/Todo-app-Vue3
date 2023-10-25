<script>
import Header from './components/Header.vue'
import TaskForm from './components/TaskForm.vue';
export default {
  components: {
    Header,
    TaskForm,
},
 data() {
    return {
     items: [
        { id: Date.now(),task: "Primera",completed: false}
      ],
    };
  },
  methods: {
    removeItem() {
    this.items = this.items.filter(item => item.completed === false);
  },
  }
}
</script>
<template>
  <Header :items="items"
  ></Header>
 <TaskForm 
 :items="items" 
 @removeItem="removeItem"
 ></TaskForm>
</template>
<style scoped>
</style>



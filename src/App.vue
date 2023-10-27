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
     items: [],
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
 <Header :items="items"/>
 <TaskForm :items="items" 
 @removeItem="removeItem"/>
</template>
<style scoped>
</style>



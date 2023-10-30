<template>
 <InputBar :files="files"/>
 <TaskForm :files="files" 
 @removeItem="removeItem"/>
</template>
<script>
import InputBar from './components/InputBar.vue'
import TaskForm from './components/TaskForm.vue';
export default {
  components: {
    InputBar,
    TaskForm,
},
 data() {
    return {
     files: [],
    };
  },
  methods: {
    removeItem() {
    this.files = this.files.filter(item => item.completed === false);
  },
  }
}
</script>
<style scoped>
</style>



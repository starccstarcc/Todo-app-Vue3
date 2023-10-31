<template>
 <InputBar :files="files"/>
 <TaskForm :files="files" 
 @removeTaskObject="removeTaskObject"/>
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
    removeTaskObject() {
    this.files = this.files.filter(taskObject => !taskObject.completed);
  },
  }
}
</script>
<style scoped>
</style>



 <template>
 <div 
 class="container"
 @submit.prevent="addTaskObject"
 >
       <div class="input-bar">
           <input
         type="text"
         v-model="newTaskObject"
         @keyup.enter="addTaskObject"
       />
   <Button 
   buttonClass="primary"
   @click="addTaskObject"
   >Añadir
</Button>
       </div>
      </div>
 <Error v-if="inputError" >Ingrese una tarea por favor</Error>
 </template>

<script>

 import Button from './Button.vue'
 import Error from './Error.vue'
 export default { 
    props: {
      files: Object,
    },

    emits: ['input'],

    components: {
        Button,
        Error,
    },
    
    data() {
      return {
        newTaskObject: '',
        inputError: false,
      };
      
    },
    methods:{
    addTaskObject() {
            if (this.newTaskObject.trim() === '') {
          this.inputError = true;
          setTimeout(() => {
            this.inputError = false;
          }, 900);
          return; 
        }
        this.files.push({ id: Date.now(), task: this.newTaskObject, completed: false });
    this.newTaskObject='' 
},
}    
 }
</script>
<style scoped>
.container  {
  background-color:white;
  border-radius: 2px;
  margin-bottom: 20px;
  padding: 13px;
  display: flex;
  box-shadow: 3px 3px 3px lightgray;
}

.input-bar {
  width: 100%;
  display: flex;
    max-width: 100%;
    position: relative;
  }

.input-bar input {
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

.input-bar button {
  display: block;
    height: 70%;
  
     position: absolute; 
    right:2%;
    transform: translateX(-10%);
    top: 17%;
  }

  @media (prefers-color-scheme: dark) {
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
     
   } 
 
</style>


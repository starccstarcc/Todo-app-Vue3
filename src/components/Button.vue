<template>
   <button 
   v-if="buttonClass"
   :class="buttonClass" 
   @click="handleClick">
       <slot></slot>
    </button>
         <button v-if="toggle ==false || toggle ==true" 
         @click="handleClick"
     v-bind:class="{'button-completed-true': toggle,
      'button-completed-false': !toggle}"
       > 
       {{toggle? "✔": "" }} 
       </button> 
      
</template>
<script>
 export default {
    props: {
      toggle: String, 
      buttonClass: String 
    },
    methods: {
      handleClick() {
        this.$emit('click');
      },
    },
  };
</script>
<style>
button  {
    border:none;
    padding:10px ;
    font-size: 16px;
    border-radius: 8px;
    cursor:pointer;
    transition: opacity 0.25s;
}
button:hover {
    opacity: .7;
}

button[disabled] {
    cursor: not-allowed;
    opacity: .5;
}

button[disabled]:hover {
   opacity: .2;
}
.primary {
    background-color:lightpink; 
    border:none;
    padding:10px ;
    font-size: 16px;
    border-radius: 8px;
    cursor:pointer;
    }
    .button-completed-false {
      border: 3px solid lightseagreen; 
      color: lightseagreen;
      margin-right: 10px;
      border-radius: 6px;
      margin-left: 8px;
    }
      .button-completed-true {
        color: lightseagreen;
        margin-right: 6px;
        border-radius: 6px;
        font-size: 12px;
        margin-left: 8px;
      } 
    .secondary {
          background-color: darkcyan; 
          border-radius: 6px;
        }
        .container-form .secondary {
            position: absolute; 
            position:-webkit-sticky;
             margin-left: 20px;
           margin-top: 6px;
        }  

@media (prefers-color-scheme: light) {
  .button-completed-true {
    background-color: white;
  }
  .button-completed-false  {
    background-color: white; 
  }
  button {
    color: white;
  }
}

@media (prefers-color-scheme: dark) {

  .button-completed-true {
    background-color: dimgray;
    
  }
  .button-completed-false  {
    background-color: dimgray; 
  }
}

</style>
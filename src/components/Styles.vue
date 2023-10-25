<script>
</script>
<template>
</template>
<style>

.container  {
  background-color:white;
  border-radius: 2px;
  margin-bottom: 20px;
  padding: 13px;
  display: flex;
  box-shadow: 3px 3px 3px lightgray;
}

.header {
  width: 100%;
  display: flex;
    max-width: 100%;
    position: relative;
  }

.header input {
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

.header button {
  display: block;
    height: 70%;
  
     position: absolute; 
    right:2%;
    transform: translateX(-10%);
    top: 17%;
  }

  .containerL {
  background-color:white;
  border-radius: 2px;
  margin-bottom: 20px;
  padding: 1px;
  width: 100%;
}

.list {
  width: 100%;
    color:darkcyan;
    padding-top: 5px;
    padding-bottom: 10px;
    padding-inline: 20px;
    position: relative;
  }
  
.no-text {
    text-decoration: line-through  lightseagreen 2px;
    color: rgb(225, 225, 225);
    padding: 2px;
  }

.text {
  padding: 2px;
    
  }

  .container  {
  background-color:white;
  border-radius: 2px;
  margin-bottom: 20px;
  padding: 13px;
  display: flex;
  box-shadow: 3px 3px 3px lightgray;
}

.header {
  width: 100%;
  display: flex;
    max-width: 100%;
    position: relative;
  }

.header input {
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

.header button {
  display: block;
    height: 70%;
  
     position: absolute; 
    right:2%;
    transform: translateX(-10%);
    top: 17%;
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
      .containerL {
        background-color:dimgrey;
        box-shadow: 3px 3px 3px gray
      }
   } 
 
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
        .list .secondary {
            position: absolute; 
            position:-webkit-sticky;
             left: 30%;
            bottom: 2%;
        } 
</style>

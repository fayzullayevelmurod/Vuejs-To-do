<template>
  <div id="app">
    <label for="todo">Add programming languages</label>
    <input type="text" id="todo" v-model="enteredValue" placeholder="programming...">
    <button @click="addTodo">Add</button>
    <ul>
      <li v-for="todo in todo">
        {{ todo }}
      </li>
    </ul>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data(){
    return  {
      todo: [],
      enteredValue: ''
    }
  },
  methods:{
    addTodo(){
      if(this.enteredValue==''){
        alert('Entry is empty')
      }else{
        this.todo.push(this.enteredValue)
        this.enteredValue=''
      }

    }
  }
}
</script>

<style scoped>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  list-style: none;
}
#app{
  box-shadow: 0 1px 10px #323131;
  max-width: 1440px;
  margin: 0 auto;
  padding: 10px;
}
label,
input,
button{
  display: block;
}
label{
  font-family: sans-serif;
  text-align: center;
  font-weight: 900;
  font-size: 30px;
  color: grey;
  margin-bottom: 20px;
}
input{
  font-family: sans-serif;
  width: 300px;
  margin: 0 auto;
  padding: 0 5px;
  height: 30px;
  font-size: 16px;
  color: grey;
}
input:focus{
  outline: none;
}

button{
  cursor: pointer;
  color: grey;
  border: none;
  width: 300px;
  margin: 20px auto;
  height: 30px;
}
ul{
  width: 300px;
  margin: 0 auto;
}
li{
  margin-bottom: 10px;
  background-color: rgb(239, 236, 236);
  font-family: sans-serif;
  font-size: 18px;
  color: grey;
  padding: 5px;
}


@media (max-width: 576px){
  input,
  button,
  ul{
    width: 95%;
  }
  label{
    font-size: 25px;
  }
}
</style>

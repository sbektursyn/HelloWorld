<script>
  //my demo method===========================
  /*export default {
    data(){
      return {
        check: false,
        check2: false,
        styleObj: {
          color: 'red',
          fontSize: '30px'
        }
      }
    }
  }*/
  //=========================================

  export default {
    components: { 
      props: ['title'],
      emits: ['remove'] 
    },
    data() {
      return {
        newTodoText: '',
        todos: [
          {
            id: 1,
            title: 'новая заметка',
            isLine: false
          }
        ],
        nextTodoId: 2
      }
    },
    methods: {
      addNewTodo() {
        this.todos.push({
          id: this.nextTodoId++,
          title: this.newTodoText,
          isLine: false
        })
        this.newTodoText = ''
      },
      toggle(todo) {
        todo.isLine = !todo.isLine;
      }
    }
  }
  
</script>

<template>
<!-- stil my method===================================== -->
  <!-- <div class="do">

    <div class="items" v-if="!check">
      <input type="checkbox" name="" class="checkbox" v-model="check"><p class="action">do homework</p>
    </div>

    <div class="items2" v-else-if="check">
      <input type="checkbox" name="" class="checkbox" checked v-model="check"><p class="action2">do homework</p>
    </div>

    <div class="items" v-if="!check2">
      <input type="checkbox" name="" class="checkbox" v-model="check2"><p class="action" >do to do list</p>
    </div>

    <div class="items2" v-else-if="check2">
      <input type="checkbox" name="" class="checkbox" checked v-model="check2"><p class="action2">do to do list</p>
    </div>

  </div> -->
<!-- stil my method===================================== -->
  <form v-on:submit.prevent="addNewTodo">
    <input
      v-model="newTodoText"
      id="new-todo"
      placeholder="actions"
      class="find"
    />
    <button class="add">Add</button>
  </form>
  <ul v-for="(todo, index) in todos">
    <li :key="todo.id" 
        :style="{ 'text-decoration': todo.isLine ? 'line-through' : 'none', 'cursor':  'pointer'}"
        @click="toggle(todo)" >
        {{todo.title}}
        <button @click="todos.splice(index, 1)" class="remove">x</button>
    </li>
  </ul>
</template>

<style scoped>
.find{
  width: 220px;
  border:none;
  border-bottom:1px solid #000;
  margin-left: 25px;
}
.find:hover{
  border-radius: 5px;
}

.add{
  border:1px solid #888;
  border-radius: 10px;
  background: white;
}

.add:hover{
  border-color: black;
}

.add:active{
  background: #a8a8a8;
}

li{
  font-style: italic;
  border-bottom:1px solid black;
  max-width: 220px;
}
.remove{
  border:none;
  background: white;
  cursor: pointer;
}
</style>


































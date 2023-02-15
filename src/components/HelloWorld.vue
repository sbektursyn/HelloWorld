<script>
  //my demo method===========================
  export default {
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
  }
  //=========================================
  /*import TodoItem from './TodoItem.vue'
  export default {
    components: { TodoItem },
    data() {
      return {
        newTodoText: '',
        todos: [
          {
            id: 1,
            title: 'новая заметка'
          }
        ],
        nextTodoId: 2
      }
    },
    methods: {
      addNewTodo() {
        this.todos.push({
          id: this.nextTodoId++,
          title: this.newTodoText
        })
        this.newTodoText = ''
      }
    }
  }*/
  
</script>

<template>
<!-- stil my method===================================== -->
  <div class="do">

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

  </div>
<!-- stil my method===================================== -->
<!-- <form v-on:submit.prevent="addNewTodo">
    <input
      v-model="newTodoText"
      id="new-todo"
      placeholder="actions"
    />
    <button>Add</button>
  </form>
  <ul>
    <todo-item
      v-for="(todo, index) in todos"
      :key="todo.id"
      :title="todo.title"
      @remove="todos.splice(index, 1)"
    ></todo-item>
  </ul> -->
</template>

<style scoped>
table{border:1px solid #000; color:#a88;}
td{border:1px solid #000;}

.do{
  width: 400px;
  height: 300px;
  border:2px solid black;
  display: flex;
  flex-direction: column;
}
.checkbox{
  width: 15px;
  height: 15px;
  margin-top: 5px;
}


.items{
  display: flex;
  flex-direction: row;
}
.items2{
  display: flex;
  flex-direction: row;
}

.action{
  padding-left: 20px;
}
.action2{
  padding-left: 20px;
  text-decoration: line-through;
}

h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>

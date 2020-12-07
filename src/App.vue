<template>
  <main>
    <div class="container">
      <h1>Welcome to use Vue3.0 Todo APP.</h1>
      <todo-add :tid="todos.length" @add-todo="addTodo"/>
      <todo-filter :selected="filter" @change-filter="filter = $event"/>
      <todo-list :todos="filteredTodos"/>
    </div>
  </main>
</template>

<script>
import { computed, ref } from 'vue'
import TodoAdd from './components/TodoAdd.vue'
import TodoFilter from './components/TodoFilter.vue'
import TodoList from './components/TodoList.vue'

export default {
  name: 'App',
  components: {
    TodoAdd,
    TodoFilter,
    TodoList
  },
  setup() {
    const todos = ref([]);
    const addTodo = (todo) => todos.value.push(todo);
    const filter = ref('all');
    const filteredTodos = computed(() => {
      switch(filter.value) {
        case 'done':
          return todos.value.filter((todo) => todo.completed);
        case 'todo':
          return todos.value.filter((todo) => !todo.completed);
          default:
            return todos.value;
      }
    })
    return {
      todos,
      addTodo,
      filter,
      filteredTodos,
    };
  },
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: Arial, Helvetica, sans-serif;
}
main {
  width: 100vw;
  min-height: 100vh;
  display: grid;
  align-items: center;
  justify-items: center;
  background: rgb(203, 210, 240);
}
.container {
  width: 60%;
  max-width: 550px;
  box-shadow: 0px 0px 24px rbga(0,0,0, .15);
  border-radius: 24px;
  padding: 48px 28px;
  background-color: rgb(245, 246, 252);
}
h1 {
  margin: 24px 0;
  font-size: 28px;
  color: #414873;
}
</style>

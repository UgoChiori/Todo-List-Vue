<template>
  <div class="title">TODOS</div>

  <div class="input-container">
    <input type="text" v-model="todo" placeholder="Add ToDo" />

    <button class="add-btn" @click="addTodo" :disabled="!todo">Add Todo</button>
  </div>
  <ul>
    <li
      v-for="(todo, i) in todos"
      :key="i"
      class="todo-item"
      :class="{ 'has-line-through': todo.isCompleted }"
    >
      <span> {{ todo.name }}</span>
      <button @click="removeTodo(todo.id)" class="delete-btn">Delete</button>
      <button id="todo.id" @click="updateTodo(todo.id)">
        {{ todo.isCompleted ? "UNDO" : "Complete" }}
      </button>
    </li>
  </ul>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      todo: "",
      todos: [],
    };
  },
  methods: {
    addTodo() {
      this.todos.push({
        id: this.todos.length + 1,
        name: this.todo,
        isCompleted: false,
      });
      this.todo = "";
    },
    removeTodo(todoId) {
      this.todos = this.todos.filter((todo) => todo.id !== todoId);
    },
    updateTodo(todoId) {
      this.todos.map((todo) =>
        todo.id === todoId ? (todo.isCompleted = !todo.isCompleted) : null
      );
    },
    deleteTodo() {},
  },
};
</script>

<style>
.title {
  margin-bottom: 15px;
  font-size: 18px;
  font-weight: 600;
  text-align: center;
}
.input-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  margin-bottom: 10px;
  margin-top: 20px;
 }
ul {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 10px;
}
.add-btn {
  margin-left: 5px;
  cursor: pointer;
  border-radius: 5px;
}
.add-btn:disabled {
  cursor: not-allowed;
  background-color: #ccc;
}
.add-btn:hover {
  background-color: #ccc;
  transition: 0.3s;
}

.delete-btn {
  margin-left: 5px;
  margin-right: 10px;
  border-radius: 5px;
  cursor: pointer;
}
.delete-btn:hover {
  background-color: #ccc;
  transition: 0.3s;
}

.todo-item {
  margin-bottom: 10px;
  align-items: center;
}

.has-line-through {
  text-decoration: line-through;
}
</style>

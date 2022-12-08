<!-- <template>
  <div class="title">TODOS</div>

  <ul>
    <li v-for="(todo, i) in todos" :key="i" class="todo-item">
      <span >👉 {{ todo.name }}</span>
      <button class="delete-btn">Delete</button>
      <button @click="$emit('has-line-through')" class="has-line-through">👉 {{ todo.name }}Complete</button>
    </li>
  </ul>

  <div class="input-container">
    <input type="text" v-model="todo" />

    <button class="add-btn" @click="addTodo" :disabled="!todo">Add Todo</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      todo: "",
      todos: [
        {
          id: 1,
          name: "Buy Bread",
          isCompleted: false,
        },
      ],
    };
  },
  methods: {
    addTodo() {
      this.todos.push({
        id: this.todos.length + 1,
        name: this.todo,
        isCompleted: false,
      });
    },
    removeTodo() {},
    updateTodo() {},
    deleteTodo() {},
  },
};
</script>

<style>
.title {
  margin-bottom: 15px;
  font-size: 18px;
  font-weight: 600;
}

.add-btn {
  margin-left: 5px;
}

.delete-btn {
  margin-right: 5px;
  margin-left: 20px;
}

.input-container {
  margin-top: 20px;
}

.todo-item {
  margin-bottom: 10px;
}

.has-line-through {
  text-decoration: line-through;
}
</style> -->
// todos: [
      //   {
      //     id: 1,
      //     name: "Buy Bread",
      //     isCompleted: false,
      //   },
      // ],

      this.todos.push({
        id: this.todos.length + 1,
        name: this.todo,
        isCompleted: false,
      });
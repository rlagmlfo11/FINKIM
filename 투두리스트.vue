<template>
  <div id="app">
    <div class="container">
      <div class="col-md-6 offset-md-3">
        <h1 class="text-center mb-4">Todo App</h1>
        <input
          type="text"
          class="form-control mb-4"
          v-model="userInput"
          @keyup.enter="addNewTodo"
        />

        <div class="list-group mb-4">
          <template v-for="todo in activeTodolist" :key="todo">
            <button
              class="list-group-item text-left"
              @click="toggleTodoState(todo)"
            >
              {{ todo.label }}
            </button>
          </template>
        </div>

        <div class="text-right">
          <button
            type="button"
            class="btn btn-sm"
            @click="currentState('active')"
          >
            할 일
          </button>
          <button
            type="button"
            class="btn btn-sm"
            @click="currentState('done')"
          >
            완료
          </button>
          <button type="button" class="btn btn-sm" @click="currentState('all')">
            전체
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      userInput: "",
      todoList: [],
      currentState: "active",
    };
  },
  computed: {
    activeTodolist() {
      return this.todoList.filter(
        (todo) =>
          this.currentState === "all" || todo.state === this.currentState
      );
    },
  },
  methods: {
    ChangeCurrentState(state) {
      this.currentState = state;
    },
    addNewTodo() {
      this.todoList.push({
        label: this.userInput,
        state: "active",
      });
      this.userInput = "";
    },
    toggleTodoState(todo) {
      todo.state = todo.state === "active" ? "done" : "active";
    },
  },
};
</script>

<style></style>

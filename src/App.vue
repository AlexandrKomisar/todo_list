<template>
  <div class="container">
    <div class="nav">
      <router-link to="/">Главная</router-link>
      <router-link to="/todos">Все заметки</router-link>
    </div>
    <router-view />
    <my-dialog :show="false"> </my-dialog>
    <todo-form :todos="todos" @create="createTodo" />
    <todo-list :todos="todos" @remove="removeTodo" />
  </div>
</template>

<script>
import TodoForm from "@/components/TodoForm.vue";
import TodoList from "@/components/TodoList.vue";
import MyDialog from "@/components/my/MyDialog.vue";

export default {
  name: "Home",
  components: {
    TodoForm,
    TodoList,
    MyDialog,
  },
  data() {
    return {
      todos: [
        {
          title: "1 Заголовок",
          list: "1 Список",
        },
        {
          title: "2 Заголовок",
          list: "2 Список",
        },
      ],
    };
  },
  methods: {
    createToto(todo) {
      this.todos.push(todo);
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((t) => t.id !== todo.id);
    },
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  box-sizing: border-box;
}
.container {
  margin: 0 auto;
  width: 1200px;
}

#app {
  background-color: #444444;
  color: #cccccc;
  min-height: 100vh;
}

.nav {
  padding: 30px;

  a {
    color: #cccccc;
    padding: 10px;
    text-decoration: none;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

@media (max-width: 1200px) {
  .container {
    width: 992px;
  }
}
@media (max-width: 992px) {
  .container {
    width: 768px;
  }
}
@media (max-width: 768px) {
  .container {
    width: 720px;
  }
}
@media (max-width: 576px) {
  .container {
    width: 350px;
  }
}
</style>

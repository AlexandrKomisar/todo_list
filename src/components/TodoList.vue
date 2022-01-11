<template>
  <div>
    <div v-show="todos.length > 0">
      <h3>Мои заметки</h3>
      <todo-item
        v-for="todo in todos"
        :todo="todo"
        :key="todo.id"
        @remove="$emit('remove', todo)"
      />
    </div>
    <h3 v-show="todos.length === 0">Добавте первую заметку</h3>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem.vue";
export default {
  components: {
    TodoItem,
  },
  props: {
    todos: {
      type: Array,
      required: true,
    },
  },
};
</script>

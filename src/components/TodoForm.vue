<template>
  <div class="todoForm">
    <form @submit.prevent class="createTodo__content">
      <h4>Создание заметки</h4>
      <my-input
        v-model:value="todo.title"
        type="text"
        placeholder="Заголовок"
      />
      <my-input v-model:value="todo.list" type="text" placeholder="Список" />
      <my-button @click="createTodo">Создать</my-button>
    </form>
  </div>
</template>

<script>
import MyButton from "@/components/my/MyButton.vue";
import MyInput from "@/components/my/MyInput.vue";

export default {
  components: {
    MyButton,
    MyInput,
  },
  data() {
    return {
      todo: {
        title: "",
        list: "",
      },
    };
  },
  methods: {
    createTodo() {
      this.todo.id = Date.now();
      this.$emit("create", this.todo);
      this.todo = {
        title: "",
        list: "",
      };
    },
  },
};
</script>

<style scoped lang="scss">
.todoForm {
  display: flex;
  flex-direction: column;
}
</style>

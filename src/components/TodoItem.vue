<template>
  <div class="todo">
    <div>
      <h3>{{ todo.title }}</h3>
      <p>{{ todo.list }}</p>
    </div>
    <div class="todo__btns">
      <my-button @click="$emit('remove', todo)">Удалить</my-button>
      <my-button>Открыть</my-button>
    </div>
  </div>
</template>

<script>
import MyButton from "@/components/my/MyButton.vue";

export default {
  components: {
    MyButton,
  },
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.todo {
  padding: 15px;
  border: 2px solid teal;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>

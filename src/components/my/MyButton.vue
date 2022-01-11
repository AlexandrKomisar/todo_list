<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "MyButton",
};
</script>

<style lang="scss" scoped>
.btn {
  font-weight: 700;
  width: 200px;
  height: 30px;
  border-radius: 5px;
  border: none;
  background: #35b801;
  color: #ffffff;
  margin: 5px;
  &:hover {
    background: #2ea100;
  }
}
</style>

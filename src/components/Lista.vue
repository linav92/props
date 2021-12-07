<template>
  <div>
    <ul>
      <li v-for="(item, index) in tareas" :key="index">
        {{ item }} <button @click="deleteItem(index)">eliminar</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: ["tareas"],
  methods: {
    deleteItem(index) {
      this.$emit("delete-item", index);
    },
  },
}
</script>


<style scoped>
  ul {
    margin: 30px 60px;
  }
  li {
    margin: 10px 0;
  }
  button {
    margin-left: 10px;
    background-color: salmon;
    color: white;
    padding: 5px 10px;
    border: none;
    cursor: pointer;
    border-radius: 4px;
  }
</style>

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
};
</script>

<style>

div {
font-family: 'Montserrat', sans-serif;
display: flex;
justify-content: center;
margin-top: 5rem;
}

h2 {
  margin: 4rem 6rem;

}

button {
  margin: 0.2rem;
  background-color: white;
  border-radius: 10%;
  border-color: rgb(206, 202, 202);
  padding: 0.1rem 0.5rem;
}

input {
border: 2px solid rgb(206, 202, 202);
}

ul {
  margin-top: 1rem;
}
</style>

<template>
  <h1>{{title}}</h1>
  <input type="text" ref="name" />
  <button @click="handleClick">click me</button>
  <Modal :header="header" :text="text" :count="count" theme="sale" />
  <Modal :header="header" :text="text" :count="count" theme="normal" />
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'Training Vue App 🙂',
      header:"Sign up for the Giveaway!",
      text: "Grab everything for half of price.",
      count: [1, 2, 3, '...']
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: #fff;
}


</style>

<template>
  <h1>{{title}}</h1>
  <br />
  <input type="text" ref="name" />
  <button @click="handleClick">click me</button>
  <br />
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
      <a href="#">sign up now</a>
      <a href="#">more info</a>
    </template>
      <h1>Ninja givaway</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </teleport>
  <div>
    <Modal theme="normal" v-if="showModalTwo" @close="toggleModalTwo">
      <template v-slot:links>
      <a href="#">sign up now</a>
      <a href="#">more info</a>
    </template>
      <h1>Hello World</h1>
      <p>I hope you are having a wonderful day 🙂</p>
    </Modal>
  </div>
  <button @click.alt="toggleModal">open modal (alt)</button>
  <br />
  <button @click.shift="toggleModalTwo">open modal (shift)</button>

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
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    handleClick() {
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }
}
</script>

<style>
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: #fff;
}


</style>

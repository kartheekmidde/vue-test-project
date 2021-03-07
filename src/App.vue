<template>
  <h1>{{ title }}</h1>
  <p>Welcome..</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">More info</a>
      </template>
      <h1>Welcome to my blog</h1>
      <p>Learn VueJS SPA</p>
    </Modal>
  </div>
  <div v-if="showModalTwo">
    <Modal theme="sales" @close="toggleModalTwo">
      <template v-slot:pwd>
        <a href="#">Forgot Password</a>
      </template>
    </Modal>
  </div>
  <button @click.alt="toggleModal">Open modal (alt)</button>
  <button @click.alt="toggleModalTwo">Open modal 2 (alt)</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "My First Vue App",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>

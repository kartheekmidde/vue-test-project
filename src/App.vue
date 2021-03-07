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
  <button @click.alt="toggleModal">Open modal (alt)</button>
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
      header: "Sign up",
      subText: "Remember me",
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
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

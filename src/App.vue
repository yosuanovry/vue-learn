<template>
  <header>
    <h1>{{ title }}</h1>
    <input type="text" ref="username" />
    <button @click="handleClick">enter</button>
    <button @click="toggleModal">show modal</button>
    <div v-if="showModal">
      <Modal :header="header" :text="text" theme="light" @close="toggleModal"/>
    </div>
  </header>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  components: { Modal },
  data() {
    return {
      title: "Learning vue.js",
      header: "This is a header",
      text: "This is a text",
      showModal: false,
    };
  },
  methods: {
    // handle refs add class to ref
    handleClick() {
      this.$refs.username.classList.add("active");
      this.$refs.username.focus();
    },

    toggleModal() {
      this.showModal = !this.showModal
    }
  },
};
</script>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
  width: 100%;
  text-align: center;
  background-color: beige;
  padding: 20px 0px;
}

header h1 {
  font-weight: 600;
  color: cadetblue;
}
</style>

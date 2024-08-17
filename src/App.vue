<template>
  <img id="logo" alt="Vue logo" src="./assets/logo.png" />
  <test msg="My First vue app" mdat="kk" />

  <input type="text" ref="title" />
  <div class="modalcontainer" v-if="showModal">
    <ModalView
      :header="header"
      :text="text"
      :theme="theme"
      @CloseModal="toggleModal"
    />
  </div>
  <button @dblclick="handleClick" @click="toggleModal">Click Me!</button>
</template>

<script>
import test from "./components/test.vue";
import ModalView from "./components/ModalView.vue";

export default {
  name: "App",
  components: {
    test,
    ModalView,
  },
  data() {
    return {
      vis: "hidden",
      header: "Sales Hedader",
      text: "This is the text",
      theme: "sales",
      showModal: false,
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs);
      console.log(this.$refs.title.focus());
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>

<style>
#app {
  border: 25px solid black;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
#logo {
  max-width: 50px;
  margin: auto;
}
.modalcontainer {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>

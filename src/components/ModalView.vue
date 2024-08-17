<template>
  <div class="backdrop" @click="closeModal">
    <div class="modal" :class="{ sales: theme === 'sales' }">
      <h2>{{ header }}</h2>
      <div clsaa="space">.</div>
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalView",
  props: ["header", "text", "theme"],
  methods: {
    closeModal() {
      this.$emit("CloseModal");
    },
  },
};
</script>

<style scoped>
.backdrop {
  margin: 0;
  display: flex;
  flex-wrap: wrap2;
  justify-content: center;
  align-items: center;
  position: fixed;
  background-color: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.modal {
  display: flex;
  align-items: center;
  flex-direction: column;
  background-color: #fff;
  border-radius: 12px;
  padding: 40px;
  width: 200px;
  margin: 0 auto;
  padding: 40px;
}
.modal h2 {
  justify-self: flex-start;
  color: cyan;
  margin: 0 auto;
  padding: 5px;
  border: 1px solid cyan;
}
.modal.sales {
  background-color: crimson;
}
.modal.sales h2 {
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
  color: aliceblue;
}
.modal.sales p {
  justify-self: flex-end;
  color: aliceblue;
  font-style: oblique;
}
.space {
  flex: 1;
}
</style>

<template>
  <h1>Hello Test</h1>
  <h3 id="dd">This is a dynamic value {{ msg }}</h3>
  <h3 id="dd">This is a data value {{ mdat }}</h3>
</template>

<script>
export default {
  name: "TeSt",
  props: {
    msg: String,
  },
  data() {
    return {
      mdat: "Hello val",
    };
  },
};
</script>

<style>
#dd {
  color: rgb(59, 195, 105);
}
</style>

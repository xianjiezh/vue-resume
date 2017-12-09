<template>
<div>
  <div id="app">
    <pre>
    {{code}}
    </pre>
  </div>
  <div v-html="styleCode">
  </div>
  </div>
</template>

<script>
export default {
  name: "app",
  components: {},
  data() {
    return {
      code: ``,
      finalCode: `
      body{
        background: red;
      }
      `
    };
  },
  created() {
    var n = 0;
    setInterval(() => {
      this.code = this.finalCode.substring(0, n);
      n++;
    }, 100);
  },
  computed: {
    styleCode() {
      return "<style>" + this.code + "</style>";
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>

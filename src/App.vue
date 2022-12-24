<template>
  <div id="editor"></div>
</template>

<script>
import Editor from "@toast-ui/editor";
import "@toast-ui/editor/dist/toastui-editor.css";
import "@toast-ui/editor/dist/theme/toastui-editor-dark.css";

export default {
  name: 'App',
  data() {
    return {
      editor: null
    }
  },
  mounted() {
    this.editor = new Editor({
      el: document.querySelector("#editor"),
      height: "500px",
      initialEditType: "markdown",
      theme: 'dark'
    })
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: start;
  color: #2c3e50;
  margin: 60px;
  direction:rtl;
}
</style>

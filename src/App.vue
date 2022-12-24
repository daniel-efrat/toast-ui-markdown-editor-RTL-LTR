<template>
 <div>
   <div ref="editor" class="editor" id="editor"></div>

  <div class="buttons">
    <button class="ltr" ref="ltr" @click="onClickLTR($event)">LTR</button>
    <button class="rtl on" ref="rtl" @click="onClickRTL($event)">RTL</button>
  </div>
 </div>
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
  },
  methods: {
    onClickLTR(event) {
      this.$refs.editor.classList.remove('editor')
      this.$refs.rtl.classList.remove('on')
      this.$refs.ltr.classList.add('on')
    },
    onClickRTL(event) {
      this.$refs.editor.classList.add('editor')
      this.$refs.ltr.classList.remove('on')
      this.$refs.rtl.classList.add('on')
    },

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
  
}
.buttons{
  width: 100vw;
  display: flex;
  justify-content: center;
}
button {
  margin-right: 1rem;
  margin-top: 1rem;
  width: 80px;
  padding: 1rem;
}

.on {
  background: rgb(12, 162, 105);
}
.editor {
  direction:rtl;
}
</style>

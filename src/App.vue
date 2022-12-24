<template>
 <div class="wrapper">
  <h1>RTL / LTR Markdown Editor</h1>
 <div class="free">
   <div class="line"></div>
   <h2> 100% Free </h2>
   <div class="line"></div>
 </div>
  <div class="btns">
    <button class="btn ltr" ref="ltr" @click="onClickLTR($event)">LTR</button>
     <button class="btn rtl on" ref="rtl" @click="onClickRTL($event)">RTL</button>
  </div>
   <div ref="editor" class="editor" id="editor"></div>

  
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
      editor: null,
      language: 'he',
  useCommandShortcut: true,
    }
  },
  mounted() {
    this.editor = new Editor({
      el: document.querySelector("#editor"),
      height: "500px",
      initialEditType: "markdown",
      theme: 'dark',
      previewStyle: 'vertical'
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

@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;1,300;1,400;1,500;1,600;1,700;1,800&display=swap'); 

html, body{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
h1{
  text-transform: uppercase;
  font-weight: 900;
  font-size: 5rem;
  margin-bottom: -2.5rem;
  margin-top: -8.5rem;
  background: -webkit-linear-gradient(rgb(208, 189, 231), rgb(121, 70, 187));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.free {
  display: flex;
  width: 100%;
  justify-content: center;
  align-items: center;
}

h2{
  color: rgb(255, 255, 255);
  text-transform: uppercase;
  width: max-content;
  padding: .5rem 2rem;

}

.line {
  width: 100px;
  background: rgb(254, 254, 254);
  height: 1px;
}

#app {
  font-family: 'Open Sans', Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: start;
  color: #2c3e50;
  margin: 0;
  padding: 0;
 
  
}

.wrapper {
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: rgb(73, 73, 73);
  background-image: url(./assets/dots.png);
  background-size: 2.5%;
}

.btns{
  padding-bottom: 60px;
}

.btn {
  margin-right: 1rem;
  margin-top: 1rem;
  padding: 1rem 2rem;
  box-shadow: 2px 2px 6px rgb(0,0,0,0.4),
   -2px -2px 6px rgba(255, 255, 255, 0.305);
   border:none;
   cursor: pointer;
   transition: all 500ms ease;
   background: rgb(207, 207, 207);
   color: rgb(119, 119, 119);
   font-weight: 800;
   letter-spacing: 2px;
   font-size: 1.2rem;
}

.btn:hover {
  box-shadow: 4px 4px 10px rgb(0,0,0,0.4),
   -4px -4px 10px rgba(255, 255, 255, 0.305);
}
.btn:active{
  box-shadow: inset 4px 4px 10px rgba(0, 0, 0, 0.236),
   inset -4px -4px 10px rgba(255, 255, 255, 0.305);
}
.on {
  background: rgb(106, 90, 186);
  color: rgb(225, 224, 224);
   border: 1px white solid;

  
}
.editor {
  direction:rtl;
  /*height: 70vh!important;*/
}
</style>

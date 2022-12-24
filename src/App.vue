<template>
 <div class="wrapper">
  <h1 class="title">RTL / LTR Markdown Editor</h1>
 <div class="free">
   <div class="line"></div>
   <h2 class="subtitle"> 100% Free </h2>
   <div class="line"></div>
 </div>
  <div class="btns">
    <button class="btn ltr" ref="ltr" @click="onClickLTR($event)">LTR</button>
     <button class="btn rtl on" ref="rtl" @click="onClickRTL($event)">RTL</button>
  </div>
   <div ref="editor" class="editor rtl" id="editor"></div>

  
 </div>
</template>

<script>
import PayPalDonationButton from './components/PayPalDonationButton.vue';

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
   components: {
    PayPalDonationButton,
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
      this.$refs.editor.classList.remove('rtl')
      this.$refs.rtl.classList.remove('on')
      this.$refs.ltr.classList.add('on')
    },
    onClickRTL(event) {
      this.$refs.editor.classList.add('rtl')
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
  display: flex;
  justify-content: center;
  align-items: start;
}
.title{
  text-transform: uppercase;
  font-weight: 900;
  font-size: 3rem;
  background: -webkit-linear-gradient(rgb(208, 189, 231), #c3841e);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  text-align:center
}
.free {
  display: flex;
  width: 100%;
  justify-content: center;
  align-items: center;
  margin-top: -2rem;

}

.subtitle{
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
  justify-content: flex-start;
  align-items: center;
  background-color: rgb(73, 73, 73);
  background-image: url(./assets/dots.png);
  background-size:4%;
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
   color: rgba(119, 119, 119, 0.701);
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
  background: #c3841e;
  color: rgb(225, 224, 224);
   border: 1px white solid;

  
}
.editor {
  
  min-height: 60vh;
  box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.482);
  min-width: 70vw;
  max-width:98vw;
  padding: 0;
}
.rtl{
  direction: rtl;

}

@media(max-width:500px) {
.title{
  font-size: 1.2rem;

}
.subtitle{
  font-size:.8rem

}
.editor {
  width: 100vw;
  margin-top: -1rem;
  padding-bottom: 60px;
}

.btn {
  font-size: 1rem;
  padding: .5rem 1rem;
}

.wrapper {
  background-size:15%;
}
}
@media(max-width:1270px){
  .title {
    font-size: 2.2rem;
  }
  .wrapper {
  background-size:10%;
}
}
</style>

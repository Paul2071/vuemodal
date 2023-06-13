<template>
  <h1>{{title}}</h1>
  <input type="text" ref="paint">
  <button @click="handleClick()" >GET PAINT NAME</button>
  <Modal :header="header" :list="list" />
 
</template>

<script>

import Modal from "./components/Modal.vue"


export default {
  name: 'App',
  components: {Modal},
  
  data () {
    return {
      title:  "first app",
      header: "Paint collection ",
      list: ["Doomfire Magenta", "Striking Scorpion Green" ]
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.paint)
     
      this.$refs.paint.classList.add("select")
      this.$refs.paint.focus()
    }
  }

}
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
  border-bottom: 2px solid #2c3e50;
  display: inline-block;
}
</style>

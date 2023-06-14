<template>
  <h1>{{title}}</h1>
  <input type="text" ref="paint">
  <div v-if="showModal">
    <Modal :header="header" :list="list" theme="sale" @closemodal="toggleModal"/>
    
  </div>
  <button @click="handleClick()" >GET PAINT NAME</button>
  <button @click="toggleModal()" >Open</button>
 
</template>

<script>

import Modal from "./components/Modal.vue"


export default {
  name: 'App',
  components: {Modal},
  
  data () {
    return {
      showModal: false,
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
    },
    toggleModal() {
      this.showModal = !this.showModal
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
.modal sale {
    background: crimson;
   
  }
</style>

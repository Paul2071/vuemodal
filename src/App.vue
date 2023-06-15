<template>
  <h1>{{title}}</h1>
  <input type="text" ref="paint">
  <div v-if="showModal">
    <Modal  theme="sale" @closemodal="toggleModal">
   
      <li v-for="paint in paints">
        <h1>{{ paint.name }}</h1>
      </li>

      
      <template v-slot:citadel>
        <a href='aa'>sign up now</a>
      </template>
      
  </Modal>
  
</div>

<div v-if="showModalTwo">

  <Modal  theme="" @closemodal="toggleModalTwo">

    
    <li v-for="paint in paints">
        <h1>{{ paint.name }}</h1>
      </li>

    
  </Modal>

</div>
  <button @click="handleClick()" >GET PAINT NAME</button>
  <button @click="toggleModal()" >Open Citadel</button>
  <button @click="toggleModalTwo()" >Open Vallejo</button>
 
</template>

<script>

import Modal from "./components/Modal.vue"


export default {
  name: 'App',
  components: {Modal},
  
  data () {
    return {
      showModal: false,
      showModalTwo: false,
      title:  "first app",
      header: "Paint collection ",
      paints: [
          { type: "Contrast",
          name: "Doomfire Magenta",
          colour: "Purple", img: 'images/PaintMagenta.png', isOwned: true },

          { type: "Contrast",
          name: "Striking Scorpion Green",
          colour: "Green", img: 'images/PaintStriking.png', isOwned: false   },

          { type: "Contrast",
          name: "Flesh tearer red",
          colour: "Red", img: 'images/PaintFlesh.png', isOwned: true }
        ]
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
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
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

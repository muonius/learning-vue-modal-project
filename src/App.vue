<template>
<h1>{{title}}</h1>
<p>Welcome...</p>
<br>
<input type="text" ref="name">
<button @click='handleClick'>Click me</button>
<div v-if="showModal">
<Modal theme="sale" @close="toggleModal" >
<template v-slot:links>
  <a href="#">sign up now</a>
  <a href="#">more info</a>
</template>

  <h1>Ninjia Giveaway</h1>
  <p>Grab your Ninja swag for half price</p>



</Modal>
</div>
<button @click="toggleModal">Sales</button>

<div v-if="showModalTwo">
<Modal @close="toggleModalTwo" >
  <h1>Sign up to newsletter</h1>
  <p>For updates and promo codes</p>

</Modal>
</div>
<button @click="toggleModalTwo">Contact</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {Modal},
data(){
  return{
    title: 'My First Vue Project',
    header: "Sign up for the Giveaway!",
    text:"Grab your Ninja swag for half price.",
    showModal: false,
    showModalTwo:false
  }
},
methods: {
  handleClick(){
    console.log(this.$refs.name)
    this.$refs.name.classList.add('active')
    // mouse focus on input field
    this.$refs.name.focus()
  },
  toggleModal(){
    this.showModal=!this.showModal
  },
   toggleModalTwo(){
    this.showModalTwo=!this.showModalTwo
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
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>

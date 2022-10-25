<template>
 <h1>{{ title }}</h1><br/>
 <!-- <input type="text" ref="name"/>
 <button @click="handleClick">click me</button> -->
 <p>Welcome...</p>
<teleport to="#modals" v-if="showModal">
 <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/> -->
 <Modal theme="sale" @close="toggleModal">
    <template v-slot:links>
       <a href="#!">Sign Up Now!</a>
       <a href="#!">More Info</a>
    </template>
    <h1>Ninja Giveaway!</h1>
    <p>Grab your ninja swag at half price!</p>
 </Modal>
</teleport>

<teleport to="#modals" v-if="showModalTwo">
 <Modal @close="toggleModalTwo">
    <h1>Sign Up to the News Letter!</h1>
    <p>For Updates and Promo codes...</p>
 </Modal>
</teleport>
<button @click.alt="toggleModal">Open Modal (alt)</button>
<button @click="toggleModalTwo">Open Modal </button>
</template>

<script>
import Modal from "./components/Modal.vue"
export default {
  name: 'App',
  components:{Modal},
  data(){
    return {
      title: 'Interactive Vue App',
      // header:"Sign up for Giveaway",
      // text:"Grab your ninja swag for half price!",
      showModal: false,
      showModalTwo: false,
    }
  },
  methods:{
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo
    }
      // handleClick(){
    //   console.log(this.$refs.name)
    //   this.$refs.name.classList.add('active')
    //   this.$refs.name.focus()
    // }  
  }
}
</script>

<style>
#app, #modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>

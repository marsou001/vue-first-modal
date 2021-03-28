<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <teleport to='#root' v-if="showModal1">
    <Modal :heading="heading1" :text="text1" theme="sale" @close="toggleModal1">
      kkkkkkkk      
    </Modal>
  </teleport>  
  <div v-if='showModal2'>
    <Modal :heading='heading2' :text='text2' theme='sale' @close='toggleModal2' />
  </div>
  <button @click="toggleModal1">open modal 1</button>
  <button @click="toggleModal2">open modal 2</button>
</template>

<script>
import Modal from './components/Modal'
export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App!',
      heading1: 'Sign up for the Givaway!',
      text1: 'Grab your ninja swag for half price!',
      heading2: 'Modal 2',
      text2: 'Hello from modal 2',
      showModal1: false,
      showModal2: false,
    }
  },
  methods: {
    toggleModal1() {
      this.showModal1 = !this.showModal1;
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2;
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
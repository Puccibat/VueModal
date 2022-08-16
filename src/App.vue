<template>
  <h1>{{title}}</h1>
  <div v-if="showModalOne">
    <ModalItem @close='toggleModalOne' >
      <template v-slot:content>
        <h1>This the first Modal</h1>
        <p>1</p>
      </template>
    </ModalItem>
  </div>
  <div v-if="showModalTwo">
    <ModalItem @close='toggleModalTwo' >
      <template v-slot:content>
        <h1>This the second Modal</h1>
        <p>2</p>
      </template>
    </ModalItem>
  </div>
  <div v-if="showModalThree">
    <ModalItem @close='toggleModalThree' :header='header' :text='text' />
  </div>
  <div class="btns">
    <button @click.shift='toggleModalOne'>Open Modal 1 (hold shift & click)</button>
    <button @click='toggleModalTwo'>Open Modal 2</button>
    <button @click='toggleModalThree'>Open Modal 3</button>
  </div>
</template>

<script>
import ModalItem from './components/Modal-item.vue'

export default {
  name: 'App',
  components: { ModalItem },
  data() {
    return {
      title: 'My first Vue App !!! :)',
      header: 'This is my first Vue modal',
      text: 'So cool !',
      showModalOne: false,
      showModalTwo: false,
      showModalThree: false,
    }
  },
  methods: {
    toggleModalOne() {
      this.showModalOne = !this.showModalOne
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    },
    toggleModalThree() {
      this.showModalThree = !this.showModalThree
    },
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
.btns {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 250px;
  margin: auto;
}

.btns button {
  margin-bottom: 10px;
}
</style>

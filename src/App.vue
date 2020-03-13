<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>

    <v-button 
    @click="consoleClick($event)"
    :styleObject="{
          color: 'blue',
          background: 'green',
          fontSize: '25px'
        }"
    :size="'lg'"
    :icon="'code'"
    >My large btn</v-button>

    <v-button 
    @click="consoleClick($event)"
    :styleObject="{
          color: '',
          background: '',
          fontSize: ''
        }"
    :size="'md'"
    :icon="'bug'"
    >My middle btn</v-button>

    <v-button 
    @click="consoleClick($event)"
    :styleObject="{
          color: 'pink',
          background: 'grey',
          fontSize: '12px'
        }"
    :size="'sm'"
    :icon="'laptop-code'"
    >My small btn</v-button>

    <v-button 
    @click="consoleClick($event)"
    :styleObject="{
          color: 'yellow',
          background: 'blue',
          fontSize: '10px'
        }"
    :size="'xs'"
    :icon="'terminal'"
    >My xsmall btn</v-button>
    
    <router-view />
  </div>
</template>

<script>
  import CustomBtn from '@/components/CustomBtn.vue'

  export default {
    components: {
      'v-button': CustomBtn
    },
    methods: {
      consoleClick(e) {
        console.log(e)
      }
    },
  }
</script>

<style lang="scss">
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

  #nav {
    padding: 30px;

    a {
      font-weight: bold;
      color: #2c3e50;

      &.router-link-exact-active {
        color: #42b983;
      }
    }
  }
</style>
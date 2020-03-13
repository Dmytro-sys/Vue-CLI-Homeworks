<template>
  <button class="btn" :class="size" :style="styleObject" @click="onClick">
    <i :class="`fas fa-${icon}`" class="i"></i>
    <slot></slot>
  </button>
</template>

<script>
  export default {
    name: 'CustomBtn',
    props: {
      size: {
        type: String,
        required: true
      },
      icon: String,
      styleObject: {
        type: Object,
        default: function () {
          return {
          color: '#000',
          background: '#fff',
          fontSize: '16px'
          }
        }
      },
    },
    data() {
      return {
        event: this.$event,
      }
    },
    methods: {
      onClick() {
        this.$emit('click', event)
      }
    },
  }
</script>

<style scoped lang='scss'>
  .btn {
    position: relative;
    padding: 0;
    margin: 10px 20px;
    outline: none;
    border: none;
    cursor: pointer;
    transition: .5s;
    border-radius: 10px;
    font-family: "Lato", sans-serif;
    text-align: center;

    &:hover {
      color: rgb(195, 22, 22);
      transform: scale(1.1);
    }
  }

  .i {
    position: absolute;
    top: 50%;
    left: 5%;
    transform: translateY(-50%);
  }

  .lg {
    min-width: 220px;
    height: 50px;
  }

  .md {
    min-width: 170px;
    height: 40px;
  }

  .sm {
    min-width: 120px;
    height: 35px;
  }

  .xs {
    min-width: 90px;
    height: 30px;
  }
</style>
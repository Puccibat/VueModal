<template>
  <div class='backdrop' @click.self="closeModal">
    <div class="modal" :header='header' :text='text'>
      <h1>{{header}}</h1>
      <p>{{text}}</p>
      <slot name='content'></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ['header', 'text'],
  methods: {
    closeModal() {
      this.$emit('close')
    }
  }
}
</script>

<style>
  .modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
  }
  .backdrop {
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%  ;
  }
</style>
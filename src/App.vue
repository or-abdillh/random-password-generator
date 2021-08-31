<template>
   <h3>Random Password Generator</h3>
   <Form></Form>
</template>

<script>
   
   import Form from './components/Form.vue'
   
   export default {
      name: 'App',
      components: {
         Form
      }
   }
   
</script>

<style lang="scss">
   
   #app {
      margin: 0;
      padding: .75rem 1.5rem;
      font-size: 24px;
      font-family: Sans-Serif;
      box-sizing: border-box;
      
      &::after, &::before {
         display: block;
      }
   }
   
</style>
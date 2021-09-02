<template>
   <Grid></Grid>   
</template>

<script>
   
   import Form from './components/Form.vue'
   import Grid from './components/Grid.vue'
   
   export default {
      name: 'App',
      components: {
         Form,
         Grid
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
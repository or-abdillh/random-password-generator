<template>
   <section id="Form" >
      <label for="lengthPassword">How length password you want ?</label>
      <input type="number" placeholder="ex: 8" name="lengthPassword" id="lengthPassword" />
      <button type="button">Generate</button>
      <span id="result">
         43yery
      </span>
   </section>
</template>

<script>
   
   export default {
      name: 'Form'
   }
   
</script>

<style lang="scss" >
   
   #Form {
      width: 100%;
      display: flex;
      flex-wrap: wrap;
      
      label, input {
         width: 100%;
         margin-bottom: .5rem;
      }
      
      input {
         padding: .35rem .25rem;
      }
      
      button {
         padding: .25rem .35rem;
         font-size: 1rem;
         margin-bottom: 1rem;
      }
      
      #result {
         width: 100%;
         text-align: center;
         background: whitesmoke;
         padding: .35rem .25rem;
         color: rgba(black, .85);
         font-weight: bold;
      }
   }
   
   
</style>
<template>
   <section id="Form" >
      <label for="lengthPassword">How length password you want ?</label>
      <input class="border bg-gray-200 text-gray-500 bordee" v-model="lengthPassword" type="number" placeholder="ex: 8" name="lengthPassword" id="lengthPassword" />
      <button class="bg-blue-500 text-white p-3 rounded shadow " @click="generatePassword" type="button">Generate</button>
      <button class="bg-gray-100 text-gray-800 border px-3 py-2 rounded" @click="reset" type="button">Reset</button>
      <span v-if="result != ''" id="result">
         <small>Your password : </small>
         <p>{{ result }}</p>
      </span>
   </section>
</template>

<script>
   
   import { ref } from 'vue'
   
   export default {
      name: 'Form',
      setup() {
         const result = ref('')
         const lengthPassword = ref('')
         
         //Get boolean
         const getBoolean = () => {
            return ( Math.round( Math.random() * 1 ) == 1 ? true : false )
         }
         
         //Get number
         const getNumber = () => {
            const number = '1234567890'.split('')
            
            let index = Math.round(Math.random() * 9)
            
            return number[index]
         } 
         
         //Get string / character
         const getString = () => {
            const string = 'qwertyuiopasdfghjklzxcvbnm'.split('')
            const isUpper = getBoolean()
            let index = Math.round(Math.random() * 25)
            
            if (isUpper) {
               return string[index].toUpperCase()
            } else {
               return string[index]
            }
         }
         
         //Generate password
         const generatePassword = () => {
            
            result.value = ''
            let password = []
            
            for (let i = 0; i < parseInt(lengthPassword.value); i++ ) {
               let isNumber = getBoolean()
               
               if (isNumber) {
                  password.push(getNumber())
               } else {
                  password.push(getString())
               }
            }
            result.value = password.join('')
         }
         
         const reset = () => {
            result.value = ''
            lengthPassword.value = ''
         }
         
         return { lengthPassword, result, generatePassword, reset }
         
      }
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
         margin-right: .5rem;
      }
      
      #result {
         width: 100%;
         background: whitesmoke;
         padding: .35rem .25rem;
         color: rgba(black, .85);
         font-weight: bold;
         font-size: 1rem;
         word-break: break-all;
      }
   }
   
   
</style>
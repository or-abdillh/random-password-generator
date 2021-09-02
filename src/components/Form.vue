<template>
   <section class="bg-white border md:px-5 md:py-3 border-gray-200 md:w-1/2 border-box shadow-md rounded mx-auto px-3 py-3 mt-5" >
      <label class="text-base text-blue-500" for="lengthPassword">How length password you want ?</label>
      <input class="border-gray-500 bg-gray-100 md:block md:w-full border-box px-2 py-2 text-xl mt-2 mb-2" v-model="lengthPassword" type="number" placeholder="ex: 8" name="lengthPassword" id="lengthPassword" />
      <button class="bg-blue-500 text-sm text-white px-3 py-2 rounded shadow " @click="generatePassword" type="button">Generate</button>
      <button class="bg-gray-100 text-sm ml-3 text-gray-800 border px-3 py-2 rounded" @click="reset" type="button">Reset</button>
      <span class="block break-all bg-gray-100 mt-3 text-center px-3 py-2" v-if="result != ''" id="result">
         <small class="text-sm text-gray-500" >Your password : </small>
         <p class="text-base">{{ result }}</p>
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
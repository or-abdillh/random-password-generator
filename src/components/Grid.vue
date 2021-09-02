<template>
   <section>
      
      <div class="grid grid-cols-6 text-center mt-5 border border-black rounded overflow-hidden shadow-md">
         <div class="bg-gray-200 grid place-items-center col-span-3">
           1 
         </div>
         <div class="bg-purple-200 col-span-3 flex flex-wrap">
            <div class="bg-purple-300 w-full p-2">
               2
            </div>
            <div class="bg-purple-400 w-full p-2">
               3
            </div>
         </div>
         <div class="p-5 bg-blue-200 col-span-full">
            4
         </div>
         <div class="bg-green-200 col-span-full bg-gray-200 grid grid-cols-6">
            <template v-for="div in 6" :key="div">
               <div :class="'bg-green-' + div + '00'" class="col-span-auto p-2">
                  {{ div + 4 }}
               </div>
            </template>
         </div>
      </div>
      
   </section>
</template>

<script>
   
   export default {
      name: 'Grid'
   }
   
</script>
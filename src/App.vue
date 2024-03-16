

<script setup>
import {ref} from 'vue';

let message = ref('');

let shownMessage = ref('');
let count = ref(0);

function increment(){
  count.value++
}


function getName(event){
  // here i assign the value of message to shownMessage 
  // then i can display shownMessage
  shownMessage.value = message.value;
  
}
</script>



<template>

  <!-- nav bar  -->
  <nav class="bg-blue-500 p-4">
        <div class="container mx-auto flex items-center justify-between">
            <!-- Brand -->
            <div class="text-white text-lg font-bold">
                Todo
            </div>

            <!-- Navigation Links (Add your links here) -->
            <ul class="flex space-x-4">
                <li><a href="#" class="text-white">Home</a></li>
                <li><a href="#" class="text-white">About</a></li>
                <li><a href="#" class="text-white">Contact</a></li>
            </ul>
        </div>
    </nav>

    <main>
      <div class="m-2 flex items-center justify-center ">
      <p class="text-black">{{ shownMessage }}</p>
        <input
          v-model="message"
         placeholder="enter todo"
        class="peer h-full  border-b border-blue-gray-200 bg-transparent pt-4 pb-1.5 font-sans text-sm font-normal text-blue-gray-700 outline outline-0 transition-all placeholder-shown:border-blue-gray-200 focus:border-gray-900 focus:outline-0 disabled:border-0 disabled:bg-blue-gray-50"
       />
        <button @click="getName" class="ml-2 bg-blue-500 text-white px-4 py-2 rounded-md hover:bg-blue-700 focus:outline-none focus:ring focus:border-blue-300">Submit</button>
      </div>

      <!-- div for count and practising counting  -->
      <div class="flex justify-center m-2">
        <button class="bg-blue-500 text-white px-4 py-2 rounded-md hover:bg-blue-700 focus:outline-none focus:ring focus:border-blue-300" @click="increment">{{ count }}</button>
      </div>


      <!-- table to show todolist  -->
      <table class="min-w-full bg-white shadow-md rounded-md overflow-hidden">
        <thead class="bg-blue-500 text-white">
            <tr>
                <th class="px-6 py-4">Todo</th>
            </tr>
        </thead>
        <tbody class="bg-gray-100">
            <tr>
                <td class="px-6 py-4">Row Content</td>
            </tr>
        </tbody>
      </table>
    </main>
</template>

<style scoped>

</style>

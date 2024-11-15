<script setup>
import {ref} from 'vue'

    let qty = ref(1);
    
    function add () {
        qty.value++
        console.log(qty)
    }
    
    function subtract (){
       if(qty.value>0){
        qty.value--
       }else{
        'para'
       }
    }
</script>

<template >
    <div class="max-w-80 mx-auto p-6 bg-purple-300 rounded">
        <div 
        v-if="qty > 0"
        class="bg-green-500 text-white size-8 rounded-full inline-flex justify-center items-center font-bold"
        :class="{'bg-orange-500': qty > 3}"
        >
        {{ qty }}
        </div>
        <div v-else >
            Nadie te visita :(
        </div>
        <div 
        @click="add"
        class="mx-12 bg-blue-400 text-white rounded size-6 inline-flex justify-center items-center">
            +
        </div>
        <div
        @click="subtract"
        class="bg-green-400 text-white rounded inline-flex justify-center items-center size-6">
            -
        </div>
    </div>
</template>
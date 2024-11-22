<script setup>
    import { ref } from 'vue';

    const name = "Pepito"
    let counter = ref(5)

    let characters = ref([])
    
    function add(){
        counter.value++
        characters.value.push(counter.value)
    }
     
    function rest(){
        counter.value--
        console.log(counter)
    }
</script>

<template>
    <div class=" mx-auto max-w-96 rounded py-4 px-6 bg-blue-300">
        Hola mundo {{ name }}

        <div 
        v-if="counter > 0"
        class=" bg-red-600 text-white size-8 rounded-full flex items-center justify-center">
            {{ counter }}
        </div>

        <div v-else>
            Nadie te escribe : :(
        </div>

        <div 
        @click="add"
        class=" bg-blue-600 text-white size-8 rounded-full flex items-center justify-center">
            +
        </div>

        <div 
        @click="rest"
        class=" bg-sky-600 text-white size-8 rounded-full flex items-center justify-center">
            -
    </div>
    </div>
    <div 
    v-for="(name, index) in characters"
    :key="index"
    class=" bg-green-600 mb-1">
    {{ name }}
</div>
</template>
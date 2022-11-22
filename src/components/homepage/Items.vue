<script setup>
import {ref} from 'vue'
import ItemsCard from './../ItemsCard.vue'

const items = ref([
  {id:1, image: '/src/assets/img/items-1.jpg',title:'Mobile UI Kit' ,category: 'Mobile UI Kit'},
  {id:2, image: '/src/assets/img/items-2.jpg',title:'Online Doctor Consultation' ,category: 'Mobile UI Kit'},
  {id:3, image: '/src/assets/img/items-3.jpg',title:'Banking Crypto' ,category: 'Mobile UI Kit'},
])
</script>

<template>
  <div class="container px-4 mx-auto my-16 md:px-12">
      <h2 class="mb-4 text-xl font-medium md:mb-0 md:text-lg">New Items</h2>
      <div class="flex flex-wrap -mx-1 lg:-mx-4">
        <ItemsCard 
          v-for="item in items" 
          :key="item.id" 
          :image="item.image" 
          :title="item.title" 
          :category="item.category" 
        />
      </div>
    </div>
</template>
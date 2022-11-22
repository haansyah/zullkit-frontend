<script setup>
import {ref} from 'vue'
import ItemCard from '../ItemCard.vue'

const items = ref([
  {id:1, image: '/src/assets/img/items-1.jpg',title:'Mobile UI Kit' ,description: 'Mobile UI Kit'},
  {id:2, image: '/src/assets/img/items-2.jpg',title:'Online Doctor Consultation' ,description: 'Mobile UI Kit'},
  {id:3, image: '/src/assets/img/items-3.jpg',title:'Banking Crypto' ,description: 'Mobile UI Kit'},
])
</script>

<template>
  <div class="container px-4 mx-auto my-16 md:px-12">
      <h2 class="mb-4 text-xl font-medium md:mb-0 md:text-lg">New Items</h2>
      <div class="flex flex-wrap -mx-1 lg:-mx-4">
        <ItemCard 
          v-for="item in items" 
          :key="item.id" 
          :id="item.id"
          :image="item.image" 
          :title="item.title" 
          :description="item.description" 
        />
      </div>
    </div>
</template>
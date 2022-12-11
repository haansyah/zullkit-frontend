<script setup>
import { onMounted, computed } from 'vue'
import {RouterLink} from 'vue-router'
import { useUserStore } from '@/stores/user'

defineProps({
  id: Number,
  image: String,
  title: String,
  description: String
})

const userStore = useUserStore()
const isLoggedIn = computed(() => userStore.isLoggedIn)

onMounted(() => {
  userStore.fetchUser();
})

</script>

<template>
  <div class="w-full px-1 my-1 md:w-1/2 lg:my-4 lg:px-4 lg:w-1/3">
          <div class="overflow-hidden border border-gray-200 rounded-xl">
            <RouterLink :to="isLoggedIn ? '/product/' + id : '/login'">
              <div class="m-4 overflow-hidden rounded-xl">
                <img
                  alt="Placeholder"
                  class="block w-full h-auto"
                  :src="image"
                />
              </div>
            </RouterLink>

            <header class="px-4 mb-4 leading-tight">
              <h1 class="text-lg">
                <RouterLink
                class="font-semibold text-black no-underline hover:underline"
                :to="isLoggedIn ? '/product/' + id : '/login'"
                >
                  {{title}}
                </RouterLink>
              </h1>
              <span class="block text-sm font-light text-gray-500 no-underline">
                {{description}}
              </span>
            </header>
          </div>
        </div>
</template>
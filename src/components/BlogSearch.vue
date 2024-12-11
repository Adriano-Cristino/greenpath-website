<template>
  <div class="relative">
    <div class="max-w-3xl mx-auto mb-12">
      <div class="flex flex-col sm:flex-row gap-4">
        <div class="flex-1">
          <label for="search" class="sr-only">Buscar posts</label>
          <div class="relative">
            <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
              <MagnifyingGlassIcon class="h-5 w-5 text-gray-400" />
            </div>
            <input
              id="search"
              v-model="searchQuery"
              type="text"
              class="block w-full pl-10 pr-3 py-2 border border-gray-300 rounded-md leading-5 bg-white placeholder-gray-500 focus:outline-none focus:placeholder-gray-400 focus:ring-1 focus:ring-green-500 focus:border-green-500 sm:text-sm"
              placeholder="Buscar posts..."
              @input="handleSearch"
            >
          </div>
        </div>
        <div class="sm:w-48">
          <select
            v-model="selectedCategory"
            class="block w-full pl-3 pr-10 py-2 text-base border-gray-300 focus:outline-none focus:ring-green-500 focus:border-green-500 sm:text-sm rounded-md"
            @change="handleSearch"
          >
            <option value="">Todas categorias</option>
            <option v-for="category in categories" :key="category" :value="category">
              {{ category }}
            </option>
          </select>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, watch } from 'vue'
import { MagnifyingGlassIcon } from '@heroicons/vue/24/outline'

const props = defineProps({
  categories: {
    type: Array,
    default: () => []
  }
})

const emit = defineEmits(['search'])

const searchQuery = ref('')
const selectedCategory = ref('')

const handleSearch = () => {
  emit('search', {
    query: searchQuery.value,
    category: selectedCategory.value
  })
}

// Debounce search
let timeout = null
watch(searchQuery, () => {
  clearTimeout(timeout)
  timeout = setTimeout(handleSearch, 300)
})
</script>

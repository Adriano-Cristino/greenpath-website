<template>
  <article class="card overflow-hidden group hover:shadow-xl transition-shadow duration-300">
    <div class="relative pb-48">
      <img :src="post.imageUrl" :alt="post.title" 
           class="absolute h-full w-full object-cover transform group-hover:scale-105 transition-transform duration-500">
    </div>
    <div class="p-6">
      <div>
        <div class="flex flex-wrap gap-2 mb-4">
          <div v-for="category in post.categories" :key="category" 
               class="inline-flex items-center px-3 py-0.5 rounded-full text-sm font-medium bg-green-100 text-green-800">
            {{ category }}
          </div>
        </div>
        <router-link :to="{ name: 'blog' }" class="block">
          <h3 class="text-xl font-semibold text-gray-900 group-hover:text-green-600 transition-colors duration-300">
            {{ post.title }}
          </h3>
          <p class="mt-3 text-base text-gray-500">{{ post.description }}</p>
        </router-link>
      </div>
      <div class="mt-6 flex items-center">
        <div class="flex-shrink-0">
          <img class="h-10 w-10 rounded-full" :src="post.author.imageUrl" :alt="post.author.name">
        </div>
        <div class="ml-3">
          <p class="text-sm font-medium text-gray-900">{{ post.author.name }}</p>
          <div class="flex space-x-1 text-sm text-gray-500">
            <time :datetime="post.datetime">{{ post.date }}</time>
            <span aria-hidden="true">&middot;</span>
            <span>{{ post.readingTime }} min de leitura</span>
          </div>
        </div>
      </div>
    </div>
  </article>
</template>

<script setup>
defineProps({
  post: {
    type: Object,
    required: true
  }
})
</script>

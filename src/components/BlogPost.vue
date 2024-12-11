<template>
  <article class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
    <div class="text-center mb-12">
      <div class="flex justify-center space-x-3 mb-6">
        <div v-for="category in post.categories" :key="category" 
             class="inline-flex items-center px-3 py-0.5 rounded-full text-sm font-medium bg-green-100 text-green-800">
          {{ category }}
        </div>
      </div>
      <h1 class="text-4xl font-bold text-gray-900 mb-4">{{ post.title }}</h1>
      <div class="flex items-center justify-center space-x-4">
        <div class="flex items-center">
          <img :src="post.author.imageUrl" :alt="post.author.name" class="h-10 w-10 rounded-full">
          <span class="ml-2 text-gray-600">{{ post.author.name }}</span>
        </div>
        <div class="text-gray-500">
          <time :datetime="post.datetime">{{ post.date }}</time>
          <span class="mx-1">&middot;</span>
          <span>{{ post.readingTime }} min de leitura</span>
        </div>
      </div>
    </div>

    <div class="prose prose-green max-w-none">
      <img v-if="post.imageUrl" :src="post.imageUrl" :alt="post.title" class="w-full h-96 object-cover rounded-xl mb-8">
      <div v-html="post.content"></div>
    </div>

    <div class="mt-12 border-t border-gray-200 pt-8">
      <div class="flex items-center justify-between">
        <div class="flex items-center space-x-4">
          <button @click="handleShare" class="inline-flex items-center px-4 py-2 border border-gray-300 rounded-md shadow-sm text-sm font-medium text-gray-700 bg-white hover:bg-gray-50">
            <ShareIcon class="h-5 w-5 mr-2 text-gray-500" />
            Compartilhar
          </button>
          <button @click="handleBookmark" class="inline-flex items-center px-4 py-2 border border-gray-300 rounded-md shadow-sm text-sm font-medium text-gray-700 bg-white hover:bg-gray-50">
            <BookmarkIcon class="h-5 w-5 mr-2 text-gray-500" />
            Salvar
          </button>
        </div>
        <div class="flex items-center space-x-4">
          <router-link :to="{ name: 'blog' }" class="text-green-600 hover:text-green-700">
            Voltar para o Blog
          </router-link>
        </div>
      </div>
    </div>

    <!-- Related Posts -->
    <div v-if="relatedPosts.length" class="mt-12 border-t border-gray-200 pt-8">
      <h2 class="text-2xl font-bold text-gray-900 mb-6">Posts Relacionados</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <div v-for="relatedPost in relatedPosts" :key="relatedPost.id" 
             class="group relative">
          <div class="aspect-w-16 aspect-h-9 rounded-lg overflow-hidden">
            <img :src="relatedPost.imageUrl" :alt="relatedPost.title" 
                 class="object-cover transform group-hover:scale-105 transition-transform duration-300">
          </div>
          <div class="mt-4">
            <h3 class="text-lg font-semibold text-gray-900 group-hover:text-green-600">
              <router-link :to="{ name: 'post', params: { slug: relatedPost.slug }}">
                {{ relatedPost.title }}
              </router-link>
            </h3>
            <p class="mt-2 text-sm text-gray-500">{{ relatedPost.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </article>
</template>

<script setup>
import { ref, computed } from 'vue'
import { ShareIcon, BookmarkIcon } from '@heroicons/vue/24/outline'

const props = defineProps({
  post: {
    type: Object,
    required: true
  },
  relatedPosts: {
    type: Array,
    default: () => []
  }
})

const handleShare = () => {
  if (navigator.share) {
    navigator.share({
      title: props.post.title,
      text: props.post.description,
      url: window.location.href
    })
  }
}

const handleBookmark = () => {
  // Implementar lógica de bookmark
  console.log('Bookmark post:', props.post.id)
}
</script>

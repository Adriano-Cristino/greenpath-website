<template>
  <div class="bg-white">
    <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
      <div v-if="currentPost" class="article-content">
        <div class="text-center mb-12">
          <div class="flex justify-center space-x-3 mb-6">
            <div v-for="category in currentPost.categories" :key="category" 
                 class="inline-flex items-center px-3 py-0.5 rounded-full text-sm font-medium bg-green-100 text-green-800">
              {{ category }}
            </div>
          </div>
          <h1 class="text-4xl font-bold text-gray-900 mb-4">{{ currentPost.title }}</h1>
          <div class="flex items-center justify-center space-x-4">
            <div class="flex items-center">
              <img :src="currentPost.author.imageUrl" :alt="currentPost.author.name" class="h-10 w-10 rounded-full">
              <span class="ml-2 text-gray-600">{{ currentPost.author.name }}</span>
            </div>
            <div class="text-gray-500">
              <time :datetime="currentPost.datetime">{{ currentPost.date }}</time>
              <span class="mx-1">&middot;</span>
              <span>{{ currentPost.readingTime }} min de leitura</span>
            </div>
          </div>
        </div>

        <div class="prose prose-green max-w-none">
          <img v-if="currentPost.imageUrl" :src="currentPost.imageUrl" :alt="currentPost.title" class="w-full h-96 object-cover rounded-xl mb-8">
          <div v-html="currentPost.content"></div>
        </div>

        <div class="mt-12 border-t border-gray-200 pt-8">
          <div class="flex items-center justify-between">
            <div class="flex items-center space-x-4">
              <button @click="handleShare" class="inline-flex items-center px-4 py-2 border border-gray-300 rounded-md shadow-sm text-sm font-medium text-gray-700 bg-white hover:bg-gray-50">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2 text-gray-500" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8.684 13.342C8.886 12.938 9 12.482 9 12c0-.482-.114-.938-.316-1.342m0 2.684a3 3 0 110-2.684m0 2.684l6.632 3.316m-6.632-6l6.632-3.316m0 0a3 3 0 105.367-2.684 3 3 0 00-5.367 2.684zm0 9.316a3 3 0 105.368 2.684 3 3 0 00-5.368-2.684z" />
                </svg>
                Compartilhar
              </button>
              <button @click="handleBookmark" class="inline-flex items-center px-4 py-2 border border-gray-300 rounded-md shadow-sm text-sm font-medium text-gray-700 bg-white hover:bg-gray-50">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2 text-gray-500" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z" />
                </svg>
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
      </div>
      <div v-else class="text-center py-12">
        <h2 class="text-2xl font-bold text-gray-900">Post não encontrado</h2>
        <router-link :to="{ name: 'blog' }" class="mt-4 inline-block text-green-600 hover:text-green-700">
          Voltar para o Blog
        </router-link>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const posts = [
  {
    id: 1,
    slug: 'como-reduzir-pegada-carbono',
    title: 'Como reduzir sua pegada de carbono no dia a dia',
    content: `
      <p class="mb-4">A redução da pegada de carbono é um dos principais desafios da nossa geração. Com pequenas mudanças em nossos hábitos diários, podemos contribuir significativamente para um futuro mais sustentável.</p>

      <h2 class="text-2xl font-bold mt-8 mb-4">1. Transporte Sustentável</h2>
      <p class="mb-4">Opte por meios de transporte mais sustentáveis sempre que possível:</p>
      <ul class="list-disc ml-6 mb-4">
        <li>Use transporte público</li>
        <li>Considere andar de bicicleta para trajetos curtos</li>
        <li>Organize caronas com colegas de trabalho</li>
      </ul>

      <h2 class="text-2xl font-bold mt-8 mb-4">2. Consumo Consciente</h2>
      <p class="mb-4">Suas escolhas de consumo têm um impacto direto na sua pegada de carbono:</p>
      <ul class="list-disc ml-6 mb-4">
        <li>Prefira produtos locais e sazonais</li>
        <li>Reduza o consumo de carne</li>
        <li>Evite embalagens desnecessárias</li>
      </ul>

      <h2 class="text-2xl font-bold mt-8 mb-4">3. Eficiência Energética</h2>
      <p class="mb-4">Em casa, várias ações podem reduzir seu consumo de energia:</p>
      <ul class="list-disc ml-6 mb-4">
        <li>Use lâmpadas LED</li>
        <li>Aproveite a luz natural</li>
        <li>Mantenha seus aparelhos em bom estado</li>
      </ul>
    `,
    imageUrl: 'https://images.unsplash.com/photo-1542601906990-b4d3fb778b09?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2070&q=80',
    date: '10 Mar, 2024',
    datetime: '2024-03-10',
    categories: ['Sustentabilidade', 'Dicas'],
    author: {
      name: 'Maria Silva',
      href: '#',
      imageUrl: 'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
    },
    readingTime: 6,
  },
  // Adicione mais posts aqui...
]

const currentPost = computed(() => {
  return posts.find(post => post.slug === route.params.slug)
})

const relatedPosts = computed(() => {
  if (!currentPost.value) return []
  
  return posts
    .filter(post => {
      return post.id !== currentPost.value.id && 
        post.categories.some(category => 
          currentPost.value.categories.includes(category)
        )
    })
    .slice(0, 2)
})

const handleShare = () => {
  if (navigator.share) {
    navigator.share({
      title: currentPost.value.title,
      text: currentPost.value.description,
      url: window.location.href
    })
  }
}

const handleBookmark = () => {
  // Implementar lógica de bookmark
  console.log('Bookmark post:', currentPost.value.id)
}
</script>

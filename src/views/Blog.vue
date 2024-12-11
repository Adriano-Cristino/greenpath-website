<template>
  <div class="min-h-screen">
    <!-- Hero Section -->
    <div class="relative bg-green-800 pb-32">
      <div class="absolute inset-0">
        <img class="w-full h-full object-cover" src="/images/blog-hero.jpg" alt="Blog Hero">
        <div class="absolute inset-0 bg-green-800 mix-blend-multiply"></div>
      </div>
      <div class="relative max-w-7xl mx-auto py-24 px-4 sm:py-32 sm:px-6 lg:px-8">
        <h1 class="text-4xl font-extrabold tracking-tight text-white md:text-5xl lg:text-6xl">Blog</h1>
        <p class="mt-6 max-w-3xl text-xl text-green-100">
          Artigos, dicas e novidades sobre sustentabilidade, meio ambiente e práticas eco-friendly.
        </p>
      </div>
    </div>

    <!-- Content Section -->
    <div class="relative -mt-32 pb-20">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Category Filter -->
        <div class="bg-white rounded-lg shadow-lg p-8 mb-8">
          <div class="flex flex-wrap gap-4 justify-center">
            <button 
              v-for="category in categories" 
              :key="category"
              @click="selectedCategory = category === selectedCategory ? null : category"
              :class="[
                'px-4 py-2 rounded-full text-sm font-medium transition-colors duration-200',
                category === selectedCategory
                  ? 'bg-green-600 text-white'
                  : 'bg-green-100 text-green-800 hover:bg-green-200'
              ]"
            >
              {{ category }}
            </button>
          </div>
        </div>

        <!-- Blog Grid -->
        <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
          <BlogCard 
            v-for="post in filteredPosts" 
            :key="post.id" 
            :post="post"
            class="bg-white rounded-lg shadow-lg transform hover:-translate-y-1 transition-all duration-300"
          />
        </div>

        <!-- Empty State -->
        <div v-if="filteredPosts.length === 0" class="bg-white rounded-lg shadow-lg p-12 text-center">
          <svg class="mx-auto h-12 w-12 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.172 16.172a4 4 0 015.656 0M9 10h.01M15 10h.01M12 12h.01M12 12h.01M12 12h.01M12 12h.01M12 12h.01M12 12h.01M12 12h.01M12 12h.01M12 12h.01M12 12h.01M12 12h.01" />
          </svg>
          <h3 class="mt-2 text-sm font-medium text-gray-900">Nenhum post encontrado</h3>
          <p class="mt-1 text-sm text-gray-500">Tente selecionar outra categoria.</p>
        </div>
      </div>
    </div>

    <!-- Newsletter Section -->
    <section class="bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <div class="bg-green-700 rounded-2xl shadow-xl overflow-hidden">
          <div class="px-6 py-12 sm:px-12 lg:px-16">
            <div class="max-w-3xl mx-auto text-center">
              <h2 class="text-3xl font-extrabold text-white sm:text-4xl">
                Receba nossas atualizações
              </h2>
              <p class="mt-4 text-lg leading-6 text-green-100">
                Inscreva-se para receber as últimas notícias e artigos sobre sustentabilidade e meio ambiente.
              </p>
              <div class="mt-8 flex justify-center">
                <form class="sm:flex">
                  <label for="email-address" class="sr-only">Email</label>
                  <input
                    id="email-address"
                    name="email"
                    type="email"
                    autocomplete="email"
                    required
                    class="w-full px-5 py-3 border border-transparent placeholder-gray-500 focus:ring-2 focus:ring-offset-2 focus:ring-offset-green-700 focus:ring-white focus:border-white sm:max-w-xs rounded-md"
                    placeholder="Digite seu email"
                  />
                  <div class="mt-3 rounded-md shadow sm:mt-0 sm:ml-3 sm:flex-shrink-0">
                    <button
                      type="submit"
                      class="w-full flex items-center justify-center px-5 py-3 border border-transparent text-base font-medium rounded-md text-green-600 bg-white hover:bg-green-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-green-700 focus:ring-white"
                    >
                      Inscrever-se
                    </button>
                  </div>
                </form>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import BlogCard from '../components/BlogCard.vue'

const selectedCategory = ref(null)

const categories = [
  'Sustentabilidade',
  'Licenciamento Ambiental',
  'Gestão Ambiental',
  'Legislação',
  'Tecnologia Verde',
  'Estudos Ambientais'
]

const posts = [
  {
    id: 1,
    title: 'Como obter sua Licença Ambiental de forma eficiente',
    description: 'Guia completo sobre o processo de licenciamento ambiental e as melhores práticas para garantir sua aprovação.',
    imageUrl: '/images/blog/licenciamento.jpg',
    categories: ['Licenciamento Ambiental', 'Legislação'],
    author: {
      name: 'Ana Silva',
      imageUrl: '/images/team/ana.jpg'
    },
    date: '10 Dec 2024',
    datetime: '2024-12-10',
    readingTime: 8
  },
  {
    id: 2,
    title: 'Tecnologias sustentáveis para empresas modernas',
    description: 'Descubra as últimas inovações em tecnologia verde que podem transformar sua empresa.',
    imageUrl: '/images/blog/tech.jpg',
    categories: ['Tecnologia Verde', 'Sustentabilidade'],
    author: {
      name: 'Carlos Santos',
      imageUrl: '/images/team/carlos.jpg'
    },
    date: '8 Dec 2024',
    datetime: '2024-12-08',
    readingTime: 6
  },
  {
    id: 3,
    title: 'Gestão de resíduos industriais',
    description: 'Aprenda as melhores práticas para gerenciar resíduos industriais de forma sustentável e econômica.',
    imageUrl: '/images/blog/residuos.jpg',
    categories: ['Gestão Ambiental', 'Sustentabilidade'],
    author: {
      name: 'Marina Costa',
      imageUrl: '/images/team/marina.jpg'
    },
    date: '5 Dec 2024',
    datetime: '2024-12-05',
    readingTime: 10
  }
]

const filteredPosts = computed(() => {
  if (!selectedCategory.value) return posts
  return posts.filter(post => post.categories.includes(selectedCategory.value))
})
</script>

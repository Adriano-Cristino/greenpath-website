<template>
  <div>
    <!-- Header Section -->
    <section class="relative py-32 animated-gradient">
      <div class="absolute inset-0 bg-black/40"></div>
      <div class="relative container mx-auto px-4">
        <div class="max-w-3xl mx-auto text-center text-white">
          <h1 class="text-5xl md:text-6xl font-bold mb-6">Sobre Nós</h1>
          <p class="text-xl opacity-90">
            Desde 2024, a GreenPath tem sido referência em consultoria ambiental, 
            ajudando empresas a alcançarem seus objetivos de sustentabilidade.
          </p>
        </div>
      </div>
      <div class="absolute bottom-0 left-0 right-0">
        <svg class="w-full h-24 text-white" viewBox="0 0 1440 74" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M0,0 C240,70 480,70 720,35 C960,0 1200,0 1440,35 L1440 74 L0 74 Z" fill="currentColor"/>
        </svg>
      </div>
    </section>

    <!-- Mission, Vision, Values Section -->
    <section class="py-20 bg-white">
      <div class="container mx-auto px-4">
        <div class="grid grid-cols-1 gap-8 lg:grid-cols-3">
          <div class="lg:col-span-2">
            <div class="space-y-8">
              <div class="hover-scale p-6 bg-white rounded-2xl shadow-lg transition-all">
                <h3 class="text-2xl font-bold text-gray-900 mb-4 flex items-center">
                  <span class="text-green-600 mr-3">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" />
                    </svg>
                  </span>
                  Missão
                </h3>
                <p class="text-lg text-gray-600">
                  Promover o desenvolvimento sustentável através de soluções inovadoras 
                  e práticas ambientalmente responsáveis, contribuindo para um futuro 
                  mais verde e equilibrado.
                </p>
              </div>

              <div class="hover-scale p-6 bg-white rounded-2xl shadow-lg transition-all">
                <h3 class="text-2xl font-bold text-gray-900 mb-4 flex items-center">
                  <span class="text-green-600 mr-3">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z" />
                    </svg>
                  </span>
                  Visão
                </h3>
                <p class="text-lg text-gray-600">
                  Ser reconhecida como líder em consultoria ambiental, inspirando 
                  mudanças positivas e estabelecendo novos padrões de sustentabilidade 
                  no mercado.
                </p>
              </div>

              <div class="hover-scale p-6 bg-white rounded-2xl shadow-lg transition-all">
                <h3 class="text-2xl font-bold text-gray-900 mb-4 flex items-center">
                  <span class="text-green-600 mr-3">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z" />
                    </svg>
                  </span>
                  Valores
                </h3>
                <ul class="text-lg text-gray-600 space-y-3">
                  <li class="flex items-center">
                    <span class="text-green-500 mr-2">•</span>
                    Compromisso com a sustentabilidade
                  </li>
                  <li class="flex items-center">
                    <span class="text-green-500 mr-2">•</span>
                    Inovação e excelência técnica
                  </li>
                  <li class="flex items-center">
                    <span class="text-green-500 mr-2">•</span>
                    Ética e transparência
                  </li>
                  <li class="flex items-center">
                    <span class="text-green-500 mr-2">•</span>
                    Responsabilidade social
                  </li>
                  <li class="flex items-center">
                    <span class="text-green-500 mr-2">•</span>
                    Parceria com clientes
                  </li>
                </ul>
              </div>
            </div>
          </div>

          <div class="lg:col-span-1">
            <div class="sticky top-8">
              <div class="aspect-w-3 aspect-h-2 rounded-2xl overflow-hidden shadow-xl">
                <img class="object-cover w-full h-full transform hover:scale-110 transition-transform duration-500" 
                     src="../assets/team.jpg" 
                     alt="Equipe GreenPath">
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Team Section -->
    <section class="py-20 bg-gray-50">
      <div class="container mx-auto px-4">
        <h2 class="text-4xl font-bold text-gray-900 mb-12 text-center">Nossa Equipe</h2>
        <div class="grid grid-cols-1 gap-12 lg:grid-cols-3 sm:grid-cols-2">
          <div v-for="member in team" :key="member.name" 
               class="hover-scale bg-white p-6 rounded-2xl shadow-lg transition-all">
            <div class="aspect-w-3 aspect-h-3 mb-6">
              <img class="object-cover w-full h-full rounded-xl shadow-md" 
                   :src="member.imageUrl" 
                   :alt="member.name">
            </div>
            <div class="space-y-4">
              <div class="text-center">
                <h3 class="text-xl font-bold text-gray-900">{{ member.name }}</h3>
                <p class="text-green-600 font-medium">{{ member.role }}</p>
              </div>
              <p class="text-gray-600 text-center">{{ member.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
const team = [
  {
    name: 'Ana Silva',
    role: 'CEO & Fundadora',
    imageUrl: '../assets/team-1.jpg',
    description: 'Especialista em gestão ambiental com mais de 15 anos de experiência.',
  },
  {
    name: 'Carlos Santos',
    role: 'Diretor Técnico',
    imageUrl: '../assets/team-2.jpg',
    description: 'Engenheiro Ambiental com foco em projetos de sustentabilidade.',
  },
  {
    name: 'Marina Costa',
    role: 'Consultora Sênior',
    imageUrl: '../assets/team-3.jpg',
    description: 'Especialista em legislação ambiental e licenciamento.',
  },
]
</script>

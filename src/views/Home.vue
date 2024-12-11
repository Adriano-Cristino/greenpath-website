<template>
  <div>
    <!-- Hero Section -->
    <section class="relative min-h-screen animated-gradient">
      <div class="absolute inset-0">
        <!-- Video Background with Fallback -->
        <div class="absolute inset-0">
          <img 
            src="https://images.unsplash.com/photo-1542601906990-b4d3fb778b09?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2070&q=80"
            alt="Nature Background"
            class="w-full h-full object-cover"
          >
          <video 
            class="absolute inset-0 w-full h-full object-cover hidden md:block"
            autoplay
            loop
            muted
            playsinline
          >
            <source src="https://player.vimeo.com/external/517090081.hd.mp4?s=89e34840123c7a0d1434874b16b171570f7c7930&profile_id=175" type="video/mp4">
          </video>
        </div>
        <div class="absolute inset-0 bg-gradient-to-r from-green-900/80 to-black/50"></div>
      </div>
      <div class="relative container mx-auto px-4 py-32 flex flex-col justify-center min-h-screen">
        <div class="max-w-4xl">
          <h1 class="text-5xl md:text-7xl font-bold text-white mb-6 animate-float">
            Soluções Sustentáveis para um Futuro Melhor
          </h1>
          <p class="text-xl md:text-2xl text-white/90 mb-8">
            Transformando negócios através de consultoria ambiental especializada e inovadora
          </p>
          <div class="flex flex-wrap gap-4">
            <router-link to="/contact" class="btn-primary">
              Fale Conosco
              <ArrowRightIcon class="ml-2 h-5 w-5" />
            </router-link>
            <router-link to="/services" class="glass-card px-6 py-3 text-white hover:bg-white/40 transition-all">
              Nossos Serviços
              <ChevronRightIcon class="ml-2 h-5 w-5 inline" />
            </router-link>
          </div>
        </div>
      </div>
      <div class="absolute bottom-0 left-0 right-0">
        <svg class="w-full h-24 text-white" viewBox="0 0 1440 74" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M0,0 C240,70 480,70 720,35 C960,0 1200,0 1440,35 L1440 74 L0 74 Z" fill="currentColor"/>
        </svg>
      </div>
    </section>

    <!-- Features Section -->
    <section class="py-20 bg-white">
      <div class="container mx-auto px-4">
        <div class="text-center mb-16">
          <h2 class="section-title gradient-text mb-4">Por que escolher a GreenPath?</h2>
          <p class="section-subtitle">Oferecemos soluções completas em consultoria ambiental, combinando experiência e inovação</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="(feature, index) in features" :key="index" 
               class="card p-6 hover-scale">
            <div class="h-14 w-14 rounded-xl bg-green-100 flex items-center justify-center mb-6">
              <component :is="feature.icon" class="h-8 w-8 text-green-600" />
            </div>
            <h3 class="text-xl font-semibold mb-3">{{ feature.title }}</h3>
            <p class="text-gray-600">{{ feature.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Stats Section -->
    <section class="py-20 bg-gray-50">
      <div class="container mx-auto px-4">
        <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
          <div v-for="(stat, index) in stats" :key="index" 
               class="text-center glass-card p-6 bg-white">
            <div class="text-4xl font-bold text-green-600 mb-2">{{ stat.value }}</div>
            <div class="text-gray-600">{{ stat.label }}</div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section with Parallax -->
    <section class="relative py-32 overflow-hidden bg-[url('https://images.unsplash.com/photo-1511497584788-876760111969?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2070&q=80')] bg-cover bg-fixed">
      <div class="absolute inset-0 bg-[radial-gradient(circle_at_top_right,rgba(32,128,96,0.5),transparent)] mix-blend-overlay"></div>
      <div class="relative container mx-auto px-4">
        <div class="max-w-4xl mx-auto text-center">
          <div class="glass-card p-12 rounded-3xl backdrop-blur-sm border border-white/20 shadow-2xl">
            <h2 class="text-4xl md:text-5xl font-bold mb-6 text-white drop-shadow-lg">
              Pronto para transformar seu negócio?
            </h2>
            <p class="text-xl text-white mb-10 max-w-2xl mx-auto">
              Entre em contato conosco hoje e descubra como podemos ajudar sua empresa 
              a alcançar seus objetivos de sustentabilidade.
            </p>
            <div class="flex flex-col sm:flex-row items-center justify-center gap-6">
              <router-link 
                to="/contact" 
                class="inline-flex items-center px-8 py-4 text-lg font-semibold rounded-xl bg-white text-green-700 hover:bg-green-50 transform transition-all duration-300 hover:scale-105 shadow-xl hover:shadow-2xl"
              >
                Agende uma Consulta
                <ArrowRightIcon class="ml-2 h-6 w-6 inline-block" />
              </router-link>
              <router-link 
                to="/services" 
                class="inline-flex items-center px-6 py-3 text-white border-2 border-white/30 rounded-xl hover:bg-white/10 transition-all duration-300"
              >
                Conheça Nossos Serviços
                <ChevronRightIcon class="ml-2 h-5 w-5" />
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ArrowRightIcon, ChevronRightIcon, LightBulbIcon, ChartBarIcon, UserGroupIcon, GlobeAltIcon, SparklesIcon, ShieldCheckIcon } from '@heroicons/vue/24/outline'

const features = [
  {
    icon: LightBulbIcon,
    title: 'Soluções Inovadoras',
    description: 'Desenvolvemos estratégias personalizadas e inovadoras para atender às necessidades específicas do seu negócio.'
  },
  {
    icon: ChartBarIcon,
    title: 'Resultados Comprovados',
    description: 'Nossa metodologia garante resultados mensuráveis e impacto positivo para sua empresa.'
  },
  {
    icon: UserGroupIcon,
    title: 'Equipe Especializada',
    description: 'Contamos com profissionais altamente qualificados e experientes em consultoria ambiental.'
  },
  {
    icon: GlobeAltIcon,
    title: 'Compromisso Ambiental',
    description: 'Promovemos práticas sustentáveis que beneficiam tanto o meio ambiente quanto seu negócio.'
  },
  {
    icon: SparklesIcon,
    title: 'Tecnologia Avançada',
    description: 'Utilizamos as mais recentes tecnologias para otimizar processos e maximizar resultados.'
  },
  {
    icon: ShieldCheckIcon,
    title: 'Conformidade Total',
    description: 'Garantimos que seu negócio esteja em conformidade com todas as regulamentações ambientais.'
  }
]

const stats = [
  { value: '100+', label: 'Projetos Realizados' },
  { value: '95%', label: 'Clientes Satisfeitos' },
  { value: '50+', label: 'Empresas Parceiras' },
  { value: '10+', label: 'Anos de Experiência' }
]
</script>

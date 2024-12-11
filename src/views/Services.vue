<template>
  <div>
    <!-- Header Section -->
    <section class="relative py-32 animated-gradient">
      <div class="absolute inset-0 bg-black/40"></div>
      <div class="relative container mx-auto px-4">
        <div class="max-w-3xl mx-auto text-center text-white">
          <h1 class="text-5xl md:text-6xl font-bold mb-6">Nossos Serviços</h1>
          <p class="text-xl opacity-90">
            Soluções completas em consultoria ambiental para impulsionar a sustentabilidade do seu negócio
          </p>
        </div>
      </div>
      <div class="absolute bottom-0 left-0 right-0">
        <svg class="w-full h-24 text-white" viewBox="0 0 1440 74" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M0,0 C240,70 480,70 720,35 C960,0 1200,0 1440,35 L1440 74 L0 74 Z" fill="currentColor"/>
        </svg>
      </div>
    </section>

    <!-- Services Grid -->
    <section class="py-20 bg-white">
      <div class="container mx-auto px-4">
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="service in services" :key="service.id" 
               class="group relative overflow-hidden rounded-2xl shadow-lg hover-scale bg-white h-[500px]">
            <div class="aspect-w-16 aspect-h-9">
              <img :src="service.image" :alt="service.title" 
                   class="object-cover w-full h-full transform group-hover:scale-110 transition-transform duration-500">
            </div>
            <div class="absolute inset-0 bg-gradient-to-t from-green-900 via-green-900/90 to-transparent">
              <div class="absolute bottom-0 p-8 text-white w-full">
                <div class="bg-green-800/80 backdrop-blur-sm rounded-xl p-4 mb-6">
                  <div class="flex items-center gap-4">
                    <div class="p-2 bg-white/20 rounded-lg">
                      <component :is="service.icon" class="h-8 w-8" />
                    </div>
                    <h3 class="text-2xl md:text-3xl font-bold text-white">{{ service.title }}</h3>
                  </div>
                </div>
                <p class="text-white text-lg mb-6 leading-relaxed">{{ service.description }}</p>
                <button @click="openServiceModal(service)" 
                        class="inline-flex items-center px-6 py-3 text-sm font-semibold rounded-lg bg-white hover:bg-green-50 text-green-800 backdrop-blur-sm transition-all duration-300">
                  Saiba mais
                  <ArrowRightIcon class="h-4 w-4 ml-2" />
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Process Section -->
    <section class="py-20 bg-gray-50">
      <div class="container mx-auto px-4">
        <div class="text-center mb-16">
          <h2 class="section-title gradient-text mb-4">Nosso Processo</h2>
          <p class="section-subtitle">
            Uma abordagem estruturada para garantir resultados excepcionais
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div v-for="(step, index) in process" :key="index" 
               class="relative flex">
            <div class="glass-card p-8 text-center hover-scale flex-1 flex flex-col min-h-[320px]">
              <div class="flex-1 flex flex-col items-center">
                <div class="w-16 h-16 rounded-full bg-green-100 flex items-center justify-center mb-6">
                  <component :is="step.icon" class="h-8 w-8 text-green-600" />
                </div>
                <div class="text-3xl font-bold text-green-600 mb-4">{{ index + 1 }}</div>
                <h3 class="text-xl font-semibold mb-4">{{ step.title }}</h3>
                <p class="text-gray-600 flex-1">{{ step.description }}</p>
              </div>
            </div>
            <div v-if="index < process.length - 1" 
                 class="hidden lg:block absolute top-1/2 left-full w-full h-0.5 bg-green-200 transform -translate-y-1/2 z-10">
              <div class="absolute right-0 -top-1.5 w-4 h-4 rounded-full bg-green-400"></div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="relative py-20 overflow-hidden bg-white">
      <div class="container mx-auto px-4">
        <div class="max-w-4xl mx-auto">
          <div class="glass-card p-12 text-center relative overflow-hidden">
            <div class="relative z-10">
              <h2 class="text-4xl font-bold text-gray-900 mb-6">
                Pronto para começar seu projeto?
              </h2>
              <p class="text-xl text-gray-600 mb-8">
                Nossa equipe está pronta para ajudar você a alcançar seus objetivos de sustentabilidade
              </p>
              <router-link to="/contact" class="btn-primary">
                Solicitar Orçamento
                <ArrowRightIcon class="ml-2 h-5 w-5" />
              </router-link>
            </div>
            <div class="absolute top-0 left-0 w-full h-full animated-gradient opacity-10"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- Service Modal -->
    <TransitionRoot appear :show="isModalOpen" as="template">
      <Dialog as="div" @close="closeServiceModal" class="relative z-50">
        <TransitionChild
          as="template"
          enter="duration-300 ease-out"
          enter-from="opacity-0"
          enter-to="opacity-100"
          leave="duration-200 ease-in"
          leave-from="opacity-100"
          leave-to="opacity-0"
        >
          <div class="fixed inset-0 bg-black/75" />
        </TransitionChild>

        <div class="fixed inset-0 overflow-y-auto">
          <div class="flex min-h-full items-center justify-center p-4">
            <TransitionChild
              as="template"
              enter="duration-300 ease-out"
              enter-from="opacity-0 scale-95"
              enter-to="opacity-100 scale-100"
              leave="duration-200 ease-in"
              leave-from="opacity-100 scale-100"
              leave-to="opacity-0 scale-95"
            >
              <DialogPanel class="w-full max-w-2xl transform overflow-hidden rounded-2xl bg-white p-6 text-left shadow-xl transition-all">
                <div v-if="selectedService" class="space-y-4">
                  <div class="aspect-w-16 aspect-h-9 rounded-lg overflow-hidden">
                    <img :src="selectedService.image" :alt="selectedService.title" class="object-cover">
                  </div>
                  <DialogTitle as="h3" class="text-2xl font-bold leading-6 text-gray-900 flex items-center">
                    <component :is="selectedService.icon" class="h-6 w-6 mr-2 text-green-600" />
                    {{ selectedService.title }}
                  </DialogTitle>
                  <div class="text-gray-600 space-y-4">
                    <p>{{ selectedService.description }}</p>
                    <ul class="space-y-2">
                      <li v-for="(benefit, index) in selectedService.benefits" :key="index" 
                          class="flex items-start">
                        <CheckCircleIcon class="h-5 w-5 text-green-500 mr-2 mt-0.5" />
                        <span>{{ benefit }}</span>
                      </li>
                    </ul>
                  </div>
                  <div class="mt-6 flex justify-end space-x-4">
                    <button @click="closeServiceModal" 
                            class="btn-secondary">
                      Fechar
                    </button>
                    <router-link to="/contact" class="btn-primary">
                      Solicitar Serviço
                    </router-link>
                  </div>
                </div>
              </DialogPanel>
            </TransitionChild>
          </div>
        </div>
      </Dialog>
    </TransitionRoot>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { Dialog, DialogPanel, DialogTitle, TransitionChild, TransitionRoot } from '@headlessui/vue'
import { 
  ArrowRightIcon, 
  CheckCircleIcon,
  ClipboardDocumentCheckIcon,
  DocumentChartBarIcon,
  AcademicCapIcon,
  ShieldCheckIcon,
  BeakerIcon,
  BuildingOfficeIcon,
  MagnifyingGlassCircleIcon,
  ClockIcon,
  ChatBubbleBottomCenterTextIcon,
  DocumentCheckIcon
} from '@heroicons/vue/24/outline'

const services = [
  {
    id: 1,
    title: 'Licenciamento Ambiental',
    description: 'Assessoria completa em processos de licenciamento ambiental, garantindo conformidade com a legislação.',
    image: 'https://images.unsplash.com/photo-1600880292203-757bb62b4baf?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80',
    icon: ClipboardDocumentCheckIcon,
    benefits: [
      'Análise completa da documentação necessária',
      'Acompanhamento de todo o processo junto aos órgãos ambientais',
      'Elaboração de estudos técnicos',
      'Assessoria na implementação das condicionantes'
    ]
  },
  {
    id: 2,
    title: 'Gestão de Resíduos',
    description: 'Desenvolvimento e implementação de planos de gerenciamento de resíduos sólidos.',
    image: 'https://images.unsplash.com/photo-1532996122724-e3c354a0b15b?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80',
    icon: DocumentChartBarIcon,
    benefits: [
      'Diagnóstico da situação atual',
      'Elaboração de PGRS',
      'Treinamento de equipes',
      'Monitoramento e relatórios de desempenho'
    ]
  },
  {
    id: 3,
    title: 'Educação Ambiental',
    description: 'Programas de conscientização e treinamento em práticas sustentáveis.',
    image: 'https://images.unsplash.com/photo-1522202176988-66273c2fd55f?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1741&q=80',
    icon: AcademicCapIcon,
    benefits: [
      'Workshops e palestras personalizadas',
      'Material didático especializado',
      'Atividades práticas e dinâmicas',
      'Avaliação de resultados'
    ]
  },
  {
    id: 4,
    title: 'Auditoria Ambiental',
    description: 'Avaliação completa da conformidade ambiental e identificação de oportunidades de melhoria.',
    image: 'https://images.unsplash.com/photo-1454165804606-c3d57bc86b40?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80',
    icon: ShieldCheckIcon,
    benefits: [
      'Análise de conformidade legal',
      'Identificação de riscos ambientais',
      'Recomendações de melhorias',
      'Relatório detalhado com plano de ação'
    ]
  },
  {
    id: 5,
    title: 'Análises Ambientais',
    description: 'Realização de análises e monitoramento de parâmetros ambientais.',
    image: 'https://images.unsplash.com/photo-1532187863486-abf9dbad1b69?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80',
    icon: BeakerIcon,
    benefits: [
      'Análises de água, solo e ar',
      'Monitoramento de ruídos e vibrações',
      'Laudos técnicos',
      'Interpretação de resultados'
    ]
  },
  {
    id: 6,
    title: 'Consultoria ESG',
    description: 'Assessoria em práticas ambientais, sociais e de governança para empresas.',
    image: 'https://images.unsplash.com/photo-1460925895917-afdab827c52f?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1715&q=80',
    icon: BuildingOfficeIcon,
    benefits: [
      'Diagnóstico ESG',
      'Desenvolvimento de estratégias',
      'Implementação de práticas sustentáveis',
      'Relatórios de sustentabilidade'
    ]
  }
]

const process = [
  {
    icon: MagnifyingGlassCircleIcon,
    title: 'Diagnóstico',
    description: 'Análise detalhada da situação atual e necessidades específicas do cliente'
  },
  {
    icon: DocumentCheckIcon,
    title: 'Planejamento',
    description: 'Desenvolvimento de estratégias e planos de ação personalizados'
  },
  {
    icon: ChatBubbleBottomCenterTextIcon,
    title: 'Implementação',
    description: 'Execução das ações planejadas com acompanhamento constante'
  },
  {
    icon: ClockIcon,
    title: 'Monitoramento',
    description: 'Avaliação contínua dos resultados e ajustes quando necessário'
  }
]

const isModalOpen = ref(false)
const selectedService = ref(null)

const openServiceModal = (service) => {
  selectedService.value = service
  isModalOpen.value = true
}

const closeServiceModal = () => {
  isModalOpen.value = false
}
</script>

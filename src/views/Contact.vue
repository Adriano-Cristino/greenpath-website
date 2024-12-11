<template>
  <div>
    <!-- Header Section -->
    <section class="relative py-32 animated-gradient">
      <div class="absolute inset-0 bg-black/40"></div>
      <div class="relative container mx-auto px-4">
        <div class="max-w-3xl mx-auto text-center text-white">
          <h1 class="text-5xl md:text-6xl font-bold mb-6">Fale Conosco</h1>
          <p class="text-xl opacity-90">
            Estamos prontos para ajudar você a alcançar seus objetivos de sustentabilidade
          </p>
        </div>
      </div>
      <div class="absolute bottom-0 left-0 right-0">
        <svg class="w-full h-24 text-white" viewBox="0 0 1440 74" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M0,0 C240,70 480,70 720,35 C960,0 1200,0 1440,35 L1440 74 L0 74 Z" fill="currentColor"/>
        </svg>
      </div>
    </section>

    <!-- Contact Section -->
    <section class="py-20 bg-white">
      <div class="container mx-auto px-4">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16">
          <!-- Contact Info -->
          <div class="space-y-12">
            <div>
              <h2 class="text-3xl font-bold mb-6">Entre em Contato</h2>
              <p class="text-gray-600">
                Estamos aqui para responder suas dúvidas e ajudar sua empresa a implementar 
                soluções sustentáveis. Entre em contato conosco pelos canais abaixo:
              </p>
            </div>

            <div class="space-y-8">
              <div class="flex items-start space-x-4">
                <div class="flex-shrink-0">
                  <div class="p-3 bg-green-100 rounded-lg">
                    <MapPinIcon class="h-6 w-6 text-green-600" />
                  </div>
                </div>
                <div>
                  <h3 class="font-semibold text-gray-900">Endereço</h3>
                  <p class="mt-1 text-gray-600">
                    Rua Example, 123<br>
                    Bairro Centro<br>
                    São Paulo - SP
                  </p>
                </div>
              </div>

              <div class="flex items-start space-x-4">
                <div class="flex-shrink-0">
                  <div class="p-3 bg-green-100 rounded-lg">
                    <PhoneIcon class="h-6 w-6 text-green-600" />
                  </div>
                </div>
                <div>
                  <h3 class="font-semibold text-gray-900">Telefone</h3>
                  <p class="mt-1 text-gray-600">
                    +55 (11) 1234-5678<br>
                    +55 (11) 98765-4321
                  </p>
                </div>
              </div>

              <div class="flex items-start space-x-4">
                <div class="flex-shrink-0">
                  <div class="p-3 bg-green-100 rounded-lg">
                    <EnvelopeIcon class="h-6 w-6 text-green-600" />
                  </div>
                </div>
                <div>
                  <h3 class="font-semibold text-gray-900">Email</h3>
                  <p class="mt-1 text-gray-600">
                    contato@greenpathconsultoria.com.br<br>
                    comercial@greenpathconsultoria.com.br
                  </p>
                </div>
              </div>

              <div class="flex items-start space-x-4">
                <div class="flex-shrink-0">
                  <div class="p-3 bg-green-100 rounded-lg">
                    <ClockIcon class="h-6 w-6 text-green-600" />
                  </div>
                </div>
                <div>
                  <h3 class="font-semibold text-gray-900">Horário de Atendimento</h3>
                  <p class="mt-1 text-gray-600">
                    Segunda a Sexta: 9h às 18h<br>
                    Sábado: 9h às 13h
                  </p>
                </div>
              </div>
            </div>

            <!-- Social Media -->
            <div>
              <h3 class="font-semibold text-gray-900 mb-4">Siga-nos nas Redes Sociais</h3>
              <div class="flex space-x-4">
                <a href="#" class="p-3 bg-green-100 rounded-lg hover:bg-green-200 transition-colors">
                  <svg class="h-6 w-6 text-green-600" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M8.29 20.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0022 5.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.072 4.072 0 012.8 9.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 012 18.407a11.616 11.616 0 006.29 1.84" />
                  </svg>
                </a>
                <a href="#" class="p-3 bg-green-100 rounded-lg hover:bg-green-200 transition-colors">
                  <svg class="h-6 w-6 text-green-600" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M12.315 2c2.43 0 2.784.013 3.808.06 1.064.049 1.791.218 2.427.465a4.902 4.902 0 011.772 1.153 4.902 4.902 0 011.153 1.772c.247.636.416 1.363.465 2.427.048 1.067.06 1.407.06 4.123v.08c0 2.643-.012 2.987-.06 4.043-.049 1.064-.218 1.791-.465 2.427a4.902 4.902 0 01-1.153 1.772 4.902 4.902 0 01-1.772 1.153c-.636.247-1.363.416-2.427.465-1.067.048-1.407.06-4.123.06h-.08c-2.643 0-2.987-.012-4.043-.06-1.064-.049-1.791-.218-2.427-.465a4.902 4.902 0 01-1.772-1.153 4.902 4.902 0 01-1.153-1.772c-.247-.636-.416-1.363-.465-2.427-.047-1.024-.06-1.379-.06-3.808v-.63c0-2.43.013-2.784.06-3.808.049-1.064.218-1.791.465-2.427a4.902 4.902 0 011.153-1.772A4.902 4.902 0 015.45 2.525c.636-.247 1.363-.416 2.427-.465C8.901 2.013 9.256 2 11.685 2h.63zm-.081 1.802h-.468c-2.456 0-2.784.011-3.807.058-.975.045-1.504.207-1.857.344-.467.182-.8.398-1.15.748-.35.35-.566.683-.748 1.15-.137.353-.3.882-.344 1.857-.047 1.023-.058 1.351-.058 3.807v.468c0 2.456.011 2.784.058 3.807.045.975.207 1.504.344 1.857.182.466.399.8.748 1.15.35.35.683.566 1.15.748.353.137.882.3 1.857.344 1.054.048 1.37.058 4.041.058h.08c2.597 0 2.917-.01 3.96-.058.976-.045 1.505-.207 1.858-.344.466-.182.8-.398 1.15-.748.35-.35.566-.683.748-1.15.137-.353.3-.882.344-1.857.048-1.055.058-1.37.058-4.041v-.08c0-2.597-.01-2.917-.058-3.96-.045-.976-.207-1.505-.344-1.858a3.097 3.097 0 00-.748-1.15 3.098 3.098 0 00-1.15-.748c-.353-.137-.882-.3-1.857-.344-1.023-.047-1.351-.058-3.807-.058zM12 6.865a5.135 5.135 0 110 10.27 5.135 5.135 0 010-10.27zm0 1.802a3.333 3.333 0 100 6.666 3.333 3.333 0 000-6.666zm5.338-3.205a1.2 1.2 0 110 2.4 1.2 1.2 0 010-2.4z" />
                  </svg>
                </a>
                <a href="#" class="p-3 bg-green-100 rounded-lg hover:bg-green-200 transition-colors">
                  <svg class="h-6 w-6 text-green-600" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M8.29 20.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0022 5.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.072 4.072 0 012.8 9.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 012 18.407a11.616 11.616 0 006.29 1.84" />
                  </svg>
                </a>
                <a href="#" class="p-3 bg-green-100 rounded-lg hover:bg-green-200 transition-colors">
                  <svg class="h-6 w-6 text-green-600" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z" />
                  </svg>
                </a>
              </div>
            </div>
          </div>

          <!-- Contact Form -->
          <div class="glass-card p-8">
            <form @submit.prevent="handleSubmit" class="space-y-6">
              <div>
                <label for="name" class="block text-sm font-medium text-gray-700">Nome</label>
                <input type="text" id="name" v-model="form.name" required
                       class="input-field">
              </div>

              <div>
                <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
                <input type="email" id="email" v-model="form.email" required
                       class="input-field">
              </div>

              <div>
                <label for="phone" class="block text-sm font-medium text-gray-700">Telefone</label>
                <input type="tel" id="phone" v-model="form.phone" required
                       class="input-field">
              </div>

              <div>
                <label for="subject" class="block text-sm font-medium text-gray-700">Assunto</label>
                <select id="subject" v-model="form.subject" required
                        class="input-field">
                  <option value="">Selecione um assunto</option>
                  <option v-for="subject in subjects" :key="subject" :value="subject">
                    {{ subject }}
                  </option>
                </select>
              </div>

              <div>
                <label for="message" class="block text-sm font-medium text-gray-700">Mensagem</label>
                <textarea id="message" v-model="form.message" rows="4" required
                          class="input-field"></textarea>
              </div>

              <div class="flex items-center">
                <input type="checkbox" id="privacy" v-model="form.privacy" required
                       class="h-4 w-4 text-green-600 focus:ring-green-500 border-gray-300 rounded">
                <label for="privacy" class="ml-2 block text-sm text-gray-700">
                  Concordo com a <a href="#" class="text-green-600 hover:text-green-500">Política de Privacidade</a>
                </label>
              </div>

              <div>
                <button type="submit" 
                        class="w-full btn-primary flex justify-center">
                  <span v-if="loading" class="animate-spin mr-2">
                    <svg class="h-5 w-5" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                      <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                      <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                    </svg>
                  </span>
                  Enviar Mensagem
                </button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </section>

    <!-- Map Section -->
    <section class="py-20 bg-gray-50">
      <div class="container mx-auto px-4">
        <div class="max-w-4xl mx-auto">
          <div class="aspect-w-16 aspect-h-9 rounded-2xl overflow-hidden shadow-lg">
            <iframe 
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3657.1975829726973!2d-46.65429492375831!3d-23.56334646162707!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94ce59c8da0aa315%3A0x63b9f907f81346c1!2sAv.%20Paulista%2C%20S%C3%A3o%20Paulo%20-%20SP!5e0!3m2!1spt-BR!2sbr!4v1687456892154!5m2!1spt-BR!2sbr"
              width="100%"
              height="100%"
              style="border:0;"
              allowfullscreen=""
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade">
            </iframe>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
import { MapPinIcon, PhoneIcon, EnvelopeIcon, ClockIcon } from '@heroicons/vue/24/outline'

const subjects = [
  'Licenciamento Ambiental',
  'Gestão de Resíduos',
  'Educação Ambiental',
  'Auditoria Ambiental',
  'Análises Ambientais',
  'Consultoria ESG',
  'Outros'
]

const form = reactive({
  name: '',
  email: '',
  phone: '',
  subject: '',
  message: '',
  privacy: false
})

const loading = ref(false)

const handleSubmit = async () => {
  loading.value = true
  try {
    // Simular envio do formulário
    await new Promise(resolve => setTimeout(resolve, 2000))
    alert('Mensagem enviada com sucesso!')
    // Limpar formulário
    Object.keys(form).forEach(key => {
      if (key === 'privacy') {
        form[key] = false
      } else {
        form[key] = ''
      }
    })
  } catch (error) {
    alert('Erro ao enviar mensagem. Tente novamente.')
  } finally {
    loading.value = false
  }
}
</script>

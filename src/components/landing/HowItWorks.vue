<script setup>
import { Upload, Brain, FileCheck } from 'lucide-vue-next'

const steps = [
  {
    icon: Upload,
    step: '01',
    title: 'Uploadez vos photos',
    description: 'Prenez 1 à 3 photos de votre peau en lumière naturelle et uploadez-les sur notre plateforme sécurisée.',
    color: 'from-blue-500 to-blue-600'
  },
  {
    icon: Brain,
    step: '02',
    title: "L'IA analyse votre peau",
    description: 'Notre intelligence artificielle examine la texture, les imperfections, les rougeurs et le grain de votre peau.',
    color: 'from-primary-500 to-primary-600'
  },
  {
    icon: FileCheck,
    step: '03',
    title: 'Obtenez votre diagnostic',
    description: 'Recevez un diagnostic complet avec des conseils personnalisés et des recommandations de produits adaptés.',
    color: 'from-green-500 to-green-600'
  }
]
</script>

<template>
  <section id="comment-ca-marche" class="py-20 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl sm:text-4xl font-bold text-gray-900">
          Comment ça marche ?
        </h2>
        <p class="mt-4 text-lg text-gray-600 max-w-2xl mx-auto">
          Un diagnostic complet en 3 étapes simples, en moins d'une minute.
        </p>
      </div>

      <div class="grid md:grid-cols-3 gap-8 lg:gap-12">
        <div
          v-for="(item, i) in steps"
          :key="i"
          class="relative text-center group"
        >
          <!-- Connector line -->
          <div
            v-if="i < steps.length - 1"
            class="hidden md:block absolute top-12 left-[60%] w-[80%] h-0.5 bg-gray-200"
          ></div>

          <div class="relative z-10">
            <div :class="['w-24 h-24 rounded-3xl bg-gradient-to-br flex items-center justify-center mx-auto mb-6 shadow-lg group-hover:scale-105 transition-transform duration-300', item.color]">
              <component :is="item.icon" class="w-10 h-10 text-white" />
            </div>
            <span class="text-xs font-bold text-primary-500 uppercase tracking-widest">Étape {{ item.step }}</span>
            <h3 class="text-xl font-bold text-gray-900 mt-2 mb-3">{{ item.title }}</h3>
            <p class="text-sm text-gray-600 leading-relaxed max-w-xs mx-auto">{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

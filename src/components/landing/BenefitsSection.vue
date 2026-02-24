<script setup>
import { Microscope, Heart, ShoppingBag, Zap } from 'lucide-vue-next'

const benefits = [
  {
    icon: Microscope,
    title: 'Diagnostic précis',
    description: 'Notre IA analyse votre peau en détail et identifie les problèmes cutanés avec précision.',
    color: 'bg-blue-50 text-blue-500'
  },
  {
    icon: Heart,
    title: 'Conseils personnalisés',
    description: 'Des recommandations adaptées à votre type de peau, vos habitudes et votre mode de vie.',
    color: 'bg-green-50 text-green-500'
  },
  {
    icon: ShoppingBag,
    title: 'Produits adaptés',
    description: 'Les meilleurs ingrédients actifs recommandés pour chaque problème identifié.',
    color: 'bg-orange-50 text-orange-500'
  },
  {
    icon: Zap,
    title: 'Rapide et gratuit',
    description: 'Obtenez votre diagnostic complet en quelques secondes, sans inscription obligatoire.',
    color: 'bg-purple-50 text-purple-500'
  }
]
</script>

<template>
  <section class="py-20 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl sm:text-4xl font-bold text-gray-900">
          Pourquoi choisir <span class="text-primary-500">SkinAI</span> ?
        </h2>
        <p class="mt-4 text-lg text-gray-600 max-w-2xl mx-auto">
          Une technologie de pointe au service de votre peau, accessible à tous.
        </p>
      </div>

      <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-8">
        <div
          v-for="(benefit, i) in benefits"
          :key="i"
          class="group text-center p-6 rounded-2xl hover:shadow-lg transition-all duration-300 hover:-translate-y-1"
        >
          <div :class="['w-14 h-14 rounded-2xl flex items-center justify-center mx-auto mb-5', benefit.color]">
            <component :is="benefit.icon" class="w-7 h-7" />
          </div>
          <h3 class="text-lg font-semibold text-gray-900 mb-2">{{ benefit.title }}</h3>
          <p class="text-sm text-gray-600 leading-relaxed">{{ benefit.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

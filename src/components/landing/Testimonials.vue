<script setup>
import { Star } from 'lucide-vue-next'

const testimonials = [
  {
    name: 'Karim B.',
    role: 'Utilisateur depuis 3 mois',
    rating: 5,
    text: "J'avais des problèmes de poils incarnés depuis des années. SkinAI m'a recommandé les bons produits et une routine adaptée. En 2 mois, ma peau est transformée !",
    avatar: 'K'
  },
  {
    name: 'Sophie M.',
    role: 'Utilisatrice Premium',
    rating: 5,
    text: "Impressionnant ! L'IA a identifié exactement les mêmes problèmes que mon dermatologue. Les conseils sont concrets et faciles à suivre au quotidien.",
    avatar: 'S'
  },
  {
    name: 'Thomas L.',
    role: 'Utilisateur depuis 1 mois',
    rating: 4,
    text: 'Super outil pour comprendre sa peau. Les recommandations de produits sont pertinentes, avec les bons ingrédients actifs. Je recommande vivement.',
    avatar: 'T'
  },
  {
    name: 'Amina R.',
    role: 'Utilisatrice Premium',
    rating: 5,
    text: "En tant que femme à la peau foncée, j'avais du mal à trouver des solutions pour l'hyperpigmentation. SkinAI m'a guidée efficacement avec des conseils adaptés.",
    avatar: 'A'
  }
]
</script>

<template>
  <section class="py-20 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl sm:text-4xl font-bold text-gray-900">
          Ils ont testé <span class="text-primary-500">SkinAI</span>
        </h2>
        <p class="mt-4 text-lg text-gray-600 max-w-2xl mx-auto">
          Découvrez les retours de nos utilisateurs satisfaits.
        </p>
      </div>

      <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
        <div
          v-for="(testimonial, i) in testimonials"
          :key="i"
          class="bg-gray-50 rounded-2xl p-6 hover:shadow-md transition-shadow duration-300"
        >
          <!-- Avatar & Info -->
          <div class="flex items-center gap-3 mb-4">
            <div class="w-10 h-10 rounded-full bg-primary-100 text-primary-600 flex items-center justify-center font-bold text-sm">
              {{ testimonial.avatar }}
            </div>
            <div>
              <p class="text-sm font-semibold text-gray-900">{{ testimonial.name }}</p>
              <p class="text-xs text-gray-500">{{ testimonial.role }}</p>
            </div>
          </div>

          <!-- Stars -->
          <div class="flex gap-0.5 mb-3">
            <Star
              v-for="s in 5"
              :key="s"
              class="w-4 h-4"
              :class="s <= testimonial.rating ? 'text-yellow-400 fill-yellow-400' : 'text-gray-300'"
            />
          </div>

          <!-- Text -->
          <p class="text-sm text-gray-600 leading-relaxed">{{ testimonial.text }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import { ChevronDown } from 'lucide-vue-next'

const faqs = [
  {
    question: 'SkinAI peut-il remplacer une consultation chez le dermatologue ?',
    answer: 'Non. SkinAI est un outil d\'aide à l\'analyse cutanée basé sur l\'intelligence artificielle. Il fournit des indications et des conseils généraux, mais ne remplace en aucun cas l\'avis d\'un dermatologue ou d\'un professionnel de santé qualifié. En cas de problème persistant ou sévère, consultez un médecin.'
  },
  {
    question: 'Mes photos sont-elles conservées ou partagées ?',
    answer: 'Non. Vos photos sont analysées en temps réel et ne sont jamais stockées sur nos serveurs. Elles sont envoyées de manière sécurisée à notre IA pour analyse, puis immédiatement supprimées après traitement. Votre confidentialité est notre priorité.'
  },
  {
    question: 'Comment prendre de bonnes photos pour un diagnostic optimal ?',
    answer: 'Pour obtenir les meilleurs résultats, prenez vos photos en lumière naturelle, sans flash. Assurez-vous que la zone de peau est bien visible et nette. Évitez les photos trop sombres, floues ou prises de trop loin. Si les photos ne sont pas suffisantes, l\'IA vous posera des questions complémentaires.'
  },
  {
    question: 'Combien de diagnostics gratuits ai-je droit ?',
    answer: 'Vous bénéficiez de 3 diagnostics gratuits par mois, sans inscription. Pour un accès illimité ainsi que des fonctionnalités avancées comme l\'historique et le suivi de progression, vous pouvez passer au plan Premium à 9,90€/mois.'
  },
  {
    question: 'L\'IA est-elle fiable pour tous les types de peau ?',
    answer: 'Notre IA a été entraînée sur une grande diversité de types de peau (claires, mates, foncées) et de problématiques cutanées. Cependant, comme tout outil technologique, elle peut avoir des limites selon la qualité des photos et la complexité du problème. Les résultats sont fournis à titre indicatif.'
  },
  {
    question: 'Les produits recommandés sont-ils sponsorisés ?',
    answer: 'Non. SkinAI recommande des types de produits et des ingrédients actifs génériques, sans citer de marques spécifiques. Nos recommandations sont basées uniquement sur l\'efficacité prouvée des ingrédients pour les problèmes identifiés, sans aucun partenariat commercial.'
  }
]

const openIndex = ref(null)

const toggle = (index) => {
  openIndex.value = openIndex.value === index ? null : index
}
</script>

<template>
  <section class="py-20 bg-white">
    <div class="max-w-3xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl sm:text-4xl font-bold text-gray-900">
          Questions fréquentes
        </h2>
        <p class="mt-4 text-lg text-gray-600">
          Tout ce que vous devez savoir sur SkinAI.
        </p>
      </div>

      <div class="space-y-3">
        <div
          v-for="(faq, i) in faqs"
          :key="i"
          class="border border-gray-200 rounded-xl overflow-hidden transition-all duration-200"
          :class="openIndex === i ? 'shadow-md' : ''"
        >
          <button
            @click="toggle(i)"
            class="w-full px-6 py-4 flex items-center justify-between text-left hover:bg-gray-50 transition-colors"
          >
            <span class="text-sm font-medium text-gray-900 pr-4">{{ faq.question }}</span>
            <ChevronDown
              class="w-5 h-5 text-gray-400 flex-shrink-0 transition-transform duration-200"
              :class="openIndex === i ? 'rotate-180' : ''"
            />
          </button>

          <Transition
            enter-active-class="transition duration-200 ease-out"
            enter-from-class="opacity-0 max-h-0"
            enter-to-class="opacity-100 max-h-96"
            leave-active-class="transition duration-150 ease-in"
            leave-from-class="opacity-100 max-h-96"
            leave-to-class="opacity-0 max-h-0"
          >
            <div v-if="openIndex === i" class="px-6 pb-4">
              <p class="text-sm text-gray-600 leading-relaxed">{{ faq.answer }}</p>
            </div>
          </Transition>
        </div>
      </div>
    </div>
  </section>
</template>

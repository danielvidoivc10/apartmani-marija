<template>
  <section id="faq" class="py-24 bg-[#fdfbf9]">
    <div class="max-w-3xl mx-auto px-6">
      
      <div class="text-center mb-20">
        <h2 class="text-4xl font-serif font-bold text-[#402507] uppercase tracking-[0.2em] mb-4">Česta pitanja</h2>
        <div class="w-20 h-1 bg-[#926934] mx-auto"></div>
      </div>

      <div class="space-y-8">
        <div 
          v-for="(item, index) in pitanja" 
          :key="index"
          class="border border-[#dcccb8]/50 rounded-4xl overflow-hidden transition-all duration-300 bg-white shadow-md hover:shadow-lg"
        >
          <button 
            @click="toggle(index)"
            class="w-full flex items-center justify-between p-7 md:p-9 text-left transition-colors hover:bg-[#fcfaf7]"
          >
            <span class="text-xl font-bold text-[#402507] pr-4 leading-tight">{{ item.pitanje }}</span>
            
            <div class="shrink-0 bg-[#f4f1ee] p-2 rounded-full">
              <svg 
                class="w-5 h-5 text-[#926934] transform transition-transform duration-500"
                :class="{ 'rotate-180': otvoreno === index }"
                fill="none" 
                stroke="currentColor" 
                viewBox="0 0 24 24"
              >
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
              </svg>
            </div>
          </button>

          <div 
            v-show="otvoreno === index"
            class="px-8 md:px-10 pb-10 text-gray-600 text-lg leading-relaxed"
          >
            <div class="h-px bg-[#f4f1ee] mb-8"></div>
            {{ item.odgovor }}
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const otvoreno = ref(null)

const toggle = (index) => {
  otvoreno.value = otvoreno.value === index ? null : index
}

const pitanja = [
  {
    pitanje: "U koliko sati je prijava (Check-in) i odjava (Check-out)?",
    odgovor: "Prijava u apartmane je od 14:00 sati, a odjava je do 10:00 sati ujutro. Ukoliko vam je potrebna ranija prijava, molimo da nas kontaktirate unaprijed."
  },
  {
    pitanje: "Je li osiguran parking za goste?",
    odgovor: "Da, svim našim gostima osiguran je besplatan, privatan i siguran parking u sklopu objekta koji nije potrebno unaprijed rezervirati."
  },
  {
    pitanje: "Nudite li besplatan WiFi?",
    odgovor: "Naravno! Cijeli objekt je pokriven besplatnim brzim optičkim internetom koji je dostupan u svim sobama i na terasama."
  },
  {
    pitanje: "Koliko su apartmani udaljeni od centra?",
    odgovor: "Naši apartmani se nalaze na izvrsnoj lokaciji, samo par minuta lagane šetnje od glavnih sadržaja, ali dovoljno povučeni da uživate u miru i tišini."
  },
  {
    pitanje: "Dozvoljavate li boravak kućnim ljubimcima?",
    odgovor: "Kako bismo osigurali maksimalnu čistoću za sve naše goste, nažalost ne dopuštamo boravak kućnim ljubimcima."
  }
]
</script>

<style scoped>

</style>
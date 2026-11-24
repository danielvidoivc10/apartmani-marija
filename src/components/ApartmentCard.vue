<template>
  <div class="bg-white rounded-[2.5rem] shadow-xl overflow-hidden border border-gray-100 transition-all duration-500 hover:-translate-y-3 hover:shadow-2xl flex flex-col h-full">
    
    <div class="relative overflow-hidden group h-80 cursor-pointer" @click="$emit('otvori-galeriju', tip)">
      <img 
        :src="slika" 
        :alt="naslov" 
        class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110"
      >
      <div class="absolute inset-0 bg-black/20 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
        <span class="bg-white/20 backdrop-blur-md text-white px-4 py-2 rounded-full border border-white/30 text-xs font-bold uppercase tracking-widest">
          Pogledaj slike 📸
        </span>
      </div>
    </div>
    
    <div class="p-8 flex flex-col grow text-center">
      <h3 class="text-3xl font-serif font-bold text-[#402507] mb-3 uppercase tracking-tight">
        {{ naslov }}
      </h3>
      
      <p class="text-gray-500 mb-8 italic text-sm px-4">
        Uživajte u luksuzu i udobnosti našeg {{ naslov.toLowerCase() }}.
      </p>
      
      <div class="flex flex-wrap justify-center gap-2 mb-10 mt-auto">
        <span v-for="tag in karakteristike" :key="tag" 
              class="bg-[#f4f1ee] text-[#926934] text-[10px] font-bold px-4 py-2 rounded-xl uppercase tracking-wider">
          {{ tag }}
        </span>
      </div>
      
      <button 
        @click="posaljiUpit" 
        class="group relative overflow-hidden w-full py-4 bg-[#926934] text-white rounded-2xl font-bold uppercase tracking-[0.2em] text-xs transition-all duration-300 shadow-lg active:scale-95"
      >
        <div class="absolute inset-0 bg-linear-to-tr from-transparent via-white/20 to-white/40 opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
        <span class="relative z-10">Rezerviraj</span>
      </button>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  naslov: String,
  slika: String,
  tip: String,
  karakteristike: Array
});


const emit = defineEmits(['otvori-galeriju']);

const posaljiUpit = () => {
  const brojMobitela = '38763382331'; 
  const poruka = `Pozdrav! Želim rezervirati ${props.naslov}. Molim vas info o dostupnosti.`;
  window.open(`https://wa.me/${brojMobitela}?text=${encodeURIComponent(poruka)}`, '_blank');
};
</script>
<template>
  <section id="rezervacija" class="py-12 px-6 bg-[#f4f1ee]">
    <div class="max-w-7xl mx-auto bg-white p-6 md:p-8 rounded-4xl shadow-2xl -mt-24 relative z-20">
      <div class="grid grid-cols-1 md:grid-cols-5 gap-4 items-end">
        
        <div class="flex flex-col gap-1.5">
          <label class="text-[#402507] font-bold uppercase text-[10px] tracking-widest ml-2">Apartman</label>
          <select v-model="odabraniApartman" class="w-full p-3 bg-gray-50 border-none rounded-xl focus:ring-2 focus:ring-[#926934] outline-none text-gray-600 text-sm appearance-none cursor-pointer">
            <option value="Delux Apartman">Delux Apartman</option>
            <option value="Superior Apartman">Superior Apartman</option>
          </select>
        </div>

        <div class="flex flex-col gap-1.5">
          <label class="text-[#402507] font-bold uppercase text-[10px] tracking-widest ml-2">Dolazak</label>
          <input v-model="dolazak" type="date" class="w-full p-3 bg-gray-50 border-none rounded-xl focus:ring-2 focus:ring-[#926934] outline-none text-gray-600 text-sm cursor-pointer">
        </div>

        <div class="flex flex-col gap-1.5">
          <label class="text-[#402507] font-bold uppercase text-[10px] tracking-widest ml-2">Odlazak</label>
          <input v-model="odlazak" type="date" class="w-full p-3 bg-gray-50 border-none rounded-xl focus:ring-2 focus:ring-[#926934] outline-none text-gray-600 text-sm cursor-pointer">
        </div>

        <div class="flex flex-col gap-1.5">
          <label class="text-[#402507] font-bold uppercase text-[10px] tracking-widest ml-2">Gosti</label>
          <select v-model="gosti" class="w-full p-3 bg-gray-50 border-none rounded-xl focus:ring-2 focus:ring-[#926934] outline-none text-gray-600 text-sm appearance-none cursor-pointer">
            <option value="1">1 Osoba</option>
            <option value="2">2 Osobe</option>
            <option value="3">3 Osobe</option>
            <option value="4">4 Osobe</option>
            <option value="5">5 Osoba</option>
            <option value="6">6 Osoba</option>
          </select>
        </div>

        <button 
          @click="posaljiRezervaciju"
          class="w-full bg-[#926934] text-white p-4 rounded-xl font-bold uppercase text-xs tracking-widest hover:bg-[#926934] transition-all duration-300 shadow-lg active:scale-95"
        >
          Rezerviraj
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const odabraniApartman = ref('Delux Apartman');
const dolazak = ref('');
const odlazak = ref('');
const gosti = ref('1');

const posaljiRezervaciju = () => {

  const brojMobitela = '38763382331'; 
  
  const poruka = `Pozdrav! Želim rezervirati smještaj:
🏨 Apartman: ${odabraniApartman.value}
📅 Dolazak: ${dolazak.value || 'Nije odabrano'}
📅 Odlazak: ${odlazak.value || 'Nije odabrano'}
👥 Broj osoba: ${gosti.value}`;

  const url = `https://wa.me/${brojMobitela}?text=${encodeURIComponent(poruka)}`;
  window.open(url, '_blank');
};
</script>
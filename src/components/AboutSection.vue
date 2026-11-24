<template>
  <section class="py-24 bg-white overflow-hidden">
    <div class="max-w-6xl mx-auto px-6">
      <div class="flex flex-col md:flex-row items-center gap-16">
        
        <div class="md:w-1/2">
          <h2 class="text-[#926934] uppercase tracking-[0.3em] text-sm font-bold mb-4">Dobrodošli</h2>
          <h3 class="text-4xl md:text-5xl font-serif font-bold text-[#402507] mb-8 leading-tight">
            Apartmani Marija – Vaša mirna luka u Međugorju
          </h3>
          <p class="text-gray-600 text-lg leading-relaxed mb-8 italic font-light">
            "Apartmani Marija su više od smještaja – oni su vaša mirna luka u Međugorju. Bilo da dolazite tražiti duhovni mir ili istraživati ljepote Hercegovine, naši luksuzni apartmani (Deluxe i Superior) pružaju vam privatnost i udobnost kakvu zaslužujete."
          </p>
          
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mt-10">
            <div class="bg-[#fcfaf7] border border-[#dcccb8]/50 p-6 rounded-2xl shadow-sm">
              <span class="block text-[#926934] font-black uppercase text-[10px] mb-2 tracking-widest">Transport</span>
              <p class="text-sm text-[#402507] leading-relaxed">
                Mostar (25 km)<br>
                Split (140 km)
              </p>
            </div>
            <div class="bg-[#fcfaf7] border border-[#dcccb8]/50 p-6 rounded-2xl shadow-sm">
              <span class="block text-[#926934] font-black uppercase text-[10px] mb-2 tracking-widest">Parking</span>
              <p class="text-sm text-[#402507] leading-relaxed">
                Besplatan privatni parking osiguran za sve goste.
              </p>
            </div>
          </div>
        </div>

        <div class="md:w-1/2 relative">
          <div class="absolute -inset-4 border-2 border-[#dcccb8] rounded-[3rem] translate-x-4 translate-y-4 opacity-40"></div>
          <img 
            :src="slika" 
            alt="Međugorje" 
            class="relative z-10 rounded-[2.5rem] shadow-2xl object-cover h-125 w-full"
          />
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
const slika = new URL('../assets/deluxe slike/IMG_1080.jpeg.jpg', import.meta.url).href
</script>
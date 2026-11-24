<template>
  <TheNavbar />
  <HeroSection />
  <BookingSearch />
  <AboutSection />



  <section class="py-20 bg-[#dcccb8] text-[#926934] text-center">
    <h3 class="text-4xl font-serif font-bold mb-6">U ponudi</h3>
    <p class="max-w-2xl mx-auto text-lg px-6 leading-relaxed">
      Apartman Deluxe odlikuje se elegantnim interijerom, prostranim sobama i modernom opremom, savršen za goste koji žele dodatnu razinu udobnosti. Apartman Superior nudi vrhunsku funkcionalnost i stil, s pažljivo osmišljenim prostorom za opuštanje i boravak do više osoba.
    </p>
  </section>

  <div id="apartmani" class="py-20 bg-white">
    <h2 class="text-4xl font-serif font-bold text-[#402507] text-center mb-16 uppercase tracking-widest">
      Naši apartmani
    </h2>

    <div class="max-w-6xl mx-auto px-6 grid grid-cols-1 md:grid-cols-2 gap-12">
      <ApartmentCard 
        naslov="Apartman Deluxe"
        :slika="imgDeluxe"
        tip="deluxe"
        :karakteristike="['🛏️ 2 Sobe', '🚿 Kupaonica', '📺 WiFi', '👥 6 osoba']"
        @otvori-galeriju="otvoriGalerijuZa" 
      />

      <ApartmentCard 
        naslov="Apartman Superior"
        :slika="imgSuperior"
        tip="superior"
        :karakteristike="['🛏️ 2 Sobe', '🚿 2 Kupaonice', '📺 WiFi', '👥 6 osoba']"
        @otvori-galeriju="otvoriGalerijuZa" 
      />
    </div>
  </div>

  <FAQSection />

  <div id="lokacija" class="w-[85%] mx-auto my-20">
    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2166.329730915363!2d17.669068765206987!3d43.19996166578806!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x134b6d4a5ce2e91f%3A0x1609e03d6ee5a2a!2sApartman%20Marija!5e0!3m2!1shr!2sba!4v1770995435258!5m2!1shr!2sba" width="100%" height="450" style="border:0; border-radius: 2rem;" allowfullscreen="" loading="lazy"></iframe>
  </div>

  <WeatherWidget />
  <TheFooter />

  <GalleryModal 
    :isOpen="galerijaOtvorena" 
    :currentImage="aktivneSlike[trenutniIndeks]?.src" 
    :currentIndex="trenutniIndeks"
    :totalImages="aktivneSlike.length"
    @close="galerijaOtvorena = false" 
    @next="sljedecaSlika"
    @prev="prethodnaSlika"
  />
</template>

<script setup>
import { ref } from 'vue'
import TheNavbar from './components/TheNavbar.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import BookingSearch from './components/BookingSearch.vue'
import ApartmentCard from './components/ApartmentCard.vue'
import FAQSection from './components/FAQSection.vue'
import TheFooter from './components/TheFooter.vue'
import GalleryModal from './components/GalleryModal.vue'
import WeatherWidget from './components/WeatherWidget.vue'

const imgDeluxe = new URL('./assets/deluxe slike/IMG_0867.jpeg.jpg', import.meta.url).href
const imgSuperior = new URL('./assets/deluxe slike/IMG_1026.jpeg.jpg', import.meta.url).href


const galerijaOtvorena = ref(false)
const aktivneSlike = ref([])
const trenutniIndeks = ref(0) 


const slikeDeluxe = [
  { src: new URL('./assets/deluxe slike/IMG_0867.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0874.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0845.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0851.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0859.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0925.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0908.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0914.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0919.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0888.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0955.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_1080.jpeg.jpg', import.meta.url).href },
]

const slikeSuperior = [
  { src: new URL('./assets/deluxe slike/IMG_1026.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0998.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0991.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_1006.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_1016.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_1042.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0980.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_1045.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_1049.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0966.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0968.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_1077.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_0955.jpeg.jpg', import.meta.url).href },
  { src: new URL('./assets/deluxe slike/IMG_1080.jpeg.jpg', import.meta.url).href },

]


const otvoriGalerijuZa = (tip) => {
  trenutniIndeks.value = 0
  if (tip === 'deluxe') {
    aktivneSlike.value = slikeDeluxe
  } else {
    aktivneSlike.value = slikeSuperior
  }
  galerijaOtvorena.value = true
}


const sljedecaSlika = () => {
  if (trenutniIndeks.value < aktivneSlike.value.length - 1) {
    trenutniIndeks.value++
  } else {
    trenutniIndeks.value = 0
  }
}

const prethodnaSlika = () => {
  if (trenutniIndeks.value > 0) {
    trenutniIndeks.value--
  } else {
    trenutniIndeks.value = aktivneSlike.value.length - 1
  }
}
</script>

<style>
:global(html) { scroll-behavior: smooth; font-family: 'Inter', sans-serif; }
section[id], div[id] { scroll-margin-top: 100px; }
#rezervacija {
  scroll-margin-top: 250px !important;
}
</style>
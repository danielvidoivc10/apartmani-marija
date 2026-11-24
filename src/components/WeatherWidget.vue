<template>
  <div v-if="weatherData" class="max-w-xl mx-auto my-10 p-6 bg-[#fcfaf7] border border-[#dcccb8] rounded-3xl text-center shadow-sm">
    <h4 class="text-[#926934] font-bold uppercase text-xs tracking-widest mb-2">Trenutno u Međugorju</h4>
    <div class="text-3xl font-serif font-bold text-[#402507] mb-2">
      {{ weatherData.temperature }}°C
    </div>
    <p class="text-gray-600 italic">{{ weatherMessage }}</p>
  </div>
</template>

<script setup>
import { ref, onMounted, computed } from 'vue'

const weatherData = ref(null)


const fetchWeather = async () => {
  try {
    const response = await fetch('https://api.open-meteo.com/v1/forecast?latitude=43.19&longitude=17.67&current_weather=true')
    const data = await response.json()
    weatherData.value = data.current_weather
  } catch (error) {
    console.error("Greška pri dohvatu vremena:", error)
  }
}


onMounted(() => {
  fetchWeather()
})


const weatherMessage = computed(() => {
  if (!weatherData.value) return ""
  const temp = weatherData.value.temperature
  

  if (temp > 25) return "Savršeno sunčano vrijeme za posjet Brdu Ukazanja! ☀️"
  if (temp > 15) return "Ugodno vrijeme za šetnju i molitvu. 🌤️"
  return "Malo je svježije, ponesite topliju odjeću. ☁️"
})
</script>
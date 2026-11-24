<template>
  <Transition name="fade">
    <div 
      v-if="isOpen" 
      class="fixed inset-0 z-3000 flex items-center justify-center bg-black/95 backdrop-blur-md p-4"
      @click.self="$emit('close')"
    >
      
      <button 
        @click="$emit('close')" 
        class="absolute top-6 right-6 text-white/50 hover:text-white transition-all hover:rotate-90 duration-300 z-3001"
      >
        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>

      <div class="relative w-full max-w-5xl flex items-center justify-center">
        
        <button 
          @click="$emit('prev')" 
          class="absolute left-2 md:-left-20 bg-white/5 hover:bg-white/10 text-white p-4 rounded-full border border-white/10 transition-all group active:scale-90 z-3002"
        >
          <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 group-hover:-translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
          </svg>
        </button>

        <div class="relative group">
          <img 
            :src="currentImage" 
            class="max-h-[80vh] w-auto rounded-2xl shadow-[0_0_50px_rgba(0,0,0,0.8)] border border-white/10 object-contain select-none"
            alt="Galerija apartmana"
          />
          
          <div class="absolute -bottom-12 left-1/2 -translate-x-1/2 bg-[#926934]/20 backdrop-blur-md text-[#926934] border border-[#926934]/30 px-6 py-1 rounded-full text-xs font-bold tracking-[0.2em] uppercase">
            Slika {{ currentIndex + 1 }} / {{ totalImages }}
          </div>
        </div>

        <button 
          @click="$emit('next')" 
          class="absolute right-2 md:-right-20 bg-white/5 hover:bg-white/10 text-white p-4 rounded-full border border-white/10 transition-all group active:scale-90 z-3002"
        >
          <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 group-hover:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
          </svg>
        </button>
      </div>

    </div>
  </Transition>
</template>

<script setup>

defineProps({
  isOpen: Boolean,
  currentImage: String,
  currentIndex: Number,
  totalImages: Number
});


defineEmits(['close', 'next', 'prev']);
</script>

<style scoped>

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
<template>
  <nav class="fixed top-0 left-0 w-full bg-[#dcccb8] shadow-sm z-1000 flex justify-between items-center px-6 md:px-16 h-25">
    
    <div class="flex flex-col leading-[0.8] text-[#926934] cursor-default font-serif">
      <span class="text-4xl md:text-3xl">Apartmani</span>
      <span class="text-4xl md:text-3xl ml-6">Marija</span>
    </div>

    <div class="flex items-center gap-6">
      <ul class="hidden lg:flex gap-8 text-[#926934] font-medium text-base tracking-wide">
        <li><a href="#pocetna" class="hover:text-white transition-colors duration-300">Početna</a></li>
        <li><a href="#rezervacija" class="hover:text-white transition-colors duration-300">Rezervacija</a></li>
        <li><a href="#apartmani" class="hover:text-white transition-colors duration-300">Apartmani</a></li>
        <li><a href="#lokacija" class="hover:text-white transition-colors duration-300">Lokacija</a></li>
        <li><a href="#o-nama" class="hover:text-white transition-colors duration-300">O nama</a></li>
      </ul>

      <a 
        href="#rezervacija" 
        class="bg-white text-[#926934] px-5 py-2 rounded-md font-bold text-base shadow-sm hover:bg-[#926934] hover:text-white transition-all duration-300"
      >
        Rezerviraj
      </a>
    </div>
  </nav>
</template>
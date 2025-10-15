<script>
  import Navbar from './Navbar.svelte';
  import HeroSection from './HeroSection.svelte';
  import bgImage from '$lib/assets/Rectangle 1.png';
</script>

<div 
  class="min-h-screen bg-cover" 
  style="
    background-image: url({bgImage});
    background-position: 65% center;
  "
>
  <!-- Estilos responsive para cada dispositivo -->
  <style>
    /* Mobile: mostrar laptop y reloj */
    @media (max-width: 767px) {
      div[style*='background-image'] {
        background-position: 67% 40% !important;
      }
    }
    
    /* Tablet: mostrar laptop completa hasta H y planta */
    @media (min-width: 768px) and (max-width: 1279px) {
      div[style*='background-image'] {
        background-position: 90% center !important;
      }
    }
    
    /* Desktop: mostrar camisa y brazo derecho */
    @media (min-width: 1280px) {
      div[style*='background-image'] {
        background-position: 50% 45% !important;
      }
    }
  </style>

  <!-- Overlay blanco difuminado (SOLO MOBILE) -->
  <div class="md:hidden absolute inset-0 bg-white/70"></div>
  
  <!-- Contenido (encima del overlay) -->
  <div class="relative px-5 md:px-[84px] xl:px-[122px] pt-9 md:pt-[45px] xl:pt-[35px]">
    <div class="flex flex-col gap-16 md:gap-[161px] xl:gap-[165px]">
      <Navbar />
      <HeroSection />
    </div>
  </div>
</div>
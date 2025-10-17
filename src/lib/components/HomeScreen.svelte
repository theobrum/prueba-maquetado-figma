<script>
  import Navbar from './Navbar.svelte';
  import HeroSection from './HeroSection.svelte';
  import bgImage from '$lib/assets/Rectangle 1.png';
</script>

<div 
  class="min-h-screen bg-cover bg-center" 
  style="background-image: url({bgImage})"
>
  <style>
    /* Mobile: centrado */
    @media (max-width: 767px) {
      div[style*='background-image'] {
        background-position: 70% 40% !important;
      }
    }
    
    /* Tablet: NUEVO - mostrar planta, laptop y brazo */
    @media (min-width: 768px) and (max-width: 1279px) {
      div[style*='background-image'] {
        background-position: 10% !important;
        background-size: cover !important;
      }
    }
    
    /* Desktop: camisa y brazo visibles */
    @media (min-width: 1280px) {
      div[style*='background-image'] {
        background-position: 55% 45% !important;
      }
    }
  </style>

  <div class="md:hidden absolute inset-0 bg-white/70"></div>
  
  <div class="relative px-5 md:px-[84px] xl:px-[122px] pt-9 md:pt-[45px] xl:pt-[35px]">
    <div class="flex flex-col gap-16 md:gap-[161px] xl:gap-[165px]">
      <Navbar />
      <HeroSection />
    </div>
  </div>
</div>
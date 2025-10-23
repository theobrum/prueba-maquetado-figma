<script>
  import Navbar from './Navbar.svelte';
  import HeroSection from './HeroSection.svelte';
  import SectionsContainer from './SectionsContainer.svelte';
  import bgImage from '$lib/assets/imgs/Rectangle 1.png';
</script>

<div 
  class="min-h-screen bg-cover bg-center" 
  style="background-image: url({bgImage})"
>
  <style>
    @media (max-width: 767px) {
      div[style*='background-image'] {
        background-position: 67.5% !important;
      }
    }
    
    @media (min-width: 768px) and (max-width: 1279px) {
      div[style*='background-image'] {
        background-position: 40% center !important;
      }
    }
    
    @media (min-width: 1280px) {
      div[style*='background-image'] {
        background-position: 55% 45% !important;
      }
    }
  </style>

  <div class="md:hidden absolute inset-0 bg-white/40"></div>
  
  <SectionsContainer fullWidth={true} className="relative pt-9 md:pt-[45px] xl:pt-[35px]">
    <div class="flex flex-col gap-16 md:gap-[161px] xl:gap-[165px]">
      <Navbar />
      <HeroSection />
    </div>
  </SectionsContainer>
</div>
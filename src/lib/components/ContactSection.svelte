<script>
  import Button from './Button.svelte';
  import SectionsContainer from './SectionsContainer.svelte';
  import twoUsersIcon from '$lib/assets/icons/shapes/TwoUsersRedCircle.png';
</script>

<section class="bg-white py-24 md:py-40 xl:py-36">
  <SectionsContainer fullWidth={true}>
    
    <div class="flex flex-col items-center justify-center gap-3 md:gap-3 xl:gap-6">
      
      <div class="mb-2 md:mb-4">
        <img 
          src={twoUsersIcon} 
          alt="Bize Ulaşın" 
          class="w-[80px] h-[80px] md:w-[100px] md:h-[100px] xl:w-[120px] xl:h-[120px] object-contain"
        />
      </div>
      
      <h2 class="font-manrope font-extrabold text-[36px] leading-[32px] md:text-[48px] md:leading-[32px] text-black text-center">
        Bize Ulaşın
      </h2>
      
      <p class="font-manrope font-medium text-[14px] leading-[25px] md:text-[18px] md:leading-[32px] text-black text-center max-w-[650px]">
        Çözüm, hizmet ve ürünlerimiz hakkında detaylı bilgi için bizimle irtibata geçin.
      </p>
      
      <div class="mt-4 md:mt-6">
        <Button class="w-[200px] md:w-[220px] xl:w-[240px] h-[48px] md:h-[52px] xl:h-[56px] rounded-[8px] px-4 py-3 text-[14px] md:text-[16px] leading-[24px] font-semibold">
          Bize Ulaşın
        </Button>
      </div>
      
    </div>
    
  </SectionsContainer>
</section>
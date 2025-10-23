<script lang="ts">
  import { onMount } from 'svelte';
  import Button from './Button.svelte';
  
  export let title: string = '';
  export let titleMobile: string = '';
  export let titleTablet: string = '';
  export let titleDesktop: string = '';
  export let description: string = '';
  export let descriptionMobile: string = '';
  export let descriptionTablet: string = '';
  export let descriptionDesktop: string = '';
  export let buttonText: string;
  export let imageDesktop: string;
  export let imageTablet: string;
  export let imageMobile: string;
  export let imagePosition: 'left' | 'right' = 'right';
  export let largeGap: boolean = false;
  export let hasMultipleVersions: boolean = false;
  
  const flexDirection = imagePosition === 'right' 
    ? 'md:flex-row-reverse' 
    : 'md:flex-row';
  
  const gapClass = largeGap ? 'xl:gap-47' : 'xl:gap-20';
  
  let currentBreakpoint: 'mobile' | 'tablet' | 'desktop' = 'desktop';
  
  function updateBreakpoint(): void {
    if (typeof window !== 'undefined') {
      const width = window.innerWidth;
      if (width < 768) {
        currentBreakpoint = 'mobile';
      } else if (width < 1280) {
        currentBreakpoint = 'tablet';
      } else {
        currentBreakpoint = 'desktop';
      }
    }
  }
  
  onMount(() => {
    updateBreakpoint();
    window.addEventListener('resize', updateBreakpoint);
    return () => window.removeEventListener('resize', updateBreakpoint);
  });
  
  $: displayTitle = hasMultipleVersions
    ? (currentBreakpoint === 'mobile' ? titleMobile : 
       currentBreakpoint === 'tablet' ? titleTablet : 
       titleDesktop)
    : title;
  
  $: displayDescription = hasMultipleVersions
    ? (currentBreakpoint === 'mobile' ? descriptionMobile : 
       currentBreakpoint === 'tablet' ? descriptionTablet : 
       descriptionDesktop)
    : description;
</script>

<div class="flex flex-col gap-8 {flexDirection} md:gap-16 {gapClass}">
  
  <div class="w-full md:w-[45%] xl:w-[42%] flex items-center justify-center flex-shrink-0">
    <img 
      src={imageMobile} 
      alt={displayTitle}
      class="block md:hidden w-full aspect-square rounded-[12px] object-cover"
    />
    <img 
      src={imageTablet} 
      alt={displayTitle}
      class="hidden md:block xl:hidden w-full aspect-square rounded-[12px] object-cover"
    />
    <img 
      src={imageDesktop} 
      alt={displayTitle}
      class="hidden xl:block w-full aspect-square rounded-[12px] object-cover"
    />
  </div>
  
  <div class="w-full md:w-1/2 flex flex-col justify-center md:aspect-square">
    <h2 class="font-manrope font-bold text-[36px] leading-[41.5px] md:text-[54px] md:leading-[59.5px] md:max-w-none xl:text-[64px] xl:leading-[76px] xl:max-w-[510px] text-[#2E2E2E] mb-4 md:mb-6 text-center md:text-left">
      {displayTitle}
    </h2>
    
    <p class="font-manrope font-normal text-[14px] leading-[28.5px] md:text-[13px] md:leading-[28.5px] md:max-w-none xl:text-[16px] xl:leading-[32px] xl:max-w-[520px] text-[#808080] mb-8 md:mb-20 xl:mb-24 text-center md:text-left">
      {displayDescription}
    </p>
    
    <div class="flex justify-center md:justify-start">
      <Button class="w-[338px] md:w-[160px] h-[48px] rounded-[8px] px-3 py-3 text-[14px] leading-[24px] font-semibold">
        {buttonText}
      </Button>
    </div>
  </div>
  
</div>
<script lang="ts">
  export let text: string;
  export let icon: string = '';
  export let iconMobile: string = '';
  
  const mobileIcon = iconMobile || icon;
  const hasIcon = icon !== '';
</script>

<div class="flex flex-col items-center gap-3 md:flex-row {hasIcon ? 'md:justify-between' : 'md:justify-start'} md:gap-4">
  <p class="font-manrope font-bold text-[15px] leading-[18px] md:text-[12px] md:leading-[21.5px] md:flex-1 xl:text-[18px] xl:leading-[31px] text-white text-center md:text-left">
    {@html text}
  </p>
  
  {#if mobileIcon && mobileIcon !== ''}
    <img src={mobileIcon} alt="" class="block md:hidden w-9 h-9 flex-shrink-0" />
  {/if}
  
  {#if icon && icon !== ''}
    <img src={icon} alt="" class="hidden md:block w-[28px] h-[27px] xl:w-8 xl:h-8 flex-shrink-0" />
  {/if}
</div>
<script lang="ts">
  export let text: string;
  export let icon: string;
  export let iconMobile: string;
  
  const hasIcon = icon !== '';
</script>

<div class="flex flex-col items-center gap-4 md:flex-row md:items-center md:gap-6 xl:gap-5">
  <p class="font-manrope font-bold text-[18px] leading-[18px] max-w-[190px] md:text-[12px] md:leading-[21.5px] md:max-w-[170px] xl:text-[18px] xl:leading-[31px] xl:max-w-[240px] text-white text-center md:text-left">
    {@html text}
  </p>

  {#if hasIcon}
    <img src={iconMobile} alt="" class="block md:hidden w-9 h-9 flex-shrink-0" />
    <img src={icon} alt="" class="hidden md:block w-[28px] h-[27px] xl:w-8 xl:h-8 flex-shrink-0" />
  {/if}
</div>
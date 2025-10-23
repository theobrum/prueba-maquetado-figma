<script lang="ts">
  export let circleIcon: string;
  export let mainIcon: string;
  export let circlePosition: string = 'top-right';
  export let circleOffsetX: string = '0px';
  export let circleOffsetY: string = '0px';
  export let title: string;
  export let description: string;
  
  function getCircleStyle(position: string): string {
    const baseStyles: Record<string, string> = {
      'top-left': `top: ${circleOffsetY}; left: ${circleOffsetX};`,
      'top-right': `top: ${circleOffsetY}; right: ${circleOffsetX};`,
      'bottom-left': `bottom: ${circleOffsetY}; left: ${circleOffsetX};`,
      'bottom-right': `bottom: ${circleOffsetY}; right: ${circleOffsetX};`,
      'center': 'top: 50%; left: 50%; transform: translate(-50%, -50%);'
    };
    return baseStyles[position] || `top: ${circleOffsetY}; right: ${circleOffsetX};`;
  }
</script>

<div class="flex flex-col items-center text-center p-6 rounded-lg">
  
  <div class="relative mb-6 md:mb-8 w-[76px] h-[76px]">
    <img 
      src={circleIcon} 
      alt="" 
      class="absolute w-[45px] h-[45px] z-0"
      style={getCircleStyle(circlePosition)}
    />
    
    <img src={mainIcon} alt="" class="relative w-full h-full z-10" />
  </div>
  
  <h3 class="font-bold font-manrope text-black mb-3 md:mb-4 text-lg md:text-xl xl:text-2xl">
    {title}
  </h3>
  
  <p class="font-manrope font-normal text-gray-600 text-sm md:text-base xl:text-lg leading-relaxed">
    {description}
  </p>
  
</div>
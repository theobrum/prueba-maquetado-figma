<script lang="ts">
  export let className: string = '';
  export let fullWidth: boolean = false;
  
  $: containerClass = `${fullWidth ? 'w-full' : 'max-w-7xl mx-auto'} px-5 md:px-[100px] xl:px-[150px] ${className}`;
</script>

<div class={containerClass}>
  <slot />
</div>
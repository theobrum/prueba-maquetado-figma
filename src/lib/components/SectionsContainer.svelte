<script lang="ts">
  export let className: string = '';
  export let fullWidth: boolean = false;
</script>

<div class="{fullWidth ? 'w-full' : 'max-w-7xl mx-auto'} px-5 md:px-[84px] xl:px-[122px] {className}">
  <slot />
</div>
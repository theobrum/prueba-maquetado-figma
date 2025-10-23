<script lang="ts">
  export let logoSrc: string;
  export let logoAlt: string;
</script>

<div class="bg-white rounded-[12px] shadow-[0px_30px_40px_0px_rgba(212,217,232,0.2)] p-[15px] md:p-[19px] flex items-center justify-center min-h-[80px] md:min-h-[100px]">
  <img src={logoSrc} alt={logoAlt} class="max-w-full max-h-[50px] md:max-h-[60px] object-contain" />
</div>
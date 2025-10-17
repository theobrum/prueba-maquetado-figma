<script>
  import Button from './Button.svelte';
</script>

<div class="flex flex-col items-center md:items-start xl:items-start">

  <h1 class="
    mb-5
    text-center md:text-left xl:text-left
    text-[42px] md:text-[56px] xl:text-[64px]
    font-extrabold text-black font-manrope
    leading-[57.5px] md:leading-[73.5px] xl:leading-[82px]
  ">
    Bilgi Teknolojilerinde<br/>23 Yıllık Tecrübe
  </h1>
  
  <p class="
    mb-[50px]
    text-center md:text-left xl:text-left
    font-manrope font-normal
    text-[12px] md:text-[16px] xl:text-[20px]
    leading-[23px] md:leading-[28px] xl:leading-9
    tracking-[0.2px]
    text-black
    max-w-full md:max-w-[600px] xl:max-w-none
  ">
    Müşterilerimizin yüksek kalite seviyelerini koruyabilmeleri için farklı<br class="hidden xl:block"/> 
    sektörlerde tecrübe kazanmış uzman kadrolarımızla Proje Yönetimi, İş<br class="hidden xl:block"/>
    Analizi ve Test Yönetimi hizmetleri sunmaktayız.
  </p>
  
  <div class="
    relative
    w-full md:w-[450px] xl:w-[502px]
    h-[60px] md:h-[68px] xl:h-[73px]
  ">
    <input 
      type="email" 
      placeholder="Mail bültenimize kayıt ol" 
      class="
        w-full h-full
        px-4 pr-28
        rounded-[8px] bg-white border-0
        text-sm md:text-base
        placeholder:text-gray-400
      "
    >
    <div class="absolute right-2 top-1/2 -translate-y-1/2">
      <Button class="
        w-[110px] md:w-[125px] xl:w-[136px]
        h-[50px] md:h-[55px] xl:h-[61px]
        rounded-[8px]
        text-sm md:text-base
      ">
        Kayıt Ol
      </Button>
    </div>
  </div>
</div>
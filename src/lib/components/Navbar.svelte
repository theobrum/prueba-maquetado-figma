<script>
  import Button from './Button.svelte';
  
  let menuOpen = false;
  
  function toggleMenu() {
    menuOpen = !menuOpen;
  }
</script>

<header class="flex justify-between items-center relative">
  
  <!-- Menú hamburguesa (solo visible en mobile) -->
  <button 
    class="md:hidden w-8 h-8 flex items-center justify-center text-2xl font-bold"
    on:click={toggleMenu}
    aria-label="Menu"
  >
    {#if menuOpen}
      ✕
    {:else}
      ☰
    {/if}
  </button>

  <!-- Navegación desktop/tablet (oculta en mobile) -->
  <nav class="hidden md:flex md:flex-1 md:justify-end md:gap-8 md:items-center font-manrope font-bold text-[14px] leading-5 text-black">
    <a href="#" class="hover:text-gray-600 transition-colors">Çözüm ve Hizmetler</a>
    <a href="#" class="hover:text-gray-600 transition-colors">Ürünler</a>
    <a href="#" class="hover:text-gray-600 transition-colors">Teknolojiler</a>
    <a href="#" class="hover:text-gray-600 transition-colors">İnsan Kaynakları</a>
    <a href="#" class="hover:text-gray-600 transition-colors">Kurumsal</a>
    
    <Button class="w-[91px] h-[40px] rounded-[5px] px-[20px] py-[10px]">İletişim</Button>
  </nav>

  <!-- Botón mobile (siempre visible en mobile) -->
  <div class="md:hidden">
    <Button class="w-[91px] h-[40px] rounded-[5px] px-[20px] py-[10px]">İletişim</Button>
  </div>

  <!-- Menú desplegable mobile -->
  {#if menuOpen}
    <nav class="md:hidden absolute top-full left-0 right-0 bg-white shadow-lg rounded-b-lg py-4 z-50 mt-2">
      <div class="flex flex-col gap-4 px-6">
        <a href="#" class="py-2 font-manrope font-bold text-[14px] text-black hover:text-gray-600 transition-colors border-b border-gray-100">
          Çözüm ve Hizmetler
        </a>
        <a href="#" class="py-2 font-manrope font-bold text-[14px] text-black hover:text-gray-600 transition-colors border-b border-gray-100">
          Ürünler
        </a>
        <a href="#" class="py-2 font-manrope font-bold text-[14px] text-black hover:text-gray-600 transition-colors border-b border-gray-100">
          Teknolojiler
        </a>
        <a href="#" class="py-2 font-manrope font-bold text-[14px] text-black hover:text-gray-600 transition-colors border-b border-gray-100">
          İnsan Kaynakları
        </a>
        <a href="#" class="py-2 font-manrope font-bold text-[14px] text-black hover:text-gray-600 transition-colors">
          Kurumsal
        </a>
      </div>
    </nav>
  {/if}
  
</header>
<script lang="ts">
  import PartnerCard from './PartnerCard.svelte';
  import SectionsContainer from './SectionsContainer.svelte';
  
  import akbankLogo from '$lib/assets/imgs/logos/Akbank-Logo.png';
  import akcanLogo from '$lib/assets/imgs/logos/Akcan-Logo.png';
  import aktasLogo from '$lib/assets/imgs/logos/Aktas-Logo.png';
  import amazonLogo from '$lib/assets/imgs/logos/Amazon-Logo.png';
  import bookMyShowLogo from '$lib/assets/imgs/logos/BookMyShow-Logo.png';
  import borusanLogo from '$lib/assets/imgs/logos/Borusan-Logo.png';
  import istanbulBigiLogo from '$lib/assets/imgs/logos/IstanbulBigi-Logo.png';
  import olaLogo from '$lib/assets/imgs/logos/Ola-Logo.png';
  import tumunuLogo from '$lib/assets/imgs/logos/Tumunu-Logo.png';
  
  interface Partner {
    id: number;
    logoSrc: string;
    logoAlt: string;
  }
  
  const allPartners: Partner[] = [
    { id: 1, logoSrc: borusanLogo, logoAlt: 'Borusan' },
    { id: 2, logoSrc: istanbulBigiLogo, logoAlt: 'Istanbul Bilgi Üniversitesi' },
    { id: 3, logoSrc: bookMyShowLogo, logoAlt: 'BookMyShow' },
    { id: 4, logoSrc: akbankLogo, logoAlt: 'Akbank' },
    { id: 5, logoSrc: akcanLogo, logoAlt: 'Akçan' },
    { id: 6, logoSrc: aktasLogo, logoAlt: 'Aktaş' },
    { id: 7, logoSrc: amazonLogo, logoAlt: 'Amazon' },
    { id: 8, logoSrc: olaLogo, logoAlt: 'Ola' },
    { id: 9, logoSrc: tumunuLogo, logoAlt: 'Tümünü Gör' }
  ];
  
  const desktopLayout = {
    col1: [allPartners[0]],
    col2: [allPartners[1], allPartners[2]],
    col3: [allPartners[3], allPartners[4], allPartners[8]],
    col4: [allPartners[5], allPartners[7]],
    col5: [allPartners[6]]
  };
  
  const mobilePartners: Partner[] = [
    allPartners[0],
    allPartners[1],
    allPartners[2],
    allPartners[3],
    allPartners[4],
    allPartners[8]
  ];
</script>

<section class="bg-[#F4F5F7] py-9 md:py-16 xl:py-16">
  <SectionsContainer fullWidth={true}>
    
    <div class="text-center mb-12 md:mb-16 xl:mb-20">
      <h2 class="font-manrope font-extrabold text-[36px] leading-[41.5px] md:text-[48px] md:leading-[64px] text-[#18191F] mb-4">
        Referanslarımız
      </h2>
      <p class="font-manrope font-medium text-[14px] leading-[32px] md:text-[18px] text-[#18191F]">
        Bize güvenen ve beraber çalıştığımız iş ortaklarımız
      </p>
    </div>
    
    <div class="hidden md:grid md:grid-cols-5 gap-6 md:gap-8 xl:gap-12 items-center mb-12 xl:mb-16">
      
      <div class="flex flex-col gap-6 md:gap-8 xl:gap-12 justify-center">
        {#each desktopLayout.col1 as partner (partner.id)}
          <PartnerCard logoSrc={partner.logoSrc} logoAlt={partner.logoAlt} />
        {/each}
      </div>
      
      <div class="flex flex-col gap-6 md:gap-8 xl:gap-12 justify-center">
        {#each desktopLayout.col2 as partner (partner.id)}
          <PartnerCard logoSrc={partner.logoSrc} logoAlt={partner.logoAlt} />
        {/each}
      </div>
      
      <div class="flex flex-col gap-6 md:gap-8 xl:gap-12 justify-center">
        {#each desktopLayout.col3 as partner (partner.id)}
          <PartnerCard logoSrc={partner.logoSrc} logoAlt={partner.logoAlt} />
        {/each}
      </div>
      
      <div class="flex flex-col gap-6 md:gap-8 xl:gap-12 justify-center">
        {#each desktopLayout.col4 as partner (partner.id)}
          <PartnerCard logoSrc={partner.logoSrc} logoAlt={partner.logoAlt} />
        {/each}
      </div>

      <div class="flex flex-col gap-6 md:gap-8 xl:gap-12 justify-center">
        {#each desktopLayout.col5 as partner (partner.id)}
          <PartnerCard logoSrc={partner.logoSrc} logoAlt={partner.logoAlt} />
        {/each}
      </div>     
    </div>
    
    <div class="md:hidden flex flex-col items-center gap-6">
      {#each mobilePartners as partner (partner.id)}
        <div class="w-full max-w-[140px]">
          <PartnerCard logoSrc={partner.logoSrc} logoAlt={partner.logoAlt} />
        </div>
      {/each}
    </div>
    
  </SectionsContainer>
</section>
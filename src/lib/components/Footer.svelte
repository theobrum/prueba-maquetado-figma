<script lang="ts">
  import SectionsContainer from './SectionsContainer.svelte';
  import socialNetworkLogos from '$lib/assets/icons/shapes/SocialNetworks-Logos.png';
  
  interface FooterColumn {
    title: string;
    links: string[];
  }
  
  const footerColumns: FooterColumn[] = [
    {
      title: 'Çözüm ve Hizmetler',
      links: [
        'Yazılım Geliştirme',
        'Outsourcing',
        'Kalite ve Süreç Yönetimi',
        'Danışmanlık',
        'IoT Destekli Çözümler'
      ]
    },
    {
      title: 'Ürünler',
      links: [
        'Eğitim Yönetim Sistemi',
        'İnsan Sermayesi Yönetim Sistemi',
        'Müşteri İlişkileri Yönetim Sistemi',
        'İçerik Yönetim Sistemi'
      ]
    },
    {
      title: 'Kurumsal',
      links: [
        'Hakkımızda',
        'Belge ve Yetkinlikler',
        'İş Ortakları'
      ]
    },
    {
      title: 'İletişim',
      links: [
        'Bilgi İstek Formu',
        'Uzman Talep Formu'
      ]
    }
  ];
</script>

<footer class="bg-[#F8464A] py-12 md:py-16 xl:py-20">
  <SectionsContainer fullWidth={true}>
    
    <div class="grid grid-cols-1 md:grid-cols-4 gap-8 md:gap-6 xl:gap-12 mb-12 md:mb-16">
      
      {#each footerColumns as column}
        <div class="flex flex-col gap-4">
          <h3 class="font-inter font-bold text-[12px] leading-[24px] text-white">
            {column.title}
          </h3>
          
          <ul class="flex flex-col gap-4">
            {#each column.links as link}
              <li>
                <a 
                  href="#" 
                  class="font-inter font-normal text-[12px] leading-[32px] text-[#E6E6E6] hover:text-white transition-colors"
                >
                  {link}
                </a>
              </li>
            {/each}
          </ul>
        </div>
      {/each}
      
    </div>
    
    <div class="flex flex-col md:flex-row items-start md:items-center md:justify-between gap-6">
  
        <div class="flex items-center self-start md:self-auto md:order-2">
            <img 
            src={socialNetworkLogos} 
            alt="Redes sociales" 
            class="h-[32px] md:h-[36px] object-contain"
            />
        </div>
        
        <p class="font-inter font-normal text-[14px] md:text-[16px] text-white text-left md:order-1">
            © Copyright 2010-2021 - Can Çevik
        </p>
        
    </div>
    
  </SectionsContainer>
</footer>
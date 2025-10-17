<script>
  import ServiceCard from './ServiceCard.svelte';
  import SectionsContainer from './SectionsContainer.svelte';
  
  import circlePink from '$lib/assets/icons/circles/PinkCircle.svg';
  import circlePurple from '$lib/assets/icons/circles/PurpleCircle.svg';
  import circleBlue from '$lib/assets/icons/circles/BlueCircle.svg';
  import circleSkyblue from '$lib/assets/icons/circles/SkyblueCircle.svg';
  import circleYellow from '$lib/assets/icons/circles/YellowCircle.svg';
  import circleRed from '$lib/assets/icons/circles/RedCircle.svg';

  import fileIcon from '$lib/assets/icons/shapes/File.svg';
  import starIcon from '$lib/assets/icons/shapes/Star.svg';
  import chartBarIcon from '$lib/assets/icons/shapes/ChartBar.svg';
  import pieIcon from '$lib/assets/icons/shapes/Pie.svg';
  import figmaLogoIcon from '$lib/assets/icons/shapes/FigmaLogo.svg';
  import crownIcon from '$lib/assets/icons/shapes/Crown.svg';

  const services = [
    {
      id: 1,
      circleIcon: circlePink,
      mainIcon: fileIcon,
      circlePosition: 'top-right',
      circleOffsetX: '0px',
      circleOffsetY: '0px',
      title: 'Doküman Analizi',
      description: 'Ante vulputate ut at accumsan et. Feugiat at tempus, est senectus amet, elementum.',
      orderMobile: 1,
      orderTablet: 1,
      orderDesktop: 1
    },
    {
      id: 2,
      circleIcon: circlePurple,
      mainIcon: starIcon,
      circlePosition: 'top-left',
      circleOffsetX: '-6px',
      circleOffsetY: '8px',
      title: 'Kabul ve Değerlendirme',
      description: 'Ante vulputate ut at accumsan et. Feugiat at tempus, est senectus amet, elementum.',
      orderMobile: 2,
      orderTablet: 2,
      orderDesktop: 2
    },
    {
      id: 3,
      circleIcon: circleSkyblue,
      mainIcon: crownIcon,
      circlePosition: 'top-right',
      circleOffsetX: '-15px',
      circleOffsetY: '7px',
      title: 'İş Kuralları Analizi',
      description: 'Ante vulputate ut at accumsan et. Feugiat at tempus, est senectus amet, elementum.',
      orderMobile: 6,
      orderTablet: 5,
      orderDesktop: 3
    },
    {
      id: 4,
      circleIcon: circleBlue,
      mainIcon: chartBarIcon,
      circlePosition: 'top-left',
      circleOffsetX: '-1px',
      circleOffsetY: '5px',
      title: 'Akış Diyagramları',
      description: 'Ante vulputate ut at accumsan et. Feugiat at tempus, est senectus amet, elementum.',
      orderMobile: 4,
      orderTablet: 3,
      orderDesktop: 4
    },
    {
      id: 5,
      circleIcon: circleRed,
      mainIcon: pieIcon,
      circlePosition: 'top-right',
      circleOffsetX: '-7px',
      circleOffsetY: '-2px',
      title: 'Paydaş Analizi',
      description: 'Ante vulputate ut at accumsan et. Feugiat at tempus, est senectus amet, elementum.',
      orderMobile: 3,
      orderTablet: 4,
      orderDesktop: 5
    },
    {
      id: 6,
      circleIcon: circleYellow,
      mainIcon: figmaLogoIcon,
      circlePosition: 'top-right',
      circleOffsetX: '8px',
      circleOffsetY: '-6px',
      title: 'Prototipleme',
      description: 'Ante vulputate ut at accumsan et. Feugiat at tempus, est senectus amet, elementum.',
      orderMobile: 5,
      orderTablet: 6,
      orderDesktop: 6
    }
  ];
</script>

<section class="bg-white py-16 md:py-20 xl:py-24">
  <SectionsContainer fullWidth={true}>
    
    <div class="text-center mb-12 xl:mb-16">
      <h2 class="text-3xl md:text-4xl xl:text-5xl font-bold text-black mb-4 font-manrope">
        Kalite ve Süreç Yönetimi
      </h2>
      <p class="text-sm md:text-base xl:text-lg text-gray-700 max-w-3xl mx-auto font-manrope">
        Müşterilerimizin yüksek kalite seviyelerini koruyabilmeleri için farklı 
        sektörlerde tecrübe kazanmış uzman kadrolarımızla Proje Yönetimi, İş Analizi 
        ve Test Yönetimi hizmetleri sunmaktayız.
      </p>
    </div>
    
    <div class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-8 md:gap-10 xl:gap-12">
      
      {#each services as service (service.id)}
        <div class="order-{service.orderMobile} md:order-{service.orderTablet} xl:order-{service.orderDesktop}">
          <ServiceCard 
            circleIcon={service.circleIcon}
            mainIcon={service.mainIcon}
            circlePosition={service.circlePosition}
            circleOffsetX={service.circleOffsetX}
            circleOffsetY={service.circleOffsetY}
            title={service.title}
            description={service.description}
          />
        </div>
      {/each}
      
    </div>
    
  </SectionsContainer>
</section>
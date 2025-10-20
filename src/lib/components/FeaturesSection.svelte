<script>
  import FeatureCard from './FeatureCard.svelte';
  import SectionsContainer from './SectionsContainer.svelte';
  import arrowIcon from '$lib/assets/icons/shapes/arrow-circle.svg';
  import arrowIconMobile from '$lib/assets/icons/shapes/arrow-circle-mobile.svg';
  import dotPattern from '$lib/assets/imgs/dot-pattern.png';

  const features = [
    {
      id: 1,
      text: 'Yazılım Kalitesini Arttırıyoruz',
      hasIcon: true
    },
    {
      id: 2,
      text: 'Olası Hataları Önceden Belirliyoruz',
      hasIcon: true
    },
    {
      id: 3,
      text: 'Oluşabilecek Riskleri Önlüyoruz',
      hasIcon: true
    },
    {
      id: 4,
      text: 'Zaman ve Maliyetten Tasarruf Sağlıyoruz',
      hasIcon: false
    }
  ];
</script>

<section class="bg-[#F8464A] py-16 md:py-20 xl:py-24 relative overflow-hidden">
  
  <div 
    class="absolute inset-0 opacity-40"
    style="
      background-image: url({dotPattern});
      background-size: cover;
      background-position: -58px -329px;
      mix-blend-mode: lighten;
    "
  ></div>
  
  <SectionsContainer fullWidth={true} className="relative z-10">
    
    <div class="text-center mb-12 xl:mb-16">
      <h2 class="font-manrope font-extrabold text-[36px] leading-[47px] md:text-[48px] md:leading-[64px] text-white mb-4">
        Test Yönetimiyle Neler Sağlıyoruz?
      </h2>
      <p class="font-manrope font-normal text-[14px] md:text-[18px] leading-[32px] text-white">
        IoT Destekli Çözümler
      </p>
    </div>
    
    <div class="grid grid-cols-1 md:grid-cols-4 xl:grid-cols-4 gap-16 md:gap-8 xl:gap-8 justify-items-center">
      {#each features as feature (feature.id)}
        <FeatureCard 
          text={feature.text}
          icon={feature.hasIcon ? arrowIcon : ''}
          iconMobile={feature.hasIcon ? arrowIconMobile : ''}
        />
      {/each}
    </div>
    
  </SectionsContainer>
</section>
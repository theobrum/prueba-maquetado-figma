<script lang="ts">
  import InfoCard from './InfoCard.svelte';
  import SectionsContainer from './SectionsContainer.svelte';
  
  import workConferenceMobile from '$lib/assets/imgs/WorkConference.png';
  import workConferenceTablet from '$lib/assets/imgs/WorkConference.png';
  import workConferenceDesktop from '$lib/assets/imgs/WorkConference.png';
  
  import macOnTableMobile from '$lib/assets/imgs/MacOnTable.png';
  import macOnTableTablet from '$lib/assets/imgs/MacOnTable.png';
  import manBehindMacDesktop from '$lib/assets/imgs/ManBehindBlackMacBook.png';
  
  interface InfoCardData {
    id: number;
    title?: string;
    titleMobile?: string;
    titleTablet?: string;
    titleDesktop?: string;
    description?: string;
    descriptionMobile?: string;
    descriptionTablet?: string;
    descriptionDesktop?: string;
    buttonText: string;
    imageDesktop: string;
    imageTablet: string;
    imageMobile: string;
    imagePosition: 'left' | 'right';
    hasMultipleVersions: boolean;
  }
  
  const infoCards: InfoCardData[] = [
    {
      id: 1,
      title: "Kalite ve Süreç Yönetimi",
      description: "Deneyimli kadromuz; birçok farklı sektörden deneyimli, PMP® sertifikasına sahip, uzman proje yöneticilerinden oluşmaktadır. Projelerinizin yönetimine destek olmak, zayıf olduğunu düşündüğünüz alanları güçlendirmek, uluslararası geçerliliği olan PMI® metodolojisini şirketinizde uygulamak ve geliştirmek için yanınızdayız.",
      buttonText: "Keşfet",
      imageDesktop: workConferenceDesktop,
      imageTablet: workConferenceTablet,
      imageMobile: workConferenceMobile,
      imagePosition: 'right',
      hasMultipleVersions: false
    },
    {
      id: 2,
      titleMobile: "Kalite ve Süreç Yönetimi",
      titleTablet: "Kalite ve Süreç Yönetimi",
      titleDesktop: "Test Yönetimi ve Analizi",
      descriptionMobile: "Deneyimli kadromuz; birçok farklı sektörden deneyimli, PMP® sertifikasına sahip, uzman proje yöneticilerinden oluşmaktadır. Projelerinizin yönetimine destek olmak, zayıf olduğunu düşündüğünüz alanları güçlendirmek, uluslararası geçerliliği olan PMI® metodolojisini şirketinizde uygulamak ve geliştirmek için yanınızdayız.",
      descriptionTablet: "Deneyimli kadromuz; birçok farklı sektörden deneyimli, PMP® sertifikasına sahip, uzman proje yöneticilerinden oluşmaktadır. Projelerinizin yönetimine destek olmak, zayıf olduğunu düşündüğünüz alanları güçlendirmek, uluslararası geçerliliği olan PMI® metodolojisini şirketinizde uygulamak ve geliştirmek için yanınızdayız.",
      descriptionDesktop: "Danışmanlarımız yürüttüğümüz projelerde yazılım hatalarını önlemek amacıyla gerçekleştirdiğimiz testler her proje aşamasında manuel ya da test otomasyonu ile dikkatli uygulanmaktadır. Deneyimli test ekibimiz, kurumunuza yüksek kalitede yazılım testleri hizmeti ile baştan sona güvenli, kaliteli ve teminatli bir müşteri deneyimi sunmaktadır.",
      buttonText: "Keşfet",
      imageDesktop: manBehindMacDesktop,
      imageTablet: macOnTableTablet,
      imageMobile: macOnTableMobile,
      imagePosition: 'left',
      hasMultipleVersions: true
    }
  ];
</script>

<section class="bg-white py-16 md:py-20 xl:py-24">
  <SectionsContainer fullWidth={true}>
    
    <div class="grid grid-cols-1 gap-16 md:gap-20 xl:gap-16">
      {#each infoCards as card, index (card.id)}
        <InfoCard 
          title={card.title || ''}
          titleMobile={card.titleMobile || ''}
          titleTablet={card.titleTablet || ''}
          titleDesktop={card.titleDesktop || ''}
          description={card.description || ''}
          descriptionMobile={card.descriptionMobile || ''}
          descriptionTablet={card.descriptionTablet || ''}
          descriptionDesktop={card.descriptionDesktop || ''}
          buttonText={card.buttonText}
          imageDesktop={card.imageDesktop}
          imageTablet={card.imageTablet}
          imageMobile={card.imageMobile}
          imagePosition={card.imagePosition}
          largeGap={index === 1}
          hasMultipleVersions={card.hasMultipleVersions}
        />
      {/each}
    </div>
    
  </SectionsContainer>
</section>
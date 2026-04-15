<!-- Swiper JS -->
<script lang="ts">
  import { onMount } from 'svelte';
  import Swiper from 'swiper';
  import { Navigation, Pagination, EffectCoverflow } from 'swiper/modules';

  import 'swiper/css';
  import 'swiper/css/navigation';
  import 'swiper/css/pagination';
  import 'swiper/css/effect-coverflow';

  let swiperContainer: HTMLDivElement;

  const elements = [
    {
      name: 'Roshen szelet mandulával és kókuszos 29 g',
      image: 'termekkepek/Roshen-szelet-mandulaval-kokuszos-29g.png',
    },
    {
      name: 'Roshen tejcsokoládé szelet crème brulée 33 g',
      image: 'termekkepek/Roshen-tejcsokolade-creme-brulee-33g.png',
    },
    {
      name: 'Roshen tejcsokoládé szelet karamell 30 g',
      image: 'termekkepek/Roshen-tejcsokolade-karamell-30g.png',
    },
    {
      name: 'Tibi Aerated étcsokoládé 80g',
      image: 'termekkepek/Tibi-aerated-etcsokolade-80g.png',
    },
    {
      name: 'Tibi Aerated tejcsokoládé 80g',
      image: 'termekkepek/Tibi-aerated-tejcsokolade-80g.png',
    },
    {
      name: 'Tibi epres torta ízű tejcsokoládé 275 g',
      image: 'termekkepek/Tibi-epres-torta-275g.png',
    },
    {
      name: 'Tibi ét ananász ízű krémmel 90 g',
      image: 'termekkepek/Tibi-et-ananasz-90g.png',
    },
    {
      name: 'Tibi ét banán ízű krémmel 90 g',
      image: 'termekkepek/Tibi-et-banan-90g.png',
    },
    {
      name: 'Tibi ét eper ízű krémmel 90 g',
      image: 'termekkepek/Tibi-et-eper-90g.png',
    },
    {
      name: 'Tibi ét kajszi ízű krémmel 90 g',
      image: 'termekkepek/Tibi-et-kajszi-90g.png',
    },
    {
      name: 'Tibi ét kakaókrémmel 90 g',
      image: 'termekkepek/Tibi-et-kakaokrem-90g.png',
    },
    {
      name: 'Tibi ét meggyes és csokoládés krémes 90 g',
      image: 'termekkepek/Tibi-et-meggyes-csokolades-90g.png',
    },
    {
      name: 'Tibi étcsokoládé 90 g',
      image: 'termekkepek/Tibi-etcsokolade-90g.png',
    },
    {
      name: 'Tibi étcsokoládé tejes és kakaós krémmel, ostyával 265 g',
      image: 'termekkepek/Tibi-etcsokolade-tejes-kakaos-265g.png',
    },
    {
      name: 'Tibi étcsokoládé tiramisu ízű krémmel és keksszel 290 g',
      image: 'termekkepek/Tibi-etcsokolade-tiramisu-290g.png',
    },
    {
      name: 'Tibi tej crème brulée ízű krémmel 90 g',
      image: 'termekkepek/Tibi-tej-creme-brulee-90g.png',
    },
    {
      name: 'Tibi tej feketeribizli ízű krémmel 90 g',
      image: 'termekkepek/Tibi-tej-feketeribizli-90g.png',
    },
    {
      name: 'Tibi tej karamell krémmel 87 g',
      image: 'termekkepek/Tibi-tej-karamell-87g.png',
    },
    {
      name: 'Tibi tej körte ízű krémmel 90 g',
      image: 'termekkepek/Tibi-tej-korte-90g.png',
    },
    {
      name: 'Tibi tej tejkrémmel és keksszel 100 g',
      image: 'termekkepek/Tibi-tej-tejkrem-keks-100g.png',
    },
    {
      name: 'Tibi tej tejkrémmel és ostyával 90 g',
      image: 'termekkepek/Tibi-tej-tejkrem-ostya-90g.png',
    },
    {
      name: 'Tibi tej tejkrémmel, karamellel és keksszel 100 g',
      image: 'termekkepek/Tibi-tej-tejkrem-karamell-keks-100g.png',
    },
    {
      name: 'Tibi tejcsokoládé 90 g',
      image: 'termekkepek/Tibi-tejcsokolade-90g.png',
    },
    {
      name: 'Tibi tejcsokoládé csokoládés-mogyorós krémmel és keksszel 290 g',
      image: 'termekkepek/Tibi-tejcsokolade-csokolades-mogyoros-290g.png',
    },
    {
      name: 'Tibi tejcsokoládé földimogyoróval, földimogyorós krémmel és karamellel 295 g',
      image: 'termekkepek/Tibi-tejcsokolade-foldimogyoro-karamell-295g.png',
    },
    {
      name: 'Tibi tejcsokoládé mandulával és kókusszal 280 g',
      image: 'termekkepek/Tibi-tejcsokolade-mandulaval-kokusszal-280g.png',
    },
  ];

  onMount(() => {
    new Swiper(swiperContainer, {
      modules: [Navigation, Pagination, EffectCoverflow],

      effect: 'coverflow',
      grabCursor: true,
      centeredSlides: true,
      loop: true,
      slidesPerView: 2,

      coverflowEffect: {
        rotate: 0,
        stretch: 0,
        depth: 150,
        modifier: 2.5,
        slideShadows: false,
      },

      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },

      pagination: {
        el: '.swiper-pagination',
      },

      breakpoints: {
        768: {
          slidesPerView: 3,
        },
      },
    });
  });
</script>

<section class="collection SweetSansBold text-[#003366] bg-[#ffe6c7]">
  <div bind:this={swiperContainer} class="swiper mySwiper">
    <div class="swiper-wrapper scale-[0.975]">
      {#each elements as element}
        <div class="content swiper-slide">
          <div class="text-content text-center">
            <img src={element.image} alt={element.name} />
            <h3>{element.name}</h3>
          </div>
        </div>
      {/each}
    </div>
    <div class="md:block hidden swiper-pagination"></div>
    <!-- jobbra balra nyilak -->
    <div class="swiper-button-prev md:block! hidden! translate-y-[10vw]"></div>
    <div class="swiper-button-next md:block! hidden! translate-y-[10vw]"></div>
  </div>
</section>

<style>
  .swiper {
    height: 28vw;
  }

  .collection {
    padding-inline: 5%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .collection .content {
    padding: 1rem;
    height: 22vw;
    background-color: white;
    box-shadow:
      0 4px 8px 0 rgba(0, 0, 0, 0.1),
      0 6px 20px 0 rgba(0, 0, 0, 0.1);
    border-radius: 2.5rem;
    margin-top: 1rem;
    overflow: hidden;
  }

  .swiper-slide img {
    width: 18vw;
  }

  .text-content {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }
  .text-content h3 {
    font-size: 1.6vw;
    font-weight: 500;
  }

  /* Bigger text, taller cards on mobile view */
  @media (max-width: 1024px) {
    .text-content h3 {
      font-size: 4vw;
      line-height: 1.1;
    }

    .swiper-slide img {
      width: 50vw;
    }

    .swiper {
      height: 70vw;
    }

    .collection .content {
      height: 60vw;
    }
  }

  /* .text-content p {
    max-width: 22rem;
    font-size: 0.8rem;
    font-weight: 400;
    text-align: center;
  } */
</style>

<script setup>
import Divider from './Divider.vue';
import Carousel from './Carousel.vue';

const locationImages = [
  'location/location1.jpg',
  'location/location2.jpg',
  'location/location3.jpg',
  'location/location4.jpg',
  'location/location5.jpg',
];

const piattiImages = [
  'piatti/piatto1.jpg',
  'piatti/piatto2.jpg',
  'piatti/piatto3.jpg',
  'piatti/piatto4.jpg',
  'piatti/piatto5.jpg',
  'piatti/piatto6.jpg',
  'piatti/piatto7.jpg',
  'piatti/piatto8.jpg',
  'piatti/piatto9.jpg',
];
</script>

<template>
  <main>
    <div class="container-md py-3">
      <section class="location rounded rounded-3">
        <h1 class="text-center py-2 display-3 fw-light">
          Claro de Luna, Ristorante&Pizzeria
        </h1>
        <h3 class="text-center display-5">Di Massimo&Ramona</h3>
        <Divider />
        <h5 class="title text-center mb-3">
          <span class="text">La Location</span>
        </h5>
        <p class="first">
          Il nostro ristorante abbraccia uno stile tradizionale tipico delle
          nostre zone, in un clima caldo e accogliente d’inverno e fresco e
          silenzioso d’estate.
        </p>
        <p>
          Il locale si adatta a pranzi e cene con la famiglia e gli amici ma
          anche a cerimonie e incontri di lavoro. La veranda esterna, nel
          periodo estivo, offre una fresca brezza per ripararsi dal caldo delle
          città.
        </p>

        <Carousel :slides="locationImages" />
        <Divider />
      </section>

      <section class="ristorante rounded-3">
        <h5 class="title text-center mb-3">
          <span class="text">Ristorante&Pizzeria</span>
        </h5>

        <p class="first">
          Il nostro ristorante offre un menù ricco, che affonda le proprie
          radici nella tradizione della cucina locale del nostro appennino e si
          estende verso una cucina moderna e innovativa, rielaborando piatti
          tipici in chiave rivisitata. I piatti uniscono il sapore del mare al
          piacere delle carni locali con gusto e fantasia.
        </p>

        <p>
          I nostri dolci, creati appositamente dallo chef, si rivolgono ad un
          palato raffinato ed esigente, amante dei gusti dolci ma delicati.
        </p>

        <p>
          Offriamo menù a base di carne del luogo e pesce fresco e per chi non
          gradisse la cucina e per i bambini, offriamo un servizio di pizzeria
          con forno a legna!
        </p>

        <Carousel :slides="piattiImages" />
        <Divider />
      </section>

      <section class="menu rounded-3">
        <h5 class="title text-center mb-3">
          <span class="text">Il Menù</span>
        </h5>

        <h5 class="fw-bold text-center">La Cucina</h5>
      </section>
    </div>
  </main>
</template>

<style lang="scss" scoped>
@import '@/assets/style/partials/variables';
@import '@/assets/style/partials/mixin';

main {
  background: linear-gradient(215deg, $primary, $secondary);
  background-size: 400% 400%;

  -webkit-animation: AnimationName 30s ease infinite;
  -moz-animation: AnimationName 30s ease infinite;
  animation: AnimationName 30s ease infinite;

  .location {
    @include push-up;
    @include card;
  }

  .ristorante {
    @include push-up-little;
    @include card;
  }

  .menu {
    @include card;

    h5 {
      color: $black;
    }
  }
}

@-webkit-keyframes AnimationName {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
@-moz-keyframes AnimationName {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
@keyframes AnimationName {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
</style>

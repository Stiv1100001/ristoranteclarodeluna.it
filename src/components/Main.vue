<script setup>
  import Divider from './Divider.vue';
  import Carousel from './Carousel.vue';
  import MenuItem from './MenuItem.vue';
  import * as piattiRistorante from '@/assets/data/ristorante.json';
  import * as pizzeria from '@/assets/data/pizzeria.json';
  import * as vini from '@/assets/data/vini.json';
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
    <div class="container-lg py-3">
      <section class="location rounded rounded-3" id="location">
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

      <section class="ristorante rounded-3" id="ristorante">
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

      <section class="menu rounded-3" id="menu">
        <h5 class="title text-center mb-3">
          <span class="text">Il Menù</span>
        </h5>

        <h5 class="fw-bold text-center">La Cucina</h5>
        <div id="ristorante">
          <h6 class="menu-title">Antipasti</h6>
          <h6 class="menu-subtitle">Pesce</h6>
          <MenuItem
            v-for="antipasto in piattiRistorante.antipasti.pesce"
            :key="antipasto.nome"
            :plate="antipasto"
          />

          <h6 class="menu-subtitle">Carne</h6>
          <MenuItem
            v-for="antipasto in piattiRistorante.antipasti.carne"
            :key="antipasto.nome"
            :plate="antipasto"
          />

          <h6 class="menu-title">Primi</h6>
          <MenuItem
            v-for="primi in piattiRistorante.primi"
            :key="primi.nome"
            :plate="primi"
          />

          <h6 class="menu-title">Secondi</h6>
          <MenuItem
            v-for="secondi in piattiRistorante.secondi"
            :key="secondi.nome"
            :plate="secondi"
          />

          <h6 class="menu-title">Contorni</h6>
          <MenuItem
            v-for="contorni in piattiRistorante.contorni"
            :key="contorni.nome"
            :plate="contorni"
          />

          <h6 class="menu-title">Dolci</h6>
          <MenuItem
            v-for="dolci in piattiRistorante.dolci"
            :key="dolci.nome"
            :plate="dolci"
          />

          <h6 class="menu-title">Sorbetti</h6>
          <MenuItem
            v-for="sorbetti in piattiRistorante.sorbetti"
            :key="sorbetti.nome"
            :plate="sorbetti"
          />

          <h6 class="menu-title">Vini</h6>
          <MenuItem
            v-for="vini in piattiRistorante.vini"
            :key="vini.nome"
            :plate="vini"
          />

          <h6 class="menu-title">Menù fisso</h6>
          <MenuItem
            :key="piattiRistorante.menuFisso.name"
            :plate="piattiRistorante.menuFisso"
          />
        </div>

        <Divider />
        <h5 class="fw-bold text-center">La Pizzeria</h5>
        <div class="pizzeria">
          <h6 class="menu-title">Pizze classiche</h6>
          <MenuItem
            v-for="pizza in pizzeria.classiche"
            :key="pizza.nome"
            :plate="pizza"
          />

          <h6 class="menu-title">Specialità</h6>
          <MenuItem
            v-for="pizza in pizzeria.specialita"
            :key="pizza.nome"
            :plate="pizza"
          />
        </div>

        <Divider />

        <h5 class="fw-bold text-center">Carta dei vini</h5>
        <div class="vini">
          <MenuItem v-for="vino in vini.vini" :key="vino.nome" :plate="vino" />
        </div>

        <Divider />
      </section>

      <section class="dove rounded-3" id="dove">
        <h5 class="title text-center mb-3">
          <span class="text">Dove trovarci</span>
        </h5>

        <p class="first">
          Potete trovarci a Montefredente, nel comune di San Benedetto Val di
          Sambro, in mezzo alle montagne dell’Appennino Tosco-Emiliano. Venite a
          godere del tramonto sui monti e del fresco in estate, o un locale
          caldo e accogliente in inverno!
        </p>

        <p>Gradite le prenotazioni</p>
        <p class="mb-0">324 613 6737</p>
        <p>clarodeluna787@gmail.com</p>

        <div class="row">
          <div class="col-12 col-md-6 text-center">
            <h4>Orario estivo</h4>
            <h6>12:00 – 14:00</h6>
            <h6>19:00 – 22:00</h6>
            <h6>Chiuso il martedì</h6>
          </div>
          <div class="col-12 col-md-6">
            <h4 class="text-center">Orario invernale</h4>
            <h6>12:00 – 14:00</h6>
            <h6>19:00 – 22:00</h6>
            <h6>Chiuso il martedì e il lunedì sera</h6>
          </div>
        </div>
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

      .menu-title {
        font-size: 1.2rem;
        font-style: italic;
        text-decoration: underline;
        font-weight: 600;
      }

      .menu-subtitle {
        font-size: 1.1rem;
        font-style: italic;
      }
    }

    .dove {
      @include card;
      @include push-down-little;
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

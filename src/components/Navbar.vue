<script setup>
  import { ref } from 'vue';

  const navItems = ref([
    {
      text: 'Claro de Luna',
      href: '#',
      active: true,
    },
    {
      text: 'Location',
      href: '#location',
      active: false,
    },
    {
      text: 'Ristorante&Pizzeria',
      href: '#ristorante',
      active: false,
    },
    {
      text: 'Il Menù',
      href: '#menu',
      active: false,
    },
    {
      text: 'Dove trovarci',
      href: '#dove',
      active: false,
    },
  ]);

  function setActive(index) {
    navItems.value.forEach((item) => (item.active = false));
    navItems.value[index].active = true;
  }
</script>

<template>
  <header>
    <nav
      class="navbar navbar-expand-lg navbar-light bg-light vw-100 py-2 position-fixed"
      id="navbar"
    >
      <div class="container-fluid w-100">
        <div class="d-flex justify-content-between px-3" id="left">
          <a class="navbar-brand claro fs-4" href="#">Claro De Luna</a>
          <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#menu-list"
            aria-controls="menu-list"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <span class="navbar-toggler-icon"></span>
          </button>
        </div>
        <div class="collapse navbar-collapse" id="menu-list">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li
              v-for="(item, index) in navItems"
              :key="item.href"
              class="nav-item"
              :class="{ active: item.active }"
            >
              <a class="nav-link" :href="item.href" @click="setActive(index)">{{
                item.text
              }}</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
</template>

<style lang="scss" scoped>
  @import '@/assets/style/partials/variables';

  header {
    background-image: url('@/assets/img/jumbotron.jpg');
    background-size: cover;
    background-attachment: fixed;
    background-position: center -20em;
    height: 50vh;
  }

  nav {
    background-color: $secondary !important;
    z-index: 200;

    #left {
      width: 100%;
    }

    .claro {
      color: $primary;
      text-shadow: 0 0 5px $black;
    }

    .navbar-collapse {
      flex-basis: content;
      flex-grow: 0;
    }

    .navbar-toggler {
      border-color: $primary;
      &:focus {
        box-shadow: 0 0 2px 0.25rem $primary;
      }
    }

    .nav-item {
      a {
        color: $black;
        &:hover {
          color: black;
        }
      }
      &.active {
        a {
          color: black;
          font-weight: 600;
        }
      }
    }
  }

  @media screen and (min-width: 992px) {
    nav {
      #left {
        width: auto;
      }
    }
  }
</style>

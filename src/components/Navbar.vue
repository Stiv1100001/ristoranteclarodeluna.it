<script setup>
import { ref } from 'vue';

const navItems = ref([
  {
    text: 'Home',
    href: '#',
    active: true,
  },
  {
    text: 'Location',
    href: '#',
    active: false,
  },
  {
    text: 'Ristorante&Pizzeria',
    href: '#',
    active: false,
  },
  {
    text: 'Il Menù',
    href: '#',
    active: false,
  },
  {
    text: 'Dove trovarci',
    href: '#',
    active: false,
  },
]);

function setActive(index) {
  this.navItems.forEach((item) => (item.active = false));
  this.navItems[index].active = true;
}
</script>

<template>
  <header>
    <nav
      class="navbar navbar-expand-lg navbar-light bg-light position-fixed w-100"
    >
      <div class="container justify-content-between">
        <a class="navbar-brand claro fs-4" href="#">Claro de Luna</a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarNavDropdown"
          aria-controls="navbarNavDropdown"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNavDropdown">
          <ul class="navbar-nav">
            <li
              v-for="(item, index) in navItems"
              :key="item.text"
              class="nav-item"
              :class="{ active: item.active }"
            >
              <a class="nav-link" href="#" @click="setActive(index)">{{
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
</style>

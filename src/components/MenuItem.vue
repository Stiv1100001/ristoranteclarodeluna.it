<script setup>
  import { computed } from '@vue/runtime-core';

  const props = defineProps({
    plate: {
      type: Object,
      required: true,
    },
  });

  const price = computed(() => {
    return props.plate.prezzo?.toFixed(2);
  });
</script>

<template>
  <div class="menu-item mb-3">
    <div class="upper d-flex align-items-center">
      <div class="name">{{ props.plate.nome }}</div>
      <div class="separator flex-grow-1"></div>
      <div class="price" v-if="price">{{ price }}&euro;</div>
    </div>
    <p class="description p-0 m-0" v-if="props.plate.descrizione">
      {{ props.plate.descrizione }}
    </p>
    <p class="description p-0 m-0" v-else-if="props.plate.ingredienti">
      {{ props.plate.ingredienti }}
    </p>
    <p class="description p-0 m-0" v-else-if="props.plate.marca">
      {{ props.plate.marca }}
    </p>
  </div>
</template>

<style lang="scss" scoped>
  @import '@/assets/style/partials/variables';

  .upper {
    .name {
      font-size: 1rem;
      color: $secondary;
      font-weight: 600;
    }

    .separator {
      margin-inline: 1rem;
      border-bottom: 3px $accent dotted;
    }

    .price {
      // color: black;
      font-size: 1.2rem;
      text-shadow: 0px 0px 3px 3px black;
    }
  }
  .description {
    font-size: 0.9rem;
  }
</style>

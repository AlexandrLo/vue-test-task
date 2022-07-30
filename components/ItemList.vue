<template>
  <transition-group name="list" tag="div" class="items-grid">
    <ItemCard
      v-for="item in items"
      :key="item.id"
      :image="item.image"
      :name="item.name"
      :description="item.description"
      :price="item.price"
    />
  </transition-group>
</template>

<script>
  import ItemCard from "./ItemCard.vue";
  export default {
    components: { ItemCard },
    props: {
      items: {
        type: Array,
        default() {
          return [];
        },
      },
    },
  };
</script>

<style lang="scss" scoped>
  .items-grid {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    grid-column-gap: 1rem;
    grid-row-gap: 1rem;
  }
  @media (min-width: $breakpoint-md) {
    .items-grid {
      grid-template-columns: repeat(1, 1fr);
    }
  }
  @media (min-width: $breakpoint-lg) {
    .items-grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  @media (min-width: $breakpoint-xl) {
    .items-grid {
      grid-template-columns: repeat(3, 1fr);
    }
  }
</style>

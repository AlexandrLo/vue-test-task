<template>
  <div class="container">
    <header class="header">
      <h1>Добавление товара</h1>
      <StyledSelect />
    </header>
    <main class="content">
      <div class="sidebar">
        <CreateItemCard />
      </div>
      <ItemList :items="items" />
    </main>
  </div>
</template>

<script>
  import StyledSelect from "@/components/StyledSelect.vue";
  import items from "@/static/items.json";
  export default {
    name: "IndexPage",
    components: { StyledSelect },
    data() {
      return {
        items,
      };
    },
  };
</script>

<style lang="scss" scoped>
  .header {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 1rem;
    @media (min-width: $breakpoint-md) {
      margin-bottom: 0;
      flex-direction: row;
    }
  }
  .container {
    margin: auto;
    max-width: 1440px;
    padding: 2rem;
  }
  .content {
    display: flex;
    align-items: flex-start;
    flex-direction: column;
    & > .sidebar {
      position: static;
      margin-bottom: 1rem;
      min-width: 100%;
    }
    @media (min-width: $breakpoint-md) {
      flex-direction: row;
      & > .sidebar {
        position: sticky;
        top: 1.5rem;
        margin-right: 1rem;
        min-width: 332px;
      }
    }
  }
</style>

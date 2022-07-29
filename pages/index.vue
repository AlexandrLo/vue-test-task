<template>
  <div class="container">
    <div class="header">
      <h1>Добавление товара</h1>
      <StyledSelect />
    </div>

    <div class="content">
      <div class="sidebar">
        <CreateItemCard />
      </div>
      <div class="list">
        <ItemList />
      </div>
    </div>
  </div>
</template>

<script>
  import StyledSelect from "~/components/StyledSelect.vue";
  export default {
    name: "IndexPage",
    components: { StyledSelect },
  };
</script>

<style lang="scss" scoped>
  .header {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: start;
    margin-bottom: 1rem;
    @media (min-width: $breakpoint-md) {
      flex-direction: row;
      align-items: center;
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
      margin-bottom: 1rem;
      min-width: 100%;
    }
    & > .list {
    }
    @media (min-width: $breakpoint-md) {
      flex-direction: row;
      & > .sidebar {
        margin-right: 1rem;
        min-width: 332px;
      }
    }
  }
</style>

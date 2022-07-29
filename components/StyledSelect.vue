<template>
  <select>
    <option>По умолчанию</option>
  </select>
</template>

<script>
  export default {};
</script>

<style lang="scss" scoped>
  select {
    height: 2.25rem;
    outline: none;
    border: none;
    border-radius: 0.25rem;
    border-right: 1rem solid transparent;
    padding-left: 1rem;
    box-shadow: $shadow-300;
    background-color: $white;
    color: $gray-500;
    transition: $transition;
    transition-property: transform, box-shadow;
    &:hover {
      transform: translateY(-0.25rem);
      box-shadow: $shadow-400;
    }
    &:active {
      transform: translateY(-0.125rem);
      box-shadow: $shadow-300;
    }
  }
</style>

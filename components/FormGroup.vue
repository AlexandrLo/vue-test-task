<template>
  <div class="form-group">
    <slot />
  </div>
</template>

<style lang="scss" scoped>
  .form-group {
    margin-bottom: 1rem;
    display: flex;
    flex-direction: column-reverse;
    &:last-of-type {
      margin-bottom: 1.5rem;
    }
    & > input[required] + label::after {
      content: "";
      position: absolute;
      display: inline-block;
      width: 0.25rem;
      height: 0.25rem;
      border-radius: 100%;
      background: $red-500;
    }
  }
</style>

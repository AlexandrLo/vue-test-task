<template>
  <input v-bind="$props" />
</template>

<style lang="scss" scoped>
  input {
    &[type="text"] {
      background: $white;
      border: 2px solid transparent;
      border-radius: 0.25rem;
      box-shadow: $shadow-300;
      height: 2.25rem;
      padding-inline: 1rem;
      font-size: 0.75rem;
      transition: $transition;
      transition-property: border-color;
      outline: none;
      &::placeholder {
        color: $gray-500;
      }
      &:hover {
        border-color: $gray-400;
      }
      &:active,
      &:focus {
        border-color: $dark;
      }
    }
    &[type="submit"] {
      background: $green-500;
      color: $white;
      border: none;
      border-radius: 0.625rem;
      box-shadow: $shadow-300;
      height: 2.25rem;
      padding-inline: 1rem;
      font-size: 0.75rem;
      font-weight: 600;
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
  }
</style>

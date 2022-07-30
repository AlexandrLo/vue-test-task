<template>
  <textarea v-bind="$props"></textarea>
</template>

<style lang="scss" scoped>
  textarea {
    background: $white;
    border: 2px solid transparent;
    border-radius: 0.25rem;
    box-shadow: $shadow-300;
    padding-inline: 1rem;
    padding-block: 0.625rem;
    font-size: 0.75rem;
    transition: $transition;
    transition-property: border-color;
    outline: none;
    resize: vertical;
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
</style>

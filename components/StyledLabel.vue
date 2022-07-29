<template>
  <label v-bind="$props">
    <slot />
  </label>
</template>

<style lang="scss" scoped>
label {
  position: relative;
  font-size: 0.625rem;
  margin-bottom: 0.25rem;
}
</style>

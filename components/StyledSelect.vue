<template>
  <div class="select-wrapper">
    <select>
      <option>По умолчанию</option>
    </select>
    <div class="chevron-wrapper">
      <img src="@/assets/svg/chevron-down.svg" alt="Стрелка" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .select-wrapper {
    position: relative;
    & > .chevron-wrapper {
      position: absolute;
      right: 1rem;
      color: $gray-500;
      height: 100%;
      right: 1rem;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      pointer-events: none;
    }
    & > select {
      font-size: 0.75rem;
      height: 2.25rem;
      padding-left: 1rem;
      padding-right: 1.75rem;
      border: 2px solid transparent;
      border-radius: 0.25rem;
      background-color: $white;
      color: $gray-500;
      box-shadow: $shadow-300;
      -webkit-appearance: none;
      -moz-appearance: none;
      appearance: none;
      outline: none;
      transition: $transition;
      transition-property: transform, box-shadow;
      &:hover {
        border-color: $gray-400;
      }
      &:active,
      &:focus {
        border-color: $dark;
      }
    }
  }
</style>

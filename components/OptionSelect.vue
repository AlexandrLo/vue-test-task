<template>
  <div class="select-wrapper">
    <select :value="value" @input="$emit('input', $event.target.value)">
      <option
        v-for="(option, index) in options"
        :key="index"
        :value="option.value"
        :selected="value === option.value"
      >
        {{ option.name }}
      </option>
    </select>
    <div class="chevron-wrapper">
      <img src="@/assets/svg/chevron-down.svg" alt="Стрелка" />
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      value: {
        type: String,
        default: "",
      },
      options: {
        type: Array,
        required: true,
      },
    },
  };
</script>

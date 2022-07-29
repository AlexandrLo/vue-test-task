<template>
  <div class="card">
    <form>
      <FormGroup>
        <StyledInput
          id="new-item-name"
          type="text"
          placeholder="Введите наименование товара"
          required
        />
        <StyledLabel for="new-item-name">Наименование товара</StyledLabel>
      </FormGroup>

      <FormGroup>
        <StyledInput
          id="new-item-description"
          type="text"
          placeholder="Введите описание товара"
        />
        <StyledLabel for="new-item-description">Описание товара</StyledLabel>
      </FormGroup>

      <FormGroup>
        <StyledInput
          id="new-item-image"
          type="text"
          placeholder="Введите ссылку на изображение товара"
          required
        />
        <StyledLabel for="new-item-image">
          Ссылка на изображение товара
        </StyledLabel>
      </FormGroup>

      <FormGroup>
        <StyledInput
          id="new-item-price"
          type="text"
          placeholder="Введите цену товара"
          required
        />
        <StyledLabel for="new-item-price">Цена товара</StyledLabel>
      </FormGroup>

      <StyledInput type="submit" value="Добавить товар" />
    </form>
  </div>
</template>

<script>
  import StyledInput from "./StyledInput.vue";
  import StyledLabel from "./StyledLabel.vue";
  import FormGroup from "./FormGroup.vue";
  export default { components: { StyledInput, StyledLabel, FormGroup } };
</script>

<style lang="scss" scoped>
  .card {
    border-radius: 0.25rem;
    background: $white;
    box-shadow: $shadow-500;
    padding: 1.5rem;
  }
</style>

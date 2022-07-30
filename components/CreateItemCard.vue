<template>
  <div class="card">
    <form @submit.prevent="createItem">
      <div class="form-group">
        <p v-if="errors.name" class="error">{{ errors.name }}</p>
        <input
          id="new-item-name"
          v-model="name"
          :class="errors.name ? 'invalid' : ''"
          type="text"
          placeholder="Введите наименование товара"
          required
        />
        <label for="new-item-name">Наименование товара</label>
      </div>

      <div class="form-group">
        <textarea
          id="new-item-description"
          v-model="description"
          placeholder="Введите описание товара"
          rows="5"
        />
        <label for="new-item-description">Описание товара</label>
      </div>

      <div class="form-group">
        <p v-if="errors.image" class="error">{{ errors.image }}</p>
        <input
          id="new-item-image"
          v-model="image"
          :class="errors.image ? 'invalid' : ''"
          type="text"
          placeholder="Введите ссылку на изображение товара"
          required
        />
        <label for="new-item-image"> Ссылка на изображение товара </label>
      </div>

      <div class="form-group">
        <p v-if="errors.price" class="error">{{ errors.price }}</p>
        <input
          id="new-item-price"
          v-model="price"
          :class="errors.price ? 'invalid' : ''"
          type="number"
          placeholder="Введите цену товара"
          required
        />
        <label for="new-item-price">Цена товара</label>
      </div>

      <input ref="submit" type="submit" value="Добавить товар" disabled />
    </form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        errors: {},
        name: "",
        description: "",
        image: "",
        price: null,
      };
    },
    computed: {
      newItem() {
        return {
          name: this.name,
          description: this.description,
          image: this.image,
          price: +this.price,
        };
      },
    },
    watch: {
      newItem() {
        this.validate();
      },
    },
    methods: {
      validate() {
        this.errors = {};
        if (!this.newItem.name) {
          this.errors.name = "Поле является обязательным";
        }
        if (!this.newItem.image) {
          this.errors.image = "Поле является обязательным";
        }
        if (!this.newItem.price) {
          this.errors.price = "Поле является обязательным";
        }
        if (Object.keys(this.errors).length === 0) {
          this.$refs.submit.disabled = false;
        } else {
          this.$refs.submit.disabled = true;
        }
      },
      createItem(e) {
        this.$emit("createItem", { id: this._uid, ...this.newItem });
      },
    },
  };
</script>

<style lang="scss" scoped>
  .card {
    border-radius: 0.25rem;
    background: $white;
    box-shadow: $shadow-500;
    padding: 1.5rem;
    & > form {
      display: flex;
      flex-direction: column;
    }
  }
</style>

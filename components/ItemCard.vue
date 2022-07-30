<template>
  <div class="card">
    <div class="image-wrapper">
      <img :src="image" alt="Изображение товара" />
    </div>
    <div class="body">
      <h3>{{ name }}</h3>
      <p class="description">
        {{ description }}
      </p>
      <p class="price">
        {{
          new Intl.NumberFormat("ru-RU", {
            style: "decimal",
          }).format(price)
        }}
        руб.
      </p>
    </div>
    <button class="delete-button">
      <img src="@/assets/svg/delete.svg" alt="Удалить товар" />
    </button>
  </div>
</template>

<script>
  export default {
    props: {
      image: {
        type: String,
        default: "",
      },
      name: {
        type: String,
        default: "Нет наименования товара",
      },
      description: {
        type: String,
        default: "Нет описания",
      },
      price: {
        type: Number,
        default: 0,
      },
    },
  };
</script>

<style lang="scss" scoped>
  .card {
    position: relative;
    border-radius: 0.25rem;
    background: $white;
    box-shadow: $shadow-500;
    .image-wrapper {
      border-top-left-radius: 0.25rem;
      border-top-right-radius: 0.25rem;
      height: 200px;
      width: 100%;
      overflow: hidden;
      & > img {
        height: 100%;
        width: 100%;
        object-fit: cover;
      }
    }
    .body {
      padding: 1rem;
    }
    .description {
      margin-bottom: 2rem;
    }
    .price {
      font-size: 1.5rem;
      font-weight: 600;
    }
    .delete-button {
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1;
      position: absolute;
      right: -0.5rem;
      top: -0.5rem;
      opacity: 0;
      border: none;
      height: 2rem;
      width: 2rem;
      background: $red-500;
      color: $white;
      border-radius: 0.625rem;
      box-shadow: $shadow-300;
      transition: $transition;
      transition-property: transform, box-shadow, opacity;
      &:focus {
        opacity: 1;
      }
    }
    &:hover > .delete-button {
      opacity: 1;
      &:hover {
        transform: translateY(-0.25rem);
        box-shadow: $shadow-400;
      }
      &:active {
        transform: translateY(0);
        box-shadow: $shadow-300;
      }
    }
  }
</style>

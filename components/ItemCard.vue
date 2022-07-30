<template>
  <div class="card">
    <div class="image-wrapper">
      <img
        src="https://images.unsplash.com/photo-1542826438-bd32f43d626f?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1592&q=80"
        alt="Item image"
      />
    </div>
    <div class="body">
      <div class="title">Наименование товара</div>
      <div class="description">
        Довольно-таки интересное описание товара в несколько строк.
        Довольно-таки интересное описание товара в несколько строк
      </div>
      <div class="price">10 000 руб.</div>
    </div>
    <button class="delete-button">
      <img src="@/assets/svg/delete.svg" />
    </button>
  </div>
</template>

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
    .title {
      font-size: 1.25rem;
      font-weight: 600;
      margin-bottom: 1rem;
    }
    .description {
      font-size: 1rem;
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

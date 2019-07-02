<template>
  <div class="navbar">
    <div class="navbar__brand">
      <span class="navbar__title">
        BISS
      </span>
      <span class="navbar__desc">
        Safe IoT with Blockchain
      </span>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.navbar {
  &__brand {
    width: 100%;
    height: 5rem;
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(to right, #4BB5F8, #8EF6FC);
  }

  &__title {
    font-weight: 900;
    font-size: 3.5rem;
  }

  &__desc {
    font-weight: 300;
    font-size: 1.5rem;
    margin-left: 0.8rem;
  }

  @media (max-width: 600px) {
    &__brand {
      height: 4rem;
    }

    &__title {
      font-size: 2.5rem;
    }

    &__desc {
      font-size: 1rem;
    }
  }
}
</style>

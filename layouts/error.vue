<template>
  <div class="error-layout">
    <div class="error-content">
      <h1 class="error-title">Ошибка 404</h1>
      <nuxt-link to="/">Вернуться на главную</nuxt-link>
    </div>
  </div>
</template>

<script>
  export default {
    name: "error"
  }
</script>

<style lang="scss" scoped>
  .error-title {
    color: brown;
  }

  .error-layout {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    flex-direction: column;
  }

  .error-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-top: 4rem;
  }
</style>

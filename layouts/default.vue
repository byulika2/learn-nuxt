<template>
  <div>
    <header class="title">
      <NuxtLink class="logo" to="/">Nuxt Shopping</NuxtLink>
<!--      <NuxtLink to="/">홈 페이지</NuxtLink>-->
<!--      <NuxtLink to="/main">메인 페이지</NuxtLink>-->
<!--      <NuxtLink to="/product">상품 페이지</NuxtLink>-->
    </header>
    <Nuxt/>
  </div>
</template>

<script>
export default {
  // created() {
  //   console.log(this.$route)
  // },
}
</script>

<style scoped>
header {
  height: 60px;
  display: flex;
  align-items: center;
  padding: 0 0.5rem;
}
.logo {
  font-weight: 900;
}
.logo:visited {
  color: inherit;
}
</style>

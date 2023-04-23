<template>
  <div>
    <div class="container">
      <div class="main-panel">
        <img
          class="product-image"
          :src="product.imageUrl"
          :alt="product.name"
        />
      </div>
      <div class="side-panel">
        <p class="name">{{ product.name }}</p>
        <p class="price">{{ product.price }}</p>
        <button class="btn" @click="addToCart">Add to Cart</button>
      </div>
    </div>
  </div>
</template>

<script>
import { fetchProductById } from '~/api'
export default {
  // this 가아닌 context를 사용해야함
  // asyncData의 에러 핸들링: https://joshua1988.github.io/vue-camp/nuxt/data-fetching.html#asyncdata%EC%9D%98-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0
  // Nuxt.js context 속성 문서: https://nuxtjs.org/docs/internals-glossary/context/
  async asyncData({ params }) {
    const response = await fetchProductById(params.id)
    const product = response.data

    return { product }
  },
  methods:{
    addToCart(){
      this.$store.commit('addCartItem', this.product);
      this.$router.push('/cart')
    },
  }
}
</script>
<style scoped>
.container {
  display: flex;
  justify-content: center;
  margin: 2rem 0;
}
.product-image {
  width: 500px;
  height: 375px;
}
.side-panel {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 220px;
  text-align: center;
  padding: 0 1rem;
}
</style>

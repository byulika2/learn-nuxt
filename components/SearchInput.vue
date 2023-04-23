<template>
  <div class="input-wrapper flex">
    <input
      type="text"
      class="search-input"
      :value="searchKeyword"
      @input="$emit('input', $event.target.value)"
    />
    <button class="btn" type="button" @click="$emit('search')">search</button>
  </div>
</template>

<script>
export default {
  props: {
    // 상위에서 컴퍼넌트 이용시 props의 이름은 value를 사용해야함 다른이름 사용할려면 model사용
    value: {
      type: String,
      default: () => '',
    },
  },
}
</script>

<style scoped>
.input-wrapper {
  height: 40px;
  margin: 1rem 0;
}
.search-input {
  width: 200px;
  font-size: 1.2rem;
  font-weight: 500;
}
.btn {
  font-size: 1.2rem;
  font-weight: 500;
}
</style>

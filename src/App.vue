<template>
  <div class="wrapper">
    <TheHeader/>
    <main class="main">
      <AppForm
        class="main__form"
        @add-product="addProduct"
      />
      <AppList
        class="main__list"
        :products="products"
      />
    </main>
  </div>
</template>
<script>
import TheHeader from './components/TheHeader'
import AppForm from './components/AppForm'
import AppList from './components/AppList'
import {ref} from 'vue'

export default {
  setup() {
    const products = ref([])
    const addProduct = product => {
      console.log(product)
      products.value.push(product)
      console.log(products.value)
    }
    return {
      products,
      addProduct
    }
  },
  components: { TheHeader, AppForm, AppList }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  border: 0;
  outline: 0;
  background: 0;
  box-sizing: border-box;
  text-decoration: none;
  list-style: none;
  font-family: 'Source Sans Pro', sans-serif;
}

body {
  width: 100%;
  min-height: 100vh;
  background: rgba(255, 254, 251, 0.8);
}

.wrapper {
  max-width: 1440px;
  margin: 0 auto;
  padding: 32px;
}

.main {
  display: flex;
  align-items: flex-start;

  &__form {
    min-width: 332px;
    margin-right: 16px;
  }

  &__list {
    max-width: 1028px;
  }
}
</style>

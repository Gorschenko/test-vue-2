<template>
  <div class="wrapper">
    <TheHeader
      v-model="sorting"
    />
    <main class="main">
      <AppForm
        class="main__form"
        @add-product="addProduct"
      />
      <AppList
        class="main__list"
        :products="sortedProducts"
        @delete-product="deleteProduct"
      />
    </main>
  </div>
</template>
<script>
import TheHeader from './components/TheHeader'
import AppForm from './components/AppForm'
import AppList from './components/AppList'
import {ref, computed, onMounted} from 'vue'

export default {
  setup() {
    onMounted(() => {
      if (localStorage.getItem('products')) {
        try {
          products.value = JSON.parse(localStorage.getItem('products'))
        } catch(e) {
          localStorage.removeItem('products')
        }
      }
    })
    const products = ref([])

    const addProduct = product => {
      products.value.splice(products.value.length, 0, product)
      saveProducts()
    }
    const deleteProduct = idx => {
      products.value.splice(idx, 1)
      saveProducts()
    }
    const saveProducts = () => localStorage.setItem('products', JSON.stringify(products.value))

    const sorting = ref('default')
    const sortedProducts = computed(() => {
      if (sorting.value === 'max') {
        return products.value.slice().sort((a, b) => Number(a.price) - Number(b.price))
      }
      if (sorting.value === 'min') {
        return products.value.slice().sort((a, b) => Number(b.price) - Number(a.price))
      }
      if (sorting.value === 'name') {
        return products.value.slice().sort((a, b) => (a.name.toLowerCase() > b.name.toLowerCase()) ? 1 : -1)
      }
      return products.value
    })

    return {
      products,
      addProduct,
      deleteProduct,
      saveProducts,
      sorting,
      sortedProducts
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

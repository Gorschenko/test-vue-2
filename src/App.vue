<template>
<div class="wrapper">
  <main class="main">
    <AppForm class="main__form"/>
    <AppList class="main__list"/>
  </main>
</div>
</template>
<script>
import AppForm from './components/AppForm'
import AppList from './components/AppList'

export default {
components: { AppForm, AppList }
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

.wrapper {
  width: 100%;
  min-height: 100vh;
  background: rgba(255, 254, 251, 0.8);
}

.main {
  display: flex;
  align-items: flex-start;
  max-width: 1440px;
  margin: 0 auto;
  padding: 32px;
  &__form {
    min-width: 332px;
    margin-right: 16px;
  }
  &__list {
    max-width: 1028px;
  }
}
</style>

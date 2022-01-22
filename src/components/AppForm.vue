<template>
<form class="form" @submit.prevent>
  <div class="form__control">
    <label for="name" class="form__control-label">
      <span class="form__control-label-mark"></span>
      Наименование товара
    </label>
    <input 
      id="name"
      type="text"
      class="form__control-input" 
      placeholder="Введите наименование товара"
      v-model="name"
    >
  </div>
  <div class="form__control">
    <label for="description" class="form__control-label">
      Описание товара
    </label>
    <textarea
      id="description"
      type="text"
      class="form__control-textarea" 
      placeholder="Введите описание товара"
      v-model="description"
    ></textarea>
  </div>
  <div class="form__control">
    <label for="image" class="form__control-label">
      <span class="form__control-label-mark"></span>
      Ссылка на изображение товара
    </label>
    <input 
      id="image"
      type="text"
      class="form__control-input" 
      placeholder="Введите ссылку"
      v-model="image"
    >
  </div>
  <div class="form__control">
    <label for="price" class="form__control-label">
      <span class="form__control-label-mark"></span>
      Цена товара
    </label>
    <input 
      id="price"
      type="text"
      class="form__control-input" 
      placeholder="Введите цену"
      v-model="price"
    >
  </div>
  <button class="form__button" :disabled="isDisabled">Добавить товар</button>
</form>
</template>

<script>
import {ref, computed} from 'vue'
export default {
  setup() {
    const name = ref('')
    const description = ref('')
    const image = ref('')
    const price = ref('')
    const isDisabled = computed(() => !name.value || !image.value || !price.value)
    return {
      name, description, image, price,
      isDisabled
    }
  }
}
</script>

<style scoped lang="scss">


.form {
  padding: 24px;
  border-radius: 4px;
  background: rgba(255, 254, 251, 1);
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);

  &__control {
    width: 100%;
    margin-bottom: 16px;

    &-label {
      position: relative;
      display: inline-block;
      margin-bottom: 4px;
      font-size: 10px;
      line-height: 13px;
      letter-spacing: -0.02rem;
      color: rgba(73, 72, 94, 1);

      &-mark {
        position: absolute;
        top: 0;
        left: 100%;
        width: 4px;
        height: 4px;
        border-radius: 50%;
        background: rgba(255, 132, 132, 1);
      }
    }

    &-input {
      width: 100%;
      height: 36px;
      padding: 10px 16px 11px 16px;
      border-radius: 4px;
      box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
      font-size: 12px;
      color: rgba(63, 63, 63, 1);
    }

    &-textarea {
      width: 100%;
      height: 108px;
      padding: 10px 16px 11px 16px;
      border-radius: 4px;
      box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
      font-size: 12px;
      color: rgba(63, 63, 63, 1);
      resize: none;
    }
  }

  &__button {
    width: 100%;
    height: 36px;
    margin-top: 8px;
    padding: 10px 0 11px 0;
    border-radius: 10px;
    font-size: 12px;
    line-height: 15px;
    letter-spacing: -0.02em;
    font-weight: 600;
    background: rgba(123, 174, 115, 1);
    color: rgba(255, 255, 255, 1);   
    cursor: pointer;
    
    &:disabled {
      background: rgba(238, 238, 238, 1);
      color: rgba(180, 180, 180, 1);
      cursor: not-allowed;
    }
  }

  ::placeholder {
  color: rgba(180, 180, 180, 1)
  }
}
</style>
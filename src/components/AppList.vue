<template>
<ul class="list">
  <li class="list__item">
    <div class="list__item-remove">
      <img src="../assets/remove.svg">
    </div>
    <div
      class="list__item-image"
      style="background: url(https://avatars.mds.yandex.net/get-zen_doc/98986/pub_6117c0c474a4fa168760abb3_6117c0c6cdef433a852d14f7/scale_1200); background-size: cover">
    </div>
    <div class="list__item-content">
      <h3 class="list__item-content-title">Наименование товара</h3>
      <p class="list__item-content-description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae nisi consequatur magni doloremque quisquam ex ad a quidem commodi provident!</p>
      <span class="list__item-content-price">10 000 руб.</span>
    </div>
  </li>
</ul>
</template>

<script>
export default {
  
}
</script>

<style scoped lang="scss">
.list {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;

  &__item {
    position: relative;
    width: calc(100%/3 - 32px/3);
    margin-bottom: 16px;
    border-radius: 4px;
    background: rgba(255, 254, 251, 1);
    box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
    color: rgba(63, 63, 63, 1);

    &-remove {
      display: flex;
      justify-content: center;
      align-items: center;
      position: absolute;
      left: 100%;
      top: 0;
      transform: translate(-24px,-8px);
      width: 32px;
      height: 32px;
      background: rgba(255, 132, 132, 1);
      border-radius: 10px;
      box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
      cursor: pointer;
    }

    &-image {
      width: 100%;
      height: 200px;
      border-radius: 4px 4px 0 0;
    }

    &-content {
      padding: 16px 16px 24px 16px;

      &-title {
        margin-bottom: 16px;
        font-size: 20px;
        line-height: 25px;
        font-weight: 600;
      }

      &-description {
        margin-bottom: 32px;
        font-size: 16px;
        line-height: 20px;
      }

      &-price {
        font-size: 24px;
        line-height: 30px;
        font-weight: 600;
      }
    }
  }
}
</style>
<template>
  <div class="toolTip">
    <p v-text="item.name"></p>
    <div class="toolTip__menu">
          <div class="toolTip__menu--header">
            <div>Название</div>
            <div>Размер</div>
            <div>Сорт</div>
            <div>Стоимость</div>
            <div>Кол-во</div>
            <div>Сумма</div>
          </div>
          <div
            class="toolTip__menu--row"
            v-for="(common, i) in item.items"
            :key="i"
          >
            <div>
              <span v-text="common.name"></span>
              <img :src="common.img" width="100" height="100">
            </div>
            <div v-text="common.size"></div>
            <div v-text="common.sort"></div>
            <div v-text="common.price"></div>
            <div>
              <span @click="increment(i)">+ </span>
              <span v-text="common.count"></span>
              <span @click="decrement(i)"> -</span>
            </div>
            <div v-text="common.calc"></div>
          </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "toolTip",
    props: {
      item: Object
    },
    methods: {
      updateCalc(i) {
        this.item.items[i].calc = this.item.items[i].count * this.item.items[i].price
      },
      increment(i) {
        this.item.items[i].count +=1;
        this.updateCalc(i);
      },
      decrement(i) {
        this.item.items[i].count -=1;
        this.updateCalc(i)
      }
    }
  }
</script>

<style lang="scss">
.toolTip {
  position: absolute;
  z-index: 5;
  &__menu {
    padding: 25px;
    background-color: #f7f8fb;
    border-radius: 25px;
  }
  &__scroll {
    position: relative;

  }
}
</style>

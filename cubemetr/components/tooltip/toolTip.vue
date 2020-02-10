<template>
  <div class="toolTip"
    @click="closeToolTip"
  >
    <div class="toolTip__header">
      <span v-text="item.name"></span>
    </div>
    <div class="toolTip__menu">
      <div
        class="toolTip__helper"
        @click="missClick"
        v-text="helper.text"
      >
      </div>
      <div class="toolTip__menu--header">
        <div>Название</div>
        <div>Размер</div>
        <div>Сорт</div>
        <div>Цена</div>
        <div>Кол-во</div>
        <div>Сумма</div>
      </div>
      <div class="toolTip__wrapper">
        <div
          class="toolTip__menu--row"
          v-for="(common, i) in item.items"
          :key="i"
          :class="(!common.enabled) ? 'disabled' : ''"
        >
          <div>
            <span v-text="common.name"></span>
            <img :src="common.img">
          </div>
          <div><span v-text="common.size"></span></div>
          <div><span v-text="common.sort"></span></div>
          <div><span v-text="common.price"></span></div>
          <div>
            <div class="pointer" @click="increment(i)"><span>+</span></div>
            <span v-text="common.count"></span>
            <div class="pointer" @click="decrement(i)"><span>-</span></div>
          </div>
          <div v-text="common.calc"></div>
        </div>
      </div>
      <advertising v-if="item.advertising !== null" :advertising="item.advertising"/>
    </div>
  </div>
</template>

<script>
  import Advertising from "./advertising";
  export default {
    name: "toolTip",
    components: {Advertising},
    props: {
      item: Object
    },
    data: () => ({
      helper: {
        text: 'Чтобы закрыть, просто кликните на затемненную область'
      }
    }),
    methods: {
      missClick() {
        this.$emit('closeToolTip')
      },
      closeToolTip(e) {
        if (e.target.classList.value === 'toolTip') {
          this.$emit('closeToolTip')
        }
      },
      updateCalc(i) {
        this.item.items[i].calc = this.item.items[i].count * this.item.items[i].price
      },
      increment(i) {
        this.item.items[i].count +=1;
        this.updateCalc(i);
      },
      decrement(i) {
        if ((this.item.items[i].count - 1) >= 0) {
          this.item.items[i].count -=1;
          this.updateCalc(i)
        }
      }
    }
  }
</script>

<style lang="scss">
.toolTip {
  background-color: rgba(0, 0, 0, 0.45);
  top: 0;
  transition: background-color .3s;
  position: fixed;
  z-index: 5;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  color: #493f39;
  &__helper {
    color: #7f828b;
    position: absolute;
    font-size: 16px;
    top: 10px;
    width: 150px;
    z-index: 99999;
    right: -160px;
    transition: color .3s;
    cursor: pointer;
    &:hover {
      color: #f7f8fb;
    }
  }
  .disabled {
    pointer-events: none;
    position: relative;
    &:before {
      content: 'Временно отутствует';
      font-size: 26px;
      display: flex;
      justify-content: center;
      align-items: center;
      position: absolute;
      top: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(120, 110, 103, 0.42);
    }
  }
  .pointer {
    border-radius: 50%;
    background-color: transparent;
    transition: background-color .5s;
    width: 30px !important;
    height: 30px !important;
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
    padding-bottom: unset !important;
    &:hover {
      background-color: rgba(73, 63, 57, 0.63);
    }
  }
  &__header {
    width: 720px;
    overflow: hidden;
    > span {
      position: relative;
      font-size: 36px;
      color: wheat;
      width: 720px;
      &:before {
        content: '';
        position: absolute;
        top: 50%;
        right: -100%;
        border-bottom: 1px solid wheat;
        width: 100%;
      }
    }
  }
  &__wrapper {
    padding-top: 5px;
    display: flex;
    flex-direction: column;
    overflow-y: scroll;
  }
  &__menu {
    padding: 25px;
    width: 720px;
    height: 720px;
    background-color: #f7f8fb;
    border-radius: 25px;
    position: relative;
    display: flex;
    flex-direction: column;
    &--header {
      height: 30px;
      font-size: 20px;
      border-bottom: 1px solid #786e67;
    }
    &--row {
      padding-top: 10px;
      padding-bottom: 5px;
      border-bottom: 1px solid #786e67;
      div {
        padding-bottom: 30px;
        &:nth-child(1) {
          padding-bottom: unset;
        }
        &:nth-child(5) {
          display: flex;
          flex-direction: column;
          align-items: center;
          justify-content: center;
          font-size: 20px;
        }
      }
    }
    &--header,
    &--row {
      display: flex;
      > div {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        &:nth-child(1) {
          width: 200px;
          img {
            top: 0;
            left: 0;
            width: 100px;
            height: 100px;
            transition: height .3s, width .3s, top .3s, left .3s;
            &:hover {
              left: -50px;
              top: -50px;
              width: 200px;
              height: 200px;
              z-index: 9999;
            }
          }
        }
        &:nth-child(2) {
          width: 150px;
        }
        &:nth-child(3) {
          width: 75px;
        }
        &:nth-child(4) {
          width: 80px;
        }
        &:nth-child(5) {
          width: 80px;
        }
        &:nth-child(6) {
          width: 150px;
        }
      }
    }
  }
  &__scroll {
    position: relative;

  }
}
@media only screen and (max-width: 640px) {
  .toolTip {
    &__header,
    &__menu {
      width: 80%;
    }
    &__header {
      > span {
        font-size: 22px;
      }
    }
    &__wrapper {
      overflow-x: scroll;
      display: block;
    }
    &__menu {
      height: 60%;
      &--header {
        font-size: 12px;
      }
      &--header,
      &--row {
        div {
          font-size: 12px;
          &:nth-child(1) {
            width: 100px;
            img {
              width: 75px;
              height: 75px;
            }
          }
          &:nth-child(2) {
            width: 75px;
          }
          &:nth-child(3) {
            width: 30px;
          }
          &:nth-child(4) {
            width: 30px;
          }
          &:nth-child(5) {
            .pointer {
              font-size: 14px;
            }
            width: 30px;
          }
          &:nth-child(6) {
            width: 60px;
          }
        }
      }
    }
  }
}

</style>

<template>
  <div class="targetBlock c-flex-column">
    <div
      class="targetBlock-img c-flex-align-items-center"
      :style="getStyle()"
    >
      <img :src="img"/>
    </div>
    <div class="targetBlock-bottom c-flex-column c-flex-align-items-center">
      <h3
        class="targetBlock-title"
        v-if="title"
        v-text="`${ejTitleLeft}${title}${ejTitleRight}`"/>
      <h6 class="targetBlock-description" v-if="description" v-html="description"/>
      <p class="targetBlock-price" v-if="price" v-text="price"/>
      <div>
        <span class="targetBlock-ej" v-if="ejPhone !== ''" v-text="ejPhone"/>
        <a
          v-if="number"
          :href="`tel:${number.replace(/\s|-/g, '')}`"
          class="targetBlock-number"
          v-text="number"/>
      </div>
    </div>
  </div>
</template>

<script>

  export default {
    name: "targetBlock",
    props: {
      size: String,
      imgH: String,
      imgW: String,
      img: String,
      title: String,
      ejTitleLeft: {
        type: String,
        default: ''
      },
      ejTitleRight: {
        type: String,
        default: ''
      },
      description: String,
      price: String,
      number: String,
      ejPhone: {
        type: String,
        default: ''
      },
    },
    methods: {
      getStyle() {
        const width = (this.imgW || this.size) ? `width: ${this.imgW || this.size}px;` : '';
        const height = (this.imgH || this.size) ? `height: ${this.imgH || this.size}px;` : '';
        return `${width}${height}`
      }
    }
  }
</script>

<style lang="less">
@import "../pages/consts";
.targetBlock {
  &-img {
    overflow: hidden;
    max-width: 370px;
    max-height: 260px;
    img {
      width: 100%;
      height: 100%;
      transition: margin-left .5s, margin-top .5s, width .5s, height .5s;
    }
    &:hover {
      img {
        margin: -10% 0 0 -10%;
        width: 120%;
        height: 120%;
      }
    }
  }
  &-bottom {
    background-color: hsla(0,0%,96.1%,.85);
    padding: 60px 20px 20px;
  }
  &-title {
    color: #232323;
    font-size: 18px;
    font-weight: 600;
    margin: 0 0 5px 0;
  }
  &-description {
    color: rgba(0, 0, 0, 0.5);
    font-size: 12px;
    font-weight: 700;
    max-width: 230px;
    text-align: center;
    font-style: normal;
    margin: 0 0 10px;
  }
  &-price {
    font-size: 16px;
    font-weight: 400;
    margin: 0 0 10px 0;
    color: #444444;
  }
  &-number {
    transition: color .2s;
    background-color: transparent;
    color: @color-yellow;
    font-size: 18px;
    text-decoration: none;
    font-weight: 600;
    margin: 20px 0 5px 0;
    &:hover {
      color: black;
    }
  }
  &-ej {
    font-size: 16px;
    margin-right: -5px;
  }
}
</style>

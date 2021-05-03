<template>
    <div class="headBlock c-flex-column">
      <div class="headBlock-content c-flex-justify-content-center">
        <h1>Имитация бруса <span class="headBlock-content--yellow">в Рыбинске </span></h1>
      </div>
    </div>
</template>

<script>
  import logo from './logo-kubometr-76.jpg'
  import TargetBlock from "./targetBlock";
  import leftBlock from './leftBlock.jpg'
  import magazin from './magazin.jpg'
  import imitation from './imitation.jpg'

  export default {
  name: "headBlock",
    components: {TargetBlock},
    data: () => ({
      image: logo,
      imitation,
      leftBlock,
      magazin
    })
  }
</script>

<style lang="less">
@import "pages/consts";

  .headBlock {
    background-color: hsla(0,0%,96.1%,.85);
    border-bottom-left-radius: 25px;
    border-bottom-right-radius: 25px;
    margin: 0 15px;
    .targetBlock {
      margin: 0 15px;
    }
    &-content {
      padding: 0 5px;
      flex-direction: column;
      background-color: rgba(245, 245, 245, 0.3);
      h1 {
        align-self: center;
        font-size: 50px;
        margin: 15px 0 15px 0;
        color: #01477f;
      }
      h3 {
        margin: 10px 0 15px 15px;
        font-size: 30px;
        text-transform: uppercase;
        color: #01477f;
      }
      h1, h3 {
        font-family: Arial;
        font-weight: bolder;
      }
      &--yellow {
        font-family: Arial;
        font-weight: bolder;
        color: @color-yellow;
      }
      &-img {
        justify-content: space-around;
        img {
          max-width: 1024px;
          width: 30%;
          -webkit-background-size: cover;
          -moz-background-size: cover;
          -o-background-size: cover;
          background-size: cover;
        }
      }
    }
    &-tovars {
      text-align: center;
      font-size: 35px;
    }
  }
  @media only screen and (max-width: 875px) {
    .headBlock {
      &-content {
        flex-direction: column;
        align-items: center;
        > div {
          margin: 10px 0;
        }
        &-img {
          flex-direction: column;
          justify-content: center;
          img {
            width: 80%;
          }
        }
      }
    }
  }
</style>

<template>
  <div class="tovars flex-column">
    <div class="c-flex-wrap c-flex-justify-content-center">
      <target-block
        v-for="(target, index) in newPlates"
        :key="index"
        :title="target.title"
        :img="target.img"
        :description="target.description"
        :price="target.price"
        img-h="260"
        img-w="370"
        class="tovars-block"
      />
      <target-block
        :title="reklama.title"
        :img="reklama.img"
        :description="reklama.description"
        :ej-phone="reklama.ejPhone"
        :number="reklama.number"
        img-h="260"
        img-w="370"
        class="tovars-block"
      />
    </div>
    <div class="tovars--telephone">
      <h2>НА САЙТЕ ПРЕДОСТАВЛЕН НЕ ВЕСЬ ПЕРЕЧЕНЬ ТОВАРОВ, УТОЧНЯЙТЕ ПО ТЕЛЕФОНУ.</h2>
    </div>
  </div>
</template>

<script>
  import tovars from "./newTovars";
  import TargetBlock from "../targetBlock";
  import reklama from "./tovarsImage/dostavka_rybinsk_kybometr76.jpg";
  export default {
    name: "tovars",
    components: {TargetBlock},
    data: () => ({
      tovars,
      tabCurrent: 1,
      reklama: {
        img: reklama,
        category: 'Реклама',
        ejPhone: '📱',
        title: 'Узнай как оплатить онлайн:',
        description: 'ГАЗЕЛЬ ДЛИННОЙ: 3М. И 6М.',
        number: '+7 908 027-07-54'
      }
    }),
    props: {
      search: String,
      category: String
    },
    computed: {
      newPlates() {
        return tovars.reduce((accum, item, index) => {
            accum.push({
                    img: item.img,
                    category: item.category,
                    title: item.title,
                    description: `${item.description} ММ.`,
                    price: `${item.price}`
                  });
            return accum
        }, [])
      },
      // plates() {
      //   const isCategory = this.category !== 'ВСЕ';
      //   const plates = this.tovars.reduce((accum, item, index) => {
      //     if (isCategory) {
      //       if (item.category !== this.category) {
      //         return accum
      //       }
      //     } else {
      //       if (this.search === '' && ((this.tabCurrent -1) * 14 > index || this.tabCurrent * 14 < index+1)) {
      //         return accum
      //       }
      //     }
      //     if (this.search !== '') {
      //       if (item.title.toLowerCase().indexOf(this.search.toLowerCase()) === -1) {
      //         return accum
      //       }
      //     }
      //     accum.push({
      //       img: item.img,
      //       category: item.category,
      //       title: item.title,
      //       description: `${item.description} ММ.`,
      //       price: `${item.price} руб/шт`
      //     });
      //     return accum
      //   }, []);
      //   return plates
      // },
      tabs() {
        return Math.ceil(this.tovars.length/14)
      }
    }
  }
</script>

<style lang="less">
  @import "../../pages/consts";
  @tabColorize: {
    background-color: black;
    color: @color-yellow;
  }
  @-webkit-keyframes pulse {
    0% {
      -webkit-box-shadow: 0 0 0 0 rgba(255, 194, 0, 0.8);
    }
    20% {
      -webkit-box-shadow: 0 0 0 5px rgba(255, 194, 0, 0.7);
    }
    60% {
      -webkit-box-shadow: 0 0 0 15px rgba(12, 96, 53, 0.3);
    }
    100% {
      -webkit-box-shadow: 0 0 0 0 rgba(13, 165, 100, 0);
    }
  }
  @keyframes pulse {
    0% {
      -moz-box-shadow: 0 0 0 0 rgba(255, 194, 0, 0.8);
      box-shadow: 0 0 0 0 rgba(255, 194, 0, 0.8);
    }
    20% {
      -moz-box-shadow: 0 0 0 5px rgba(255, 194, 0, 0.7);
      box-shadow: 0 0 0 5px rgba(255, 194, 0, 0.4);
    }
    60% {
      -moz-box-shadow: 0 0 0 15px rgba(12, 96, 53, 0.3);
      box-shadow: 0 0 0 15px rgba(12, 96, 53, 0);
    }
    100% {
      -moz-box-shadow: 0 0 0 0 rgba(13, 165, 100, 0);
      box-shadow: 0 0 0 0 rgba(13, 165, 100, 0);
    }
  }
.tovars {
  padding: 0 5% 55px;
  &--telephone {
    position: relative;
    h2 {
      z-index: 1;
      color: whitesmoke;
      text-align: center;
      left: 32px;
      top: 15px;
      position: relative;
    }
    &::before {
      z-index: 0;
      background-color: @color-yellow;
      content: "";
      position: absolute;
      right: -16px;
      top: 0px;
      width: 100%;
      padding: 15px 0;
      height: 100%;
      -webkit-transform: skewX(
        30deg
      );
      transform: skewX(
        30deg
      );
    }
  }
  &-block {
    margin: 25px;
  }
  &-tabs {
    >span {
      cursor: pointer;
      width: 30px;
      line-height: 30px;
      text-align: center;
      margin: 0 5px;
      border-radius: 50%;
      font-size: 18px;
      transition: color .5s, background-color .5s;
      background-color: @color-yellow;
      color: black;
      &:hover {
        animation: pulse .5s;
        @tabColorize()
      }
    }
    .tabActive {
      @tabColorize()
    }
  }
}
  @media only screen and (max-width: 875px) {
    .tovars {
      padding: 0 0 25px 0;
      &--telephone {
        padding: 0 48px;
        h2 {
          font-size: 14px;
          left: 0;
          text-align: center;
        }
        &::before {
          width: 80%;
          right: unset;
          left: 40px;
        }
      }
    }
  }
</style>

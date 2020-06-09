<template>
  <div class="tovars flex-column">
    <div class="c-flex-wrap c-flex-justify-content-center">
      <target-block
        v-for="(target, index) in plates"
        :key="index"
        :title="target.title"
        :img="target.img"
        :description="target.description"
        :price="target.price"
        img-h="260"
        img-w="370"
        class="tovars-block"
      />
    </div>
    <div v-if="category ==='ВСЕ' && search === ''" class="tovars-tabs c-flex-justify-content-center">
      <span
        v-for="tab in tabs"
        :key="tab"
        :class="`${tab === tabCurrent ? 'tabActive' : ''}`"
        @click="tabCurrent = tab"
        v-text="tab"
      />
    </div>
  </div>
</template>

<script>
  import tovars from "./tovarsData";
  import TargetBlock from "../targetBlock";
  export default {
    name: "tovars",
    components: {TargetBlock},
    data: () => ({
      tovars,
      tabCurrent: 1
    }),
    props: {
      search: String,
      category: String
    },
    computed: {
      plates() {
        const isCategory = this.category !== 'ВСЕ';
        const plates = this.tovars.reduce((accum, item, index) => {
          if (isCategory) {
            if (item.category !== this.category) {
              return accum
            }
          } else {
            if (this.tabCurrent*14 < index || (this.tabCurrent - 1)*14 >= index) {
              return accum
            }
          }
          if (this.search) {
            if (item.title.toLowerCase().indexOf(this.search.toLowerCase()) === -1) {
              return accum
            }
          }
          accum.push({
            img: item.img,
            category: item.category,
            title: item.title,
            description: `${item.description} ММ.`,
            price: `${item.price} руб/шт`
          });
          return accum
        }, []);
        return plates
      },
      tabs() {
        return Math.floor(this.tovars.length/14)
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
      -webkit-box-shadow: 0 0 0 0 rgba(255, 194, 0, 0.4);
    }
    70% {
      -webkit-box-shadow: 0 0 0 15px rgba(12, 96, 53, 0);
    }
    100% {
      -webkit-box-shadow: 0 0 0 0 rgba(13, 165, 100, 0);
    }
  }
  @keyframes pulse {
    0% {
      -moz-box-shadow: 0 0 0 0 rgba(255, 194, 0, 0.4);
      box-shadow: 0 0 0 0 rgba(255, 194, 0, 0.4);
    }
    70% {
      -moz-box-shadow: 0 0 0 15px rgba(12, 96, 53, 0);
      box-shadow: 0 0 0 15px rgba(12, 96, 53, 0);
    }
    100% {
      -moz-box-shadow: 0 0 0 0 rgba(13, 165, 100, 0);
      box-shadow: 0 0 0 0 rgba(13, 165, 100, 0);
    }
  }
.tovars {
  padding: 0 5%;
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
  }
}
</style>

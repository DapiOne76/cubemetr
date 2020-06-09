<template>
  <div class="tovars c-flex-wrap c-flex-justify-content-center">
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
</template>

<script>
  import tovars from "./tovarsData";
  import TargetBlock from "../targetBlock";
  export default {
    name: "tovars",
    components: {TargetBlock},
    data: () => ({
      tovars
    }),
    props: {
      search: String,
      category: String
    },
    computed: {
      plates() {
        const isCategory = this.category !== 'ВСЕ';
        const plates = this.tovars.reduce((accum, item) => {
          if (isCategory) {
            if (item.category !== this.category) {
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
      }
    }
  }
</script>

<style lang="less">
.tovars {
  padding: 0 5%;
  &-block {
    margin: 25px;
  }
}
</style>

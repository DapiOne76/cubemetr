<template>
  <div class="aboutUsSlider">
    <div :class="imgClass">
      <div class="aboutUsSlider__manage">
        <div
          v-for="(item, i) in sliders"
          :key="i"
          @click="switchSlide(i)"
          :class="isPicked(i)"
        ></div>
      </div>
    </div>
  </div>
</template>

<script>
    export default {
        name: "slider",
        props: {
            value: Number
        },
        data: () => ({
            sliders: ['slider1', 'slider2'],
        }),
        computed: {
            curImg() {
              return this.items[this.value]
            },
            imgClass() {
                return `aboutUsSlider__img ${this.sliders[this.value]}`
            }
        },
        methods: {
            switchSlide(value) {
                this.$emit('onChange', value)
            },
            isPicked(value) {
                return `aboutUsSlider__manage--option ${(value === this.value) ? 'picked' : ''}`
            }
        }
    }
</script>

<style lang="scss">
  .aboutUsSlider {
    display: flex;
    flex-direction: column;
    align-items: center;
    .slider1 {
      background-image: url(./25-sosna.png)
    }
    .slider2 {
      background-image: url(./kaka.jpg)
    }
    &__img {
      position: relative;
      -moz-background-size: 100% 100%; /* Firefox 3.6+ */
      -webkit-background-size: 100% 100%; /* Safari 3.1+ и Chrome 4.0+ */
      -o-background-size: 100% 100%; /* Opera 9.6+ */
      background-size: 100% 100%;
      background-repeat: no-repeat;
      background-position: center;
      width: 100%;
      height: 398px;
      -webkit-transition: all .3s ease-in-out;
      -moz-transition: all .3s ease-in-out;
      transition: all .3s ease-in-out;
    }
    &__manage {
      position: absolute;
      width: 100%;
      justify-content: center;
      bottom: 35px;
      display: flex;
      &--option {
        transition: background-color .5s;
        margin: 5px;
        border: 1px solid #0eb267;
        border-radius: 50%;
        width: 15px;
        height: 15px;
        &:hover {
          background-color: rgba(32, 65, 48, 0.55);
        }
      }
      .picked {
        background-color: #0eb267;
      }
    }
  }
  @media only screen and (max-width: 512px) {
    .aboutUsSlider__img {
      height: 170px;
    }
  }
</style>

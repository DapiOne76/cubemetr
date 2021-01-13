<template>
    <div class="headBlock c-flex-column">
      <div class="headBlock-img c-flex-justify-content-center">
        <img :src="image" alt="Логотип Кубометр Рыбинск Магазин"/>
      </div>
      <div class="headBlock-content c-flex-justify-content-center">
        <target-block
          :img="leftBlock"
          size="270"
          title="Наш адрес"
          ej-phone="📱"
          ej-title-left="💎"
          ej-title-right="💎"
          description="ВОЛЖСКАЯ НАБЕРЕЖНАЯ, 163 (ВХОД СО СТОРОНЫ НАБЕРЕЖНОЙ)"
          number="+7 908 027-07-43"
        />
        <div class="headBlock-video c-flex-align-items-center">
          <iframe
            title="Магазин КУБОМЕТР | РЫБИНСК"
            src="https://www.youtube.com/embed/rO__8YfZz38?feature=oembed"
            frameborder="0"
            allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen=""/>
        </div>
        <target-block
          class="headBlock-video_target"
          :img="magazin"
          size="270"
          title="Режим работы"
          ej-phone="📱"
          ej-title-left="⏳"
          ej-title-right="⌚"
          description="ПН-ПТ: 09:00 - 18:00 <br> ОБЕД: 13:00 - 14:00 <br> СБ-ВС: ВЫХОДНОЙ"
          number="+7 908 027-07-43"
        />
      </div>
    </div>
</template>

<script>
  import logo from './logo-kubometr-76.jpg'
  import TargetBlock from "./targetBlock";
  import defImg from './default.png'
  import leftBlock from './leftBlock.jpg'
  import magazin from './menu/tovarsImage/magazin_kubometr_rybinsk-1024x1024.jpg'

  export default {
  name: "headBlock",
    components: {TargetBlock},
    data: () => ({
      image: logo,
      defImg,
      leftBlock,
      magazin
    })
  }
</script>

<style lang="less">
  .headBlock {
    padding-top: 50px;
    background-color: hsla(0,0%,96.1%,.85);
    padding-bottom: 30px;
    margin: 0 15px;
    .targetBlock {
      margin: 0 15px;
    }
    &-content {
      margin-top: 50px;
      padding: 0 15px;
    }
    &-tovars {
      text-align: center;
      font-size: 35px;
    }
    &-video {
      margin: 0;
      flex: 1;
      &_target {
        white-space: pre-wrap;
      }
      >iframe {
        width: 100%;
        height: 100%;
      }
    }
    &-img {
      img {
        max-width: 1024px;
        width: 100%;
        -webkit-background-size: cover;
        -moz-background-size: cover;
        -o-background-size: cover;
        background-size: cover;
      }
    }
  }
  @media only screen and (max-width: 875px) {
    .headBlock {
      .headBlock-img {
        display: block;
      }
      &-content {
        flex-direction: column;
        align-items: center;
        > div {
          margin: 10px 0;
        }
      }
    }
  }
</style>

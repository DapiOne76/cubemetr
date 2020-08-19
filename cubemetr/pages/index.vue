<template>
  <div class="wrapper c-flex-column">
    <div class="header c-flex-justify-content-between c-flex-align-items-center"><h1 class="header-tovars">
      Магазин
      <span class="headBlock-name yellow-text">
        «КУБОМЕТР»
      </span></h1> <a href="tel:+79080270743" class="header-number">+7 908 027-07-43</a></div>
    <head-block/>
    <menu-block/>
    <client-only>
      <footer-block/>
    </client-only>
    <div class="parralax"></div>
  </div>
</template>

<script>

import HeadBlock from "../components/headBlock";
import MenuBlock from "../components/menu/menuBlock";
import FooterBlock from "../components/footerBlock";
export default {
    head: {
      title: 'Кубометр',
      htmlAttrs: {
        lang: 'ru'
      },
      meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        { "hid":"description","name":"description","content":"Строительный магазин КУБОМЕТР"},
        { "hid":"keywords", name: 'keywords', content: 're,jvtnh, re,jvtnh76, кубометр, кубометр76, имитация, имитация бруса, доска, доска пола, евровагонка, вагонка Штиль, наличник, плинтус, раскладки, угол внешний, угол внутренний, брусок строганный, поручни, тетива, подоконники, балясины, начальные столбы для лестниц, и ограждений ступени' },
        { "hid":"keywords", name: 'keywords', content: 'Сухой строганный пиломатериал, купить имитация бруса, вагонка штиль, евровагонка, доска пола, отделочные материалы, для бань, саун, бруски, балясины, ступени, тетива, поручни, мебельные щиты, площадки, столешницы, отделочные строганные пиломатериалы, помощь в отделке помещений, продажа в строительном магазине, товары для строительства, строиматериалы, ярославская обл. город Рыбинск.' },
        { name: 'yandex-verification', content: 'b61e4757c6a38f32' }
      ],
      link: [
        {
          rel: 'stylesheet',
          id: 'vc_google_fonts_montserrat-css',
          href: '//fonts.googleapis.com/css?family=Montserrat&amp;subset=latin%2Ccyrillic',
          type: 'text/css',
          media: 'all'
        }
      ]
    },
    components: {FooterBlock, MenuBlock, HeadBlock},
    data: () => ({
    }),
    methods: {
    },
    created() {
    }
}
</script>

<style lang="less">
  @import "consts";
  @import "styles";
  @import "pe-icon-7-stroke";
  *{
    font-family: 'Montserrat', sans-serif;
  }
  .parralax {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: -1;
    background: url(/56a3ebc.jpg) no-repeat fixed 50%;
    background-size: cover;
    height: 100%;
  }
  .header {
    background-color: @color-blue;
    font-weight: 600;
    padding: 8px 40px;
    color: #fff;
    &-tovars {
      text-align: center;
      margin: 0 0 0 30px;
      font-size: 40px;
    }
    &-number {
      -webkit-transition: background-color .3s,color .3s;
      transition: background-color .3s,color .3s;
      background-color: transparent;
      color: #ffc200;
      font-size: 31px;
      line-height: 31px;
      text-decoration: none;
      font-weight: 600;
      padding: 9px;
      border: 2px solid #ffc200;
      margin: 0 30px 0 0;
      &:hover {
        background-color: #ffc200;
        color: #000;
      }
    }
  }
  @media only screen and (max-width: 875px) {
    .header {
      -webkit-box-orient: vertical;
      -webkit-box-direction: normal;
      flex-direction: column;
    }
    .parralax {
      display: none;
    }
  }
</style>


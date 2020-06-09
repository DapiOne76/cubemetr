<template>
  <div class="wrapper c-flex-column">
    <div class="header c-flex-justify-content-end">
      Магазин «Кубометр»
    </div>
    <head-block/>
    <menu-block/>
    <client-only>
      <footer-block/>
    </client-only>
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
  .header {
    background-color: @color-blue;
    color: white;
    font-size: 40px;
    font-weight: 600;
    padding: 8px 40px;
  }
</style>


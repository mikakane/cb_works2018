<template>
  <section class="p-hero">
    <h2 class="p-hero__title">chatboxにできること</h2>
    <div class="p-hero__wrap">
      <div class="p-hero__backgound">
        <div class="p-hero__backgoundFilter"></div>
      </div>
      <div class="p-hero__contents">
        <div class="p-hero__catchCopy">
          <h3 class="p-hero__catchCopyMain">Webのこれからを<br>「作る」&nbsp;「伝える」&nbsp;「語り合う」</h3>
          <span class="p-hero__catchCopySub">作るだけじゃなく、伝えることで見えてくる</span>
        </div>
        <div class="p-hero__lists">
          <hero-list :item="item" :index="index" v-for="(item,index) in listItems" :key="index"></hero-list>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import HeroList from "./Hero/List.vue";
export default {
  props: {
    listItems: Array
  },
  data() {
    return {};
  },
  components: {
    HeroList
  }
};
</script>
<style lang="scss" scoped>
@import "~assets/scss/layout/_layout.scss";
@import "~assets/scss/object/component/_container.scss";
.p-hero {
  &__title {
    margin-bottom: 2.5rem;
    color: #c3504f;
    text-align: center;
    font-size: 2rem;
    font-weight: bold;
    letter-spacing: 4px;
    @include desktop {
      margin-bottom: 3.5rem;
      font-size: 2.7rem;
      letter-spacing: 6px;
    }
  }

  &__wrap {
    min-height: 920px;
    background-color: #c3504f;
    position: relative;
  }
  &__backgound {
    margin-bottom: 10px;
    display: block;
    width: 100%;
    height: 200px;
    background: url("/images/serviceThumb_create.jpg") no-repeat;
    background-position: top;
    background-size: cover;
    @include desktop {
      margin-bottom: 0;
      height: 450px;
      background-position: center;
      background: url("/images/hero_background.jpg") no-repeat;
      background-size: cover;
    }
  }
  &__backgoundFilter {
    height: 100%;
    background-color: rgba(195, 80, 79, 0.6);
  }
  &__contents {
    @include c-container;
    padding: 0 10px;
    padding-top: 30px;
    display: block;
    position: static;

    @include desktop {
      padding-top: 0;
      position: absolute;
      left: 50%;
      top: 70px;
      transform: translateX(-50%);
      z-index: 1000;
    }
  }
  &__catchCopy {
    display: inline-block;
    margin-bottom: 55px;
    padding-top: 50px;
    min-width: 100%;
    text-align: center;
    color: #fff;
    position: absolute;
    top: 0;
    left: 0;
    @include desktop {
      padding-top: 20px;
      margin-bottom: 90px;
      position: static;
    }
  }
  &__catchCopyMain {
    display: block;
    margin-bottom: 10px;
    text-align: center;
    font-size: 2rem;
    font-weight: bold;
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.4);
    color: inherit;
    line-height: 1.8;
    letter-spacing: 3px;
    @include desktop {
      font-size: 3rem;
      margin-bottom: 30px;
    }
  }
  &__catchCopySub {
    display: inline-block;
    font-size: 1.6rem;
    color: inherit;
    @include desktop {
      font-size: 2rem;
    }
  }
  &__lists {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    @include desktop {
      flex-wrap: nowrap;
    }
  }
}
</style>

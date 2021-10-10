<template>
  <transition>
    <div class="about">
      <div class="about__container _container">
        <div class="about__content">
          <div class="about__order subtitle">About Us</div>
          <h1 class="about__title title">{{title}}</h1>
          <div class="about__descript decript">{{descript}}</div>
          <div class="about__items">
            <div class="about__item" v-for="(item) in features" :key="item.title">
              <div class="about__item-body">
                <div class="about__item-title">{{item.title}}</div>
                <div class="about__item-descript">{{item.descript}}</div>
              </div>
            </div>
          </div>
        </div>
        <div class="about__images images-group">
          <div class="about__images-big about__big images-group__big">
            <img
              class="about__big-img images"
              :src="require(`@/assets/images/about/${bigImage}.png`)"
              alt="big"
            />
          </div>
          <div class="about__images-small about__small images-group__small">
            <img
              class="about__small-img images"
              :src="require(`@/assets/images/about/${smallImage}.png`)"
              alt="small"
            />
          </div>
        </div>
      </div>
    </div>
  </transition>
</template>
<script>
export default {
  layout: 'Authuser',
  transition: {
    name: 'about',
    mode: 'out-in',
  },
  data() {
    return {
      features: [
        {
          title: '10M+',
          descript: 'Visitors',
        },
        {
          title: '109',
          descript: 'Hotels',
        },
        {
          title: '29',
          descript: 'Food Shop',
        },
        {
          title: '18',
          descript: 'Related Spots',
        },
      ],
      title: 'The Perfect Travel Place For You & Your Family',
      bigImage: '1',
      smallImage: '2',
      descript:
        "how travel can be one of the best tools for personal growth. We share some of the life lessons we've learned on the road that has provided us insight into empathy, mindfulness, meditation, comfort zones, two-way storytelling, being present, connection and more.",
    }
  },
}
</script>
<style lang="scss">
.about-enter {
  transition: transform 0.5s;
  transform: translateX(2000px);
}
.about-enter-to {
  transition: transform 0.5s;
  transform: translateX(0);
}
.about-leave {
  transform: translateX(0);
}
.about-leave-to {
  transform: translateX(-2000px);
  transition: transform 0.5s;
}
.about {
  padding: 91px 0;
  &__container {
    display: flex;
    justify-content: space-between;
  }
  &__content {
    max-width: 509px;
    width: 100%;
  }
  &__items {
    margin: 0 -13px;
    display: flex;
    width: 100%;
    flex-wrap: wrap;
    margin-top: 50px;
    max-width: 400px;
  }
  &__item {
    padding: 0 13px;
    max-width: 150px;
    width: 100%;
    &:nth-child(-n + 2) {
      margin-bottom: 20px;
    }
    &-body {
      border: 2px solid #f8f8f8;
      border-radius: 10px;
      padding: 32px 8px;
      display: flex;
      flex-direction: column;
      height: 100%;
    }
    &-title {
      font-weight: 550;
      font-size: 32px;
      line-height: calc(34 / 32 * 100%);
      text-align: center;
      color: #3685fb;
    }
    &-descript {
      font-weight: 500;
      font-size: 14px;
      line-height: calc(24 / 14 * 100%);
      text-align: center;
      color: #002248;
      margin-top: 4px;
      flex: 1 1 auto;
    }
  }
  &__title {
  }
  &__images {
    max-width: 604px;
    width: 100%;
    position: relative;
    display: flex;
    justify-content: flex-end;
    &-small {
      max-width: 320px;
      height: 456px;
      left: 0;
      bottom: -22px;
    }
    &-big {
      max-width: 400px;

      height: 610px;
    }
  }
}
</style>
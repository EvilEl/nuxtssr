<template>
  <div class="find">
    <div class="find__container _container">
      <div class="find__top">
        <div class="find__subtitle subtitle">3 steps for the perfect trip</div>
        <div class="find__title title">Find travel perfection</div>
        <div
          class="find__descript descript"
        >Naturally head of the class whenit comes to luxury travel planning,bbecause we do more homework than anyone else</div>
      </div>
      <div class="find__items">
        <div class="find__body" v-for="item in findItems" :key="item.title">
          <div class="find__item">
            <div class="find__item-image" :style="item.style">
              <img
                class="find__item-img images"
                :src="require(`@/assets/images/Find/${item.image}.png`)"
                alt="tell"
              />
            </div>
            <div class="find__item-title">{{item.title}}</div>
            <div class="find__item-descript">{{item.descript}}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  layout: 'Authuser',
  data() {
    return {
      findItems: [
        {
          title: 'Tell us what you want to do',
          descript:
            'Fill out a 2-minute questionnaire about how you like to travel',
          image: '1',
          style: {
            width: '105px',
            height: '96px',
          },
        },
        {
          title: 'Share your travel preference',
          descript:
            'It all happends online,We recommend everything to your vision',
          image: '2',
          style: {
            width: '110px',
            height: '111px',
          },
        },
        {
          title: 'We’ll give you recommendations',
          descript:
            'Once you’re happy with your final plan, We handle everything for you',
          image: '3',
          style: {
            width: '140px',
            height: '115px',
          },
        },
      ],
    }
  },
}
</script>
<style lang="scss">
.find {
  padding: 60px 0;
  &__top {
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-bottom: 60px;
  }
  &__descript {
    max-width: 568px;
    margin-top: 20px;
    width: 100%;
  }
  &__items {
    display: flex;
    margin: 0 -15px;
  }
  &__body {
    padding: 0 15px;
    flex: 0 1 33.33333%;
  }
  &__item {
    background: #ffffff;
    border: 2px solid #f8f8f8;
    border-radius: 10px;
    padding: 70px 58px;
  }
  &__item-image {
    width: 105px;
    height: 96px;
    margin: auto;
  }
  &__item-title {
    margin-top: 58px;
    font-weight: 500;
    font-size: 20px;
    line-height: calc(28 / 20 * 100%);
    text-align: center;
    color: #002248;
  }
  &__item-descript {
    font-weight: 400;
    font-size: 16px;
    line-height: calc(28 / 16 * 100%);
    text-align: center;
    color: #697687;
  }
}
</style>
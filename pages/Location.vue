<template>
  <transition>
    <div class="location">
      <div class="location__container _container">
        <div class="location__top">
          <div class="location__top-subtitle subtitle">Location</div>
          <div class="location__top-title title">Suggested Location</div>
          <div
            class="location__top-descript decript"
          >Travel is my life. Since 1999, I’ve been traveling around the world nonstop. If you also love travel, you’re in the right place!</div>
        </div>
        <div class="location__gallery">
          <div
            class="location__gallery-item gallery-item"
            v-for="item in gallery"
            :key="item.title"
          >
            <div class="gallery-item__body">
              <div class="gallery-item__image">
                <img
                  class="gallery-item__img images"
                  :src="require(`@/assets/images/Location/${item.image}`)"
                  alt="gallery1"
                />
              </div>
              <div class="gallery-item__content">
                <div class="gallery-item__content-top">
                  <div class="gallery-item__content-title">{{item.title}}</div>
                  <div class="gallery-item__content-star"></div>
                </div>
                <div class="gallery-item__content-bottom">
                  <div class="gallery-item__content-text">{{item.text}}</div>
                  <div class="gallery-item__content-price">{{item.price}}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </transition>
</template>
<script>
export default {
  transition: {
    name: 'location',
    mode: 'out-in',
  },
  layout: 'Authuser',
  data() {
    return {
      gallery: [
        {
          title: 'Bali Handara Gate',
          star: 5,
          text: 'Indonesia',
          price: '$1200',
          image: '1.png',
        },
        {
          title: 'Buddhist shrine',
          star: 5,
          text: 'Tokyo, Japan',
          price: '$1200',
          image: '2.png',
        },
        {
          title: 'Rialto Bridge',
          star: 5,
          text: 'Italy',
          price: '$1200',
          image: '3.png',
        },
      ],
    }
  },
}
</script>
<style lang="scss">
@mixin calcLineHeight($lineHeight, $fontSize) {
  line-height: calc($lineHeight / $fontSize * 100%);
}
.location-enter {
  transition: transform 0.5s;
  transform: translateX(2000px);
}
.location-enter-to {
  transition: transform 0.5s;
  transform: translateX(0);
}
.location-leave {
  transform: translateX(0);
}
.location-leave-to {
  transform: translateX(-2000px);
  transition: transform 0.5s;
}
.location {
  // &-enter {
  //   transition: transform 0.2s ease-in;
  //   transform: translateX(-4000px);
  // }
  // &-enter-to {
  //   transform: translateX(0);
  // }
  // &-leave {
  //   transition: transform 0.2s ease-in;
  //   transform: translateX(-4000px);
  // }
  // &-leave-to {
  //   transform: translateX(-4000px);
  // }
  background: #f8f8f8;
  padding: 30px 0;
  &__top {
    margin-bottom: 71px;
    max-width: 538px;
    width: 100%;
  }
  &__gallery {
    margin: 0 -15px;
    display: flex;
    .gallery-item {
      padding: 0 15px;
      max-width: 370px;
      width: 100%;
      &__body {
        min-height: 500px;
        position: relative;
        display: flex;
        align-items: flex-end;
      }
      &__image {
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        width: 100%;
        height: 100%;
      }
      &__content {
        background: rgba(0, 34, 72, 0.3);
        backdrop-filter: blur(20px);
        border-radius: 10px;
        color: #ffffff;
        display: flex;
        flex-wrap: wrap;
        max-width: 310px;
        width: 100%;
        padding: 23px 20px;
        margin: 0 30px 30px;
      }
      &__content-top {
        font-family: 'airb-medium';
        font-weight: 500;
        justify-content: space-between;
        flex: 1 1 100%;
      }
      &__content-bottom {
        flex: 1 1 auto;
        display: flex;
        justify-content: space-between;
        margin-top: 7px;
      }
      &__content-title {
        font-size: 20px;
        @include calcLineHeight(20, 20);
      }
      &__content-text {
        font-size: 16px;
        @include calcLineHeight(28, 16);
      }
      &__content-price {
        font-size: 20px;
        @include calcLineHeight(24, 20);
      }
    }
  }
}
</style>
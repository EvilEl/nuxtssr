<template>
  <transition>
    <div class="hero">
      <div class="hero__container _container">
        <div class="hero__images images-group">
          <div class="hero__images-big hero__big images-group__big">
            <img
              class="hero__big-img images"
              :src="require(`@/assets/images/main/${bigImage}.png`)"
              alt="big"
            />
          </div>
          <div class="hero__images-small hero__small images-group__small">
            <img
              class="hero__small-img images"
              :src="require(`@/assets/images/main/${smallImage}.png`)"
              alt="small"
            />
          </div>
        </div>
        <div class="hero__content">
          <div class="hero__order subtitle">Book Now</div>
          <h1 class="hero__title">
            {{title}}
            <span class="hero__title-icon">
              <img
                class="hero__title-image"
                :src="require(`@/assets/images/main/${imageRocker}.png`)"
                alt="rocket"
              />
            </span>
          </h1>
          <div class="hero__descript">{{descript}}</div>
          <Button class="hero__button" title="Start Now" />
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
import Button from '@/components/Ui/Button'

export default {
  transition: {
    name: 'hero',
    mode: 'out-in',
  },
  layout: 'Authuser',
  components: {
    Button,
  },
  data() {
    return {
      title: 'Let’s Enjoy Your Trip with TripGoal',
      imageRocker: '3',
      bigImage: '1',
      smallImage: '2',
      descript:
        "Thinking of taking a break from every day's busy life? Planning to go out of the country with your loved ones to have some fun and quality time in a cost-effective way?",
    }
  },
}
</script>

<style lang="scss">
.hero-enter {
  transition: transform 0.5s;
  transform: translateX(-2000px);
}
.hero-enter-to {
  transition: transform 0.5s;
  transform: translateX(0);
}
.hero-leave {
  transform: translateX(0);
}
.hero-leave-to {
  transform: translateX(2000px);
  transition: transform 0.5s;
}
body,
html {
  font-family: 'airb-book';
}

.hero {
  padding: 91px 0;
  &__container {
    display: flex;
    justify-content: space-between;
  }
  &__images {
    position: relative;
    max-width: 500px;
    width: 100%;
    &-big {
      max-width: 400px;
      height: 540px;
    }
    &-small {
      position: absolute;
      right: 0;
      bottom: -60px;
      z-index: 2;
      max-width: 320px;
      height: 430px;
    }
  }
  &__content {
    max-width: 523px;
    width: 100%;
    margin-top: 85px;
  }

  &__title {
    font-family: 'airb-medium';
    font-weight: 500;
    font-size: 55px;
    line-height: calc(72 / 55 * 100%);
    margin-top: 15px;
    color: #002248;
    &-icon {
      display: inline-block;
      margin-left: 20px;
      &:hover {
        animation: moveRocker 3s ease-in alternate;
      }
    }
  }
  &__descript {
    font-weight: 400;
    font-size: 16px;
    line-height: calc(28 / 16 * 100%);
    color: #697687;
    margin-top: 20px;
  }
  &__button {
    margin-top: 50px;
    max-width: 170px;
  }
}
</style>
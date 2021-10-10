<template>
  <div class="container__main">
    <header class="header">
      <div class="container _container">
        <nuxt-link to="/" class="logo">
          <img
            class="logo__image images"
            :src="require(`@/assets/images/${logoImage}.png`)"
            alt="TripGoal"
          />
        </nuxt-link>
        <nav class="menu">
          <ul class="menu__list">
            <li class="menu__item" v-for="(item) in navItems" :key="item.name">
              <nuxtLink class="menu__link" :to="item.link">{{item.title}}</nuxtLink>
            </li>
          </ul>
        </nav>
        <Button title="Register" />
      </div>
    </header>
    <main class="main">
      <nuxt />
    </main>
    <footer class="footer">
      <div class="footer__text">© 2021. All copyrights reserved by RH Agency</div>
    </footer>
  </div>
</template>
<script>
import Button from '@/components/Ui/Button'
export default {
  components: {
    Button,
  },
  data() {
    return {
      logoImage: 'Logo',
      navItems: [
        {
          title: 'Home',
          link: '/',
        },
        {
          title: 'About',
          link: '/About',
        },
        {
          title: 'Packages',
          link: '/Packages',
        },
        {
          title: 'Packages',
          link: '/Packages',
        },
        {
          title: 'FAQ',
          link: '/FAQ',
        },
      ],
    }
  },
}
</script>
<style lang="scss" scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
}
.container__main {
  display: flex;
  flex-direction: column;
  height: 100vh;
}
.main {
  flex: 1 1 auto;
}
.header {
  padding: 25px 0;
  .logo {
    width: 106px;
  }
}
.footer {
  padding: 30px 0px 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-top: 1.5px solid rgba(105, 118, 135, 0.1);
  &__text {
    font-weight: normal;
    font-size: 14px;
    line-height: calc(14 / 14 * 100%);
    text-align: center;
    color: #697687;
  }
}
.menu {
  flex: 1 1 auto;
  &__list {
    display: flex;
    align-content: center;
    justify-content: center;
  }
  &__item {
    list-style: none;
    &:not(:first-child) {
      margin-left: 40px;
    }
    &:hover .menu__link {
      color: #3685fb;
    }
  }
  &__link {
    text-decoration: none;
    color: #002248;
    font-weight: 400;
    font-size: 16px;
    line-height: calc(18 / 16 * 100%);
    transition: color 0.2s;
  }
}
</style>
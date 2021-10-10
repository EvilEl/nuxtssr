<template>
  <div class="ui-button">
    <button class="ui-button__btn" @click="useButton">{{title}}</button>
  </div>
</template>
<script>
export default {
  /*
   props:{
     tjtle - для заголвка
   }
   methods:{
     useButton эмитит событие => @click 
   }
  */
  props: {
    title: {
      type: String,
      default: 'Заголок',
    },
  },
  methods: {
    useButton() {
      this.$emit('click')
    },
  },
}
</script>
<style lang="scss">
.ui-button {
  max-width: 120px;
  width: 100%;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;

  &__btn {
    border: none;
    background: #3685fb;
    font-weight: 500;
    font-size: 16px;
    color: #ffffff;
    line-height: calc(18 / 16 * 100%);
    height: 100%;
    width: 100%;
    border-radius: 10px;
    transition: all 0.5s ease-in;
    &:hover {
      background: #05224e;
    }
  }
}
</style>
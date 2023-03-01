<template>
  <div>
    <full-page :options="options" ref="page" >
      <div class="section">
        <div class="slide">slide1</div>
        <div class="slide">slide2</div>
        <div class="slide">slide3</div>
      </div>
      <div class="section">section2</div>
      <div class="section">section3</div>
      <div class="section">section4</div>
      <div class="section">section5</div>
    </full-page>
  </div>
</template>

<script>
export default {
  data () {
    return {
      options: {
        // key
        licenseKey: 'OPEN-SOURCE-GPLV3-LICENSE',
        // 是否显示导航，默认为false
        navigation: true,
        // 是否显示横向幻灯片的导航
        slidesNavigation: true,
        // 横向幻灯片导航的位置，可以为top或者bottom
        slidesNavPosition: 'bottom',
        // 横向slide幻灯片是否循环滚动
        loopHorizontal: true,
        // 用来控制slide幻灯片的箭头，设置为false，两侧的箭头会消失
        controlArrows: true,
        // 是否循环滚动，不会出现跳动，效果很平滑
        continuousVertical: false,
        // 是否使用插件滚动方式，设为false后，会出现浏览器自带的滚动条，将不会按页滚动
        // autoScrolling: true,
        // 设置每个section底部的padding，当我们要设置一个固定在底部的菜单、导航、元素等时使用
        // paddingBottom: '0',
        // 滚动到某一屏的回调
        afterLoad: this.afterLoad,
        onLeave: this.onLeave,
        beforeLeave: this.beforeLeave
      }
    }
  },
  methods:{
    // onLeave(origin, destination, direction, trigger){
    //   // console.log(origin,destination,direction,trigger,'onLeave');
    //   // return false
    // },
    beforeLeave(origin, destination, direction, trigger){
      console.log(origin,destination,direction,trigger,'beforeLeave');
      return false
    }
  }
};
</script>

<style>
</style>
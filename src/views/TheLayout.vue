<template>
  <div class="main">
    <left-bar />
    <section class="right-content">
      <the-header />
      <div class="viewer">
        <transition name="fade-move">
          <router-view class="viewer-detail"></router-view>
        </transition>
      </div>
    </section>
  </div>
</template>

<script>
import TheHeader from '@/components/global/TheHeader'
import LeftBar from '@/components/global/LeftBar'
// import TheFooter from '@/components/global/TheFooter'
export default {
  name: 'TheLayout',
  components: {
    TheHeader,
    LeftBar
    // TheFooter
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/index.scss';
.main {
  font-size: 14px;
  font-family: -apple-system,BlinkMacSystemFont,Segoe UI,PingFang SC,Hiragino Sans GB,Microsoft YaHei,Helvetica Neue,Helvetica,Arial,sans-serif,Apple Color Emoji,Segoe UI Emoji,Segoe UI Symbol;
  @include flex(row);
  .right-content {
    flex: 1;
    @include flex;
  }
  .viewer {
    background: #FAFAFA;
    flex: 1;
    overflow: auto;
    overflow-x: hidden;
    margin-top: 5px;
    position: relative;
    @include flex;
    &-detail {
      padding-top: 15px;
      padding-left: 10px;
      padding-right: 10px;
      box-sizing: border-box;
      width: 100%;
      position: absolute;
    }
  }
  .fade-move-enter-active,.fade-move-leave-active {
    transition: .3s all ease;
    // position: absolute
  }
  .fade-move-enter,.fade-move-leave-to {
    opacity: 0;
    transform: translateX(-100px);
  }
  .fade-move-enter-to,.fade-move-leave {
    opacity: 1;
    transform: translateX(0);
  }
}
</style>

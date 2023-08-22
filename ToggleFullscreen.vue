<template>
      <span :class="$style.fullscontrol" @click="toggleFullscreen">
        <img :class="$style.fullsImg" :src="fullScreenIconSrc"/>
      </span>
</template>
  
  <script>
  export default {
    name: 'ToggleFullscreen',
    data () {
      return {
        fullScreenIconExit:'data:image/png;base64,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',
        fullScreenIcon:'data:image/png;base64,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',
        isFullScreen: false
      }
    },
    created () {
      window.addEventListener('keydown', this.KeyDown, true) // 监听按钮事件
    },
    mounted () {
      let that = this
      window.onresize = () => {
        that.checkFull()
      }
    },
    methods: {
      screen () {
        document.documentElement.requestFullscreen()
        this.isFullScreen = true
      },
      KeyDown (event) {
        if (event.keyCode === 122) {
          event.returnValue = false
          this.toggleFullscreen()
        }
      },
      checkFull () {
        if ((!document.fullscreenElement) || (!document.webkitFullscreenElement)) {
          this.isFullScreen = false
        } else {
          this.isFullScreen = true
        }
      },
      toggleFullscreen () {
        if ((!document.fullscreenElement) || (!document.webkitFullscreenElement)) {
          document.documentElement.requestFullscreen()
          // this.isFullScreen = true
        } else {
          this.exitFullscreen()
        }
      },
      exitFullscreen () {
        if (document.exitFullscreen) {
          document.exitFullscreen()
        } else if (document.webkitExitFullscreen) {
          document.webkitExitFullscreen()
        } else if (document.mozCancelFullScreen) {
          document.mozCancelFullScreen()
        } else if (document.msExitFullscreen) {
          document.msExitFullscreen()
        }
      }
    },
    computed: {
      fullScreenIconSrc () {
        return this.isFullScreen ? this.fullScreenIconExit : this.fullScreenIcon
      }
    },
    watch: {
      isFull (newvalue, oldvalue) {
        if (newvalue !== oldvalue) {
          console.log('退出全屏后的事件')
        }
      }
    }
  }
  </script>
  
  <style module>
    .fullscontrol {
      display: flex;
      justify-content: space-between;
      flex-shrink: 0;
      position: absolute;
      top: 0.5%;
      right: 0.5%;
    }
   .fullsImg {
    width: 35px ;
    height: 35px ;
    filter: grayscale(100%) ;
    transition: filter 0.3s ;
    /* opacity: 0.8; */
    :hover {
      filter: none ;
      cursor: pointer ;
      transform: scale(1.2) ;
      }
    }
  </style>
  


  <!-- 
    引用方法：
  <template>
    <div>
      <div>      
        <toggle-fullscreen></toggle-fullscreen> 
      </div>
    </div>
  </template>
  
  <script>
  import ToggleFullscreen from './ToggleFullscreen.vue'; 
  export default {
    components: {
      ToggleFullscreen
    }
  };
  </script> -->
  <!-- toggle-fullscreen使用组件 这里定义为ToggleFullscreen，大写字母改为小写，中间加“-”。或者直接引用也行-->
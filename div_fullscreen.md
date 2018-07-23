## div全屏 放大/缩小
- 放大
```
 launchIntoFullscreen() {
      this.isFullscreenStatus = true
      let element = document.getElementById("demo")
      console.log(element)
      if(element.requestFullscreen) {
        element.requestFullscreen()
      } else if(element.mozRequestFullScreen) {
        element.mozRequestFullScreen()
      } else if(element.webkitRequestFullscreen) {
        element.webkitRequestFullscreen()
      } else if(element.msRequestFullscreen) {
        element.msRequestFullscreen()
      };
    },
```

- 缩小
```
  exitFullscreen() {
      this.isFullscreenStatus = false
      if(document.exitFullscreen) {
        document.exitFullscreen()
      } else if(document.mozCancelFullScreen) {
        document.mozCancelFullScreen()
      } else if(document.webkitExitFullscreen) {
        document.webkitExitFullscreen()
      }
    },
```
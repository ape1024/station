<template>
  <div id="app">
    <hompage></hompage>
  </div>
</template>

<script>
import hompage from './components/homepage/homepage'
export default {
    name: 'app',
    components: {
        hompage
    }
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
html, body
  width 100%
  height 100%
  overflow hidden
  position relative
#app
  width 100%
  height 100%
  font-family 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  text-align center
  color #fff
  background url("../src/assets/subject_background.png") no-repeat
  background-size cover

</style>

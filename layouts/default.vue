<template>
  <div id="app">
    <sm-nav v-if="$mq === 'xs' || $mq === 'md'"/>
    <lg-nav v-if="$mq === 'lg'"/>
    <nuxt/>
    <the-footer/>
  </div>
</template>

<script>
const SmNav = () => import('@/components/SmNav')
const LgNav = () => import('@/components/LgNav')
import TheFooter from '@/components/TheFooter'

export default {
  components: {
    TheFooter,
    LgNav,
    SmNav
  },
  scrollToTop: true
}
</script>

<style lang="sass">

  /* GLOBAL/RESET STYLES */

  html
    background: $color-primary-darker

  body
    position: relative
    background: $color-white
    font-family: $font-body
    font-size: 20px
    //height: 100%
    line-height: 1.4
    color: $color-black
    text-size-adjust: none
    @include x-large
      font-size: 22px
    @include x-small
      font-size: 18px

  a, a:visited
    text-decoration: none
    color: $color-primary-darker
    font-weight: semi-bold
    transition: transform .5s ease-in-out
    &:hover
      transform: scale(1.02)
      @include small
        transform: scale(1.01)

  ul
    list-style-type: none

  *, * + *
    margin: 0
    padding: 0
    box-sizing: border-box

  button
    background: 0
    border: 0
    box-shadow: 0

  #app
    //min-height: 100vh

  // MAIN WRAPPER
  .wrapper
    position: relative
    max-width: $normal-width
    margin: auto

  // MAIN SECTIONS
  .section
    display: flex
    flex-wrap: wrap
    padding: 4em 1em 1em
    margin: 0 auto
    @include small
      padding-top: 3em

  // HEADINGS
  .heading
    color: $color-black
    font-size: 2.4em
    font-weight: 300
    margin-bottom: .2em
    hyphens: auto
    @include small
      font-size: 2.1em

  .sub-heading
    font-weight: 600
    margin-top: 1em
    margin-bottom: .2em
    hyphens: auto

  // CONTENT
  .article, .illustration
    flex-basis: 50%
    @include small
      flex-basis: 100%

  p:not(:last-child)
    margin-bottom: 1em

  // ILLUSTRATIONS
  .illustration
    padding: 0 4em
    align-self: center
    @include small
      padding: 0 1em

  .illustration-medium
    float: right
    shape-outside: circle(50%)
    svg
      height: 300px

  .illustration svg
    width: 100%
    max-height: 600px

  // LINK STYLES
  .inline-link
    color: $color-primary
    font-weight: 600
    text-decoration: none
    cursor: pointer

  img[lazy=loading]
    opacity: 0

  img[lazy=loaded]
    opacity: 1
    transition: all .5s ease-in

</style>

<style>
.page-enter-active {
  animation: acrossIn 0.45s ease-out both;
}

.page-leave-active {
  animation: acrossOut 0.65s ease-in both;
}

@keyframes acrossIn {
  0% {
    transform: translate3d(-100%, 0, 0);
  }
  100% {
    transform: translate3d(0, 0, 0);
  }
}

@keyframes acrossOut {
  0% {
    transform: translate3d(0, 0, 0);
  }
  100% {
    transform: translate3d(100%, 0, 0);
  }
}
</style>
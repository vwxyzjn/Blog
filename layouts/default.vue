<template>
  <b-container>
    <b-row >
      <b-col cols="12" lg="4">
        <div class="sticky-top sidebar" >
          <profile-info ></profile-info>
        </div>
      </b-col>
      <b-col cols="12" lg="8"  class="content">
        <transition name="fade" mode="out-in">
          <nuxt />
        </transition>
        <!-- <resume></resume> -->
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import Vue from 'vue'
import BootstrapVue from 'bootstrap-vue'
import articleView from '@/components/articleView.vue'
import ProfileInfo from '@/components/Profile.vue'

Vue.use(BootstrapVue)
Vue.component('article-view', articleView)

export default {
  name: 'app',
  components: {
    ProfileInfo
  }
}
</script>

<style lang="sass">
@import "../node_modules/bootstrap/scss/bootstrap-grid.scss"

*
  font-family: 'Roboto', sans-serif, -apple-system, "Helvetica Neue", Arial

.fade-enter-active, .fade-leave-active
  transition: opacity .35s

.fade-enter, .fade-leave-to
  opacity: 0

.sidebar
  padding-top: 2rem
  @include media-breakpoint-up(lg) 
    padding-top: 6rem

.content
  padding: 0 20px
  padding-top: 2rem

body
  font-size: 18px
  line-height: 1.618em
  margin-bottom: 1.618em

  @include media-breakpoint-up(sm)
    font-size: 1.2rem

p
  margin-bottom: 1.618em

h1
  font-size: 2em
  line-height: 1.19em
  margin-bottom: 0.5em
  margin-top: 0.32em
  @media (min-width: 36em)
    font-size: 2.618em

</style>

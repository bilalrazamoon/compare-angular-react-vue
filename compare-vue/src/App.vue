<template>
  <div id="app">
    <div class="nav has-shadow">
      <div class="container">
        <div class="nav-left">
          <a class="nav-item">My Company</a>
        </div>

        <div class="nav-toggle" v-on:click="toggleNav" v-bind:class="{ 'is-active': isActive }">
          <span></span>
          <span></span>
          <span></span>
        </div>

        <div class="nav-right nav-menu" v-bind:class="{ 'is-active': isActive }">
          <router-link to="/" class="nav-item r-item">Home</router-link>
          <router-link to="/faq" class="nav-item r-item">Features</router-link>
          <router-link to="/faq" class="nav-item r-item">About</router-link>
          <router-link to="/faq" class="nav-item r-item">FAQ</router-link>


          <div class="nav-item">
            <p class="control">
              <a class="button is-primary is-outlined">
                <span class="icon">
                  <i class="fa fa-download"></i>
                </span>
                <span>Join Now</span>
              </a>
            </p>
          </div>

        </div>
      </div>
    </div>
    <router-view></router-view>

    <div class="footer">
      <div class="container">
        <div class="columns">
          <div class="column">
            <p>And this right here is a spiffy footer, where you can put stuff.</p>
          </div>

          <div class="column has-text-right">
            <a href="#" class="icon">
              <i class="fa fa-facebook"></i>
            </a>
            <a href="#" class="icon">
              <i class="fa fa-twitter"></i>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data: function () {
    return {
      isActive: false
    }
  },
  methods: {
    toggleNav: function () {
      this.isActive = !this.isActive
    }
  }
}
</script>

<style lang="sass">
@import '../node_modules/bulma/bulma.sass'

@import 'mq'

.nav
  background-color: #383838
  a:hover
    color: grey

  .nav-left a
    color: #fff
    font-weight: bold

  a.r-item
    color: #C1C1C1
    padding: 0.5rem 1.75rem
    +mobile
      color: grey
      &:hover
        background-color: #F1F1F1

.nav-toggle span
  background-color: #C1C1C1


.footer
  background-color: $primary !important
  color: #fff
  .icon
    color: #fff
    margin-left: 20px
</style>

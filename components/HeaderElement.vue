<template>
  <fixed-header>
    <header class="br_header header-default header-transparent light-logo--version header-fixed-width headroom--sticky header-mega-menu clearfix">
      <div class="container-fluid">
        <div class="row">
          <div class="col-12">
            <div class="header__wrapper mr--0">
              <!-- Header Left start -->
              <div class="header-left flex-20">
                <div class="logo">
                  <n-link to="/">
                    <img src="/img/logo/logo.png" alt="VaccineDallas Logo">
                  </n-link>
                </div>
              </div>
              <!-- Header Left end -->

              <!-- Mainmenu Wrap start -->
              <div class="mainmenu-wrapper d-none d-lg-block">
                <Navigation />
              </div>
              <!-- Mainmenu Wrap end -->

              <!-- Header Right start -->
              <div class="header-right">
                <!-- Start Popup Search Wrap -->
                <!-- <div class="popup-search-wrap">
                  <a class="btn-search-click" href="javascript:void(0)" @click="toggleClass('addClass', 'search-popup-open')">
                    <i class="fa fa-search" />
                  </a>
                </div> -->
                <!-- End Popup Search Wrap -->

                <!-- Start Hamberger -->
                <div class="manu-hamber popup-mobile-click d-block d-lg-none light-version d-block d-xl-none" @click="mobiletoggleClass('addClass', 'show-mobile-menu')">
                  <div>
                    <i />
                  </div>
                </div>
                <!-- End Hamberger -->
              </div>
              <!-- Header Right end -->
            </div>
          </div>
        </div>
      </div>
    </header>
  </fixed-header>
</template>

<script>
import FixedHeader from 'vue-fixed-header'
import Navigation from '@/components/Navigation'

export default {
  components: {
    FixedHeader,
    Navigation
  },

  methods: {
    // offcanvas search
    toggleClass (addRemoveClass, className) {
      const el = document.querySelector('#search-popup')
      if (addRemoveClass === 'addClass') {
        el.classList.add(className)
      } else {
        el.classList.remove(className)
      }
    },

    // offcanvas mobilemenu open
    mobiletoggleClass (addRemoveClass, className) {
      const el = document.querySelector('#offcanvas-menu')
      if (addRemoveClass === 'addClass') {
        el.classList.add(className)
      } else {
        el.classList.remove(className)
      }
    }
  }
}
</script>

<style lang="scss" scoped>
    .vue-fixed-header--isFixed {
        top: 0;
        left: 0;
        width: 100vw;
        z-index: 999;
        position: fixed !important;
        background-color: rgba($black, 0.9);
        box-shadow: 0 0 8px 1px rgba(0, 0, 0, 0.2);
        animation: 900ms cubic-bezier(0.2, 1, 0.22, 1) 0s normal none 1 running fadeInDown;
    }
</style>

<template>
  <div id="app" class="app sidebar-show">
    <header class="app-header navbar">
      <b-link class="navbar-brand" to="#">
        <img class="navbar-brand-full" src="./assets/logo.png" width="89" height="25" alt="CoreUI Logo">
        <img class="navbar-brand-minimized" src="./assets/logo.png" width="30" height="30" alt="CoreUI Logo">
      </b-link>
      <b-navbar-nav class="d-md-down-none">
        <b-nav-item class="px-3" to="/">Home</b-nav-item>
        <b-nav-item class="px-3" to="/About" exact>About</b-nav-item>
        <b-nav-item class="px-3">Settings</b-nav-item>
      </b-navbar-nav>
    </header>
    <div class="app-body">
      <div class="sidebar">
        <nav class="sidebar-nav">
          <ul class="nav">
            <li class="nav-title">Nav Title</li>
            <li class="nav-item">
              <router-link class="nav-link"  to="/"><i class="nav-icon cui-home"></i> Home</router-link>
            </li>
            <li class="nav-item">
              <router-link class="nav-link" to="/about"><i class="nav-icon cui-puzzle"></i> About</router-link>
            </li>
            <li class="nav-item nav-dropdown">
              <a class="nav-link nav-dropdown-toggle" href="#" @click="handleClick">
                <i class="nav-icon cui-puzzle"></i> Nav dropdown
              </a>
              <ul class="nav-dropdown-items">
                <li class="nav-item">
                  <a class="nav-link" href="#">
                    <i class="nav-icon cui-puzzle"></i> Nav dropdown item
                  </a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#">
                    <i class="nav-icon cui-puzzle"></i> Nav dropdown item
                  </a>
                </li>
              </ul>
            </li>
          </ul>
        </nav>
      </div>
      <main class="main">
        <div class="main-view">
          <router-view></router-view>
        </div>
      </main>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
  components: {
  },
})
export default class App extends Vue {

  public handleClick(e: Event) {
      e.preventDefault();
      (e as any).target.parentElement.classList.toggle('open');
  }
}
</script>


<style lang="scss">
  // CoreUI Icons Set
  @import '~@coreui/icons/css/coreui-icons.min.css';
  /* Import Font Awesome Icons Set */
  $fa-font-path: '~font-awesome/fonts/';
  @import '~font-awesome/scss/font-awesome.scss';
  /* Import Bootstrap Vue Styles */
  @import '~bootstrap-vue/dist/bootstrap-vue.css';
  @import "~@coreui/coreui/scss/coreui";

  .main {
    padding: 20px;
  }

  .main-view {
    background-color: white;
    padding: 20px;
  }
</style>

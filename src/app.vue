<template>
  <div id="app">
    <aside class="mdc-drawer mdc-drawer--modal">
      <div class="mdc-drawer__content">
        <nav class="mdc-list">
          <a class="mdc-list-item mdc-list-item--activated" href="#" aria-selected="true">
            <i class="material-icons mdc-list-item__graphic" aria-hidden="true">inbox</i>
            <span class="mdc-list-item__text">Inbox</span>
          </a>
          <a class="mdc-list-item" href="#">
            <i class="material-icons mdc-list-item__graphic" aria-hidden="true">send</i>
            <span class="mdc-list-item__text">Outgoing</span>
          </a>
          <a class="mdc-list-item" href="#">
            <i class="material-icons mdc-list-item__graphic" aria-hidden="true">drafts</i>
            <span class="mdc-list-item__text">Drafts</span>
          </a>
        </nav>
      </div>
    </aside>

    <div class="mdc-drawer-scrim"></div>

    <div class="mdc-drawer-app-content">
      <header class="mdc-top-app-bar app-bar" id="app-bar">
        <div class="mdc-top-app-bar__row">
          <section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-start">
            <a href="#" class="demo-menu material-icons mdc-top-app-bar__navigation-icon">menu</a>
            <span class="mdc-top-app-bar__title">Modal Drawer</span>
          </section>
        </div>
      </header>

      <main class="main-content" id="main-content">
        <div class="mdc-top-app-bar--fixed-adjust">
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        </div>
      </main>
    </div>

  </div>
</template>

<script>
  import {MDCTopAppBar} from "@material/top-app-bar"
  import {MDCDrawer} from "@material/drawer";

  document.addEventListener("DOMContentLoaded", () => {
    const drawer = MDCDrawer.attachTo(document.querySelector('.mdc-drawer'));

    const topAppBar = MDCTopAppBar.attachTo(document.getElementById('app-bar'))
    topAppBar.setScrollTarget(document.getElementById('main-content'))
    topAppBar.listen('MDCTopAppBar:nav', () => {
        drawer.open = !drawer.open;
    })
  })

  export default {
    name: 'Application'
  }
</script>

<style lang="scss">
  @import '@material/top-app-bar/mdc-top-app-bar.scss';
  @import "@material/drawer/mdc-drawer.scss";
  @import "@material/list/mdc-list.scss";

  body {
    display: flex;
    height: 100vh;
  }

  .mdc-drawer-app-content {
    flex: auto;
    overflow: auto;
    position: relative;
  }

  .main-content {
    overflow: auto;
    height: 100%;
  }

  .app-bar {
    position: absolute;
  }
</style>

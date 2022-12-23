<template>
  <div id="wrapper">
    <nav class="navbar is-dark">
      <div class="navbar-brand">
        <router-link to="/" class="navbar-item"><strong>ФК Щучин</strong></router-link>
        <a class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navbar-menu" @click="showMobileMenu = !showMobileMenu">
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>

      <div class="navbar-menu" id="navbar-menu" :class="{'is-active': showMobileMenu}">
        <div class="navbar-end">
          <router-link to="/footsal" class="navbar-item">Футзал</router-link>
          <router-link to="/beach_soccer" class="navbar-item">Пляжный футбол</router-link>
          <router-link to="/football" class="navbar-item">Большой футбол</router-link>
          <router-link to="/contacts" class="navbar-item">Контакты</router-link>
          <router-link to="/achievements" class="navbar-item">Наши достижения</router-link>
        </div>
      </div>
    </nav>

    <section class="section">
      <router-view />
    </section>

    <footer class="footer">
      <p class="has-text-centered">Футбольный клуб Щучин </p>
    </footer>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      showMobileMenu: false
    }
  },
}
</script>

<style lang="scss">
@import '../node_modules/bulma';
</style>
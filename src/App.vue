<template>
  <div id="app">
    <!-- Navbar -->
    <div id="nav" class="container nav">
      <!-- Logo site -->
      <h1>
        <router-link to="/">
          <img :src="require('@/assets/images/logo_designo.png')" alt="logo designo">
        </router-link>
      </h1>
      <!-- Button nav -->
      <div>
        <img :src="require('@/assets/images/icon_menu.svg')" alt="icon menu" 
          class="btnOpen visible"
          @click="openMenu">
          <img :src="require('@/assets/images/icon_close.svg')" alt="icon menu" 
          class="btnClose"
          @click="closeMenu">
      </div>
      <!-- Links -->
      <div class="nav__links" @click="closeMenu">
        <ul class="nav__links__ul">
          <li class="nav__links__li"><router-link to="/">our compagny</router-link></li>
          <li class="nav__links__li"><router-link to="/about">locations</router-link></li>
          <li class="nav__links__li"><router-link to="/about">contact</router-link></li>
        </ul>
      </div>
      
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
   methods: {
    openMenu() {
      document.querySelector('.nav__links').classList.add('open');
      document.querySelector('.btnOpen').classList.remove('visible');
      document.querySelector('.btnClose').classList.add('visible');
    },
    closeMenu() {
      document.querySelector('.nav__links').classList.remove('open');
      document.querySelector('.btnOpen').classList.add('visible');
      document.querySelector('.btnClose').classList.remove('visible');
    }
   }
}
</script>

<style src="@/assets/scss/app.scss" lang="scss"></style>

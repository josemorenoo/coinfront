<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header class="header">
    <div class="wrapper">
      <img alt="Coin Commit" class="logo" src="@/assets/logo_and_title.png" @click="$router.push('/')" />
      <nav>
        <RouterLink to="/">Top Ten</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
      <a href="https://twitter.com/coin_commit" target="_blank" class="logo_container">
        <img src="@/assets/twitterlogo.png" class="twitter_logo" alt="@coin_commit">
      </a>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  display: flex;
  place-items: flex-start;
  flex-wrap: nowrap;
  border-bottom: 0.005rem solid #21254A;
  height: 4rem;
  width: 100%;
}

.wrapper {
  padding-left: 6rem;
  padding-right: 6rem;
  height: 4.5rem;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background-color: #110B27;
}

.logo {
  margin: 0.2rem auto 2rem;
  height: 4rem;
  width: auto;
  max-width: 200px;
  max-height: 200px;
}

.twitter_logo {
  margin: 0.8rem 1rem 0 0;
  height: auto;
  width: auto;
  max-width: 40px;
  max-height: 40px;
}

.logo_container {
  padding-left: 2rem;
}

nav {
  width: 100%;
  text-align: center;
  margin-top: 0.4rem;
}

nav a {
  /* Body text */
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 18px;

  color: #CCD1E8;

  display: inline-block;
  padding: 0 2rem;
  text-decoration: none;
}

nav a.router-link-exact-active {
  text-decoration: underline;
  text-underline-position: under;
  text-underline-offset: 1.4rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
    border-bottom: 0.005rem solid #21254A;
    width: 100%;
    height: fit-content;
  }

  header .wrapper {
    padding-left: 6rem;
    padding-right: 6rem;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    display: flex;
    place-items: flex-start;
    flex-wrap: nowrap;
    border-bottom: 0.005rem solid #21254A;
  }

  .logo {
    height: 4rem;
  }

  .twitter_logo {
    margin: 0.8rem 1rem 0 0;
    height: auto;
    width: auto;
    max-width: 40px;
    max-height: 40px;
  }




  nav {
    text-align: left;
    margin-left: 2rem;
    font-size: 1rem;
    padding: 1rem 0;
  }

}
</style>

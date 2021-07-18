<template>
  <aside class="aside">
    <router-link to="/" class="aside__title">
      <img src="/icon-cinema.svg" alt="Cinema Icon" />
      <h1>&nbsp; MOOV APP</h1>
    </router-link>

    <nav class="aside__section">
      <header>
        <h3>MENU</h3>
      </header>
      <router-link to="/">
        <img src="/icon-home.svg" alt="Home Icon" />
        <h2>&nbsp; Home</h2>
      </router-link>
      <a href="#">
        <img src="/icon-community.svg" alt="Community Icon" />
        <h2>&nbsp; Community</h2>
      </a>
      <a href="#">
        <img src="/icon-discovery.svg" alt="Discovery Icon" />
        <h2>&nbsp; Discovery</h2>
      </a>
      <a href="#">
        <img src="/icon-comingsoon.svg" alt="Coming Soon Icon" />
        <h2>&nbsp; Coming Soon</h2>
      </a>
    </nav>

    <nav class="aside__section">
      <header>
        <h3>SOCIAL</h3>
      </header>
      <a href="#">
        <img src="/icon-friends.svg" alt="Friends Icon" />
        <h2>&nbsp; Friends</h2>
      </a>
      <a href="#">
        <img src="/icon-parties.svg" alt="Parties Icon" />
        <h2>&nbsp; Parties</h2>
      </a>
      <a href="#">
        <img src="/icon-media.svg" alt="Media Icon" />
        <h2>&nbsp; Media</h2>
      </a>
    </nav>

    <nav class="aside__section">
      <header>
        <h3>GENERAL</h3>
      </header>
      <a href="#">
        <img src="/icon-setting.svg" alt="Setting Icon" />
        <h2>&nbsp; Setting</h2>
      </a>
      <a href="#">
        <img src="/icon-logout.svg" alt="Log Out Icon" />
        <h2>&nbsp; Log Out</h2>
      </a>
    </nav>
  </aside>
</template>

<script>
export default {
  name: "Sidebar",
};
</script>

<style scoped>
</style>

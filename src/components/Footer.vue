<template>
  <footer class="footer">
    <div class="footer__pages">
      <h5 class="footer__title">PAGES</h5>
      <div class="container">
        <div class="container-section">
          <a href="#">Main</a>
          <a href="#">Series</a>
          <a href="#">TV</a>
          <a href="#">Films</a>
        </div>

        <div class="container-section">
          <a href="#">Subscribtion</a>
          <a href="#">Shop</a>
          <a href="#">Blog</a>
        </div>

        <div class="container-section">
          <a href="#">Contact</a>
          <a href="#">Support</a>
          <a href="#">Search</a>
          <a href="#">User Agreement</a>
        </div>
      </div>
    </div>

    <div class="footer__updates">
      <h5 class="footer__title">NEWS & FILMS UPDATES</h5>
      <p>Follow the interesting events in the world of movies and TV series</p>
      <form class="footer__form" action="">
        <input type="email" name="email" id="email" placeholder="Your Email" />
        <button type="submit">
          <img src="/icon-send.svg" alt="Search Bar" />
        </button>
      </form>
      <h5 class="footer__title">SOCIAL NETWORKS</h5>
      <div class="footer__icon">
        <a href="#"><img src="/icon-youtube.svg" alt="" /></a>
        <a href="#"><img src="/icon-instagram.svg" alt="" /></a>
        <a href="#"><img src="/icon-twitter.svg" alt="" /></a>
        <a href="#"><img src="/icon-facebook.svg" alt="" /></a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
</style>

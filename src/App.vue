<template>
  <main>
    <Sidebar />
    <router-view></router-view>
  </main>

  <Footer />
</template>

<script>
import Sidebar from "./components/Sidebar.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Sidebar,
    Footer,
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}

a {
  text-decoration: none;
  color: black;
}

main {
  display: flex;
  justify-content: space-between;
  background-color: #fefefe;
}

/* sidebar */
aside {
  width: 100%;
  max-width: 250px;
  padding-top: 40px;
  padding-left: 30px;
  display: flex;
  flex-direction: column;

  .aside__title {
    max-width: 170px;
    padding-bottom: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .aside__section header {
    padding-top: 40px;
    padding-bottom: 22px;
    color: #d3d3d3;
  }

  .aside__section a {
    max-width: 170px;
    padding-bottom: 15px;
    font-size: 11px;
    color: #a9a9a9;
    display: flex;
    justify-content: flex-start;
    align-items: center;
  }

  .aside__section a:hover {
    color: #000000;
  }
}
/* sidebar end */

.section {
  width: 100%;

  .search-box {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding-top: 30px;
    padding-right: 30px;
    padding-left: 30px;
    padding-bottom: 10px;
  }

  .search-box input {
    display: block;
    appearance: none;
    border: none;
    outline: none;
    background: none;
  }

  .search-box input[type="text"] {
    width: 100%;
    max-width: 1000px;
    color: #fff;
    background-color: #d3d3d3;
    font-size: 18px;
    padding: 10px 16px;
    border-radius: 8px;
    transition: 0.4s;
  }

  .search-box input::placeholder {
    color: white;
  }

  .search-box input:focus {
    box-shadow: 8px 3px 6px #00000033;
  }

  .search-box input[type="submit"] {
    width: 100%;
    max-width: 100px;
    color: #fff;
    background-color: #d3d3d3;
    font-size: 18px;
    padding: 10px 16px;
    border-radius: 8px;
    text-transform: uppercase;
    transition: 0.4s;
  }
  .search-box input:active {
    background-color: #a9a9a9;
  }

  .section__nav {
    text-align: center;
    font-size: 18px;
    padding-top: 15px;
    padding-bottom: 15px;
  }

  .section__nav a {
    color: #a9a9a9;
    font-size: 20px;
  }

  .section__nav a:hover {
    color: #000000;
  }

  .feature {
    margin-right: 30px;
    margin-left: 15px;
    margin-bottom: 20px;

    .feature-card {
      position: relative;

      .featured-img {
        display: block;
        width: 100%;
        height: 600px;
        object-fit: cover;
        position: relative;
        z-index: 0;
        border-radius: 8px;
      }
      .detail {
        position: absolute;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: #00000099;
        padding: 16px;
        z-index: 1;
        border-radius: 8px;

        h3 {
          color: #fff;
          margin-bottom: 16px;
        }

        p {
          color: #fff;
        }
      }
    }
  }
}

/* footer */
footer {
  width: 100%;
  height: 300px;
  margin-top: 45px;
  padding-right: 150px;
  padding-left: 150px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #a9a9a9;

  .footer__pages {
    width: 100%;
    max-width: 600px;
  }

  .footer__title {
    padding-bottom: 20px;
    font-size: 20px;
  }

  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .container-section {
    height: 150px;
    font-size: 18px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  .container-section a {
    margin-bottom: 10px;
  }

  .footer__updates {
    width: 100%;
    max-width: 600px;
    padding-top: 10px;
  }

  .footer__form {
    margin: 10px 0px;
    display: flex;
    align-items: center;
  }

  .footer__form input {
    padding: 7px;
    margin-right: 10px;
  }

  .footer__icon img {
    margin-right: 10px;
  }
}
/* footer end */

/* movie card */
.featured-header {
  font-size: 25px;
  margin-top: 40px;
  margin-left: 15px;
}

.movies-list {
  display: flex;
  flex-wrap: wrap;
  margin: 0px 8px;

  .movie {
    max-width: 33%;
    flex: 1 1 33%;
    padding: 16px 8px;

    .movie-link {
      display: flex;
      flex-direction: column;
      height: 100%;

      .product-image {
        position: relative;
        display: block;

        img {
          display: block;
          width: 100%;
          height: auto;
          max-height: 300px;
          object-fit: cover;
          border-radius: 8px 8px 0 0;
        }

        .type {
          position: absolute;
          padding: 8px 16px;
          background-color: #d3d3d3;
          color: #fff;
          bottom: 16px;
          left: 0px;
          text-transform: capitalize;
        }
      }

      .detail {
        background-color: #a9a9a9;
        padding: 16px 8px;
        flex: 1 1 100%;
        border-radius: 0px 0px 8px 8px;

        .year {
          color: #000000;
          font-size: 14px;
        }

        h3 {
          color: #ffffff;
          font-weight: 400;
          font-size: 18px;
        }
      }
    }
  }
}
/* movie card end */
</style>

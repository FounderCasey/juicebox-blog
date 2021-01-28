<template>
  <nav>
    <div class="logoContainer">
      <img src="../assets/logo.svg" alt="" />
      <router-link class="navLink" id="logoTitle" to="/"
        >Juicebox.<span>blog</span></router-link
      >
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style lang="scss" scoped>
nav {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 1198px;
  height: 75px;
  margin: auto;

  a {
    text-decoration: none;
    color: #2d3958;
    font-weight: 700;
    font-size: 1.4rem;
    font-family: "Poppins";
  }

  .logoContainer {
    display: flex;
    justify-content: flex-start;
    align-items: center;

    img {
      width: 25px;
      margin-right: 8px;
    }
  }

  #logoTitle {
    font-size: 1.4rem;
    font-weight: 700;
  }

  span {
    font-weight: 400;
  }

  div {
    a {
      font-weight: 400;
      font-size: 1rem;
      &:first-of-type {
        margin-right: 50px;
      }
    }
  }
}

@media only screen and (max-width: 82em) {
  nav {
    width: 90%;
    margin: auto;
  }
}
</style>

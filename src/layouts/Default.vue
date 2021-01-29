<template>
  <div class="layout">
    <Navbar />
    <div style="margin-top: 70px;"></div>
    <slot />
  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue";

export default {
  components: {
    Navbar,
  },
};
</script>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style>
body {
  font-family: "Poppins";
  margin: 0;
  padding: 0;
  line-height: 1.5;
  width: 100%;
  color: #2d3958;
}

.layout {
  margin: 0 auto;
}

.primaryInput {
  font-family: "Poppins";
  font-size: 1.025rem;
  border: none;
  outline: none;
  border-radius: 3px;
  padding: 8px 10px;
  margin-right: 15px;
  font-weight: 600;
  box-shadow: 0 0 0 2px #cacdd5;
  color: #2d3958;
}

.flexStart {
  display: flex;
  justify-content: flex-start;
  align-items: flex-start;
}
.flexBetween {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.flexEvenly {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}
.flexCenter {
  display: flex;
  justify-content: center;
  align-items: center;
}
.flexCenterStart {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding-left: 15px;
}
.flexColumnBetween {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  align-items: center;
}
.flexColumnBetweenStart {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  align-items: flex-start;
}
.flexColumnStart {
  display: flex;
  justify-content: flex-start;
  flex-direction: column;
  align-items: flex-start;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
}
</style>

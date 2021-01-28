<template>
  <Layout>
    <div class="container">
      <header>
        <h1 class="slide-in-top">Juicebox</h1>
        <p class="slide-in-bottom">
          We wanted to share what we're passionate about. Take a dive in and let
          us know what you're thinking!
        </p>
        <img src="../assets/particles.svg" alt="" />
        <img src="../assets/particles.svg" alt="" />
      </header>
      <div class="info fade-in">
        <h2>Popular Posts</h2>
        <p>
          First and foremost, we’re people. Humans, just like you. After that,
          we’re happily titled with roles like: engineer, designer, support,
          marketer, sales. We’re also 100% remote and globally distributed. We
          encourage creativety and freedom of thinking.
        </p>
      </div>
    </div>
    <Footer />
  </Layout>
</template>

<script>
import Footer from "../components/Footer";
export default {
  metaInfo: {
    title: "Hello, world!",
  },
  data() {
    return {
      email: "",
    };
  },
  components: {
    Footer,
  },
};
</script>

<style lang="scss" scoped>
.container {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  max-width: 1198px;
  margin: 0 auto;
  padding-top: 70px;

  h1 {
    margin-bottom: 0;
  }
}

.primaryButton {
  padding: 10px 40px;
  background: #6a35ff;
  color: #f8faff;
  outline: none;
  border: none;
  border-radius: 3px;
  font-size: 1.1rem;
  font-family: "Poppins";
  font-size: 1.025rem;
  cursor: pointer;

  &:active {
    background: #5525da;
  }
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
}

header {
  position: relative;
  border-radius: 5px;
  width: 1198px;
  height: 450px;
  margin: 0;
  background: #6a35ff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  color: #f8faff;
  h1 {
    font-size: clamp(1.5rem, 3vw, 3.5rem);
    margin: 0;
  }
  p {
    width: 50%;
    font-weight: 500;
    font-size: clamp(0.85rem, 1vw, 1rem);
    text-align: center;
  }
  img {
    position: absolute;
    &:first-of-type {
      left: 0;
      bottom: 0;
    }
    &:last-of-type {
      right: 0;
      bottom: -10px;
      transform: scaleX(-1);
    }
  }
}
.info {
  width: 1198px;
  margin: auto;
  padding: 55px 0;
  text-align: center;
  h2 {
    font-size: 2rem;
    margin: 0 0 15px 0;
  }
  p {
    margin: auto;
    width: 50%;
    font-weight: 500;
  }
  // &:last-of-type {
  //   padding-top: 0;
  // }
  a {
    color: #6a35ff;
    text-decoration: none;
  }
}
@media only screen and (max-width: 1198px) {
  #about {
    header,
    .info {
      width: 90%;
      margin: auto;
    }
    img {
      width: 25%;
    }
  }
}
@media only screen and (max-width: 768px) {
  header {
    height: 350px;
  }
  header,
  .info {
    width: 90%;
    margin: auto;
    h1,
    h2,
    h3 {
      font-size: clamp(1.5rem, 3vw, 3.5rem);
    }
    h3 {
      margin-bottom: 15px;
    }
    p {
      width: 90%;
      margin: inherit auto;
      font-size: clamp(0.85rem, 1vw, 1rem);
    }
  }
  img {
    width: 25%;
  }
}
.slide-in-top {
  -webkit-animation: slide-in-top 1s ease-out both;
  animation: slide-in-top 1s ease-out both;
}
.slide-in-bottom {
  -webkit-animation: slide-in-bottom 1s ease-out both;
  animation: slide-in-bottom 1s ease-out both;
}
.fade-in {
  -webkit-animation: fade-in 0.95s ease-out both;
  animation: fade-in 0.95s ease-out both;
}
@-webkit-keyframes slide-in-top {
  0% {
    -webkit-transform: translateY(-300px);
    transform: translateY(-300px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    opacity: 1;
  }
}
@keyframes slide-in-top {
  0% {
    -webkit-transform: translateY(-300px);
    transform: translateY(-300px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    opacity: 1;
  }
}
@-webkit-keyframes slide-in-bottom {
  0% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    opacity: 1;
  }
  100% {
    -webkit-transform: translateY(-300px);
    transform: translateY(-300px);
    opacity: 0;
  }
}
@keyframes slide-in-bottom {
  0% {
    -webkit-transform: translateY(300px);
    transform: translateY(300px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    opacity: 1;
  }
}
@-webkit-keyframes fade-in {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
@keyframes fade-in {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>

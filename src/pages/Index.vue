<template>
  <Layout>
    <div class="container">
      <header id="hero">
        <h1 class="slide-in-top">Juicebox's Blog</h1>
        <p class="slide-in-bottom">
          We wanted to share what we're passionate about. Take a dive in and let
          us know what you're thinking!
        </p>
        <img src="../assets/particles.svg" alt="" />
        <img src="../assets/particles.svg" alt="" />
      </header>
      <div class="info fade-in">
        <h2>Popular Posts</h2>
        <br />
        <div class="posts">
          <PostCard
            v-for="edge in $page.posts.edges"
            :key="edge.node.id"
            :post="edge.node"
          />
        </div>
      </div>
    </div>
    <Footer />
  </Layout>
</template>

<page-query>
query {
  posts: allPost(filter: { published: { eq: true }}) {
    edges {
      node {
        id
        title
        date (format: "D. MMMM YYYY")
        timeToRead
        description
        cover_image (width: 1200, height: 250, blur: 10)
        path
        tags {
          id
          title
          path
        }
      }
    }
  }
}
</page-query>

<script>
import Footer from "../components/Footer";
import Author from "~/components/Author.vue";
import PostCard from "~/components/PostCard.vue";
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
    Author,
    PostCard,
  },
};
</script>

<style lang="scss" scoped>
.container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  max-width: 1198px;
  margin: 0 auto;

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

#hero {
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
  height: auto;
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
  #hero,
  .info {
    width: 90%;
    margin: auto;
  }
  img {
    width: 25%;
  }
}

@media only screen and (max-width: 768px) {
  #hero {
    height: 350px;
  }
  #hero,
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
    width: 35%;
    &:first-of-type {
      transform: scaleY(-1);
      top: -40px;
    }
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

<template>
  <footer>
    <div class="container">
      <div class="linksContainer">
        <div class="links">
          <a href="//blog.getjuicebox.io/" class="title">Blog</a>
          <a href="//blog.getjuicebox.io/">Remote Teams</a>
          <a href="//blog.getjuicebox.io/">Success Stories</a>

          <a href="//blog.getjuicebox.io/">Transparency</a>
        </div>
        <div class="links">
          <a href="//help.getjuicebox.io/" class="title">Knowledgebase</a>
          <a href="//help.getjuicebox.io/en/category/general-tpqz9g/"
            >General</a
          >
          <a href="//help.getjuicebox.io/en/category/members-thurbv/"
            >Members</a
          >
          <a href="//help.getjuicebox.io/en/category/admins-upxba0/">Admins</a>
        </div>
        <div class="links">
          <router-link class="title" to="/">Juicebox</router-link>
          <router-link to="/about">About Us</router-link>

          <router-link to="/careers">Careers</router-link>
          <a href="//twitter.com/useJuicebox">Our Twitter</a>
        </div>
      </div>
      <div class="betaContainer" v-if="$route.name != 'Rewards'">
        <h1 v-if="showBeta">Hey! Join our <br />beta, it's free!</h1>
        <h1 v-else>Thanks for joining!</h1>

        <input
          class="primaryInput"
          type="email"
          v-model="email"
          placeholder="Email"
          v-on:keyup.enter="beta"
        />
        <Button :onClick="beta">Join Beta</Button>
      </div>
    </div>
    <div class="flexBetween">
      <div class="flexCenterStart">
        <div class="logoContainer">
          <img src="../assets/logo.svg" alt="" />
          <p>Copyright © 2020 Juicebox. All Rights Reserved</p>
        </div>
      </div>
      <a href="mailto:help@getjuicebox.io">help@getjuicebox.io</a>
    </div>
  </footer>
</template>

<script>
import { db } from "../main";
import Button from "./Button";
export default {
  name: "Footer",
  data() {
    return {
      email: "",
      showBeta: true,
    };
  },

  methods: {
    beta: function() {
      db.collection("beta")
        .doc(this.email)
        .set({
          email: this.email,
          created: new Date(),
        })
        .then(() => {
          this.showBeta = false;
        });
    },
  },
  components: {
    Button,
  },
};
</script>

<style lang="scss" scoped>
footer {
  background: #2d3958;
  color: white;
  padding: 50px 0 10px 0;

  .linksContainer {
    display: flex;

    .links {
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      align-items: flex-start;
      margin-right: 75px;

      .title {
        font-weight: 700;
      }

      a {
        font-size: 1rem;
        margin: 7px 0;

        &:first-of-type {
          margin-top: 0;
        }

        &:last-of-type {
          margin-bottom: 0;
        }
      }
    }
  }

  .betaContainer {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-end;

    h1 {
      margin: 0;
    }

    .primaryInput {
      margin: 20px 0 25px;

      width: 100%;
    }
  }

  .container {
    max-width: 1198px;
    margin: auto;

    display: flex;
    justify-content: space-between;
    align-items: center;

    h1 {
      font-size: clamp(1.5rem, 3vw, 2.5rem);
      margin-top: 0;
      font-weight: 600;
    }

    a {
      text-decoration: none;
      color: white;

      &:hover {
        color: #6a35ff;
      }
    }
  }
}

.flexBetween {
  max-width: 1198px;
  margin: 45px auto 0 auto;

  a {
    text-decoration: none;
    color: white;
  }

  .flexCenterStart {
    padding-left: 0;
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
}

@media only screen and (max-width: 1198px) {
  footer {
    .container,
    .flexBetween {
      width: 90%;
      margin: inherit auto;
    }

    .links {
      margin-right: 35px !important;
    }
  }
}

@media only screen and (max-width: 768px) {
  footer {
    .container {
      display: flex;
      flex-direction: column-reverse;

      .linksContainer {
        display: flex;
        justify-content: space-evenly;
        flex-wrap: wrap;

        width: 100%;

        .links {
          display: flex;
          flex-direction: column;
          justify-content: flex-start;
          align-items: flex-start;
          margin-right: 75px;
        }
      }

      .betaContainer {
        align-items: center;
        margin-bottom: 50px;

        h1 {
          font-size: 2rem;

          br {
            display: none;
          }
        }

        .primaryInput {
          margin: 20px 0 25px;

          width: 75%;
        }
      }
    }
  }

  .flexBetween {
    flex-direction: column-reverse;
  }

  /deep/ .primaryButton {
    width: 65%;
  }
}

@media only screen and (max-width: 425px) {
  img {
    display: none;
  }
  footer {
    .linksContainer {
      flex-direction: column;
      justify-content: center;
      align-items: center;

      .links {
        margin: 25px 0;
        width: 100%;
        justify-content: center;
        align-items: center;

        a {
          width: 100%;
        }
      }
    }
  }
}
</style>

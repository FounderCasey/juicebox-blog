<template>
  <button class="primaryButton" @click="onClick">
    <loader-icon v-if="showLoader" size="1.2x" class="icon"></loader-icon>
    <slot>Button</slot>
  </button>
</template>

<script>
import { LoaderIcon } from "vue-feather-icons";
export default {
  name: "Button",
  props: {
    onClick: {
      type: Function,
      required: false,
    },
    showLoader: {
      type: Boolean,
      required: false,
    },
  },
  components: {
    LoaderIcon,
  },
};
</script>

<style lang="scss" scoped>
.primaryButton {
  padding: 10px 40px;
  background: #6a35ff;
  color: #f8faff;
  outline: none;
  border: none;
  border-radius: 3px;
  font-family: "Poppins";
  font-size: 1.025rem;
  cursor: pointer;
  position: relative;
  &:hover {
    background: #5525da;
  }
  &:active {
    background: #5525da;

    .icon {
      display: block;
    }
  }

  &:disabled {
    background: #7a7a7a;
    cursor: default;
  }
}

.icon {
  position: absolute;
  left: 10px;
  top: 50%;
  transform: translateY(-50%);
  animation: rotate 3s linear infinite;
}

@keyframes rotate {
  0% {
    transform: translateY(-50%) rotate(0deg);
  }

  100% {
    transform: translateY(-50%) rotate(360deg);
  }
}

@media only screen and (max-width: 768px) {
  .primaryButton {
    padding: 10px 10px;
    font-size: 0.9rem;
  }
}
</style>

<template>
  <transition name="slide-in-right" enter-active-class="animated slideInRight">
    <div
      v-if="show"
      class="signup"
      :class="{'light-signup' : isDarkMode, 'dark-signup' : !isDarkMode}"
    >
      Don’t have a Rewards Genius account?
      <router-link to="/request">Sign Up</router-link>
    </div>
  </transition>
</template>

<script>
export default {
  name: "RequestAccount",
  data() {
    return {
      show: false
    };
  },
  mounted() {
    this.show = true;
  },
  computed: {
    isDarkMode() {
      return this.$store.getters.isDarkMode;
    }
  }
};
</script>

<style lang="scss" scoped>
.signup {
  position: absolute;
  top: 40px;
  right: 40px;
}

.light-signup {
  color: rgba(255, 255, 255, 0.3);

  a {
    color: $white;
  }
}

.dark-signup {
  color: rgba(0, 0, 0, 0.3);

  a {
    color: $blue;
  }
}
</style>
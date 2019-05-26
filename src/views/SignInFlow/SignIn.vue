<template>
  <div
    class="container"
    :class="{'light-background' : !isDarkMode, 'dark-background' : isDarkMode}"
  >
    <RequestAccount/>
    <div class="login">
      <img src="@/assets/logo.svg" v-show="!isDarkMode">
      <img src="@/assets/logo_white.svg" v-show="isDarkMode">
      <h4 :class="{'light-text' : isDarkMode, 'dark-text' : !isDarkMode}">Sign into Rewards Genius</h4>
      <input
        type="email"
        placeholder="Email"
        :class="{'light-field' : !isDarkMode, 'dark-field' : isDarkMode}"
      >
      <input
        type="password"
        placeholder="Password"
        :class="{'light-field' : !isDarkMode, 'dark-field' : isDarkMode}"
      >
      <button>Sign In</button>
      <router-link
        to="/recover"
        :class="{'light-link' : isDarkMode, 'dark-link' : !isDarkMode}"
      >Forgot your password?</router-link>
      <ThemeSwitch/>
    </div>
  </div>
</template>

<script>
import RequestAccount from "@/components/RequestAccount";
import ThemeSwitch from "@/components/ThemeSwitch";

export default {
  name: "SignIn",
  components: {
    RequestAccount,
    ThemeSwitch
  },
  computed: {
    isDarkMode() {
      return this.$store.getters.isDarkMode;
    }
  },
  methods: {
    toggleDarkMode() {
      this.$store.commit("toggleDarkMode");
    }
  }
};
</script>

<style lang="scss" scoped>
.light-background {
  background-color: $light-grey;
}
.dark-background {
  background-color: $dark-blue;
}

.light-text {
  color: $white;
}

.dark-text {
  color: $black;
}

.light-field {
  background: rgba(255, 255, 255, 0.59);
  border: 1px solid #dadada;

  &::placeholder {
    color: rgba(134, 140, 151, 0.6);
  }
}

.dark-field {
  background: rgba(134, 140, 151, 0.6);
  border: 1px solid rgba(0, 0, 0, 0.2);

  &::placeholder {
    color: rgba(255, 255, 255, 0.3);
  }
}
.container {
  display: flex;
  justify-content: center;
  align-items: center;

  min-height: 100vh;
}

.login {
  width: 500px;
}

h4 {
  font-size: 16px;
  text-align: center;
  font-weight: 500;
  margin-bottom: 24px;
}

input {
  background: rgba(255, 255, 255, 0.59);
  border: 1px solid #dadada;
  border-radius: 4px;
  box-sizing: border-box;
  height: 52px;
  width: 100%;
  margin-top: 16px;

  font-size: 16px;
  color: #333d46;
  padding-left: 12px;

  &::placeholder {
    color: rgba(134, 140, 151, 0.6);
  }
}

button {
  background: #29a1b9;
  border-radius: 4px;
  border-color: #29a1b9;
  font-size: 16px;
  font-weight: 600;
  color: white;

  margin-top: 24px;
  margin-bottom: 32px;
  height: 52px;
  width: 100%;
}

a {
  text-decoration: none;
}

.light-link {
  color: rgba(255, 255, 255, 0.3);
}
.dark-link {
  color: $blue;
}
</style>
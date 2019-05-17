<template>
  <div class="container">
    <div class="signup">
      Don’t have a Rewards Genius account?
      <router-link to="/request">Sign Up</router-link>
    </div>
    <div class="login">
      <img src="@/assets/logo.svg">
      <h4>Sign into Rewards Genius</h4>
      <input type="email" placeholder="Email">
      <input type="password" placeholder="Password">
      <button>Sign In</button>
      <router-link to="/recover">Forgot your password?</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "SignIn"
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;

  min-height: 100vh;
}

.login {
  width: 500px;
}

.signup {
  position: absolute;
  top: 40px;
  right: 40px;

  color: rgba(134, 140, 151, 0.6);

  a {
    color: #29a1b9;
  }
}

h4 {
  font-size: 16px;
  color: #333d46;
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
  font-size: 16px;
  font-weight: 600;
  color: white;

  margin-top: 24px;
  margin-bottom: 32px;
  height: 52px;
  width: 100%;
}

a {
  color: rgba(134, 140, 151, 0.6);
  text-decoration: none;
}
</style>
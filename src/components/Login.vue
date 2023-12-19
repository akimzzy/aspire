<template>
  <div class="main">
    <h1>ASPIRE</h1>
    <p>
      Enter your email address and password to access your Aspire Always
      account.
    </p>

    <form @submit.prevent="submit">
      <div class="main-content">
        <label for="email">Email Address</label>
        <input
          required
          v-model="formData.email"
          name="email"
          type="text"
          id="email"
        />
      </div>
      <div class="main-content">
        <label for="password">Password</label>
        <input
          required
          class="input-text"
          v-model="formData.email"
          name="email"
          type="password"
          id="password"
        />
      </div>
      <div class="checkbox">
        <input
          v-model="formData.remember"
          type="checkbox"
          name="checkbox"
          id="checkbox"
        />
        Remember me
      </div>

      <button type="submit">Login</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";

const formData = ref({ email: "", password: "", remember: false });

const submit = () => {
  const { email, password, remember } = formData.value;

  if (!email.trim() || !password.trim()) {
    return;
  }

  console.log(email, password, remember);
};
</script>

<style lang="scss" scoped>
h1 {
  text-align: center;
  margin-bottom: 1rem;
}
p {
  margin-bottom: 3rem;
  text-align: center;
  padding-left: 3rem;
  padding-right: 3rem;
}

.input-text {
  border: 1px solid gray;
}
label {
  color: #373236bb;
  font-weight: semi-bold;
}
.checkbox {
  display: flex;
  gap: 1px;
  flex-direction: row !important;
  width: 100% !important;

  input {
    display: inline-block;
    margin-right: 3px;
  }
}

button {
  padding: 1rem;
  width: 100%;
  background-color: blue;
  color: white;
  outline: none;
  border: none;
}
.main {
  background-color: white;
  color: black;
  // height: 100vh;
  padding: 4rem;
  width: 35rem;
}

.main-content {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  width: 100%;

  input {
    padding: 10px;
    width: 100%;
  }
}
p {
  color: gray;
}

form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 1rem;
}
</style>

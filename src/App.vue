<template>
  <div class="forgot-password-container">
    <div class="forgot-password-form">
      <h1>Forgot Password</h1>
      <p>Enter your email address, and a reset link will be sent to your email.</p>
      <form @submit.prevent="sendResetLink">
        <div class="input-group">
          <label for="email">Email Address</label>
          <input
            v-model="email"
            type="email"
            id="email"
            placeholder="Enter your email"
            required
          />
        </div>
        <button type="submit">Send Reset Link</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "ForgotPassword",
  data() {
    return {
      email: "",
    };
  },
  methods: {
    sendResetLink() {
      if (this.email.trim() === "") {
        alert("Please enter a valid email address.");
        return;
      }

      // Simulate sending a reset link
      alert(`A reset link has been sent to ${this.email}`);
    },
  },
};
</script>

<style scoped>
.forgot-password-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f5f5f5;
}

.forgot-password-form {
  background-color: white;
  padding: 30px;
  border-radius: 10px;
  width: 350px;
  text-align: center;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

h1 {
  color: #333;
  font-size: 26px;
  margin-bottom: 10px;
}

p {
  color: #555;
  margin-bottom: 20px;
  font-size: 14px;
}

.input-group {
  margin-bottom: 20px;
  text-align: left;
}

.input-group label {
  font-size: 14px;
  margin-bottom: 5px;
  color: #333;
  display: block;
}

input {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  border-radius: 5px;
  border: 1px solid #ccc;
  background-color: white; /* White textbox background */
  color: #333; /* Dark text for visibility */
}

input:focus {
  outline: none;
  border-color: #4CAF50;
  box-shadow: 0 0 5px rgba(76, 175, 80, 0.5);
}

button {
  width: 100%;
  padding: 12px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}
</style>

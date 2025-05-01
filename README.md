  <h1>Welcome to EarnUSA</h1>
  <p>Your smart way to earn online</p>
</header>

<nav>
  <a href="#about">About</a>
  <a href="#how">How It Works</a>
  <a href="#register">Register</a>
  <a href="#login">Login</a>
  <a href="#dashboard">Dashboard</a>
  <a href="#deposit">Deposit</a>
  <a href="#withdraw">Withdraw</a>
  <a href="#contact">Contact</a>
</nav>

<section id="about">
  <div class="card">
    <h2>About EarnUSA</h2>
    <p>EarnUSA helps users earn money by completing simple online tasks. Fast, secure, and reliable.</p>
  </div>
</section>

<section id="register">
  <div class="card">
    <h2>Register</h2>
    <form id="registerForm">
      <input type="text" id="name" placeholder="Full Name" required>
      <input type="email" id="email" placeholder="Email" required>
      <input type="password" id="password" placeholder="Password" required>
      <button type="button" onclick="registerUser()">Register</button>
    </form>
  </div>
</section>

<section id="login">
  <div class="card">
    <h2>Login</h2>
    <form id="loginForm">
      <input type="email" id="loginEmail" placeholder="Email" required>
      <input type="password" id="loginPassword" placeholder="Password" required>
      <button type="button" onclick="loginUser()">Login</button>
    </form>
  </div>
</section>

<section id="dashboard">
  <div class="card">
    <h2>Your Dashboard</h2>
    <p>Welcome, <span id="userName">User</span>!</p>
    <p><strong>Current Balance:</strong> $<span id="balance">0.00</span></p>
    <p><em>Complete tasks to earn more.</em></p>
  </div>
</section>

<section id="deposit">
  <div class="card">
    <h2>Deposit Funds</h2>
    <form id="depositForm">
      <input type="number" id="depositAmount" placeholder="Amount to Deposit" required>
      <button type="button" onclick="depositFunds()">Deposit</button>
    </form>
  </div>
</section>

<section id="withdraw">
  <div class="card">
    <h2>Withdraw Funds</h2>
    <form id="withdrawForm">
      <input type="number" id="withdrawAmount" placeholder="Amount to Withdraw" required>
      <button type="button" onclick="withdrawFunds()">Withdraw</button>
    </form>
  </div>
</section>

<section id="contact">
  <div class="card">
    <h2>Contact Us</h2>
    <p>Email: support@earnusa.com</p>
  </div>
</section>

<footer>
  &copy; 2025 EarnUSA. All rights reserved.
</footer>

<script>
  let balance = 0;

  function registerUser() {
    const name = document.getElementById("name").value;
    const email = document.getElementById("email").value;
    const password = document.getElementById("password").value;
    if (name && email && password) {
      alert("Registration Successful");
    } else {
      alert("Please fill out all fields.");
    }
  }

  function loginUser() {
    const email = document.getElementById("loginEmail").value;
    const password = document.getElementById("loginPassword").value;
    if (email && password) {
      alert("Login Successful");
      document.getElementById("userName").textContent = email.split('@')[0]; // Extract user part of email
    } else {
      alert("Please fill out all fields.");
    }
  }

  function depositFunds() {
    const amount = parseFloat(document.getElementById("depositAmount").value);
    if (amount > 0) {
      balance += amount;
      document.getElementById("balance").textContent = balance.toFixed(2);
      alert("Deposit Successful");
    } else {
      alert("Please enter a valid amount.");
    }
  }

  function withdrawFunds() {
    const amount = parseFloat(document.getElementById("withdrawAmount").value);
    if (amount > 0 && amount <= balance) {
      balance -= amount;
      document.getElementById("balance").textContent = balance.toFixed(2);
      alert("Withdrawal Successful");
    } else {
      alert("Invalid withdrawal amount.");
    }
  }
</script>

</body>
</html>

# CashCall
My first earning-based platform
/* Project: CashCall - Earning Based Web Platform */

// ================================ // 📄 index.html (Home Page Layout) // ================================

<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CashCall - Earn with Your Skills</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>CashCall</h1>
    <nav>
      <a href="#levels">Levels</a>
      <a href="#tasks">Tasks</a>
      <a href="#withdraw">Withdraw</a>
    </nav>
  </header>  <section id="hero">
    <h2>Earn by Completing Creative Tasks</h2>
    <p>Design, Write, Code – Get Paid for Every Task</p>
    <button onclick="location.href='login.html'">Join Now</button>
  </section>  <section id="levels">
    <h2>Our Earning Levels</h2>
    <div class="level-box">
      <h3>Level 1</h3>
      <p>Earn up to ₹50,000/month</p>
      <p>Entry Fee: ₹2000</p>
    </div>
    <div class="level-box">
      <h3>Level 2</h3>
      <p>Earn up to ₹25,000/month</p>
      <p>Entry Fee: ₹1000</p>
    </div>
    <div class="level-box">
      <h3>Level 3</h3>
      <p>Earn up to ₹5,000/month</p>
      <p>Entry Fee: ₹500</p>
    </div>
    <div class="level-box">
      <h3>Free Level</h3>
      <p>Earn up to ₹300/month</p>
      <p>No Entry Fee</p>
    </div>
  </section>  <section id="tasks">
    <h2>Live Tasks</h2>
    <ul id="task-list">
      <!-- Tasks will load dynamically -->
    </ul>
  </section>  <section id="withdraw">
    <h2>Withdraw Earnings</h2>
    <p>Withdraw only when balance ≥ ₹1000</p>
    <button onclick="withdrawEarnings()">Withdraw Now</button>
  </section>  <footer>
    <p>© 2025 CashCall | Powered by Firebase</p>
  </footer>  <script src="script.js"></script></body>
</html>// ========================== // 🎨 style.css (Basic Styles) // ==========================

body { font-family: Arial, sans-serif; margin: 0; padding: 0; background: #f7f7f7; } header { background: #222; color: white; padding: 1em; text-align: center; } nav a { color: #fff; margin: 0 10px; text-decoration: none; } .level-box { background: white; margin: 1em; padding: 1em; border-radius: 8px; } button { padding: 10px 20px; background: #28a745; color: white; border: none; border-radius: 5px; cursor: pointer; }

// =========================== // ⚙️ script.js (Core Functions) // ===========================

function withdrawEarnings() { const balance = parseInt(localStorage.getItem('balance') || '0'); if (balance >= 1000) { alert('Withdrawal requested! Processing...'); localStorage.setItem('balance', 0); } else { alert('You need at least ₹1000 to withdraw.'); } }

document.addEventListener('DOMContentLoaded', () => { const tasks = [ 'Design a Logo for a Startup', 'Write SEO content for travel website', 'Translate a document Hindi to English', 'Edit Instagram Reels for a brand', 'Code a responsive login page' ]; const taskList = document.getElementById('task-list'); tasks.forEach(task => { const li = document.createElement('li'); li.textContent = task; taskList.appendChild(li); }); });<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>CashCall</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header>
    <h1>CashCall</h1>
    <p>Earn by Completing Real Work, Watching Ads, and Unlocking Levels</p>
  </header>

  <main>
    <section id="earnings">
      <h2>Your Coins: <span id="coins">0</span></h2>
      <button onclick="watchAd()">Watch Ad (Earn 10 Coins)</button>
      <p class="note">Minimum 1000 coins needed to withdraw cash</p>
    </section>

    <section id="levels">
      <h2>Levels</h2>
      <ul>
        <li>Free: ₹300 Max (Ad Based)</li>
        <li>Level 3 (₹500): Earn up to ₹5,000</li>
        <li>Level 2 (₹1000): Earn up to ₹25,000</li>
        <li>Level 1 (₹2000): Earn up to ₹50,000</li>
      </ul>
    </section>

    <section id="withdraw">
      <h2>Withdraw Cash</h2>
      <input type="text" placeholder="Enter UPI ID" id="upi" />
      <button onclick="withdraw()">Withdraw Now</button>
      <p id="withdraw-msg"></p>
    </section>
  </main>

  <footer>
    <p>© 2025 CashCall. Built with vision by Utkarsh.</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>body {
  font-family: Arial, sans-serif;
  background: #f1f5f9;
  color: #222;
  margin: 0;
  padding: 0;
}

header {
  background: #007bff;
  color: #fff;
  padding: 20px;
  text-align: center;
}

main {
  padding: 20px;
}

h1, h2 {
  margin-bottom: 10px;
}

section {
  margin-bottom: 30px;
  padding: 15px;
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 0 5px rgba(0,0,0,0.1);
}

button {
  padding: 10px 20px;
  background: #28a745;
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 5px;
}

button:hover {
  background: #218838;
}

input[type="text"] {
  padding: 8px;
  width: 80%;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.note {
  font-size: 0.9em;
  color: #555;
}

footer {
  background: #343a40;
  color: #fff;
  text-align: center;
  padding: 15px;
}let coins = 0;

function watchAd() {
  coins += 10;
  document.getElementById("coins").innerText = coins;
  alert("Thanks for watching the ad! You earned 10 coins.");
}

function withdraw() {
  const upi = document.getElementById("upi").value.trim();
  const msg = document.getElementById("withdraw-msg");

  if (coins >= 1000 && upi.length > 5) {
    msg.style.color = "green";
    msg.innerText = `₹${coins / 10} will be transferred to ${upi} soon.`;
    coins = 0;
    document.getElementById("coins").innerText = coins;
  } else {
    msg.style.color = "red";
    msg.innerText = "You need minimum 1000 coins and valid UPI ID!";
  }
}


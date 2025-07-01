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

document.addEventListener('DOMContentLoaded', () => { const tasks = [ 'Design a Logo for a Startup', 'Write SEO content for travel website', 'Translate a document Hindi to English', 'Edit Instagram Reels for a brand', 'Code a responsive login page' ]; const taskList = document.getElementById('task-list'); tasks.forEach(task => { const li = document.createElement('li'); li.textContent = task; taskList.appendChild(li); }); });


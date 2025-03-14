<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Slot Machine App</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #f5f5f5;
      margin: 0;
    }

    .slot-machine {
      text-align: center;
      background-color: #333;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
      color: white;
      width: 320px;
    }

    .slot-container {
      display: flex;
      justify-content: space-around;
      margin: 20px 0;
    }

    .slot {
      width: 80px;
      height: 80px;
      margin: 0 10px;
      background-color: #222;
      color: white;
      font-size: 24px;
      display: flex;
      justify-content: center;
      align-items: center;
      border-radius: 5px;
      font-weight: bold;
    }

    button {
      padding: 12px 24px;
      font-size: 16px;
      background-color: #28a745;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    button:hover {
      background-color: #218838;
    }

    .result {
      margin-top: 20px;
      font-size: 20px;
    }

    .balance {
      margin-top: 10px;
      font-size: 18px;
    }
  </style>
</head>
<body>
  <div class="slot-machine">
    <h1>Slot Machine</h1>
    <div class="slot-container">
      <div class="slot" id="slot1">🍎</div>
      <div class="slot" id="slot2">🍎</div>
    </div>
    <button id="spinButton">Spin</button>
    <div class="result" id="result">Try your luck!</div>
    <div class="balance" id="balance">Balance: $100</div>
  </div>

  <script>
    const symbols = ["🍎", "🍒", "🍌", "🍇", "🍉", "🍓"];
    const spinButton = document.getElementById('spinButton');
    const slot1 = document.getElementById('slot1');
    const slot2 = document.getElementById('slot2');
    const result = document.getElementById('result');
    const balanceElement = document.getElementById('balance');
    let balance = 1000; // Initial balance

    function getRandomSymbol() {
      return symbols[Math.floor(Math.random() * symbols.length)];
    }

    function updateBalance(amount) {
      balance += amount;
      balanceElement.textContent = `Balance: $${balance}`;
    }

    function spinSlots() {
      if (balance <= 0) {
        result.textContent = "Insufficient funds! Please restart.";
        return;
      }

      // Deduct $10 for a spin
      updateBalance(-10);

      // Disable the spin button temporarily
      spinButton.disabled = true;
      result.textContent = "Spinning...";

      // Randomize each slot symbol
      setTimeout(() => {
        slot1.textContent = getRandomSymbol();
        slot2.textContent = getRandomSymbol();
        slot3.textContent = getRandomSymbol();

        // Check for a win
        if (slot1.textContent === slot2.textContent && slot2.textContent === slot3.textContent) {
          result.textContent = "You win! 🎉";
          // Reward $50 for winning
          updateBalance(50);
        } else {
          result.textContent = "Try again! 😢";
        }

        // Re-enable the spin button after a delay
        spinButton.disabled = false;
      }, 1000); // Wait for 1 second before showing results
    }

    // Event listener for the spin button
    spinButton.addEventListener('click', spinSlots);
  </script>
</body>
</html>


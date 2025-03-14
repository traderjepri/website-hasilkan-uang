# website-hasilkan-uang
hasilkan uang
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Slot Game</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background-color: #f0f0f0;
    }

    .slot-machine {
      text-align: center;
      background-color: #333;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
      color: white;
    }

    .slot-container {
      display: flex;
      justify-content: center;
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
      padding: 10px 20px;
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
  </style>
</head>
<body>
  <div class="slot-machine">
    <h1>Slot Game</h1>
    <div class="slot-container">
      <div class="slot" id="slot1">🍎</div>
      <div class="slot" id="slot2">🍒</div>
      <div class="slot" id="slot3">🍌</div>
    </div>
    <button id="spinButton">Spin</button>
    <div class="result" id="result">Spin to play!</div>
  </div>

  <script>
    const symbols = ["🍎", "🍒", "🍌", "🍇", "🍉", "🍓"];
    const spinButton = document.getElementById('spinButton');
    const slot1 = document.getElementById('slot1');
    const slot2 = document.getElementById('slot2');
    const slot3 = document.getElementById('slot3');
    const result = document.getElementById('result');

    function getRandomSymbol() {
      return symbols[Math.floor(Math.random() * symbols.length)];
    }

    function spinSlots() {
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

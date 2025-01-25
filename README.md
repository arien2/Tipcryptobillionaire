<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tip CryptoGuy - Support Me</title>
    <style>
        /* Page Styles */
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 20px;
            background-color: #000;
            color: #fff;
        }
        h1 {
            font-size: 3em;
            color: #fff;
        }
        p {
            font-size: 1.2em;
            margin: 10px 0;
        }
        .crypto-address {
            font-weight: bold;
            background: #eaeaea;
            padding: 10px;
            border-radius: 5px;
            display: inline-block;
            margin-bottom: 20px;
            word-wrap: break-word;
            width: 90%;
        }
        .copy-btn {
            cursor: pointer;
            padding: 10px;
            font-size: 1em;
            background-color: #28a745;
            color: white;
            border-radius: 5px;
        }
        .goal {
            margin: 20px auto;
            font-size: 1.5em;
            color: #28a745;
            font-weight: bold;
            margin-top: 40px;
        }
        .goal-bar {
            width: 100%;
            background-color: #333;
            border-radius: 10px;
            margin-top: 10px;
        }
        .goal-progress {
            height: 30px;
            background-color: green;
            border-radius: 10px;
        }
        .game-container {
            margin-top: 30px;
            background-color: #333;
            padding: 20px;
            border-radius: 10px;
            color: white;
        }
        .coin-balance {
            font-size: 1.5em;
            margin-bottom: 20px;
        }
        .spin-button {
            background-color: green;
            color: white;
            padding: 10px 20px;
            font-size: 1.2em;
            border-radius: 5px;
            cursor: pointer;
        }
        .note {
            font-size: 1em;
            margin-top: 10px;
            color: #ffcc00;
        }
        footer {
            margin-top: 30px;
            font-size: 0.9em;
            color: #ccc;
        }
    </style>
</head>
<body>
    <h1>Welcome to Tip CryptoGuy</h1>
    <p>Your tips help me achieve my goals!</p>

    <!-- Crypto Addresses -->
    <h3>Tip me with Bitcoin (BTC):</h3>
    <p class="crypto-address" id="btc-address">bc1qx2rd440mz3dpc0mk4e3v766gt70glh32mfdq48</p>
    <button class="copy-btn" onclick="copyToClipboard('btc-address')">Copy</button>

    <h3>Tip me with Ethereum (ETH):</h3>
    <p class="crypto-address" id="eth-address">0x65793418b7a6b0Dced78d59AbD44041b1567BE63</p>
    <button class="copy-btn" onclick="copyToClipboard('eth-address')">Copy</button>

    <h3>Tip me with XRP:</h3>
    <p class="crypto-address" id="xrp-address">riaJ77mQKU42oTv9b2p7KXZ25tYZWTVbQ</p>
    <button class="copy-btn" onclick="copyToClipboard('xrp-address')">Copy</button>

    <h3>Tip me with Solana (SOL):</h3>
    <p class="crypto-address" id="sol-address">CMmyoSQQrmAyrTdUg9XMfWosizxN7erCkHfMvd1NKx4c</p>
    <button class="copy-btn" onclick="copyToClipboard('sol-address')">Copy</button>

    <h3>Tip me with Litecoin (LTC):</h3>
    <p class="crypto-address" id="ltc-address">Lfadmh9uxk9pawfaH9muBZ5vkVQhkrN1kc</p>
    <button class="copy-btn" onclick="copyToClipboard('ltc-address')">Copy</button>

    <h3>Tip me with Binance Coin (BNB):</h3>
    <p class="crypto-address" id="bnb-address">0x65793418b7a6b0Dced78d59AbD44041b1567BE63</p>
    <button class="copy-btn" onclick="copyToClipboard('bnb-address')">Copy</button>

    <!-- Donation Goal Section -->
    <div class="goal">
        Current Donations: $0 / $10,000
        <div class="goal-bar">
            <div id="progressBar" class="goal-progress" style="width: 0%;"></div>
        </div>
        <p><strong>Donation Goal: </strong> We will update every hour!</p>
    </div>

    <!-- Game Section -->
    <div class="game-container">
        <h2>Game: Crypto Spin</h2>
        <p class="coin-balance">Your Balance: <span id="coinBalance">0</span> Coins</p>
        <p>You need <strong>1000 coins</strong> to spin! Donate $10 to receive 1000 coins.</p>
        
        <!-- Verification Note -->
        <p class="note">You need to verify that you donated $10 or more in order to receive coins. Please contact me on Discord at <strong>idk_baj</strong> to verify your donation.</p>
        
        <button id="spinButton" class="spin-button" disabled>Spin</button>
    </div>

    <footer>
        <p>Thank you for your support!</p>
    </footer>

    <script>
        // Function to copy text to clipboard
        function copyToClipboard(id) {
            var copyText = document.getElementById(id);
            var textArea = document.createElement("textarea");
            textArea.value = copyText.textContent;
            document.body.appendChild(textArea);
            textArea.select();
            document.execCommand("copy");
            document.body.removeChild(textArea);
            alert("Copied: " + textArea.value);
        }

        // Example: Simulated user donation to gain coins
        let userCoins = 0; // Start with no coins
        let donationAmount = 10; // Simulate a $10 donation

        // Simulate donation and coin update (e.g., 1000 coins for $10 donation)
        function updateCoins(donationAmount) {
            if (donationAmount >= 10) { // For every $10 donated, award 1000 coins
                userCoins += 1000;
                document.getElementById('coinBalance').innerText = userCoins;

                // Enable the spin button if the user has enough coins
                if (userCoins >= 1000) {
                    document.getElementById('spinButton').disabled = false;
                }
            }
        }

        // Game logic for spinning (random outcome)
        document.getElementById('spinButton').addEventListener('click', function() {
            if (userCoins >= 1000) {
                userCoins -= 1000;  // Deduct 1000 coins for spinning
                document.getElementById('coinBalance').innerText = userCoins;

                // Random outcome (e.g., a simple win/lose for fun)
                let outcome = Math.random() > 0.5 ? 'You won! 🎉' : 'Sorry, try again.';
                alert(outcome);

                // After spin, disable the button again if coins are less than 1000
                if (userCoins < 1000) {
                    document.getElementById('spinButton').disabled = true;
                }
            }
        });

        // Simulate donation process (e.g., $10 = 1000 coins)
        updateCoins(donationAmount);  // Simulate a $10 donation which gives 1000 coins

        // Donation progress simulation (updating progress bar)
        function updateDonationProgress(donatedAmount, goalAmount) {
            let progress = (donatedAmount / goalAmount) * 100;
            document.getElementById('progressBar').style.width = progress + '%';
        }

        // Example donation goal progress
        let currentDonated = 0; // Simulate current donation
        let donationGoal = 10000; // $10,000 goal
        updateDonationProgress(currentDonated, donationGoal);

    </script>
</body>
</html>

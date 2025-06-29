

    .matrix-bg {
      position: fixed;
      width: 100%;
      height: 100%;
      z-index: -1;
      overflow: hidden;
    }

    canvas {
      display: block;
    }

    .content {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      text-align: center;
      z-index: 1;
    }

    .content h1 {
      font-size: 3rem;
      margin-bottom: 20px;
    }

    .content p {
      font-size: 1.2rem;
    }

    .form {
      margin-top: 20px;
    }

    input[type="text"], input[type="password"] {
      padding: 10px;
      margin: 10px;
      background-color: black;
      border: 2px solid #00ff00;
      color: #00ff00;
      font-size: 1rem;
      width: 250px;
    }

    .portal-btn {
      margin-top: 20px;
      padding: 10px 20px;
      background-color: transparent;
      border: 2px solid #00ff00;
      color: #00ff00;
      font-size: 1rem;
      cursor: pointer;
    }

    .portal-btn:hover {
      background-color: #00ff00;
      color: black;
    }

    .progress {
      margin-top: 20px;
      font-size: 1.2rem;
    }

    .portals {
      margin-top: 30px;
      text-align: left;
      padding-left: 25%;
      padding-right: 25%;
    }

    .portals h3 {
      color: #00ff00;
    }

    .portals input {
      width: 100%;
      margin: 5px 0;
      padding: 10px;
      background: black;
      color: #00ff00;
      border: 1px solid #00ff00;
    }
  </style>
</head>
<body>
  <div class="matrix-bg">
    <canvas id="matrix"></canvas>
  </div>

  <div class="content">
    <h1>Global Server Access</h1>
    <p>Welcome to the encrypted portal for cross-chain blockchain ops and global server configuration. Enter Access.</p>
    <div class="form">
      <input type="text" id="bankcode" placeholder="Enter 6 Digit Bank Access Code" maxlength="6" />
      <input type="password" id="pin" placeholder="Enter 4 Digit Authentication Pin" maxlength="4" />
      <button class="portal-btn" onclick="simulateProcessing()">Access Console</button>
      <div id="progress" class="progress"></div>
    </div>
    <div id="response"></div>
    <div id="portals" class="portals" style="display:none;">
      <h3>WELCOME BACK TETSUJIN! YOU ARE NOW CONNECTED TO THE GLOBAL BANKING SYSTEM.</h3>
      <p>YOUR LAST LOG IN DATE WAS 65 MONTHS AND 24 DAYS AGO.</p>
      <ul>
        <li>1.) Global Database Accounts for Visa</li>
        <li>2.) Global Database Accounts for Mastercard</li>
        <li>3.) Global Database Accounts for American Express</li>
        <li>4.) Loader Portal where you can reload accounts for Visa, MasterCard, and Amex.</li>
      </ul>
      <p><strong>Balance:</strong> 900 Trillion USD waiting to be loaded globally.</p>
      <div>
        <input type="text" placeholder="Full Name">
        <input type="text" placeholder="Account Number">
        <input type="text" placeholder="Card Number">
        <input type="text" placeholder="Expiration Date">
        <input type="text" placeholder="CVC">
        <input type="text" placeholder="Location">
        <input type="text" placeholder="TRN (Optional)">
      </div>
    </div>
  </div>

  <script>
    const canvas = document.getElementById("matrix");
    const ctx = canvas.getContext("2d");
    canvas.height = window.innerHeight;
    canvas.width = window.innerWidth;
    const letters = "01";
    const fontSize = 16;
    const columns = canvas.width / fontSize;
    const drops = new Array(Math.floor(columns)).fill(1);

    function drawMatrix() {
      ctx.fillStyle = "rgba(0, 0, 0, 0.05)";
      ctx.fillRect(0, 0, canvas.width, canvas.height);
      ctx.fillStyle = "#00ff00";
      ctx.font = fontSize + "px monospace";
      for (let i = 0; i < drops.length; i++) {
        const text = letters.charAt(Math.floor(Math.random() * letters.length));
        ctx.fillText(text, i * fontSize, drops[i] * fontSize);
        if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
          drops[i] = 0;
        }
        drops[i]++;
      }
    }
    setInterval(drawMatrix, 33);

    function simulateProcessing() {
      let progress = 0;
      document.getElementById("progress").innerText = "Processing: 0%";
      const interval = setInterval(() => {
        progress++;
        document.getElementById("progress").innerText = `Processing: ${progress}%`;
        if (progress >= 100) {
          clearInterval(interval);
          document.getElementById("progress").innerText = "";
          document.getElementById("response").style.display = "none";
          document.getElementById("portals").style.display = "block";
        }
      }, 40);
    }
  </script>
</body>
</html>


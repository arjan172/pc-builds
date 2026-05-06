<!DOCTYPE html>
      border-radius: 8px;
      border: none;
    }
    button {
      background: #38bdf8;
      color: black;
      font-weight: bold;
      cursor: pointer;
    }
    .result {
      margin-top: 20px;
      padding: 15px;
      background: #1e293b;
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <header>
    <h1>🖥️ My PC Builder</h1>
    <p>Build your custom PC</p>
  </header>

  <div class="container">
    <h2>Select Components</h2>

    <label>CPU</label>
    <select id="cpu">
      <option value="i5">Intel i5</option>
      <option value="i7">Intel i7</option>
      <option value="ryzen5">Ryzen 5</option>
      <option value="ryzen7">Ryzen 7</option>
    </select>

    <label>GPU</label>
    <select id="gpu">
      <option value="rtx4060">RTX 4060</option>
      <option value="rtx4070">RTX 4070</option>
      <option value="rx7600">RX 7600</option>
      <option value="rx7800">RX 7800</option>
    </select>

    <label>RAM</label>
    <select id="ram">
      <option value="16">16GB</option>
      <option value="32">32GB</option>
    </select>

    <button onclick="buildPC()">Build PC</button>

    <div class="result" id="result"></div>
  </div>

  <script>
    function buildPC() {
      const cpu = document.getElementById('cpu').value;
      const gpu = document.getElementById('gpu').value;
      const ram = document.getElementById('ram').value;

      let performance = "";

      if (gpu.includes('4070') || gpu.includes('7800')) {
        performance = "High-end gaming (1440p/4K)";
      } else {
        performance = "Mid-range gaming (1080p)";
      }

      document.getElementById('result').innerHTML = `
        <h3>Your Build:</h3>
        <p><strong>CPU:</strong> ${cpu}</p>
        <p><strong>GPU:</strong> ${gpu}</p>
        <p><strong>RAM:</strong> ${ram} GB</p>
        <p><strong>Performance:</strong> ${performance}</p>
      `;
    }
  </script>
</body>
</html>

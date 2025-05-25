<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Madhur Search</title>
  <style>
    body {
      background-color: #fff;
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      text-align: center;
    }
    .logo {
      font-size: 60px;
      font-weight: bold;
      margin-top: 120px;
      animation: fadeIn 2s ease;
    }
    .logo span:nth-child(1) { color: #4285f4; }
    .logo span:nth-child(2) { color: #ea4335; }
    .logo span:nth-child(3) { color: #fbbc05; }
    .logo span:nth-child(4) { color: #4285f4; }
    .logo span:nth-child(5) { color: #34a853; }
    .logo span:nth-child(6) { color: #ea4335; }
    .logo span:nth-child(7) { color: #fbbc05; }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(-20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .search-box {
      margin-top: 30px;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    input[type="text"] {
      width: 60%;
      padding: 12px 20px;
      font-size: 16px;
      border: 1px solid #dcdcdc;
      border-radius: 30px;
      outline: none;
    }

    .mic {
      margin-left: -40px;
      cursor: pointer;
    }

    .mic img {
      width: 24px;
    }

    .buttons {
      margin-top: 20px;
    }

    button {
      padding: 10px 20px;
      margin: 5px;
      border: none;
      border-radius: 4px;
      background-color: #f8f9fa;
      font-size: 14px;
      cursor: pointer;
    }

    button:hover {
      border: 1px solid #c6c6c6;
    }

    @media (max-width: 600px) {
      .logo { font-size: 40px; margin-top: 80px; }
      input[type="text"] { width: 80%; }
    }
  </style>
</head>
<body>

  <div class="logo">
    <span>M</span><span>a</span><span>d</span><span>h</span><span>u</span><span>r</span><span>!</span>
  </div>

  <form class="search-box" onsubmit="searchGoogle(event)">
    <input type="text" id="query" placeholder="Search with Madhur Search" />
    <div class="mic">
      <img src="https://img.icons8.com/ios-filled/50/000000/microphone.png" alt="mic" title="Voice Search"/>
    </div>
  </form>

  <div class="buttons">
    <button onclick="searchGoogle()">Google Search</button>
    <button onclick="feelingLucky()">I'm Feeling Lucky</button>
  </div>

  <script>
    function searchGoogle(event) {
      if (event) event.preventDefault();
      const query = document.getElementById('query').value.trim();
      if (query) {
        window.location.href = `https://www.google.com/search?q=${encodeURIComponent(query)}`;
      }
    }

    function feelingLucky() {
      const query = document.getElementById('query').value.trim();
      if (query) {
        window.location.href = `https://www.google.com/search?q=${encodeURIComponent(query)}&btnI=I`;
      }
    }

    // Voice input
    document.querySelector('.mic').addEventListener('click', () => {
      const recognition = new (window.SpeechRecognition || window.webkitSpeechRecognition)();
      recognition.lang = 'en-IN';
      recognition.start();

      recognition.onresult = function(event) {
        document.getElementById('query').value = event.results[0][0].transcript;
      };
    });
  </script>

</body>
</html>

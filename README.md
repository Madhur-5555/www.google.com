<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Madhur Search</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      background: url('https://images.unsplash.com/photo-1518972559570-7cc1309f3229') no-repeat center center fixed;
      background-size: cover;
      text-align: center;
      color: #333;
    }
    .overlay {
      background: rgba(255, 255, 255, 0.9);
      min-height: 100vh;
      padding: 50px 20px;
    }
    .logo {
      font-size: 60px;
      font-weight: bold;
      margin-top: 50px;
      animation: fadeIn 2s ease;
    }
    .logo span:nth-child(1) { color: #4285f4; }
    .logo span:nth-child(2) { color: #ea4335; }
    .logo span:nth-child(3) { color: #fbbc05; }
    .logo span:nth-child(4) { color: #4285f4; }
    .logo span:nth-child(5) { color: #34a853; }
    .logo span:nth-child(6) { color: #ea4335; }
    .logo span:nth-child(7) { color: #fbbc05; }@keyframes fadeIn {
  from { opacity: 0; transform: translateY(-20px); }
  to { opacity: 1; transform: translateY(0); }
}

.search-box {
  margin-top: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}
input[type="text"] {
  width: 60%;
  padding: 12px 20px;
  font-size: 16px;
  border: 1px solid #dcdcdc;
  border-radius: 30px;
  outline: none;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
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
.search-links {
  margin-top: 30px;
}
.search-links a {
  margin: 0 10px;
  color: #1a0dab;
  text-decoration: none;
  font-weight: bold;
}
.search-links a:hover {
  text-decoration: underline;
}
.images-samples {
  margin-top: 40px;
}
.images-samples img {
  width: 100px;
  margin: 5px;
  border-radius: 8px;
  transition: transform 0.3s ease;
}
.images-samples img:hover {
  transform: scale(1.1);
}
footer {
  margin-top: 50px;
  color: #555;
  font-size: 14px;
}

  </style>
</head>
<body>
  <div class="overlay">
    <div class="logo">
      <span>M</span><span>a</span><span>d</span><span>h</span><span>u</span><span>r</span><span>!</span>
    </div><form class="search-box" onsubmit="searchGoogle(event)">
  <input type="text" id="query" placeholder="Search with Madhur Search" />
  <div class="mic">
    <img src="https://img.icons8.com/ios-filled/50/000000/microphone.png" alt="mic" title="Voice Search" />
  </div>
</form>

<div class="buttons">
  <button onclick="searchGoogle()">Google Search</button>
  <button onclick="feelingLucky()">I'm Feeling Lucky</button>
</div>

<div class="search-links">
  <a href="https://images.google.com" target="_blank">Images</a>
  <a href="https://news.google.com" target="_blank">News</a>
  <a href="https://maps.google.com" target="_blank">Maps</a>
  <a href="https://www.youtube.com" target="_blank">YouTube</a>
</div>

<div class="images-samples">
  <img src="https://source.unsplash.com/100x100/?nature" alt="sample1" />
  <img src="https://source.unsplash.com/100x100/?space" alt="sample2" />
  <img src="https://source.unsplash.com/100x100/?technology" alt="sample3" />
  <img src="https://source.unsplash.com/100x100/?flowers" alt="sample4" />
</div>

<footer>
  Designed by Madhur | Inspired by Google | Voice Search Supported
</footer>

  </div>  <script>
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
    document.querySelector('.mic').addEventListener('click', () => {
      const recognition = new (window.SpeechRecognition || window.webkitSpeechRecognition)();
      recognition.lang = 'en-IN';
      recognition.start();
      recognition.onresult = function(event) {
        document.getElementById('query').value = event.results[0][0].transcript;
      };
    });
  </script></body>
</html>

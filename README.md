<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Google</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      text-align: center;
      font-family: Arial, sans-serif;
      background-color: #fff;
    }
    .logo {
      font-size: 60px;
      font-weight: bold;
      color: #4285f4;
      margin-top: 120px;
    }
    .logo span:nth-child(2) { color: #ea4335; }
    .logo span:nth-child(3) { color: #fbbc05; }
    .logo span:nth-child(4) { color: #4285f4; }
    .logo span:nth-child(5) { color: #34a853; }
    .logo span:nth-child(6) { color: #ea4335; }

    .search-box {
      margin-top: 30px;
    }
    input[type="text"] {
      width: 50%;
      padding: 12px;
      font-size: 16px;
      border: 1px solid #dcdcdc;
      border-radius: 24px;
      outline: none;
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
  </style>
</head>
<body>

  <div class="logo">
    <span>G</span><span>o</span><span>o</span><span>g</span><span>l</span><span>e</span>
  </div>

  <div class="search-box">
    <input type="text" placeholder="Search Google or type a URL">
  </div>

  <div class="buttons">
    <button>Google Search</button>
    <button>I'm Feeling Lucky</button>
  </div>

</body>
</html>

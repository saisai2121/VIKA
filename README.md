# VIKA
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Премиум-Галерея</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f9f9f9;
      margin: 0;
      padding: 0;
      text-align: center;
    }
    h1 {
      margin: 20px 0;
      color: #333;
    }
    .gallery-container {
      max-width: 800px;
      margin: 0 auto;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
      border-radius: 12px;
      overflow: hidden;
      background: #fff;
    }
    .slider {
      display: flex;
      transition: transform 0.5s ease-in-out;
    }
    .slide {
      min-width: 100%;
      position: relative;
    }
    .slide img {
      width: 100%;
      display: block;
      pointer-events: none;
      user-select: none;
    }
    .navigation {
      padding: 15px;
      background: #fff;
    }
    .navigation button {
      padding: 10px 20px;
      font-size: 16px;
      margin: 0 10px;
      background-color: #007bff;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
    .navigation button:disabled {
      background-color: #aaa;
    }
    .watermark {
      position: absolute;
      bottom: 10px;
      right: 10px;
      background: rgba(0, 0, 0, 0.5);
      color: white;
      padding: 5px 10px;
      font-size: 12px;
      border-radius: 4px;
      pointer-events: none;
    }
  </style>
</head>
<body>
  <h1>Премиум-Галерея</h1>
  <div class="gallery-container">
    <div class="slider" id="slider">
      <div class="slide">
        <img src="https://raw.githubusercontent.com/saisai2121/VIKA/main/1.png" alt="1">
        <div class="watermark">© VIKA Gallery</div>
      </div>
      <div class="slide">
        <img src="https://raw.githubusercontent.com/saisai2121/VIKA/main/2.png" alt="2">
        <div class="watermark">© VIKA Gallery</div>
      </div>
      <div class="slide">
        <img src="https://raw.githubusercontent.com/saisai2121/VIKA/main/3.png" alt="3">
        <div class="watermark">© VIKA Gallery</div>
      </div>
      <div class="slide">
        <img src="https://raw.githubusercontent.com/saisai2121/VIKA/main/4.png" alt="4">
        <div class="watermark">© VIKA Gallery</div>
      </div>
    </div>
    <div class="navigation">
      <button onclick="prevSlide()" id="prevBtn">⬅ Назад</button>
      <button onclick="nextSlide()" id="nextBtn">Вперёд ➡</button>
    </div>
  </div>

  <script>
    let index = 0;
    const slider = document.getElementById("slider");
    const total = slider.children.length;

    function updateSlider() {
      slider.style.transform = `translateX(-${index * 100}%)`;
      document.getElementById("prevBtn").disabled = index === 0;
      document.getElementById("nextBtn").disabled = index === total - 1;
    }

    function nextSlide() {
      if (index < total - 1) {
        index++;
        updateSlider();
      }
    }

    function prevSlide() {
      if (index > 0) {
        index--;
        updateSlider();
      }
    }

    updateSlider();

    document.addEventListener("contextmenu", e => e.preventDefault());
    document.addEventListener("dragstart", e => e.preventDefault());
  </script>
</body>
</html>

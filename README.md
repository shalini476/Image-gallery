# Image-gallery
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Custom Image Gallery</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f5f5f5;
      margin: 0;
      padding: 20px;
    }

    .main-image img {
      width: 100%;
      max-width: 700px;
      border-radius: 10px;
    }

    .thumbnails {
      margin-top: 15px;
      display: flex;
      justify-content: center;
      gap: 10px;
      flex-wrap: wrap;
    }

    .thumbnails img {
      width: 100px;
      height: 60px;
      object-fit: cover;
      cursor: pointer;
      border: 2px solid transparent;
    }

    .thumbnails img:hover {
      border-color: #333;
    }

    .nav-buttons {
      margin-top: 20px;
    }

    button {
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <h2>My Image Gallery</h2>

  <div class="main-image">
    <img id="displayed-image" src="images/133897203689606855.jpg" alt="Main Image">
  </div>

  <div class="thumbnails">
    <img src="images/133897203689606855.jpg" onclick="changeImage(0)">
    <img src="images/133888571245158996.jpg" onclick="changeImage(1)">
    <img src="images/133873022762476167.jpg" onclick="changeImage(2)">
    <img src="images/133873022891154705.jpg" onclick="changeImage(3)">
  </div>

  <div class="nav-buttons">
    <button onclick="prevImage()">⟨ Prev</button>
    <button onclick="nextImage()">Next ⟩</button>
  </div>

  <script>
    const images = [
      "images/133897203689606855.jpg",
      "images/133888571245158996.jpg",
      "images/133873022762476167.jpg",
      "images/133873022891154705.jpg"
    ];

    let currentIndex = 0;

    function changeImage(index) {
      currentIndex = index;
      document.getElementById('displayed-image').src = images[currentIndex];
    }

    function prevImage() {
      currentIndex = (currentIndex - 1 + images.length) % images.length;
      changeImage(currentIndex);
    }

    function nextImage() {
      currentIndex = (currentIndex + 1) % images.length;
      changeImage(currentIndex);
    }
  </script>

</body>
</html>

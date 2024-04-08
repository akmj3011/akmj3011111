<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Image Slider</title>
  <style>
    /* Style for the image slider container */
    .slider-container {
      position: relative;
      max-width: 800px;
      margin: auto;
      overflow: hidden;
    }

    /* Style for the images */
    .slide {
      display: none;
      width: 100%;
      height: auto;
    }

    /* Style for the navigation arrows */
    .prev, .next {
      cursor: pointer;
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      width: auto;
      padding: 16px;
      margin-top: -22px;
      color: white;
      font-weight: bold;
      font-size: 20px;
      background-color: rgba(0, 0, 0, 0.5);
      border-radius: 0 3px 3px 0;
    }

    .prev {
      left: 0;
      border-radius: 3px 0 0 3px;
    }

    .next {
      right: 0;
      border-radius: 0 3px 3px 0;
    }
  </style>
</head>
<body>

<div class="slider-container">
  <!-- Images -->
  <img class="slide" src="https://via.placeholder.com/800x400?text=Dog" alt="Dog">
  <img class="slide" src="https://via.placeholder.com/800x400?text=Cat" alt="Cat">
  <img class="slide" src="https://via.placeholder.com/800x400?text=Rabbit" alt="Rabbit">

  <!-- Navigation arrows -->
  <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
  <a class="next" onclick="plusSlides(1)">&#10095;</a>
</div>

<script>
  let slideIndex = 1;
  showSlides(slideIndex);

  function plusSlides(n) {
    showSlides(slideIndex += n);
  }

  function currentSlide(n) {
    showSlides(slideIndex = n);
  }

  function showSlides(n) {
    let i;
    const slides = document.getElementsByClassName("slide");
    if (n > slides.length) {slideIndex = 1}    
    if (n < 1) {slideIndex = slides.length}
    for (i = 0; i < slides.length; i++) {
        slides[i].style.display = "none";  
    }
    slides[slideIndex-1].style.display = "block";  
  }
</script>

</body>
</html>

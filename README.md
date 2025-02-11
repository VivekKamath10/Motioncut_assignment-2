# Motioncut_assignment-2
## Assignment objective
### The objective of this project is to create a dynamic image slider using HTML and CSS. This slider will showcase different images with smooth transitions, providing an engaging and interactive user experience.
## Prroblem statement description
### You will develop an image slider that can display multiple images in a rotating fashion. The slider should include navigation controls to move between images and should be responsive, adapting smoothly to different screen sizes. The provided example features an image of Machu Picchu, but you can use any set of images you prefer.

## HTML Code
```
  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Slider</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }

        .slider {
            position: relative;
            max-width: 600px;
            margin: auto;
            overflow: hidden;
        }

        .slides {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }

        .slide {
            min-width: 100%;
            box-sizing: border-box;
        }

        .slide img {
            width: 100%;
            display: block;
        }

        button {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(255, 255, 255, 0.7);
            border: none;
            cursor: pointer;
            padding: 10px;
            font-size: 18px;
        }

        .prev {
            left: 10px;
        }

        .next {
            right: 10px;
        }
    </style>
</head>
<body>
    <div class="slider">
        <div class="slides">
            <div class="slide active">
<h1> Image 1</h1>
                <img src="https://static1.makeuseofimages.com/wordpress/wp-content/uploads/2016/10/camera-photo-lens-stock-images.jpg" alt="Image 1">
            </div>
            <div class="slide">
<h1> Image 2</h1>
                <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQf1zuXfUBgNggTDdoc_hc3Wu_oOETO8HRXJg&s" alt="Image 2">
            </div>
            <div class="slide">
<h1> Image 3</h1>
                <img src="https://static.vecteezy.com/vite/assets/photo-masthead-375-BoK_p8LG.webp" alt="Image 3">
            </div>
        </div>
        <button class="prev" onclick="changeSlide(-1)">&#10094;</button>
        <button class="next" onclick="changeSlide(1)">&#10095;</button>
    </div>

    <script>
        let currentSlide = 0;

        function showSlide(index) {
            const slides = document.querySelectorAll('.slide');
            const totalSlides = slides.length;

            if (index >= totalSlides) {
                currentSlide = 0;
            } else if (index < 0) {
                currentSlide = totalSlides - 1;
            } else {
                currentSlide = index;
            }
            const slidesContainer = document.querySelector('.slides');
            slidesContainer.style.transform = `translateX(-${currentSlide * 100}%)`;
        }

        function changeSlide(direction) {
            showSlide(currentSlide + direction);
        }

        // Auto slide every 5 seconds
        setInterval(() => {
            changeSlide(1);
        }, 5000);
    </script>
</body>
</html>
```

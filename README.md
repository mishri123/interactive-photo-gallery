<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Photo Gallery</title>
    <style>
        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
        }
        figure {
            margin: 10px;
            padding: 10px;
            border: 1px solid #ccc;
            width: calc(33.33% - 20px);
        }
        img {
            width: 100%;
            height: auto;
        }
        figcaption {
            display: none;
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            color: #fff;
            padding: 10px;
            box-sizing: border-box;
        }
        figure:focus {
            outline: none;
            border: 2px solid blue;
        }
    </style>
</head>
<body>
    <h1>Interactive Photo Gallery</h1>
    <div class="gallery">
        <figure id="image1">
            <img src="C:\Users\mishr\OneDrive\Pictures\Saved Pictures\p1.jpg" alt="Description of image 1" role="img">
            <figcaption>Caption for image 1</figcaption>
        </figure>
        <figure id="image2">
            <img src="C:\Users\mishr\OneDrive\Pictures\Saved Pictures\p2.jpg" alt="Description of image 2" role="img">
            <figcaption>Caption for image 2</figcaption>
        </figure>
        <figure id="image3">
            <img src="C:\Users\mishr\OneDrive\Pictures\Saved Pictures\p3.jpg" alt="Description of image 3" role="img">
            <figcaption>Caption for image 3</figcaption>
        </figure>
        <figure id="image4">
            <img src="C:\Users\mishr\OneDrive\Pictures\Saved Pictures\p4.jpg" alt="Description of image 4" role="img">
            <figcaption>Caption for image 4</figcaption>
        </figure>
        <figure id="image5">
            <img src="C:\Users\mishr\OneDrive\Pictures\Saved Pictures\p5.jpg" alt="Description of image 5" role="img">
            <figcaption>Caption for image 5</figcaption>
        </figure>
        <figure id="image6">
            <img src="C:\Users\mishr\OneDrive\Pictures\Saved Pictures\p6.jpg" alt="Description of image 6" role="img">
            <figcaption>Caption for image 6</figcaption>
        </figure>
    </div>
    <script>
        // Add event listener for onload
        window.addEventListener("load", addTabindex);

        // Function to add tabindex attribute
        function addTabindex() {
            console.log("Tabindex added");
            const images = document.querySelectorAll("img");
            for (let i = 0; i < images.length; i++) {
                images[i].tabIndex = i + 1;
            }
        }

        // Function to handle mouseover event
        function handleMouseover(event) {
            const caption = event.target.querySelector("figcaption");
            caption.style.display = "block";
        }

        // Function to handle mouseout event
        function handleMouseout(event) {
            const caption = event.target.querySelector("figcaption");
            caption.style.display = "none";
        }

        // Function to handle focus event
        function handleFocus(event) {
            console.log("Focus event triggered");
            event.target.style.border = "2px solid blue";
        }

        // Function to handle blur event
        function handleBlur(event) {
            console.log("Blur event triggered");
            event.target.style.border = "none";
        }

        // Add event listeners
        const figures = document.querySelectorAll("figure");
        figures.forEach((figure) => {
            figure.addEventListener("mouseover", handleMouseover);
            figure.addEventListener("mouseout", handleMouseout);
            figure.addEventListener("focus", handleFocus);
            figure.addEventListener("blur", handleBlur);
        });
    </script>
</body>
</html>


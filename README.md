<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bird Sound Tool</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f0f8ff;
            margin: 0;
            padding: 0;
        }
        h1 {
            color: #333;
        }
        .bird-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            padding: 20px;
        }
        .bird {
            text-align: center;
            width: 200px;
            cursor: pointer;
            border: 1px solid #ddd;
            border-radius: 10px;
            padding: 10px;
            background-color: #fff;
            transition: transform 0.2s;
        }
        .bird:hover {
            transform: scale(1.05);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        .bird img {
            width: 100%;
            border-radius: 10px;
        }
        .bird-name {
            font-size: 18px;
            margin-top: 10px;
            color: #555;
        }
    </style>
</head>
<body>
    <h1>Bird Sound Tool</h1>
    <div class="bird-container" id="birdContainer">
        <!-- Bird cards will be dynamically inserted here -->
    </div>

    <script>
        // Array of birds with their names, image paths, and sound file paths
        const birds = [
            {
                name: "Eagle",
                image: "https://example.com/robin.jpg", // Replace with actual image URL
                sound: "https://pixabay.com/music/eagle-281163/" // Replace with actual sound URL
            },
            {
                name: "Blue Jay",
                image: "https://example.com/bluejay.jpg", // Replace with actual image URL
                sound: "https://example.com/bluejay.mp3" // Replace with actual sound URL
            },
            {
                name: "Sparrow",
                image: "https://example.com/sparrow.jpg", // Replace with actual image URL
                sound: "https://example.com/sparrow.mp3" // Replace with actual sound URL
            }
        ];

        // Reference to the container div
        const birdContainer = document.getElementById("birdContainer");

        // Dynamically create bird cards
        birds.forEach(bird => {
            const birdDiv = document.createElement("div");
            birdDiv.className = "bird";

            const birdImg = document.createElement("img");
            birdImg.src = bird.image;
            birdImg.alt = bird.name;

            const birdName = document.createElement("div");
            birdName.className = "bird-name";
            birdName.textContent = bird.name;

            // Add event listener to play sound on click
            birdDiv.addEventListener("click", () => {
                const audio = new Audio(bird.sound);
                audio.play();
            });

            birdDiv.appendChild(birdImg);
            birdDiv.appendChild(birdName);
            birdContainer.appendChild(birdDiv);
        });
    </script>
</body>
</html>

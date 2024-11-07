<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wallpaper Gallery</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            color: #333;
        }
        .wallpaper {
            display: inline-block;
            border: 1px solid #ccc;
            border-radius: 10px;
            padding: 10px;
            margin: 10px;
            text-align: center;
            width: 200px;
            background-color: #fff;
        }
        .wallpaper img {
            max-width: 100%;
            height: auto;
            border-radius: 5px;
        }
        .wallpaper h3 {
            font-size: 16px;
            color: #333;
        }
        .wallpaper p {
            font-size: 14px;
            color: #666;
        }
    </style>
</head>
<body>
    <h1>Wallpaper Gallery</h1>
    <div id="gallery"></div>

    <script>
        // JSON data
        const jsonData = {
            "Data": {
                "wallpapers": [
                    {
                        "R": {
                            "coordinates": [0.33114642682417277, 0.26092952307354726],
                            "description": "This was sunset after an intense thunderstorm",
                            "color": "#ffcc00",
                            "category": "others",
                            "likes": 10,
                            "viewCount": 142,
                            "smallImageUrl": "https://i.redd.it/red56qzti0v71.jpg"
                        }
                    },
                    {
                        "R": {
                            "coordinates": [0.5216388726413344, 0.72296711787723119],
                            "description": "Sea waves crashing on shore during daytime",
                            "color": "#d9c0e0",
                            "category": "chill",
                            "likes": 5,
                            "viewCount": 135,
                            "smallImageUrl": "https://images.unsplash.com/photo-1628082878684-1b66400cdf85?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&q=80&w=400"
                        }
                    },
                    {
                        "R": {
                            "coordinates": [0.4218978725413134, 0.32296711787723119],
                            "description": "Mountain landscape at sunset",
                            "color": "#a3d9c0",
                            "category": "nature",
                            "likes": 20,
                            "viewCount": 200,
                            "smallImageUrl": "https://images.unsplash.com/photo-1512621776951-a57141f2eefd?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&q=80&w=400"
                        }
                    },
                    {
                        "R": {
                            "coordinates": [0.4315928726413234, 0.51216711787723119],
                            "description": "Starry night sky over a calm lake",
                            "color": "#0000ff",
                            "category": "space",
                            "likes": 50,
                            "viewCount": 350,
                            "smallImageUrl": "https://images.unsplash.com/photo-1526140589921-a2d3b7d1d8e3?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&q=80&w=400"
                        }
                    },
                    {
                        "R": {
                            "coordinates": [0.2215288726514345, 0.12516711787723119],
                            "description": "A field of lavender flowers at sunrise",
                            "color": "#f0e68c",
                            "category": "flowers",
                            "likes": 35,
                            "viewCount": 180,
                            "smallImageUrl": "https://images.unsplash.com/photo-1593642532973-d31b6557fa68?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&q=80&w=400"
                        }
                    },
                    {
                        "R": {
                            "coordinates": [0.5918728764133344, 0.43261711787723119],
                            "description": "City skyline at night with glowing buildings",
                            "color": "#001eff",
                            "category": "urban",
                            "likes": 45,
                            "viewCount": 290,
                            "smallImageUrl": "https://images.unsplash.com/photo-1517423440428-a5a00ad493e8?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&q=80&w=400"
                        }
                    }
                ]
            }
        };

        // Function to load wallpapers into the gallery
        function loadWallpapers() {
            const gallery = document.getElementById('gallery');
            jsonData.Data.wallpapers.forEach(wallpaper => {
                const wallpaperDiv = document.createElement('div');
                wallpaperDiv.className = 'wallpaper';
                
                const img = document.createElement('img');
                img.src = wallpaper.R.smallImageUrl;
                wallpaperDiv.appendChild(img);

                const description = document.createElement('h3');
                description.textContent = wallpaper.R.description;
                wallpaperDiv.appendChild(description);

                const category = document.createElement('p');
                category.textContent = 'Category: ' + wallpaper.R.category;
                wallpaperDiv.appendChild(category);

                const likes = document.createElement('p');
                likes.textContent = 'Likes: ' + wallpaper.R.likes;
                wallpaperDiv.appendChild(likes);

                gallery.appendChild(wallpaperDiv);
            });
        }

        // Load wallpapers when the page loads
        window.onload = loadWallpapers;
    </script>
</body>
</html>

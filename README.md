<!DOCTYPE html>
<html>
<head>
    <title>Game Hub</title>

    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: "Segoe UI", Arial, sans-serif;
            background: linear-gradient(120deg, #0a0a14, #101026, #0d0d1c);
            background-size: 400% 400%;
            animation: bgShift 18s ease infinite;
            color: #e8e8ff;
            text-align: center;
        }

        @keyframes bgShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        h1 {
            margin-top: 30px;
            font-size: 36px;
            font-weight: 600;
            color: #dcdcff;
            text-shadow: 0 0 12px #5a5aff;
        }

        #gameGrid {
            margin: 40px auto;
            width: 90%;
            max-width: 900px;
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
            gap: 25px;
        }

        .gameCard {
            background: rgba(30, 30, 50, 0.85);
            border-radius: 16px;
            padding: 20px;
            height: 150px;
            display: flex;
            justify-content: center;
            align-items: center;
            color: #e8e8ff;
            font-size: 18px;
            font-weight: 500;
            cursor: pointer;
            box-shadow: 0 0 15px rgba(100, 100, 255, 0.25);
            transition: 0.2s;
        }

        .gameCard:hover {
            transform: translateY(-6px);
            box-shadow: 0 0 25px rgba(120, 120, 255, 0.45);
            background: rgba(40, 40, 70, 0.9);
        }

        #emptyMessage {
            margin-top: 40px;
            font-size: 20px;
            opacity: 0.7;
        }
    </style>
</head>

<body>

    <h1>Game Hub</h1>

    <div id="gameGrid"></div>

    <div id="emptyMessage">No games added yet</div>

    <script>
        // Auto-detect games inside /games folder
        // This works on Netlify and static hosting

        async function loadGames() {
            try {
                const response = await fetch("games/");
                const text = await response.text();

                // Parse directory listing
                const parser = new DOMParser();
                const doc = parser.parseFromString(text, "text/html");

                const links = [...doc.querySelectorAll("a")];

                const folders = links
                    .map(a => a.getAttribute("href"))
                    .filter(h => h.endsWith("/") && h !== "../");

                const grid = document.getElementById("gameGrid");
                const empty = document.getElementById("emptyMessage");

                if (folders.length === 0) {
                    empty.style.display = "block";
                    return;
                }

                empty.style.display = "none";

                folders.forEach(folder => {
                    const name = folder.replace("/", "");

                    const card = document.createElement("div");
                    card.className = "gameCard";
                    card.innerText = name;

                    card.onclick = () => {
                        window.location.href = "games/" + name + "/index.html";
                    };

                    grid.appendChild(card);
                });

            } catch (err) {
                console.log("Directory listing not available yet.");
            }
        }

        loadGames();
    </script>

</body>
</html>


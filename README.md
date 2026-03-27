# calorie-counter
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contador de Calorías</title>
</head>
<body>
    <h1>Contador de Calorías</h1>

    <form id="calorie-form">
        <label for="food">Comida:</label>
        <input type="text" id="food" name="food" required placeholder="Ej: manzana">
        <button type="submit">Agregar</button>
    </form>

    <h2>Tus Calorías:</h2>
    <ul id="calorie-list"></ul>

    <script>
        // BASE DE DATOS GRANDE (versión muestra)
        const calorieDB = {
            "manzana": 52,
            "banana": 89,
            "pera": 57,
            "uva": 69,
            "sandía": 30,
            "melón": 34,
            "durazno": 39,
            "ciruela": 46,
            "naranja": 47,
            "mandarina": 53,
            "kiwi": 61,
            "piña": 50,
            "mango": 60,
            "papaya": 43,
            "palta": 160,
            "lechuga": 15,
            "tomate": 18,
            "zanahoria": 41,
            "pepino": 16,
            "espinaca": 23,
            "brocoli": 34,
            "coliflor": 25,
            "papas": 77,
            "camote": 86,
            "arroz": 130,
            "arroz integral": 111,
            "fideos": 158,
            "pan": 80,
            "tortilla": 120,
            "huevo": 78,
            "pollo": 165,
            "carne": 250,
            "pescado": 206,
            "atun": 132,
            "salmon": 208,
            "yogurt": 59,
            "queso": 402,
            "leche": 42,
            "cereal": 379,
            "avena": 68,
            "nueces": 654,
            "almendras": 575,
            "maní": 567,
            "chocolate": 546,
            "galleta": 50,
            "pizza": 266,
            "hamburguesa": 295,
            "hot dog": 290,
            "empanada": 275
        };

        const form = document.getElementById('calorie-form');
        const calorieList = document.getElementById('calorie-list');

        form.addEventListener('submit', function(event) {
            event.preventDefault();
            const food = document.getElementById('food').value.toLowerCase().trim();

            if (!calorieDB[food]) {
                alert("Esa comida no está en la base de datos 😞\nDímela y la agrego.");
                return;
            }

            const calories = calorieDB[food];

            const listItem = document.createElement('li');
            listItem.textContent = `${food}: ${calories} calorías`;
            calorieList.appendChild(listItem);

            form.reset();
        });
    </script>
</body>
</html>

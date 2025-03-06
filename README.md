<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Tienda de Productos</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Bienvenido a Mi Tienda</h1>
        <nav>
            <ul>
                <li><a href="#">Inicio</a></li>
                <li><a href="#">Productos</a></li>
                <li><a href="#">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <section id="products">
        <h2>Productos Disponibles</h2>
        <div id="product-list">
            <!-- Los productos se cargarán aquí -->
        </div>
    </section>

    <footer>
        <p>&copy; 2025 Mi Tienda. Todos los derechos reservados.</p>
    </footer>

    <script src="app.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

header {
    background-color: #333;
    color: white;
    padding: 10px 0;
    text-align: center;
}

header nav ul {
    list-style-type: none;
    padding: 0;
}

header nav ul li {
    display: inline;
    margin: 0 15px;
}

header nav ul li a {
    color: white;
    text-decoration: none;
}

#products {
    padding: 20px;
}

#product-list {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: space-around;
}

.product {
    background-color: white;
    border: 1px solid #ddd;
    border-radius: 5px;
    width: 200px;
    padding: 10px;
    text-align: center;
}

.product img {
    max-width: 100%;
    height: auto;
    border-radius: 5px;
}

footer {
    background-color: #333;
    color: white;
    padding: 10px 0;
    text-align: center;
    position: fixed;
    width: 100%;
    bottom: 0;
}
// Array con productos
const products = [
    { id: 1, name: 'Producto 1', price: 10.99, image: 'https://via.placeholder.com/200' },
    { id: 2, name: 'Producto 2', price: 20.99, image: 'https://via.placeholder.com/200' },
    { id: 3, name: 'Producto 3', price: 30.99, image: 'https://via.placeholder.com/200' }
];

// Función para renderizar los productos en la página
function renderProducts() {
    const productList = document.getElementById('product-list');
    productList.innerHTML = ''; // Limpiar contenido actual

    products.forEach(product => {
        const productDiv = document.createElement('div');
        productDiv.classList.add('product');

        const productHTML = `
            <img src="${product.image}" alt="${product.name}">
            <h3>${product.name}</h3>
            <p>$${product.price.toFixed(2)}</p>
            <button onclick="addToCart(${product.id})">Agregar al carrito</button>
        `;

        productDiv.innerHTML = productHTML;
        productList.appendChild(productDiv);
    });
}

// Función para agregar al carrito
function addToCart(productId) {
    alert(`Producto ${productId} agregado al carrito`);
}

// Inicializar la página cargando los productos
renderProducts();

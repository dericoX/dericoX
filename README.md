<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Loja de Eletrodomésticos</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Loja de Eletrodomésticos</h1>
    </header>
    <main>
        <div class="product-container">
            <img src="geladeira.jpg" alt="Geladeira" class="product-image">
            <h2>Geladeira Frost Free</h2>
            <p class="price">R$ 1.000,00</p>
            <button id="buy-button">Comprar</button>
        </div>
    </main>
    <footer>
        <p>&copy; 2024 - Sua Loja</p>
    </footer>

    <!-- Modal de pagamento -->
    <div id="payment-modal" class="modal">
        <div class="modal-content">
            <span id="close-modal">&times;</span>
            <h3>Pagamento</h3>
            <form id="payment-form">
                <label for="card-number">Número do Cartão</label>
                <input type="text" id="card-number" required>
                
                <label for="card-expiry">Validade</label>
                <input type="text" id="card-expiry" placeholder="MM/AA" required>
                
                <label for="card-cvc">CVC</label>
                <input type="text" id="card-cvc" required>
                
                <button type="submit">Pagar</button>
            </form>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
/* Reset básico */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f5;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
}

/* Header */
header {
    background-color: #4CAF50;
    padding: 20px;
    width: 100%;
    text-align: center;
    color: white;
}

.product-container {
    background: white;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
    text-align: center;
    max-width: 300px;
}

.product-image {
    width: 100%;
    border-radius: 10px;
}

.price {
    font-size: 1.5em;
    color: #4CAF50;
    margin: 10px 0;
}

button {
    padding: 10px 20px;
    font-size: 1em;
    color: white;
    background-color: #4CAF50;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

/* Modal */
.modal {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    justify-content: center;
    align-items: center;
}

.modal-content {
    background: white;
    padding: 20px;
    border-radius: 10px;
    width: 300px;
    text-align: center;
}

#close-modal {
    float: right;
    cursor: pointer;
    font-size: 1.2em;
}
document.getElementById("buy-button").addEventListener("click", function() {
    document.getElementById("payment-modal").style.display = "flex";
});

document.getElementById("close-modal").addEventListener("click", function() {
    document.getElementById("payment-modal").style.display = "none";
});

document.getElementById("payment-form").addEventListener("submit", function(event) {
    event.preventDefault();
    alert("Pagamento realizado com sucesso!");
    document.getElementById("payment-modal").style.display = "none";
});


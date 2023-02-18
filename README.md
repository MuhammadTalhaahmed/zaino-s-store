# zaino-s-store
﻿<!DOCTYPE html>
<html>
<head>
    <title>uuuuuuuuuuZaino-s-Store</title>
    <style>
        body {
            background-image: url('https://4kwallpapers.com/images/wallpapers/windows-11-landscape-scenery-sunrise-stock-day-light-3840x2160-5661.jpg');
            background-size: cover;
        }
    </style>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 1rem;
            text-align: center;
        }

        main {
            max-width: 950px;
            margin: 0 auto;
            padding: 2rem;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
        }

        .product {
            width: 18rem;
            margin-bottom: 2rem;
            border: 1px solid #ccc;
            padding: 1rem;
            box-shadow: 2px 2px 5px #ccc;
        }

            .product img {
                max-width: 100%;
                height: auto;
            }

            .product h2 {
                margin-top: 0;
            }

            .product p {
                margin: 0;
                font-size: 0.9rem;
                margin-bottom: 0.5rem;
            }

            .product button {
                background-color: #333;
                color: #fff;
                padding: 0.5rem;
                border: none;
                cursor: pointer;
                transition: background-color 0.3s;
                margin-top: 1rem;
            }

                .product button:hover {
                    background-color: #555;
                }
    </style>
</head>
<body>
    <header>
        <h1>Zaino's Store</h1>
    </header>
    <main>
        <div class="product">
            <img src="product1.jpg" alt="Product 1">
            <h2>Product 1</h2>
            <p>Description of Product 1.</p>
            <p>Price: $10</p>
            <button>Order Now</button>
        </div>
        <div class="product">
            <img src="product2.jpg" alt="Product 2">
            <h2>Product 2</h2>
            <p>Description of Product 2.</p>
            <p>Price: $20</p>
            <button>Order Now</button>
        </div>
        <!-- continue adding products until 40 products are added -->
    </main>
    <!-- Modal HTML -->
    <div class="modal">
        <div class="modal-content">
            <span class="close">&times;</span>
            <h2>Order Form</h2>
            <form id="order-form">
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" required>
                <label for="mobile">Mobile No:</label>
                <input type="tel" id="mobile" name="mobile" required>
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>
                <label for="address">Address:</label>
                <textarea id="address" name="address" required></textarea>
                <input type="hidden" id="product-name" name="product-name">
                <input type="submit" value="Submit">
            </form>
        </div>
    </div>

    <!-- CSS -->
    <style>
        .modal {
            display: none;
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.4);
        }

        .modal-content {
            background-color: #fefefe;
            margin: 15% auto;
            padding: 20px;
            border: 1px solid #888;
            width: 60%;
        }

        .close {
            color: #aaaaaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }

            .close:hover,
            .close:focus {
                color: #000;
                text-decoration: none;
                cursor: pointer;
            }

        #order-form {
            display: grid;
            grid-template-columns: 1fr 1fr;
            grid-gap: 10px;
        }

            #order-form label {
                font-weight: bold;
            }

            #order-form input,
            #order-form textarea {
                width: 100%;
                padding: 10px;
                border: 1px solid #ccc;
                border-radius: 4px;
                box-sizing: border-box;
            }

                #order-form input[type="submit"] {
                    background-color: #4CAF50;
                    color: white;
                    border: none;
                    border-radius: 4px;
                    cursor: pointer;
                    padding: 10px;
                }

                    #order-form input[type="submit"]:hover {
                        background-color: #45a049;
                    }
    </style>
    <script>
        // Get all the "Order now" buttons
        const orderButtons = document.querySelectorAll('.order-button');

        // Get the modal and close button elements
        const modal = document.querySelector('.modal');
        const closeBtn = document.querySelector('.close');

        // Get the form and product name input elements
        const orderForm = document.querySelector('#order-form');
        const productNameInput = document.querySelector('#product-name');


        // Add event listeners to all order buttons
        const orderButtons = document.querySelectorAll('.order-button');
        orderButtons.forEach(button => {
            button.addEventListener('click', event => {
                // Prevent default button behavior
                event.preventDefault();

                // Scroll smoothly to the order form
                const orderForm = document.getElementById('order-form');
                orderForm.scrollIntoView({ behavior: 'smooth' });

                // Set the selected product name in the form
                const productName = event.target.parentNode.parentNode.querySelector('.product-name').textContent;
                document.getElementById('product-name').value = productName;
            });
        });

        // Add event listener to the form submission
        const orderForm = document.getElementById('order-form');
        orderForm.addEventListener('submit', event => {
            // Prevent default form submission behavior
            event.preventDefault();

            // Get the form data
            const formData = new FormData(orderForm);

            // Send the form data to the server
            const xhr = new XMLHttpRequest();
            xhr.open('POST', 'order.php');
            xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
            xhr.onload = function () {
                // Hide the form and show the success message
                orderForm.style.display = 'none';
                document.getElementById('success-message').style.display = 'block';
            };
            xhr.send(new URLSearchParams(formData).toString());
        });
















        // Select the form element
        const form = document.getElementById('order-form');

        // Add event listener to the form submit event
        form.addEventListener('submit', function (event) {
            event.preventDefault(); // Prevent the default form submission

            // Get the data from the form
            const name = document.getElementById('name').value;
            const mobile = document.getElementById('mobile').value;
            const email = document.getElementById('email').value;
            const address = document.getElementById('address').value;
            const product = document.getElementById('product-name').textContent;

            // Create an XMLHttpRequest object
            const xhr = new XMLHttpRequest();

            // Set the URL and request method
            xhr.open('POST', 'url-to-server', true);

            // Set the request header to send form data as JSON
            xhr.setRequestHeader('Content-Type', 'application/json');

            // Define the data to send to the server
            const data = {
                name: name,
                mobile: mobile,
                email: email,
                address: address,
                product: product
            };

            // Convert the data to JSON string
            const jsonData = JSON.stringify(data);

            // Send the data to the server
            xhr.send(jsonData);

            // Remove the order button for the current product
            const currentOrderButton = document.querySelector('.order-button.active');
            currentOrderButton.parentNode.removeChild(currentOrderButton);

            // Show a message to the user that the form was submitted successfully
            alert('Form submitted successfully!');
        });













    </script>

</body>
</html>

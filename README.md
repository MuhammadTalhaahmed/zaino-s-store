<html>
<head>

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-6110467688747925"
     crossorigin="anonymous"></script>


<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-H2R4B79ML7"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-H2R4B79ML7');
</script>


    <title>Zaino-s-Store</title>
    <style>
        body {
            background-image: url('Background.png');
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

        .product {
            display: inline-block;
            margin: 14px;
            width: 180px;
            text-align: center;
        }

            .product img {
                width: 150px;
                height: 150px;
                object-fit: cover;
            }

            .product h3 {
                font-size: 14px;
                margin-top: 7px;
                margin-bottom: 3.5px;
            }

            .product h2 {
                margin-top: 0;
            }

            .product p {
                font-size: 10px;
                margin-top: 3.5px;
                margin-bottom: 7px;
            }

            .product button {
                font-size: 10px;
                padding: 6px 14px;
                background-color: #4CAF50;
                color: white;
                border: none;
                border-radius: 3.5px;
                cursor: pointer;
            }

        .row {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
        }

        <!-- CSS -->
        
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

        .close:hover,
        .close {
            color: #aaaaaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }


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

</head>
<body>
    <header>
        <h1>Zaino's Store</h1>
    </header>
    <main>
        <!-- First product -->
        <div class="product">
            <h2>Product 1</h2>
            <img src="product1.jpg" alt="Product 1">
            <p>Description of Product 1</p>
            <p>Price: $10.00</p>
            <button onclick="showForm('Product 1')">Order now</button>

            <p id="Product 1 Status"></p>
        </div>

        <!-- Second product -->
        <div class="product">
            <h2>Product 2</h2>
            <img src="product2.jpg" alt="Product 2">
            <p>Description of Product 2</p>
            <p>Price: $15.00</p>
            <button onclick="showForm('Product 2')">Order now</button>
            <p id="Product 2 Status"></p>
        </div>
        <!-- Second product -->
        <div class="product">
            <h2>Product 2</h2>
            <img src="product2.jpg" alt="Product 2">
            <p>Description of Product 2</p>
            <p>Price: $15.00</p>
            <button onclick="showForm('Product 1')">Order now</button>

            <p id="Product 2 Status"></p>
        </div>
        <!-- Second product -->
        <div class="product">
            <h2>Product 2</h2>
            <img src="product2.jpg" alt="Product 2">
            <p>Description of Product 2</p>
            <p>Price: $15.00</p>
            <button onclick="showForm('Product 1')">Order now</button>

            <p id="Product 2 Status"></p>
        </div>
        <!-- Second product -->
        <div class="product">
            <h2>Product 2</h2>
            <img src="product2.jpg" alt="Product 2">
            <p>Description of Product 2</p>
            <p>Price: $15.00</p>
            <button onclick="showForm('Product 1')">Order now</button>
            <p id="Product 2 Status"></p>
        </div>
        <!-- Second product -->
        <div class="product">
            <h2>Product 2</h2>
            <img src="whitepurse.jpg" alt="Product 2">
            <p>Branded Decent white Bag</p>
            <p>Price: Rs 1200</p>
            <button onclick="showForm('Product 1')">Order now</button>
            <p id="Product 2 Status"></p>
        </div>

        <!-- Second product -->
        <div class="product">
            <h2>Product 2</h2>
            <img src="brownpurse.jpg" alt="Product 2">
            <p>Branded Decent Brown Bag</p>
            <p>Price: Rs 1200</p>
            <button onclick="showForm('Product 1')">Order now</button>
            <p id="Product 2 Status"></p>
        </div>



        <script>
            function showForm(productName) {
                document.getElementById('product-name').value = productName;
                document.getElementById('order-form').style.display = 'block';
                document.getElementById('order-form').scrollIntoView({ behavior: 'smooth' });
            }
        </script>
        
 

        <script>
            // Add event listeners to all "Order now" buttons
            const orderNowButtons = document.querySelectorAll('.order-now');
            orderNowButtons.forEach(button => {
                button.addEventListener('click', () => {
                    const product = button.getAttribute('data-product');
                    const form = document.getElementById('order-form');
                    const productField = form.elements['product'];
                    productField.value = product;
                    const formContainer = document.querySelector('.order-form-container');
                    formContainer.scrollIntoView({ behavior: 'smooth' });
                });
            });

            // Submit the form data to the server
            const form = document.getElementById('order-form');
            form.addEventListener('submit', (event) => {
                event.preventDefault();
                const formData = new FormData(form);
                fetch('https://zaino-s-store.000webhostapp.com/index.php', {
                    method: 'POST',
                    body: formData
                })
                    .then(response => {
                        if (response.ok) {
                            alert('Your order has been submitted. Thank you!');
                            form.reset();
                        } else {
                            throw new Error('Network response was not ok.');
                        }
                    })
                    .catch(error => {
                        console.error('There was a problem submitting the form:', error);
                    });
            });
        </script>

    </main>
<!-- Modal HTML -->
    <div class="modal">
        <div class="modal-content">
            <span class="close">&times;</span>
            <h2>Order Form</h2>
            <form id="order-form" action="https://zaino-s-store.000webhostapp.com/index.php" method="POST">
                <input type="text" id="product-name" name="product-name" readonly><br><br />
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" required>
                <label for="mobile">Mobile No:</label>
                <input type="tel" id="mobile" name="mobile" required>
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>
                <label for="address">Address:</label>
                <textarea id="address" name="address" required></textarea>
                <label for="product">Product Name:</label>
                <input type="text" id="product" name="product" required>
                <input type="hidden" id="product-name" name="product-name">
                <input type="submit" value="Submit">
            </form>
        </div>
    </div>
    
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
            xhr.open('POST', 'https://zaino-s-store.000webhostapp.com/index.php');
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
            xhr.open('POST', 'https://zaino-s-store.000webhostapp.com/index.php', true);

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

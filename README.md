<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Bukyemzy Kitchen | A Sweet Escape From The Ordinary</title>

    <style>
        /* ==============================
           RESET & VARIABLES
        ============================== */

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        :root {
            --purple: #4b176d;
            --dark-purple: #301044;
            --lilac: #d9b8ec;
            --light-lilac: #f3e5fa;
            --cream: #fff7e9;
            --gold: #b86b00;
            --brown: #8b4d18;
            --white: #ffffff;
            --text: #604b6d;
        }

        body {
            font-family: "Segoe UI", Arial, sans-serif;
            background: var(--cream);
            color: var(--purple);
            line-height: 1.6;
        }

        /* ==============================
           NAVBAR
        ============================== */

        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;

            background: rgba(255, 247, 233, 0.96);
            backdrop-filter: blur(12px);

            border-bottom: 1px solid #ead8ee;
        }

        nav {
            max-width: 1200px;
            height: 80px;
            margin: auto;
            padding: 0 25px;

            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .nav-logo img {
            width: 115px;
            height: 70px;
            object-fit: contain;
        }

        .nav-links {
            display: flex;
            align-items: center;
            gap: 32px;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--purple);
            font-weight: 600;
            transition: 0.3s;
        }

        .nav-links a:hover {
            color: var(--gold);
        }

        .order-nav {
            background: var(--purple);
            color: white !important;
            padding: 10px 20px;
            border-radius: 30px;
        }

        .order-nav:hover {
            background: var(--gold);
        }

        .menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--purple);
            font-size: 30px;
            cursor: pointer;
        }

        /* ==============================
           HERO
        ============================== */

        .hero {
            min-height: 100vh;
            padding: 130px 7% 80px;

            display: flex;
            align-items: center;

            background:
                radial-gradient(
                    circle at 80% 20%,
                    #e5c8f0 0%,
                    transparent 32%
                ),
                linear-gradient(
                    135deg,
                    #fffaf3,
                    #f4e3fa
                );

            overflow: hidden;
        }

        .hero-container {
            max-width: 1200px;
            width: 100%;
            margin: auto;

            display: grid;
            grid-template-columns: 1.1fr 0.9fr;
            gap: 60px;
            align-items: center;
        }

        .small-title {
            color: var(--gold);
            font-size: 0.85rem;
            font-weight: 800;
            letter-spacing: 3px;
            text-transform: uppercase;
            margin-bottom: 15px;
        }

        .hero h1 {
            font-family: Georgia, serif;
            font-size: clamp(3rem, 7vw, 6rem);
            line-height: 0.95;
            color: var(--purple);
            margin-bottom: 25px;
        }

        .hero h1 span {
            color: var(--gold);
        }

        .hero p {
            max-width: 570px;
            color: var(--text);
            font-size: 1.08rem;
            margin-bottom: 30px;
        }

        .hero-buttons {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        .btn {
            display: inline-block;
            padding: 14px 26px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 700;
            transition: 0.3s;
            cursor: pointer;
            border: none;
            font-size: 0.95rem;
        }

        .btn-primary {
            background: var(--purple);
            color: white;
        }

        .btn-primary:hover {
            background: var(--gold);
            transform: translateY(-3px);
        }

        .btn-secondary {
            border: 2px solid var(--purple);
            color: var(--purple);
        }

        .btn-secondary:hover {
            background: var(--purple);
            color: white;
        }

        .hero-logo {
            display: flex;
            justify-content: center;
        }

        .logo-circle {
            width: min(440px, 80vw);
            height: min(440px, 80vw);

            padding: 20px;

            background: var(--cream);
            border: 8px solid var(--purple);
            border-radius: 50%;

            box-shadow:
                0 25px 70px rgba(75, 23, 109, 0.18);

            display: flex;
            align-items: center;
            justify-content: center;
        }

        .logo-circle img {
            width: 100%;
            height: 100%;
            object-fit: contain;
            border-radius: 50%;
        }

        /* ==============================
           MENU
        ============================== */

        .menu-section {
            padding: 105px 7%;
            background: white;
        }

        .section-heading {
            text-align: center;
            margin-bottom: 55px;
        }

        .section-heading h2 {
            font-family: Georgia, serif;
            font-size: clamp(2.5rem, 5vw, 4rem);
            color: var(--purple);
        }

        .section-heading p {
            max-width: 620px;
            margin: 10px auto 0;
            color: var(--text);
        }

        .food-grid {
            max-width: 1200px;
            margin: auto;

            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }

        .food-card {
            background: var(--cream);
            border-radius: 22px;
            overflow: hidden;
            border: 1px solid #ead9ef;

            transition: 0.4s;
        }

        .food-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 18px 40px rgba(75, 23, 109, 0.13);
        }

        .food-image {
            height: 220px;

            display: flex;
            align-items: center;
            justify-content: center;

            background:
                linear-gradient(
                    135deg,
                    var(--light-lilac),
                    #fff0d9
                );

            font-size: 5rem;
        }

        .food-content {
            padding: 22px;
        }

        .food-content h3 {
            font-family: Georgia, serif;
            font-size: 1.5rem;
            color: var(--purple);
            margin-bottom: 5px;
        }

        .food-content p {
            color: var(--text);
            font-size: 0.92rem;
        }

        .food-tag {
            display: inline-block;
            margin-top: 12px;

            padding: 5px 12px;

            background: var(--lilac);
            color: var(--purple);

            border-radius: 20px;

            font-size: 0.72rem;
            font-weight: 800;
        }

        /* ==============================
           ABOUT
        ============================== */

        .about {
            padding: 105px 7%;
            background: var(--purple);
            color: white;
            text-align: center;
        }

        .about-container {
            max-width: 900px;
            margin: auto;
        }

        .about h2 {
            font-family: Georgia, serif;
            font-size: clamp(2.5rem, 5vw, 4rem);
            line-height: 1.05;
            margin-bottom: 20px;
        }

        .about p {
            color: #e7d9ed;
            font-size: 1.05rem;
        }

        .about .btn {
            margin-top: 30px;
            background: white;
            color: var(--purple);
        }

        .about .btn:hover {
            background: var(--gold);
            color: white;
        }

        /* ==============================
           ORDER SECTION
        ============================== */

        .order-section {
            padding: 105px 7%;
            background: var(--cream);
        }

        .order-container {
            max-width: 1100px;
            margin: auto;

            display: grid;
            grid-template-columns: 0.8fr 1.2fr;
            gap: 60px;
            align-items: start;
        }

        .order-info h2 {
            font-family: Georgia, serif;
            font-size: clamp(2.7rem, 5vw, 4rem);
            line-height: 1;
            color: var(--purple);
            margin-bottom: 20px;
        }

        .order-info h2 span {
            color: var(--gold);
        }

        .order-info p {
            color: var(--text);
        }

        .phone-box {
            margin-top: 30px;
            padding: 20px;

            background: white;
            border-left: 5px solid var(--gold);
            border-radius: 10px;
        }

        .phone-box small {
            display: block;
            color: #8d7895;
            margin-bottom: 4px;
        }

        .phone-box a {
            color: var(--purple);
            font-size: 1.4rem;
            font-weight: 800;
            text-decoration: none;
        }

        /* ==============================
           FORM
        ============================== */

        .order-form {
            background: white;
            padding: 35px;

            border-radius: 22px;

            box-shadow:
                0 15px 45px rgba(75, 23, 109, 0.1);
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            color: var(--purple);
            font-size: 0.85rem;
            font-weight: 700;
            margin-bottom: 7px;
        }

        input,
        select,
        textarea {
            width: 100%;

            padding: 13px 15px;

            border: 1px solid #ddcde3;
            border-radius: 10px;

            background: #fffdf9;
            color: #35135c;

            font-family: inherit;
            font-size: 0.95rem;

            outline: none;
        }

        input:focus,
        select:focus,
        textarea:focus {
            border-color: var(--purple);
            box-shadow: 0 0 0 3px rgba(75, 23, 109, 0.08);
        }

        textarea {
            min-height: 120px;
            resize: vertical;
        }

        .error {
            display: none;
            color: #b13c3c;
            font-size: 0.75rem;
            margin-top: 5px;
        }

        .success {
            display: none;

            margin-top: 15px;
            padding: 15px;

            background: #eee0f5;
            color: var(--purple);

            border-radius: 10px;
            font-weight: 600;
        }

        /* ==============================
           CONTACT
        ============================== */

        .contact {
            padding: 80px 7%;
            background: var(--dark-purple);
            color: white;
            text-align: center;
        }

        .contact h2 {
            font-family: Georgia, serif;
            font-size: clamp(2rem, 5vw, 3rem);
            margin-bottom: 10px;
        }

        .contact p {
            color: #dfcfe8;
            margin-bottom: 20px;
        }

        .contact-number {
            display: inline-block;
            color: white;
            font-size: 1.7rem;
            font-weight: 800;
            text-decoration: none;
            transition: 0.3s;
        }

        .contact-number:hover {
            color: var(--lilac);
        }

        /* ==============================
           FOOTER
        ============================== */

        footer {
            background: #210d30;
            color: #cbb8d5;
            text-align: center;
            padding: 25px;
            font-size: 0.85rem;
        }

        /* ==============================
           RESPONSIVE DESIGN
        ============================== */

        @media (max-width: 850px) {

            .menu-btn {
                display: block;
            }

            .nav-links {
                position: absolute;
                top: 80px;
                left: 0;

                width: 100%;

                background: var(--cream);

                flex-direction: column;
                align-items: center;

                padding: 25px;

                display: none;

                box-shadow: 0 10px 25px rgba(0,0,0,0.08);
            }

            .nav-links.active {
                display: flex;
            }

            .hero-container {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .hero-logo {
                order: -1;
            }

            .hero p {
                margin-left: auto;
                margin-right: auto;
            }

            .hero-buttons {
                justify-content: center;
            }

            .food-grid {
                grid-template-columns: 1fr 1fr;
            }

            .order-container {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 550px) {

            nav {
                padding: 0 15px;
            }

            .nav-logo img {
                width: 95px;
            }

            .hero {
                padding: 120px 5% 70px;
            }

            .hero h1 {
                font-size: 3.2rem;
            }

            .logo-circle {
                width: 280px;
                height: 280px;
            }

            .food-grid {
                grid-template-columns: 1fr;
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .order-form {
                padding: 22px;
            }

            .menu-section,
            .about,
            .order-section {
                padding: 80px 5%;
            }
        }
    </style>
</head>


<body>

    <!-- ==============================
         NAVIGATION
    ============================== -->

    <header>

        <nav>

            <a href="#home" class="nav-logo">

                <img
                    src="bukyemz-logo.png"
                    alt="Bukyemz Kitchen Logo"
                >

            </a>


            <button
                class="menu-btn"
                id="menuBtn"
                aria-label="Open menu"
            >
                ☰
            </button>


            <ul class="nav-links" id="navLinks">

                <li>
                    <a href="#home">Home</a>
                </li>

                <li>
                    <a href="#menu">Our Treats</a>
                </li>

                <li>
                    <a href="#about">About Us</a>
                </li>

                <li>
                    <a href="#order" class="order-nav">
                        Place an Order
                    </a>
                </li>

            </ul>

        </nav>

    </header>


    <!-- ==============================
         HERO
    ============================== -->

    <section class="hero" id="home">

        <div class="hero-container">


            <div class="hero-content">

                <div class="small-title">
                    Welcome to Bukyemz Kitchen
                </div>


                <h1>
                    A Sweet Escape
                    <span>From The Ordinary.</span>
                </h1>


                <p>
                    Delicious homemade treats made with love.
                    From fluffy puff puff and crispy samosas
                    to creamy parfait, spring rolls, meat pies
                    and beautiful celebration cakes.
                </p>


                <div class="hero-buttons">

                    <a
                        href="#menu"
                        class="btn btn-primary"
                    >
                        Explore Our Treats
                    </a>


                    <a
                        href="#order"
                        class="btn btn-secondary"
                    >
                        Order Now
                    </a>

                </div>

            </div>


            <div class="hero-logo">

                <div class="logo-circle">

                    <img
                        src="bukyemz-logo.png"
                        alt="Bukyemz Kitchen"
                    >

                </div>

            </div>

        </div>

    </section>


    <!-- ==============================
         FOOD MENU
    ============================== -->

    <section class="menu-section" id="menu">

        <div class="section-heading">

            <div class="small-title">
                Freshly Made
            </div>

            <h2>Our Delicious Treats</h2>

            <p>
                Perfect for birthdays, parties, celebrations,
                meetings or simply treating yourself.
            </p>

        </div>


        <div class="food-grid">


            <!-- PARFAIT -->

            <article class="food-card">

                <div class="food-image">
                    🍓
                </div>

                <div class="food-content">

                    <h3>Parfait</h3>

                    <p>
                        Creamy, fruity and beautifully layered
                        for the perfect sweet treat.
                    </p>

                    <span class="food-tag">
                        SWEET & FRESH
                    </span>

                </div>

            </article>


            <!-- PUFF PUFF -->

            <article class="food-card">

                <div class="food-image">
                    🍩
                </div>

                <div class="food-content">

                    <h3>Puff Puff</h3>

                    <p>
                        Soft, fluffy and golden puff puff,
                        perfect for every celebration.
                    </p>

                    <span class="food-tag">
                        PARTY FAVOURITE
                    </span>

                </div>

            </article>


            <!-- SPRING ROLL -->

            <article class="food-card">

                <div class="food-image">
                    🌯
                </div>

                <div class="food-content">

                    <h3>Spring Roll</h3>

                    <p>
                        Crispy golden rolls packed with
                        delicious savoury filling.
                    </p>

                    <span class="food-tag">
                        CRISPY & DELICIOUS
                    </span>

                </div>

            </article>


            <!-- SAMOSA -->

            <article class="food-card">

                <div class="food-image">
                    🔺
                </div>

                <div class="food-content">

                    <h3>Samosa</h3>

                    <p>
                        Golden crispy samosas filled with
                        tasty savoury goodness.
                    </p>

                    <span class="food-tag">
                        SAVOURY FAVOURITE
                    </span>

                </div>

            </article>


            <!-- MEAT PIE -->

            <article class="food-card">

                <div class="food-image">
                    🥧
                </div>

                <div class="food-content">

                    <h3>Meat Pie</h3>

                    <p>
                        Delicious golden pastry filled with
                        a tasty savoury meat filling.
                    </p>

                    <span class="food-tag">
                        HOMEMADE
                    </span>

                </div>

            </article>


            <!-- CAKE -->

            <article class="food-card">

                <div class="food-image">
                    🎂
                </div>

                <div class="food-content">

                    <h3>Celebration Cakes</h3>

                    <p>
                        Beautiful cakes made for birthdays,
                        celebrations and special moments.
                    </p>

                    <span class="food-tag">
                        MADE WITH LOVE
                    </span>

                </div>

            </article>

        </div>

    </section>


    <!-- ==============================
         ABOUT
    ============================== -->

    <section class="about" id="about">

        <div class="about-container">

            <div class="small-title">
                Why Bukyemz?
            </div>

            <h2>
                Made With Love.
                Served With Joy.
            </h2>

            <p>
                At Bukyemz Kitchen, we believe good food makes
                every moment better. Our treats are prepared
                with care, attention to detail and a whole lot
                of love.

                Whether you're planning a big celebration,
                ordering for an event or simply craving
                something delicious, we're ready to make
                your occasion extra special.
            </p>


            <a
                href="#order"
                class="btn"
            >
                Place Your Order
            </a>

        </div>

    </section>


    <!-- ==============================
         ORDER SECTION
    ============================== -->

    <section class="order-section" id="order">

        <div class="order-container">


            <!-- ORDER INFORMATION -->

            <div class="order-info">

                <div class="small-title">
                    Let's Get Cooking
                </div>


                <h2>
                    Place Your
                    <span>Order.</span>
                </h2>


                <p>
                    Fill in the form and your order details
                    will be sent directly to Bukyemz Kitchen
                    through WhatsApp.
                </p>


                <div class="phone-box">

                    <small>
                        Call or WhatsApp us
                    </small>


                    <a href="tel:08055557729">
                        08055557729
                    </a>

                </div>

            </div>


            <!-- ORDER FORM -->

            <form
                class="order-form"
                id="orderForm"
            >


                <!-- NAME + PHONE -->

                <div class="form-row">

                    <div class="form-group">

                        <label for="name">
                            Your Name
                        </label>

                        <input
                            type="text"
                            id="name"
                            placeholder="Enter your name"
                        >

                        <span
                            class="error"
                            id="nameError"
                        >
                            Please enter your name.
                        </span>

                    </div>


                    <div class="form-group">

                        <label for="phone">
                            Phone Number
                        </label>

                        <input
                            type="tel"
                            id="phone"
                            placeholder="080..."
                        >

                        <span
                            class="error"
                            id="phoneError"
                        >
                            Please enter a valid phone number.
                        </span>

                    </div>

                </div>


                <!-- FOOD -->

                <div class="form-group">

                    <label for="item">
                        What would you like to order?
                    </label>

                    <select id="item">

                        <option value="">
                            Select an item
                        </option>

                        <option value="Parfait">
                            Parfait
                        </option>

                        <option value="Puff Puff">
                            Puff Puff
                        </option>

                        <option value="Spring Roll">
                            Spring Roll
                        </option>

                        <option value="Samosa">
                            Samosa
                        </option>

                        <option value="Meat Pie">
                            Meat Pie
                        </option>

                        <option value="Cake">
                            Cake
                        </option>

                        <option value="Multiple Items">
                            Multiple Items
                        </option>

                    </select>

                    <span
                        class="error"
                        id="itemError"
                    >
                        Please select an item.
                    </span>

                </div>


                <!-- QUANTITY + DATE -->

                <div class="form-row">

                    <div class="form-group">

                        <label for="quantity">
                            Quantity
                        </label>

                        <input
                            type="number"
                            id="quantity"
                            min="1"
                            placeholder="e.g. 20"
                        >

                        <span
                            class="error"
                            id="quantityError"
                        >
                            Please enter a quantity.
                        </span>

                    </div>


                    <div class="form-group">

                        <label for="date">
                            Preferred Date
                        </label>

                        <input
                            type="date"
                            id="date"
                        >

                    </div>

                </div>


                <!-- EXTRA DETAILS -->

                <div class="form-group">

                    <label for="message">
                        Additional Details
                    </label>

                    <textarea
                        id="message"
                        placeholder="Tell us anything else about your order..."
                    ></textarea>

                </div>


                <!-- WHATSAPP BUTTON -->

                <button
                    type="submit"
                    class="btn btn-primary"
                >
                    💬 Send Order to WhatsApp
                </button>


                <div
                    class="success"
                    id="successMessage"
                >
                    🎉 Opening WhatsApp with your order...
                </div>

            </form>

        </div>

    </section>


    <!-- ==============================
         CONTACT
    ============================== -->

    <section class="contact">

        <div class="small-title">
            Ready To Order?
        </div>

        <h2>
            Let's Make Something Delicious!
        </h2>

        <p>
            Call or WhatsApp Bukyemz Kitchen today.
        </p>

        <a
            href="tel:08055557729"
            class="contact-number"
        >
            📞 08055557729
        </a>

    </section>


    <!-- ==============================
         FOOTER
    ============================== -->

    <footer>

        <p>
            © 2026 Bukyemz Kitchen.
            A sweet escape from the ordinary. 💜
        </p>

    </footer>


    <!-- ==============================
         JAVASCRIPT
    ============================== -->

    <script>

        /* ==============================
           MOBILE NAVIGATION
        ============================== */

        const menuBtn =
            document.getElementById("menuBtn");

        const navLinks =
            document.getElementById("navLinks");


        menuBtn.addEventListener("click", function() {

            navLinks.classList.toggle("active");

        });


        document
            .querySelectorAll(".nav-links a")
            .forEach(function(link) {

                link.addEventListener("click", function() {

                    navLinks.classList.remove("active");

                });

            });


        /* ==============================
           ORDER FORM
        ============================== */

        const orderForm =
            document.getElementById("orderForm");


        orderForm.addEventListener("submit", function(event) {

            event.preventDefault();


            /* Get values */

            const name =
                document.getElementById("name")
                .value
                .trim();

            const phone =
                document.getElementById("phone")
                .value
                .trim();

            const item =
                document.getElementById("item")
                .value;

            const quantity =
                document.getElementById("quantity")
                .value;

            const date =
                document.getElementById("date")
                .value;

            const message =
                document.getElementById("message")
                .value
                .trim();


            /* Error messages */

            const nameError =
                document.getElementById("nameError");

            const phoneError =
                document.getElementById("phoneError");

            const itemError =
                document.getElementById("itemError");

            const quantityError =
                document.getElementById("quantityError");

            const successMessage =
                document.getElementById("successMessage");


            /* Hide errors */

            nameError.style.display = "none";
            phoneError.style.display = "none";
            itemError.style.display = "none";
            quantityError.style.display = "none";
            successMessage.style.display = "none";


            let valid = true;


            /* ==============================
               NAME VALIDATION
            ============================== */

            if (name === "") {

                nameError.style.display = "block";

                valid = false;

            }


            /* ==============================
               PHONE VALIDATION
            ============================== */

            const phonePattern =
                /^[0-9+\-\s]{10,15}$/;


            if (
                phone === "" ||
                !phonePattern.test(phone)
            ) {

                phoneError.style.display = "block";

                valid = false;

            }


            /* ==============================
               ITEM VALIDATION
            ============================== */

            if (item === "") {

                itemError.style.display = "block";

                valid = false;

            }


            /* ==============================
               QUANTITY VALIDATION
            ============================== */

            if (
                quantity === "" ||
                Number(quantity) < 1
            ) {

                quantityError.style.display = "block";

                valid = false;

            }


            /* ==============================
               SEND TO WHATSAPP
            ============================== */

            if (valid) {


                /*
                    Bukyemz Kitchen number:

                    08055557729

                    International WhatsApp format:

                    2348055557729
                */

                const whatsappNumber =
                    "2348055557729";


                let whatsappMessage =
                    "Hello Bukyemz Kitchen! 💜🍰" +
                    "\n\n" +

                    "I would like to place an order." +
                    "\n\n" +

                    "👤 *Name:* " +
                    name +

                    "\n📞 *Phone:* " +
                    phone +

                    "\n🍴 *Order:* " +
                    item +

                    "\n🔢 *Quantity:* " +
                    quantity;


                /* Add date if provided */

                if (date !== "") {

                    whatsappMessage +=
                        "\n📅 *Preferred Date:* " +
                        date;

                }


                /* Add additional message */

                if (message !== "") {

                    whatsappMessage +=
                        "\n📝 *Additional Details:* " +
                        message;

                }


                whatsappMessage +=
                    "\n\nThank you! 💜";


                /* Encode message */

                const encodedMessage =
                    encodeURIComponent(
                        whatsappMessage
                    );


                /* Create WhatsApp URL */

                const whatsappURL =
                    "https://wa.me/" +
                    whatsappNumber +
                    "?text=" +
                    encodedMessage;


                /* Show success */

                successMessage.style.display = "block";


                /* Open WhatsApp */

                window.open(
                    whatsappURL,
                    "_blank"
                );

            }

        });

    </script>

</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Personal Webpage</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            scroll-behavior: smooth;
            background-color: #f4f4f4;
        }

        /* Basic page structure */
        header {
            position: fixed;
            width: 100%;
            top: 0;
            background-color: #333;
            color: white;
            padding: 20px 0;
            text-align: center;
            z-index: 1000;
        }

        header nav a {
            color: white;
            text-decoration: none;
            margin: 0 15px;
            font-size: 18px;
        }

        section {
            padding: 100px 20px;
            text-align: center;
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }

        section.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://source.unsplash.com/random/1600x900') no-repeat center center/cover;
            color: white;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }

        .hero h1 {
            font-size: 60px;
            margin: 0;
        }

        .hero p {
            font-size: 24px;
            margin: 20px 0;
        }

        .hero a {
            background-color: #00bcd4;
            color: white;
            padding: 10px 25px;
            text-decoration: none;
            font-size: 20px;
            border-radius: 5px;
            transition: background-color 0.3s ease;
        }

        .hero a:hover {
            background-color: #008c9e;
        }

        /* About Me Section */
        .about {
            background-color: white;
        }

        .about img {
            width: 150px;
            border-radius: 50%;
            margin-bottom: 20px;
        }

        /* Projects Section */
        .projects {
            background-color: #f9f9f9;
        }

        .projects .project {
            display: inline-block;
            width: 30%;
            margin: 15px;
            transition: transform 0.3s ease;
        }

        .projects .project img {
            width: 100%;
            border-radius: 10px;
        }

        .projects .project:hover {
            transform: scale(1.05);
        }

        /* Contact Section */
        .contact {
            background-color: #333;
            color: white;
        }

        /* Button hover effect */
        button {
            padding: 10px 20px;
            background-color: #00bcd4;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #008c9e;
        }

        /* Footer */
        footer {
            padding: 20px;
            background-color: #222;
            color: white;
            text-align: center;
        }
    </style>
</head>
<body>

    <header>
        <nav>
            <a href="#about">About Me</a>
            <a href="#projects">Projects</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <h1>Welcome to My Portfolio</h1>
        <p>I'm a Web Developer & Designer</p>
        <a href="#about">Learn More</a>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <img src="https://source.unsplash.com/random/150x150" alt="Your Photo">
        <h2>About Me</h2>
        <p>Hi, I'm [Your Name]. I love creating beautiful and functional websites. With expertise in front-end and back-end development, I strive to deliver excellent user experiences.</p>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects">
        <h2>My Projects</h2>
        <div class="project">
            <img src="https://source.unsplash.com/random/300x200" alt="Project 1">
            <h3>Project 1</h3>
            <p>A short description of the project goes here.</p>
        </div>
        <div class="project">
            <img src="https://source.unsplash.com/random/300x200" alt="Project 2">
            <h3>Project 2</h3>
            <p>A short description of the project goes here.</p>
        </div>
        <div class="project">
            <img src="https://source.unsplash.com/random/300x200" alt="Project 3">
            <h3>Project 3</h3>
            <p>A short description of the project goes here.</p>
        </div>
    </section>

    <!-- Contact Section -->
    <!-- Contact Section with Form and Validation -->
<section id="contact" class="contact">
    <h2>Contact Me</h2>
    <p>If you'd like to work together, feel free to reach out by filling out the form below!</p>
    <form
  action="https://formspree.io/f/mnnqanzv"
  method="POST"
>
  <label>
    Your email:
    <input type="email" name="email">
  </label>
  <label>
    Your message:
    <textarea name="message"></textarea>
  </label>
  <!-- your other form fields go here -->
  <button type="submit">Send</button>
</form>
</section>

<script>
    // Form validation script
    document.getElementById('contact-form').addEventListener('submit', function(event) {
        const name = document.getElementById('name').value.trim();
        const email = document.getElementById('email').value.trim();
        const message = document.getElementById('message').value.trim();

        if (!name || !email || !message) {
            alert('Please fill in all the fields.');
            event.preventDefault(); // Prevents form from submitting
        } else if (!validateEmail(email)) {
            alert('Please enter a valid email.');
            event.preventDefault();
        }

        function validateEmail(email) {
            const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            return re.test(String(email).toLowerCase());
        }
    });
</script>


    <footer>
        <p>© 2024 [Your Name]. All Rights Reserved.</p>
    </footer>

    <script>
        // Scroll animation logic
        const sections = document.querySelectorAll('section');

        function revealSection() {
            const windowHeight = window.innerHeight;
            sections.forEach(section => {
                const sectionTop = section.getBoundingClientRect().top;
                if (sectionTop < windowHeight - 150) {
                    section.classList.add('active');
                }
            });
        }

        window.addEventListener('scroll', revealSection);
        window.addEventListener('load', revealSection);
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Путешествуй с нами</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
/* Общие стили */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
    background-color: #f9f9f9;
    color: #333;
    line-height: 1.6;
}

.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

h1, h2, h3, h4 {
    margin-bottom: 20px;
    font-weight: 700;
}

h1 {
    font-size: 2.5rem;
}

h2 {
    font-size: 2rem;
    text-align: center;
    margin-bottom: 40px;
    position: relative;
}

h2::after {
    content: '';
    position: absolute;
    bottom: -10px;
    left: 50%;
    transform: translateX(-50%);
    width: 80px;
    height: 3px;
    background-color: #4CAF50;
}

p {
    margin-bottom: 15px;
}

a {
    text-decoration: none;
    color: inherit;
}

.btn {
    display: inline-block;
    padding: 12px 30px;
    background-color: #4CAF50;
    color: white;
    border-radius: 30px;
    font-weight: 600;
    transition: all 0.3s ease;
    border: none;
    cursor: pointer;
}

.btn:hover {
    background-color: #45a049;
    transform: translateY(-3px);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.btn-small {
    padding: 8px 20px;
    font-size: 0.9rem;
}

/* Шапка */
header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000;
    background-color: rgba(255, 255, 255, 0.95);
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    transition: all 0.3s ease;
}

nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 0;
}

.logo {
    font-size: 1.5rem;
    font-weight: 700;
    color: #4CAF50;
}

.nav-links {
    display: flex;
    list-style: none;
}

.nav-links li {
    margin-left: 30px;
}

.nav-links a {
    position: relative;
    padding: 5px 0;
    font-weight: 600;
    transition: color 0.3s ease;
}

.nav-links a::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 2px;
    background-color: #4CAF50;
    transition: width 0.3s ease;
}

.nav-links a:hover::after {
    width: 100%;
}

.nav-links a.active {
    color: #4CAF50;
}

.nav-links a.active::after {
    width: 100%;
}

.burger {
    display: none;
    cursor: pointer;
}

.burger div {
    width: 25px;
    height: 3px;
    background-color: #333;
    margin: 5px;
    transition: all 0.3s ease;
}

/* Герой секция */
.hero {
    height: 100vh;
    background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://images.unsplash.com/photo-1499678329028-101435549a4e?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    color: white;
    padding: 0 20px;
}

.hero-content h1 {
    font-size: 3.5rem;
    margin-bottom: 20px;
    text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
}

.hero-content p {
    font-size: 1.5rem;
    margin-bottom: 30px;
    text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.5);
}

.scroll-down {
    position: absolute;
    bottom: 30px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
}

.scroll-down span {
    display: block;
    width: 20px;
    height: 20px;
    border-bottom: 2px solid white;
    border-right: 2px solid white;
    transform: rotate(45deg);
    margin: -10px;
    animation: scroll-down 2s infinite;
}

.scroll-down span:nth-child(2) {
    animation-delay: -0.2s;
}

.scroll-down span:nth-child(3) {
    animation-delay: -0.4s;
}

@keyframes scroll-down {
    0% {
        opacity: 0;
        transform: rotate(45deg) translate(-20px, -20px);
    }
    50% {
        opacity: 1;
    }
    100% {
        opacity: 0;
        transform: rotate(45deg) translate(20px, 20px);
    }
}

/* О нас */
.about-section {
    padding: 100px 0;
    background-color: white;
}

.about-content {
    display: flex;
    align-items: center;
    gap: 50px;
}

.about-text {
    flex: 1;
}

.about-image {
    flex: 1;
    text-align: center;
}

.about-image img {
    max-width: 100%;
    border-radius: 10px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

/* Направления */
.destinations-section {
    padding: 100px 0;
    background-color: #f5f5f5;
}

.destinations-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 30px;
}

.destination-card {
    background-color: white;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.destination-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
}

.card-image {
    position: relative;
    height: 250px;
    overflow: hidden;
}

.card-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.5s ease;
}

.destination-card:hover .card-image img {
    transform: scale(1.1);
}

.card-overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    padding: 20px;
    background: linear-gradient(to top, rgba(0, 0, 0, 0.8), transparent);
    color: white;
}

.card-overlay h3 {
    margin-bottom: 5px;
}

.card-content {
    padding: 20px;
}

/* Уникальные места */
.unique-section {
    padding: 100px 0;
    background-color: white;
}

.unique-places {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 30px;
}

.unique-card {
    text-align: center;
    padding: 40px 30px;
    background-color: #f9f9f9;
    border-radius: 10px;
    transition: all 0.3s ease;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
}

.unique-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
}

.unique-icon {
    width: 80px;
    height: 80px;
    margin: 0 auto 20px;
    background-color: #4CAF50;
    color: white;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 30px;
}

/* Контакты */
.contact-section {
    padding: 100px 0;
    background-color: #f5f5f5;
}

.contact-form {
    max-width: 600px;
    margin: 0 auto;
    background-color: white;
    padding: 40px;
    border-radius: 10px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.form-group {
    margin-bottom: 20px;
}

.form-group input,
.form-group textarea {
    width: 100%;
    padding: 12px 15px;
    border: 1px solid #ddd;
    border-radius: 5px;
    font-size: 1rem;
    transition: border-color 0.3s ease;
}

.form-group input:focus,
.form-group textarea:focus {
    outline: none;
    border-color: #4CAF50;
}

.form-group textarea {
    min-height: 150px;
    resize: vertical;
}

/* Подвал */
footer {
    background-color: #333;
    color: white;
    padding: 60px 0 0;
}

.footer-content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 40px;
    margin-bottom: 40px;
}

.footer-section h3 {
    margin-bottom: 20px;
    position: relative;
    padding-bottom: 10px;
}

.footer-section h3::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 50px;
    height: 2px;
    background-color: #4CAF50;
}

.footer-section ul {
    list-style: none;
}

.footer-section ul li {
    margin-bottom: 10px;
}

.footer-section ul li a {
    transition: color 0.3s ease;
}

.footer-section ul li a:hover {
    color: #4CAF50;
}

.social-icons {
    display: flex;
    gap: 15px;
}

.social-icons a {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 40px;
    height: 40px;
    background-color: rgba(255, 255, 255, 0.1);
    border-radius: 50%;
    transition: all 0.3s ease;
}

.social-icons a:hover {
    background-color: #4CAF50;
    transform: translateY(-3px);
}

.footer-bottom {
    text-align: center;
    padding: 20px 0;
    background-color: #222;
    font-size: 0.9rem;
}

/* Анимации */
.animate-pop-in {
    animation: pop-in 0.6s cubic-bezier(0, 0.9, 0.3, 1.2) forwards;
    opacity: 0;
}

.hero-content h1 {
    animation-delay: 0.2s;
}

.hero-content p {
    animation-delay: 0.4s;
}

.hero-content .btn {
    animation-delay: 0.6s;
}

@keyframes pop-in {
    0% {
        opacity: 0;
        transform: translateY(-20px) scale(0.9);
    }
    100% {
        opacity: 1;
        transform: none;
    }
}

.floating {
    animation: floating 3s ease-in-out infinite;
}

@keyframes floating {
    0% {
        transform: translateY(0px);
    }
    50% {
        transform: translateY(-15px);
    }
    100% {
        transform: translateY(0px);
    }
}

/* Адаптивность */
@media (max-width: 768px) {
    .nav-links {
        position: fixed;
        top: 80px;
        left: 0;
        width: 100%;
        background-color: white;
        flex-direction: column;
        align-items: center;
        padding: 20px 0;
        clip-path: circle(0px at 90% -10%);
        transition: all 0.5s ease-out;
        pointer-events: none;
    }

    .nav-links.active {
        clip-path: circle(1000px at 90% -10%);
        pointer-events: all;
    }

    .nav-links li {
        margin: 15px 0;
    }

    .burger {
        display: block;
    }

    .burger.active .line1 {
        transform: rotate(-45deg) translate(-5px, 6px);
    }

    .burger.active .line2 {
        opacity: 0;
    }

    .burger.active .line3 {
        transform: rotate(45deg) translate(-5px, -6px);
    }

    .hero-content h1 {
        font-size: 2.5rem;
    }

    .hero-content p {
        font-size: 1.2rem;
    }

    .about-content {
        flex-direction: column;
    }
}

@media (max-width: 480px) {
    .hero-content h1 {
        font-size: 2rem;
    }

    .hero-content p {
        font-size: 1rem;
    }

    .btn {
        padding: 10px 20px;
    }
}
    </style>
</head>
<body>
    <header>
        <nav>
            <div class="logo">🌍 Путешествуй с нами</div>
            <ul class="nav-links">
                <li><a href="#home" class="active">Главная</a></li>
                <li><a href="#destinations">Куда поехать</a></li>
                <li><a href="#unique">Уникальные места</a></li>
                <li><a href="#contact">Контакты</a></li>
            </ul>
            <div class="burger">
                <div class="line1"></div>
                <div class="line2"></div>
                <div class="line3"></div>
            </div>
        </nav>
    </header>

    <main>
        <section id="home" class="hero">
            <div class="hero-content">
                <h1 class="animate-pop-in">Открой для себя мир</h1>
                <p class="animate-pop-in">Находи лучшие направления для своих следующих каникул</p>
                <a href="#destinations" class="btn animate-pop-in">Начать путешествие</a>
            </div>
            <div class="scroll-down">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </section>

        <section id="about" class="about-section">
            <div class="container">
                <h2>О нашем сайте</h2>
                <div class="about-content">
                    <div class="about-text">
                        <p>Мы создали этот сайт для тех, кто любит путешествия и хочет открывать для себя новые места. Наша цель - вдохновлять вас на новые приключения и помогать планировать идеальные каникулы.</p>
                        <p>Здесь вы найдете подборки самых интересных направлений, уникальных мест, которые стоит посетить, и полезные советы для путешественников.</p>
                    </div>
                    <div class="about-image">
                        <img src="https://images.unsplash.com/photo-1506929562872-bb421503ef21?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Путешествия" class="floating">
                    </div>
                </div>
            </div>
        </section>

        <section id="destinations" class="destinations-section">
            <div class="container">
                <h2>Куда поехать на каникулы</h2>
                <div class="destinations-grid">
                    <div class="destination-card">
                        <div class="card-image">
                            <img src="https://images.unsplash.com/photo-1503917988258-f87a78e3c995?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Париж">
                            <div class="card-overlay">
                                <h3>Париж</h3>
                                <p>Город любви и искусства</p>
                            </div>
                        </div>
                        <div class="card-content">
                            <p>Посетите Эйфелеву башню, Лувр и прогуляйтесь по набережной Сены.</p>
                            <a href="#" class="btn-small">Подробнее</a>
                        </div>
                    </div>

                    <div class="destination-card">
                        <div class="card-image">
                            <img src="https://images.unsplash.com/photo-1523482580672-f109ba8cb9be?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Токио">
                            <div class="card-overlay">
                                <h3>Токио</h3>
                                <p>Где традиции встречают будущее</p>
                            </div>
                        </div>
                        <div class="card-content">
                            <p>Попробуйте суши, посетите храмы и погрузитесь в неоновые улицы.</p>
                            <a href="#" class="btn-small">Подробнее</a>
                        </div>
                    </div>

                    <div class="destination-card">
                        <div class="card-image">
                            <img src="https://images.unsplash.com/photo-1518391846015-55a9cc003b25?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Нью-Йорк">
                            <div class="card-overlay">
                                <h3>Нью-Йорк</h3>
                                <p>Город, который никогда не спит</p>
                            </div>
                        </div>
                        <div class="card-content">
                            <p>Таймс-сквер, Центральный парк и Статуя Свободы ждут вас.</p>
                            <a href="#" class="btn-small">Подробнее</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="unique" class="unique-section">
            <div class="container">
                <h2>Уникальные места</h2>
                <div class="unique-places">
                    <div class="unique-card">
                        <div class="unique-icon">
                            <i class="fas fa-tree"></i>
                        </div>
                        <h3>Бамбуковый лес, Япония</h3>
                        <p>Арасияма - волшебный бамбуковый лес, где стебли шелестят на ветру, создавая умиротворяющую атмосферу.</p>
                    </div>

                    <div class="unique-card">
                        <div class="unique-icon">
                            <i class="fas fa-umbrella-beach"></i>
                        </div>
                        <h3>Пляжи с биолюминесценцией, Мальдивы</h3>
                        <p>Ночью вода светится голубым светом благодаря микроорганизмам - незабываемое зрелище!</p>
                    </div>

                    <div class="unique-card">
                        <div class="unique-icon">
                            <i class="fas fa-mountain"></i>
                        </div>
                        <h3>Заколдованный колодец, Бразилия</h3>
                        <p>Когда солнце в зените, его лучи проникают через расщелину и освещают воду, создавая волшебный эффект.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact" class="contact-section">
            <div class="container">
                <h2>Свяжитесь с нами</h2>
                <form class="contact-form">
                    <div class="form-group">
                        <input type="text" placeholder="Ваше имя" required>
                    </div>
                    <div class="form-group">
                        <input type="email" placeholder="Ваш email" required>
                    </div>
                    <div class="form-group">
                        <textarea placeholder="Ваше сообщение" required></textarea>
                    </div>
                    <button type="submit" class="btn">Отправить</button>
                </form>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>О нас</h3>
                    <p>Мы помогаем людям открывать для себя новые места и планировать идеальные путешествия.</p>
                </div>
                <div class="footer-section">
                    <h3>Быстрое меню</h3>
                    <ul>
                        <li><a href="#home">Главная</a></li>
                        <li><a href="#destinations">Куда поехать</a></li>
                        <li><a href="#unique">Уникальные места</a></li>
                        <li><a href="#contact">Контакты</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Социальные сети</h3>
                    <div class="social-icons">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2023 Путешествуй с нами. Все права защищены.
                Выполнила Кожина Яна
            </p>
        </div>
    </footer>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
    // Мобильное меню
    const burger = document.querySelector('.burger');
    const navLinks = document.querySelector('.nav-links');
    const navItems = document.querySelectorAll('.nav-links li');

    burger.addEventListener('click', () => {
        navLinks.classList.toggle('active');
        burger.classList.toggle('active');
    });

    navItems.forEach(item => {
        item.addEventListener('click', () => {
            navLinks.classList.remove('active');
            burger.classList.remove('active');
        });
    });

    // Плавная прокрутка
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
            e.preventDefault();
            
            const targetId = this.getAttribute('href');
            const targetElement = document.querySelector(targetId);
            
            window.scrollTo({
                top: targetElement.offsetTop - 80,
                behavior: 'smooth'
            });
        });
    });

    // Изменение шапки при скролле
    window.addEventListener('scroll', function() {
        const header = document.querySelector('header');
        if (window.scrollY > 100) {
            header.style.background = 'rgba(255, 255, 255, 0.98)';
            header.style.boxShadow = '0 2px 10px rgba(0, 0, 0, 0.1)';
        } else {
            header.style.background = 'rgba(255, 255, 255, 0.95)';
            header.style.boxShadow = '0 2px 10px rgba(0, 0, 0, 0.1)';
        }
    });

    // Анимация при скролле
    const animateOnScroll = function() {
        const elements = document.querySelectorAll('.unique-card, .destination-card, .about-image, .about-text');
        
        elements.forEach(element => {
            const elementPosition = element.getBoundingClientRect().top;
            const screenPosition = window.innerHeight / 1.3;
            
            if (elementPosition < screenPosition) {
                element.style.opacity = '1';
                element.style.transform = 'translateY(0)';
            }
        });
    };

    // Установка начального состояния для анимации
    document.querySelectorAll('.unique-card, .destination-card').forEach(card => {
        card.style.opacity = '0';
        card.style.transform = 'translateY(20px)';
        card.style.transition = 'all 0.6s ease';
    });

    document.querySelector('.about-image').style.opacity = '0';
    document.querySelector('.about-image').style.transform = 'translateX(-20px)';
    document.querySelector('.about-image').style.transition = 'all 0.6s ease 0.2s';

    document.querySelector('.about-text').style.opacity = '0';
    document.querySelector('.about-text').style.transform = 'translateX(20px)';
    document.querySelector('.about-text').style.transition = 'all 0.6s ease 0.2s';

    window.addEventListener('scroll', animateOnScroll);
    animateOnScroll(); // Запустить при загрузке на случай, если элементы уже видны
});
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Омск - Любовь Моя | Город моей души</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #1a9df0;
            --primary-light: #4fb8ff;
            --primary-dark: #0d7bc0;
            --accent: #ffc107;
            --light: #f0f9ff;
            --white: #ffffff;
            --text: #2d3748;
            --text-light: #718096;
            --shadow: 0 4px 20px rgba(26, 157, 240, 0.15);
        }
        
        body {
            background-color: var(--light);
            color: var(--text);
            line-height: 1.6;
        }
        
        header {
            background: linear-gradient(to right, var(--primary), var(--primary-light));
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: var(--shadow);
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo-icon {
            width: 50px;
            height: 50px;
            background-color: var(--white);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: bold;
            color: var(--primary);
            font-size: 1.2rem;
            box-shadow: var(--shadow);
        }
        
        .logo-text {
            color: var(--white);
            font-size: 1.5rem;
            font-weight: 700;
            letter-spacing: 1px;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }
        
        nav a {
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            position: relative;
            padding-bottom: 5px;
        }
        
        nav a:after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: 0;
            left: 0;
            background-color: var(--white);
            transition: width 0.3s ease;
        }
        
        nav a:hover:after, nav a.active:after {
            width: 100%;
        }
        
        .hero {
            height: 80vh;
            background: linear-gradient(rgba(26, 157, 240, 0.3), rgba(13, 123, 192, 0.7)), 
                         url('https://images.unsplash.com/photo-1596553071806-1c3dde1d0a0f?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80') no-repeat center center/cover;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            color: var(--white);
        }
        
        .hero-content {
            max-width: 800px;
            padding: 0 1rem;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            animation: fadeInDown 1s ease;
        }
        
        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2.5rem;
            animation: fadeInUp 1s ease;
        }
        
        .btn {
            display: inline-block;
            background: var(--white);
            color: var(--primary);
            padding: 0.8rem 2.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            box-shadow: var(--shadow);
            animation: fadeIn 1.5s ease;
        }
        
        .btn:hover {
            background: transparent;
            color: var(--white);
            border-color: var(--white);
            transform: translateY(-5px);
        }
        
        .btn-primary {
            background: var(--primary);
            color: var(--white);
        }
        
        .btn-primary:hover {
            background: var(--primary-dark);
            border-color: var(--primary);
        }
        
        section {
            padding: 5rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3.5rem;
            color: var(--primary-dark);
            position: relative;
        }
        
        .section-title:after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--accent);
            border-radius: 2px;
        }
        
        .intro-text {
            max-width: 800px;
            margin: 0 auto 3rem;
            text-align: center;
            font-size: 1.1rem;
            line-height: 1.8;
        }
        
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2.5rem;
            margin-top: 2rem;
        }
        
        .feature-card {
            background: var(--white);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: transform 0.3s ease;
            height: 100%;
            display: flex;
            flex-direction: column;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
        }
        
        .card-img {
            height: 250px;
            overflow: hidden;
        }
        
        .card-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .feature-card:hover .card-img img {
            transform: scale(1.1);
        }
        
        .card-content {
            padding: 1.8rem;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }
        
        .card-content h3 {
            color: var(--primary-dark);
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }
        
        .card-content p {
            color: var(--text-light);
            margin-bottom: 1.5rem;
            flex-grow: 1;
        }
        
        .attractions {
            background: var(--white);
        }
        
        .quote {
            max-width: 800px;
            margin: 4rem auto;
            padding: 2.5rem;
            background: rgba(26, 157, 240, 0.1);
            border-radius: 15px;
            border-left: 4px solid var(--primary);
            text-align: center;
            font-style: italic;
            font-size: 1.2rem;
            color: var(--text);
            position: relative;
        }
        
        .quote:before {
            content: '\201C';
            font-size: 5rem;
            position: absolute;
            left: 20px;
            top: -20px;
            color: var(--primary);
            opacity: 0.2;
            font-family: serif;
        }
        
        .gallery-section {
            background: linear-gradient(rgba(240, 249, 255, 0.9), rgba(240, 249, 255, 0.9));
        }
        
        .gallery-filters {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .filter-btn {
            padding: 0.5rem 1.5rem;
            background: var(--white);
            color: var(--primary);
            border: 2px solid var(--primary-light);
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .filter-btn:hover, .filter-btn.active {
            background: var(--primary);
            color: var(--white);
            border-color: var(--primary);
        }
        
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
            margin-top: 3rem;
        }
        
        .gallery-item {
            border-radius: 15px;
            overflow: hidden;
            height: 300px;
            box-shadow: var(--shadow);
            position: relative;
            transition: transform 0.3s ease;
        }
        
        .gallery-item:hover {
            transform: scale(1.03);
        }
        
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .gallery-item:hover img {
            transform: scale(1.1);
        }
        
        .gallery-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(26, 157, 240, 0.85);
            color: var(--white);
            padding: 1rem;
            transform: translateY(100%);
            transition: transform 0.3s ease;
        }
        
        .gallery-item:hover .gallery-caption {
            transform: translateY(0);
        }
        
        .cta {
            background: linear-gradient(to right, var(--primary), var(--primary-light));
            color: var(--white);
            text-align: center;
            padding: 5rem 0;
        }
        
        .cta h2 {
            margin-bottom: 1.5rem;
            font-size: 2.5rem;
        }
        
        .cta p {
            max-width: 700px;
            margin: 0 auto 2.5rem;
            font-size: 1.2rem;
        }
        
        footer {
            background: var(--primary-dark);
            color: var(--white);
            padding: 3rem 0 0;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            margin-bottom: 3rem;
        }
        
        .footer-section h3 {
            color: var(--accent);
            margin-bottom: 1.5rem;
            font-size: 1.3rem;
            position: relative;
            padding-bottom: 0.8rem;
        }
        
        .footer-section h3:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 3px;
            background: var(--accent);
        }
        
        .footer-section p {
            margin-bottom: 1rem;
            line-height: 1.7;
        }
        
        .socials {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }
        
        .socials a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: rgba(255, 255, 255, 0.1);
            color: var(--white);
            border-radius: 50%;
            transition: all 0.3s ease;
        }
        
        .socials a:hover {
            background: var(--accent);
            color: var(--primary-dark);
            transform: translateY(-3px);
        }
        
        .copyright {
            text-align: center;
            padding: 1.5rem 0;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
        }
        
        /* Страницы достопримечательностей */
        .attraction-page {
            padding: 6rem 0 4rem;
        }
        
        .page-header {
            margin-bottom: 3rem;
            text-align: center;
        }
        
        .breadcrumb {
            display: flex;
            justify-content: center;
            margin-bottom: 1rem;
            font-size: 0.9rem;
            color: var(--text-light);
        }
        
        .breadcrumb a {
            color: var(--primary);
            text-decoration: none;
        }
        
        .breadcrumb span {
            margin: 0 0.5rem;
        }
        
        .page-content {
            display: grid;
            grid-template-columns: 1fr 350px;
            gap: 3rem;
            margin-top: 2rem;
        }
        
        .attraction-details {
            background: var(--white);
            padding: 2rem;
            border-radius: 15px;
            box-shadow: var(--shadow);
        }
        
        .attraction-details h3 {
            color: var(--primary-dark);
            margin: 2rem 0 1rem;
            font-size: 1.4rem;
        }
        
        .attraction-details p {
            margin-bottom: 1.2rem;
            line-height: 1.8;
        }
        
        .attraction-details ul {
            margin: 1.5rem 0;
            padding-left: 1.5rem;
        }
        
        .attraction-details li {
            margin-bottom: 0.8rem;
            position: relative;
        }
        
        .attraction-details li:before {
            content: '•';
            color: var(--primary);
            position: absolute;
            left: -1rem;
        }
        
        .sidebar {
            background: var(--white);
            border-radius: 15px;
            padding: 2rem;
            box-shadow: var(--shadow);
            align-self: start;
        }
        
        .info-box {
            margin-bottom: 2rem;
        }
        
        .info-box h4 {
            color: var(--primary-dark);
            margin-bottom: 1rem;
            font-size: 1.2rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        
        .info-box p {
            margin-bottom: 0.5rem;
            display: flex;
            align-items: flex-start;
            gap: 0.7rem;
        }
        
        .info-box i {
            color: var(--primary);
            min-width: 20px;
        }
        
        .map-container {
            height: 300px;
            border-radius: 10px;
            overflow: hidden;
            margin-top: 1rem;
            background: #e6f7ff;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-weight: bold;
            border: 1px solid var(--primary-light);
        }
        
        .back-button {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            margin-top: 2rem;
            color: var(--primary);
            text-decoration: none;
            font-weight: 600;
            padding: 0.8rem 1.5rem;
            background: var(--light);
            border-radius: 50px;
            border: 1px solid var(--primary-light);
            transition: all 0.3s ease;
        }
        
        .back-button:hover {
            background: var(--primary);
            color: var(--white);
            text-decoration: none;
        }
        
        .gallery-mini {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1rem;
            margin: 1.5rem 0;
        }
        
        .gallery-mini img {
            width: 100%;
            height: 120px;
            object-fit: cover;
            border-radius: 10px;
        }
        
        @media (max-width: 992px) {
            .page-content {
                grid-template-columns: 1fr;
            }
            
            .hero h1 {
                font-size: 2.8rem;
            }
        }
        
        @media (max-width: 768px) {
            nav ul {
                gap: 1.2rem;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .header-content {
                flex-direction: column;
                text-align: center;
                gap: 1.5rem;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1.2rem;
            }
            
            .gallery-mini {
                grid-template-columns: 1fr;
            }
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>
    <!-- Главная страница -->
    <div id="home-page">
        <header>
            <div class="container">
                <div class="header-content">
                    <div class="logo">
                        <div class="logo-icon">ОМ</div>
                        <div class="logo-text">Омск - Любовь Моя</div>
                    </div>
                    <nav>
                        <ul>
                            <li><a href="#" class="active">Главная</a></li>
                            <li><a href="#about">О городе</a></li>
                            <li><a href="#attractions">Достопримечательности</a></li>
                            <li><a href="#gallery">Галерея</a></li>
                            <li><a href="#contact">Контакты</a></li>
                        </ul>
                    </nav>
                </div>
            </div>
        </header>
        
        <section class="hero">
            <div class="hero-content">
                <h1>Омск - Город Моей Души</h1>
                <p>Город, где история переплетается с современностью, а сибирское гостеприимство встречает каждого</p>
                <a href="#about" class="btn">Узнать больше</a>
            </div>
        </section>
        
        <section id="about">
            <div class="container">
                <h2 class="section-title">Омск - Город на Иртыше</h2>
                <div class="intro-text">
                    <p>Омск - один из крупнейших городов Сибири, расположенный на слиянии рек Иртыш и Омь. Основанный в 1716 году как крепость, Омск превратился в важный промышленный, культурный и образовательный центр. Город известен своей богатой историей, архитектурными памятниками и гостеприимными жителями.</p>
                    <p>Омск неоднократно становился центром исторических событий: здесь была столица Белого движения во главе с адмиралом Колчаком, а также важный тыловой город во время Великой Отечественной войны. Сегодня Омск сочетает в себе историческое наследие и современные достижения.</p>
                </div>
                
                <div class="features">
                    <div class="feature-card">
                        <div class="card-img">
                            <img src="https://images.unsplash.com/photo-1541367777708-7905fe3296c0?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="История">
                        </div>
                        <div class="card-content">
                            <h3>Богатая История</h3>
                            <p>Омск был основан как крепость для защиты южных рубежей Российской империи. Город пережил множество исторических событий: от основания до столицы Белой России и важного промышленного центра Сибири.</p>
                        </div>
                    </div>
                    
                    <div class="feature-card">
                        <div class="card-img">
                            <img src="https://images.unsplash.com/photo-1601924638867-1a6b8b78e1e9?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Архитектура">
                        </div>
                        <div class="card-content">
                            <h3>Уникальная Архитектура</h3>
                            <p>Омск славится разнообразием архитектурных стилей: от деревянного зодчества и сибирского барокко до конструктивизма и современных построек. Исторический центр города сохранил дух старого Омска.</p>
                        </div>
                    </div>
                    
                    <div class="feature-card">
                        <div class="card-img">
                            <img src="https://images.unsplash.com/photo-1573152958734-1922c188fba3?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Культура">
                        </div>
                        <div class="card-content">
                            <h3>Культурная Жизнь</h3>
                            <p>Омск - культурная столица Сибири с богатыми театральными традициями. Здесь работают драматический театр, музыкальный театр, театр кукол, а также множество музеев, галерей и выставочных залов.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <section id="attractions" class="attractions">
            <div class="container">
                <h2 class="section-title">Жемчужины Омска</h2>
                <p class="intro-text">Откройте для себя главные достопримечательности Омска, каждая из которых имеет свою уникальную историю и неповторимый облик.</p>
                
                <div class="features">
                    <div class="feature-card">
                        <div class="card-img">
                            <img src="https://images.unsplash.com/photo-1592486058513-9d48b6647a1d?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Успенский собор">
                        </div>
                        <div class="card-content">
                            <h3>Успенский кафедральный собор</h3>
                            <p>Величественный храм в центре Омска, воссозданный в 2007 году на месте разрушенного в советское время собора. Архитектурный шедевр в неовизантийском стиле, один из символов духовного возрождения России.</p>
                            <a href="#" class="btn btn-primary" data-page="uspensky">Подробнее</a>
                        </div>
                    </div>
                    
                    <div class="feature-card">
                        <div class="card-img">
                            <img src="https://images.unsplash.com/photo-1592486058513-9d48b6647a1d?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Театр драмы">
                        </div>
                        <div class="card-content">
                            <h3>Омский академический театр драмы</h3>
                            <p>Один из старейших театров Сибири, основанный в 1874 году. Здание театра - архитектурный памятник федерального значения в стиле сибирского барокко с элементами классицизма.</p>
                            <a href="#" class="btn btn-primary" data-page="drama-theater">Подробнее</a>
                        </div>
                    </div>
                    
                    <div class="feature-card">
                        <div class="card-img">
                            <img src="https://images.unsplash.com/photo-1592486058513-9d48b6647a1d?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Любинский проспект">
                        </div>
                        <div class="card-content">
                            <h3>Любинский проспект</h3>
                            <p>Пешеходная улица в историческом центре Омска - любимое место прогулок горожан и гостей города. Здесь сохранились здания XIX века, установлены памятники и скульптуры, работают кафе и магазины.</p>
                            <a href="#" class="btn btn-primary" data-page="lubinsky">Подробнее</a>
                        </div>
                    </div>
                    
                    <div class="feature-card">
                        <div class="card-img">
                            <img src="https://images.unsplash.com/photo-1592486058513-9d48b6647a1d?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Омская крепость">
                        </div>
                        <div class="card-content">
                            <h3>Омская крепость</h3>
                            <p>Историко-культурный комплекс на месте основания Омска в 1716 году. Сохранились здания XVIII-XIX веков: Тобольские ворота, гауптвахта, комендантский дом, где бывал Ф.М. Достоевский.</p>
                            <a href="#" class="btn btn-primary" data-page="fortress">Подробнее</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <section>
            <div class="container">
                <div class="quote">
                    "Омск - это не просто город на карте. Это состояние души, это особая сибирская стать, это перекресток судеб и эпох. Любить Омск - значит понимать Россию."
                </div>
            </div>
        </section>
        
        <section id="gallery" class="gallery-section">
            <div class="container">
                <h2 class="section-title">Фотогалерея Омска</h2>
                <p class="intro-text">Откройте для себя многогранную красоту Омска через объективы фотографов.</p>
                
                <div class="gallery-filters">
                    <button class="filter-btn active" data-filter="all">Все</button>
                    <button class="filter-btn" data-filter="architecture">Архитектура</button>
                    <button class="filter-btn" data-filter="nature">Природа</button>
                    <button class="filter-btn" data-filter="culture">Культура</button>
                    <button class="filter-btn" data-filter="history">История</button>
                    <button class="filter-btn" data-filter="modern">Современный Омск</button>
                </div>
                
                <div class="gallery">
                    <div class="gallery-item" data-category="architecture">
                        <img src="https://images.unsplash.com/photo-1541367777708-7905fe3296c0?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Архитектура Омска">
                        <div class="gallery-caption">Здание Омского драматического театра</div>
                    </div>
                    <div class="gallery-item" data-category="nature">
                        <img src="https://images.unsplash.com/photo-1519608487953-e999c86e7455?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Природа Омска">
                        <div class="gallery-caption">Парк Победы весной</div>
                    </div>
                    <div class="gallery-item" data-category="culture">
                        <img src="https://images.unsplash.com/photo-1504829857797-ddff29c27927?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Культура Омска">
                        <div class="gallery-caption">Выступление в Омской филармонии</div>
                    </div>
                    <div class="gallery-item" data-category="history">
                        <img src="https://images.unsplash.com/photo-1483664852095-d6cc6870702d?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Исторический Омск">
                        <div class="gallery-caption">Омская крепость</div>
                    </div>
                    <div class="gallery-item" data-category="modern">
                        <img src="https://images.unsplash.com/photo-1573152958734-1922c188fba3?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Современный Омск">
                        <div class="gallery-caption">Новый бизнес-центр</div>
                    </div>
                    <div class="gallery-item" data-category="architecture">
                        <img src="https://images.unsplash.com/photo-1601924638867-1a6b8b78e1e9?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Архитектура">
                        <div class="gallery-caption">Железнодорожный вокзал Омск-Пассажирский</div>
                    </div>
                    <div class="gallery-item" data-category="nature">
                        <img src="https://images.unsplash.com/photo-1596553071806-1c3dde1d0a0f?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Природа">
                        <div class="gallery-caption">Иртышская набережная</div>
                    </div>
                    <div class="gallery-item" data-category="culture">
                        <img src="https://images.unsplash.com/photo-1531058020387-3be344556be6?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Культура">
                        <div class="gallery-caption">Омский музей изобразительных искусств</div>
                    </div>
                    <div class="gallery-item" data-category="history">
                        <img src="https://images.unsplash.com/photo-1518998053901-5348d3961a04?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="История">
                        <div class="gallery-caption">Памятник Дмитрию Карбышеву</div>
                    </div>
                    <div class="gallery-item" data-category="modern">
                        <img src="https://images.unsplash.com/photo-1542744094-3a31f272c490?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Современный">
                        <div class="gallery-caption">Омский метромост</div>
                    </div>
                    <div class="gallery-item" data-category="architecture">
                        <img src="https://images.unsplash.com/photo-1479839672679-a46483c0e7c8?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Архитектура">
                        <div class="gallery-caption">Особняк купца Батюшкова</div>
                    </div>
                    <div class="gallery-item" data-category="nature">
                        <img src="https://images.unsplash.com/photo-1470770903675-0476a1e2d9d9?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Природа">
                        <div class="gallery-caption">Птичья гавань - природный парк в центре города</div>
                    </div>
                    <div class="gallery-item" data-category="culture">
                        <img src="https://images.unsplash.com/photo-1551632811-561732d1e306?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Культура">
                        <div class="gallery-caption">Омский государственный цирк</div>
                    </div>
                    <div class="gallery-item" data-category="history">
                        <img src="https://images.unsplash.com/photo-1505765050516-f72dcac9c60e?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="История">
                        <div class="gallery-caption">Музей воинской славы омичей</div>
                    </div>
                    <div class="gallery-item" data-category="modern">
                        <img src="https://images.unsplash.com/photo-1467232004584-a241de8bcf5d?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Современный">
                        <div class="gallery-caption">Омский Ледовый дворец спорта</div>
                    </div>
                    <div class="gallery-item" data-category="nature">
                        <img src="https://images.unsplash.com/photo-1511497584788-876760111969?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Природа">
                        <div class="gallery-caption">Зимний лес в пригороде Омска</div>
                    </div>
                </div>
            </div>
        </section>
        
        <section class="cta">
            <div class="container">
                <h2>Омск Ждет Вас!</h2>
                <p>Приезжайте и почувствуйте тепло сибирского гостеприимства</p>
                <a href="#contact" class="btn">Связаться с нами</a>
            </div>
        </section>
        
        <footer id="contact">
            <div class="container">
                <div class="footer-content">
                    <div class="footer-section">
                        <h3>О проекте</h3>
                        <p>Сайт создан с любовью к Омску его жителями. Наша цель - показать красоту и уникальность нашего города, рассказать о его богатой истории и культуре.</p>
                        <p>Мы верим, что Омск заслуживает особого места в сердцах всех, кто хоть раз побывал в этом удивительном сибирском городе.</p>
                    </div>
                    
                    <div class="footer-section">
                        <h3>Контакты</h3>
                        <p><i class="fas fa-map-marker-alt"></i> г. Омск, ул. Ленина, 1</p>
                        <p><i class="fas fa-phone"></i> +7 (3812) 123-456</p>
                        <p><i class="fas fa-envelope"></i> love-omsk@example.com</p>
                        
                        <div class="socials">
                            <a href="#"><i class="fab fa-vk"></i></a>
                            <a href="#"><i class="fab fa-telegram"></i></a>
                            <a href="#"><i class="fab fa-youtube"></i></a>
                            <a href="#"><i class="fab fa-instagram"></i></a>
                        </div>
                    </div>
                    
                    <div class="footer-section">
                        <h3>Полезные ссылки</h3>
                        <p><a href="#" style="color: #fff; text-decoration: none;">Официальный портал Омска</a></p>
                        <p><a href="#" style="color: #fff; text-decoration: none;">Культурная афиша Омска</a></p>
                        <p><a href="#" style="color: #fff; text-decoration: none;">Туристические маршруты</a></p>
                        <p><a href="#" style="color: #fff; text-decoration: none;">История Омска</a></p>
                    </div>
                </div>
                
                <div class="copyright">
                    <p>&copy; 2023 "Омск - Любовь Моя". Все права защищены. С любовью к родному городу.</p>
                </div>
            </div>
        </footer>
    </div>
    
    <!-- Страницы достопримечательностей -->
    <div id="uspensky" class="attraction-page" style="display: none;">
        <header>
            <div class="container">
                <div class="header-content">
                    <div class="logo">
                        <div class="logo-icon">ОМ</div>
                        <div class="logo-text">Омск - Любовь Моя</div>
                    </div>
                    <nav>
                        <ul>
                            <li><a href="#" class="back-to-home">Главная</a></li>
                            <li><a href="#about">О городе</a></li>
                            <li><a href="#attractions">Достопримечательности</a></li>
                            <li><a href="#gallery">Галерея</a></li>
                            <li><a href="#contact">Контакты</a></li>
                        </ul>
                    </nav>
                </div>
            </div>
        </header>
        
        <section class="attraction-page">
            <div class="container">
                <div class="breadcrumb">
                    <a href="#" class="back-to-home">Главная</a>
                    <span>/</span>
                    <a href="#attractions">Достопримечательности</a>
                    <span>/</span>
                    <span>Успенский собор</span>
                </div>
                
                <div class="page-header">
                    <h2 class="section-title">Успенский кафедральный собор</h2>
                </div>
                
                <div class="page-content">
                    <div class="attraction-details">
                        <div class="card-img">
                            <img src="https://images.unsplash.com/photo-1592486058513-9d48b6647a1d?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Успенский собор">
                        </div>
                        
                        <p>Успенский кафедральный собор — один из главных символов Омска, воссозданный в 2007 году на месте разрушенного в 1935 году храма. Современное здание является точной копией исторического собора, построенного в 1898 году по проекту архитектора Эрнеста Вирриха.</p>
                        
                        <h3>История собора</h3>
                        <p>Первый Успенский собор был заложен в 1891 году в честь спасения цесаревича Николая (будущего императора Николая II) во время покушения в Японии. Строительство велось на пожертвования горожан и завершилось в 1898 году. Храм освятили в честь Успения Пресвятой Богородицы.</p>
                        <p>В 1935 году, в период борьбы с религией, собор был взорван. На его месте разбили сквер, а позднее установили фонтан и скульптуру "Валентинка".</p>
                        <p>Возрождение святыни началось в 2005 году по инициативе губернатора Омской области Леонида Полежаева. Восстановление велось по сохранившимся чертежам и фотографиям. 15 июля 2007 года состоялось великое освящение воссозданного собора.</p>
                        
                        <div class="gallery-mini">
                            <img src="https://images.unsplash.com/photo-1592486058513-9d48b6647a1d?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Интерьер собора">
                            <img src="https://images.unsplash.com/photo-1541367777708-7905fe3296c0?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Вид с высоты">
                        </div>
                        
                        <h3>Архитектурные особенности</h3>
                        <p>Успенский собор построен в русско-византийском стиле, характерном для храмового зодчества конца XIX века:</p>
                        <ul>
                            <li>Высота собора с крестом - 47 метров</li>
                            <li>Пятиглавое завершение с центральным золотым куполом</li>
                            <li>Кирпичная кладка с декоративными элементами из белого камня</li>
                            <li>Шатровая колокольня с часами</li>
                            <li>Вместимость - до 3000 человек</li>
                        </ul>
                        
                        <h3>Современное значение</h3>
                        <p>Сегодня Успенский собор является кафедральным храмом Омской митрополии Русской Православной Церкви. Здесь хранятся важные святыни:</p>
                        <ul>
                            <li>Мощи священномученика Сильвестра Омского</li>
                            <li>Ковчег с частицами мощей многих святых</li>
                            <li>Икона Божией Матери "Скоропослушница"</li>
                            <li>Копия знамени Омской крепости</li>
                        </ul>
                        <p>Собор стал центром духовной жизни города и важным туристическим объектом. Ежегодно его посещают десятки тысяч паломников и туристов.</p>
                        
                        <a href="#" class="back-button"><i class="fas fa-arrow-left"></i> Вернуться к достопримечательностям</a>
                    </div>
                    
                    <div class="sidebar">
                        <div class="info-box">
                            <h4><i class="fas fa-info-circle"></i> Основная информация</h4>
                            <p><i class="fas fa-map-marker-alt"></i> Адрес: ул. Тарская, 7</p>
                            <p><i class="far fa-clock"></i> Часы работы: ежедневно 8:00-20:00</p>
                            <p><i class="fas fa-church"></i> Статус: Кафедральный собор</p>
                            <p><i class="fas fa-calendar-alt"></i> Год постройки: 1898 (восстановлен в 2007)</p>
                            <p><i class="fas fa-archway"></i> Архитектурный стиль: Русско-византийский</p>
                        </div>
                        
                        <div class="info-box">
                            <h4><i class="fas fa-star"></i> Интересные факты</h4>
                            <p><i class="fas fa-ruble-sign"></i> Строительство в XIX веке обошлось в 125 тысяч рублей</p>
                            <p><i class="fas fa-exclamation-triangle"></i> В 1935 году храм был полностью разрушен</p>
                            <p><i class="fas fa-gem"></i> При восстановлении использовали 13 кг сусального золота</p>
                            <p><i class="fas fa-bell"></i> Главный колокол весит 16 тонн</p>
                        </div>
                        
                        <div class="info-box">
                            <h4><i class="fas fa-map-marked-alt"></i> Расположение</h4>
                            <div class="map-container">
                                Карта: Успенский собор, Омск
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <footer>
            <div class="container">
                <div class="copyright">
                    <p>&copy; 2023 "Омск - Любовь Моя". Все права защищены.</p>
                </div>
            </div>
        </footer>
    </div>
    
    <!-- Страница Омского академического театра драмы -->
    <div id="drama-theater" class="attraction-page" style="display: none;">
        <header>
            <div class="container">
                <div class="header-content">
                    <div class="logo">
                        <div class="logo-icon">ОМ</div>
                        <div class="logo-text">Омск - Любовь Моя</div>
                    </div>
                    <nav>
                        <ul>
                            <li><a href="#" class="back-to-home">Главная</a></li>
                            <li><a href="#about">О городе</a></li>
                            <li><a href="#attractions">Достопримечательности</a></li>
                            <li><a href="#gallery">Галерея</a></li>
                            <li><a href="#contact">Контакты</a></li>
                        </ul>
                    </nav>
                </div>
            </div>
        </header>
        
        <section class="attraction-page">
            <div class="container">
                <div class="breadcrumb">
                    <a href="#" class="back-to-home">Главная</a>
                    <span>/</span>
                    <a href="#attractions">Достопримечательности</a>
                    <span>/</span>
                    <span>Театр драмы</span>
                </div>
                
                <div class="page-header">
                    <h2 class="section-title">Омский академический театр драмы</h2>
                </div>
                
                <div class="page-content">
                    <div class="attraction-details">
                        <div class="card-img">
                            <img src="https://images.unsplash.com/photo-1601924638867-1a6b8b78e1e9?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Театр драмы">
                        </div>
                        
                        <p>Омский академический театр драмы - один из старейших театров Сибири, основанный в 1874 году. Здание театра является архитектурным памятником федерального значения и образцом сибирского барокко с элементами классицизма.</p>
                        
                        <h3>История театра</h3>
                        <p>Первые театральные представления в Омске датируются 1764 годом, но официальной датой основания театра считается 1874 год, когда была создана первая профессиональная труппа. Современное здание театра было построено в 1905 году по проекту архитектора Иллиодора Хворинова.</p>
                        <p>В советское время театр получил звание "академического" - первым из провинциальных театров России. За свою историю театр пережил несколько реконструкций, последняя из которых завершилась в 2015 году.</p>
                        
                        <div class="gallery-mini">
                            <img src="https://images.unsplash.com/photo-1541367777708-7905fe3296c0?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Интерьер театра">
                            <img src="https://images.unsplash.com/photo-1573152958734-1922c188fba3?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Сцена">
                        </div>
                        
                        <h3>Архитектурные особенности</h3>
                        <p>Здание театра - настоящий шедевр архитектуры:</p>
                        <ul>
                            <li>Стиль: сибирское барокко с элементами классицизма</li>
                            <li>Фасад украшен лепниной и скульптурами</li>
                            <li>Зрительный зал на 800 мест с уникальной акустикой</li>
                            <li>Современное техническое оснащение сцены</li>
                            <li>Восстановленные исторические интерьеры</li>
                        </ul>
                        
                        <h3>Театр сегодня</h3>
                        <p>Сегодня Омский академический театр драмы - один из ведущих театров России:</p>
                        <ul>
                            <li>В репертуаре более 30 спектаклей различных жанров</li>
                            <li>Труппа театра включает заслуженных и народных артистов России</li>
                            <li>Ежегодный международный фестиваль "Академия"</li>
                            <li>Экскурсии по историческому зданию театра</li>
                        </ul>
                        <p>Театр активно сотрудничает с известными режиссерами из России и Европы, что делает его репертуар разнообразным и современным.</p>
                        
                        <a href="#" class="back-button"><i class="fas fa-arrow-left"></i> Вернуться к достопримечательностям</a>
                    </div>
                    
                    <div class="sidebar">
                        <div class="info-box">
                            <h4><i class="fas fa-info-circle"></i> Основная информация</h4>
                            <p><i class="fas fa-map-marker-alt"></i> Адрес: ул. Ленина, 8а</p>
                            <p><i class="far fa-clock"></i> Кассы: ежедневно 10:00-19:00</p>
                            <p><i class="fas fa-theater-masks"></i> Статус: Академический театр</p>
                            <p><i class="fas fa-calendar-alt"></i> Год основания: 1874</p>
                            <p><i class="fas fa-archway"></i> Архитектурный стиль: Сибирское барокко</p>
                        </div>
                        
                        <div class="info-box">
                            <h4><i class="fas fa-star"></i> Интересные факты</h4>
                            <p><i class="fas fa-crown"></i> Первый академический театр в провинции</p>
                            <p><i class="fas fa-paint-brush"></i> Уникальный занавес работы Кривцова</p>
                            <p><i class="fas fa-users"></i> Вместимость зрительного зала - 800 человек</p>
                            <p><i class="fas fa-history"></i> Здание - памятник федерального значения</p>
                        </div>
                        
                        <div class="info-box">
                            <h4><i class="fas fa-map-marked-alt"></i> Расположение</h4>
                            <div class="map-container">
                                Карта: Театр драмы, Омск
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <footer>
            <div class="container">
                <div class="copyright">
                    <p>&copy; 2023 "Омск - Любовь Моя". Все права защищены.</p>
                </div>
            </div>
        </footer>
    </div>
    
    <!-- Страница Любинского проспекта -->
    <div id="lubinsky" class="attraction-page" style="display: none;">
        <header>
            <div class="container">
                <div class="header-content">
                    <div class="logo">
                        <div class="logo-icon">ОМ</div>
                        <div class="logo-text">Омск - Любовь Моя</div>
                    </div>
                    <nav>
                        <ul>
                            <li><a href="#" class="back-to-home">Главная</a></li>
                            <li><a href="#about">О городе</a></li>
                            <li><a href="#attractions">Достопримечательности</a></li>
                            <li><a href="#gallery">Галерея</a></li>
                            <li><a href="#contact">Контакты</a></li>
                        </ul>
                    </nav>
                </div>
            </div>
        </header>
        
        <section class="attraction-page">
            <div class="container">
                <div class="breadcrumb">
                    <a href="#" class="back-to-home">Главная</a>
                    <span>/</span>
                    <a href="#attractions">Достопримечательности</a>
                    <span>/</span>
                    <span>Любинский проспект</span>
                </div>
                
                <div class="page-header">
                    <h2 class="section-title">Любинский проспект</h2>
                </div>
                
                <div class="page-content">
                    <div class="attraction-details">
                        <div class="card-img">
                            <img src="https://images.unsplash.com/photo-1519608487953-e999c86e7455?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Любинский проспект">
                        </div>
                        
                        <p>Любинский проспект - пешеходная улица в историческом центре Омска, любимое место прогулок горожан и гостей города. Проспект протянулся на 600 метров от Соборной площади до Театральной площади, сохранив атмосферу старого Омска.</p>
                        
                        <h3>История проспекта</h3>
                        <p>Проспект получил свое название в 1854 году в честь жены генерал-губернатора Западной Сибири Густава Гасфорда - Любови Федоровны. В конце XIX - начале XX века здесь селились самые богатые купцы Омска, строившие особняки в различных архитектурных стилях.</p>
                        <p>В советское время проспект был переименован в улицу Ленина, но в 1994 году ему вернули историческое название. В 2000-х годах проспект был полностью реконструирован и стал пешеходной зоной.</p>
                        
                        <div class="gallery-mini">
                            <img src="https://images.unsplash.com/photo-1483664852095-d6cc6870702d?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Зимний проспект">
                            <img src="https://images.unsplash.com/photo-1504829857797-ddff29c27927?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Летний вечер">
                        </div>
                        
                        <h3>Архитектура проспекта</h3>
                        <p>Любинский проспект - настоящий музей архитектуры под открытым небом:</p>
                        <ul>
                            <li>Особняк купца Батюшкова (эклектика)</li>
                            <li>Здание страхового общества "Саламандра" (модерн)</li>
                            <li>Торговый дом купца Волкова (неоклассицизм)</li>
                            <li>Доходный дом купчихи Шаниной (кирпичный стиль)</li>
                            <li>Гостиница "Россия" (эклектика)</li>
                        </ul>
                        
                        <h3>Что посмотреть</h3>
                        <p>На Любинском проспекте расположено множество интересных объектов:</p>
                        <ul>
                            <li>Памятник Любочке (жене генерал-губернатора)</li>
                            <li>Скульптура "Степанчиково" по мотивам Достоевского</li>
                            <li>Памятник сантехнику Степанычу</li>
                            <li>Фонтан "Изобилие"</li>
                            <li>Множество кафе и ресторанов с сибирской кухней</li>
                        </ul>
                        <p>Прогулка по Любинскому проспекту - это путешествие в прошлое Омска, где каждая деталь рассказывает свою историю.</p>
                        
                        <a href="#" class="back-button"><i class="fas fa-arrow-left"></i> Вернуться к достопримечательностям</a>
                    </div>
                    
                    <div class="sidebar">
                        <div class="info-box">
                            <h4><i class="fas fa-info-circle"></i> Основная информация</h4>
                            <p><i class="fas fa-map-marker-alt"></i> Адрес: Центр города, от ул. Ленина до ул. Музейная</p>
                            <p><i class="far fa-clock"></i> Доступ: круглосуточно</p>
                            <p><i class="fas fa-walking"></i> Статус: Пешеходная зона</p>
                            <p><i class="fas fa-ruler"></i> Протяженность: 600 метров</p>
                        </div>
                        
                        <div class="info-box">
                            <h4><i class="fas fa-star"></i> Интересные факты</h4>
                            <p><i class="fas fa-history"></i> Основан в 1854 году</p>
                            <p><i class="fas fa-monument"></i> 12 исторических зданий</p>
                            <p><i class="fas fa-camera"></i> Самое фотографируемое место Омска</p>
                            <p><i class="fas fa-tree"></i> Липовая аллея - визитная карточка</p>
                        </div>
                        
                        <div class="info-box">
                            <h4><i class="fas fa-map-marked-alt"></i> Расположение</h4>
                            <div class="map-container">
                                Карта: Любинский проспект, Омск
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <footer>
            <div class="container">
                <div class="copyright">
                    <p>&copy; 2023 "Омск - Любовь Моя". Все права защищены.</p>
                </div>
            </div>
        </footer>
    </div>
    
    <!-- Страница Омской крепости -->
    <div id="fortress" class="attraction-page" style="display: none;">
        <header>
            <div class="container">
                <div class="header-content">
                    <div class="logo">
                        <div class="logo-icon">ОМ</div>
                        <div class="logo-text">Омск - Любовь Моя</div>
                    </div>
                    <nav>
                        <ul>
                            <li><a href="#" class="back-to-home">Главная</a></li>
                            <li><a href="#about">О городе</a></li>
                            <li><a href="#attractions">Достопримечательности</a></li>
                            <li><a href="#gallery">Галерея</a></li>
                            <li><a href="#contact">Контакты</a></li>
                        </ul>
                    </nav>
                </div>
            </div>
        </header>
        
        <section class="attraction-page">
            <div class="container">
                <div class="breadcrumb">
                    <a href="#" class="back-to-home">Главная</a>
                    <span>/</span>
                    <a href="#attractions">Достопримечательности</a>
                    <span>/</span>
                    <span>Омская крепость</span>
                </div>
                
                <div class="page-header">
                    <h2 class="section-title">Омская крепость</h2>
                </div>
                
                <div class="page-content">
                    <div class="attraction-details">
                        <div class="card-img">
                            <img src="https://images.unsplash.com/photo-1483664852095-d6cc6870702d?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Омская крепость">
                        </div>
                        
                        <p>Омская крепость - историко-культурный комплекс на месте основания Омска в 1716 году. Это место, откуда начинался город, сохранившее дух первых поселенцев и военную историю Сибири.</p>
                        
                        <h3>История крепости</h3>
                        <p>Первая Омская крепость была заложена в 1716 году по приказу подполковника Ивана Бухгольца как форпост на южных рубежах Российской империи. Вторая крепость, сохранившаяся до наших дней, была построена в 1768-1771 годах по проекту инженера Мальмова.</p>
                        <p>В разные годы в крепости служили: основатель русского флота на Тихом океане Г.И. Невельской, исследователь Дальнего Востока Г.И. Шелихов, писатель Ф.М. Достоевский. Крепость утратила военное значение в XIX веке, а в советское время многие здания были разрушены.</p>
                        
                        <div class="gallery-mini">
                            <img src="https://images.unsplash.com/photo-1505765050516-f72dcac9c60e?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Тобольские ворота">
                            <img src="https://images.unsplash.com/photo-1518998053901-5348d3961a04?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Гауптвахта">
                        </div>
                        
                        <h3>Архитектурные объекты</h3>
                        <p>На территории крепости сохранились уникальные исторические здания:</p>
                        <ul>
                            <li>Тобольские ворота (1791-1794 гг.)</li>
                            <li>Омские ворота (1791-1794 гг.)</li>
                            <li>Здание гауптвахты (1781-1785 гг.)</li>
                            <li>Кинотеатр "Художественный" (1916 г.)</li>
                            <li>Казарма дисциплинарных рот (1820-е гг.)</li>
                            <li>Комендантский дом (1799 г.)</li>
                        </ul>
                        
                        <h3>Музейный комплекс</h3>
                        <p>Сегодня Омская крепость - это музей под открытым небом:</p>
                        <ul>
                            <li>Музей воинской славы омичей</li>
                            <li>Экспозиция "Омск - столица Белой России"</li>
                            <li>Выставка о пребывании Достоевского в Омске</li>
                            <li>Историческая реконструкция солдатских казарм</li>
                            <li>Мастерские традиционных ремесел</li>
                        </ul>
                        <p>Крепость стала культурным центром города, где регулярно проводятся исторические реконструкции, фестивали и культурные мероприятия.</p>
                        
                        <a href="#" class="back-button"><i class="fas fa-arrow-left"></i> Вернуться к достопримечательностям</a>
                    </div>
                    
                    <div class="sidebar">
                        <div class="info-box">
                            <h4><i class="fas fa-info-circle"></i> Основная информация</h4>
                            <p><i class="fas fa-map-marker-alt"></i> Адрес: ул. Партизанская, 5а</p>
                            <p><i class="far fa-clock"></i> Часы работы: 10:00-18:00 (вт-вс)</p>
                            <p><i class="fas fa-landmark"></i> Статус: Историко-культурный комплекс</p>
                            <p><i class="fas fa-calendar-alt"></i> Год основания: 1716</p>
                        </div>
                        
                        <div class="info-box">
                            <h4><i class="fas fa-star"></i> Интересные факты</h4>
                            <p><i class="fas fa-book"></i> Здесь отбывал каторгу Ф.М. Достоевский</p>
                            <p><i class="fas fa-flag"></i> В 1918-1919 гг. - ставка Колчака</p>
                            <p><i class="fas fa-door-open"></i> Тобольские ворота - символ Омска</p>
                            <p><i class="fas fa-ruler"></i> Площадь комплекса - 6 га</p>
                        </div>
                        
                        <div class="info-box">
                            <h4><i class="fas fa-map-marked-alt"></i> Расположение</h4>
                            <div class="map-container">
                                Карта: Омская крепость
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <footer>
            <div class="container">
                <div class="copyright">
                    <p>&copy; 2023 "Омск - Любовь Моя". Все права защищены.</p>
                </div>
            </div>
        </footer>
    </div>
    
    <script>
        // Простая навигация между страницами
        document.addEventListener('DOMContentLoaded', function() {
            // Показываем главную страницу по умолчанию
            document.getElementById('home-page').style.display = 'block';
            document.getElementById('uspensky').style.display = 'none';
            document.getElementById('drama-theater').style.display = 'none';
            document.getElementById('lubinsky').style.display = 'none';
            document.getElementById('fortress').style.display = 'none';
            
            // Обработка перехода на страницы достопримечательностей
            const attractionLinks = document.querySelectorAll('a[data-page]');
            attractionLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const pageId = this.getAttribute('data-page');
                    
                    // Скрываем все страницы
                    document.getElementById('home-page').style.display = 'none';
                    document.getElementById('uspensky').style.display = 'none';
                    document.getElementById('drama-theater').style.display = 'none';
                    document.getElementById('lubinsky').style.display = 'none';
                    document.getElementById('fortress').style.display = 'none';
                    
                    // Показываем выбранную страницу
                    document.getElementById(pageId).style.display = 'block';
                    window.scrollTo(0, 0);
                });
            });
            
            // Обработка возврата на главную
            const backLinks = document.querySelectorAll('.back-to-home, .back-button');
            backLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    // Скрываем все страницы достопримечательностей
                    document.getElementById('uspensky').style.display = 'none';
                    document.getElementById('drama-theater').style.display = 'none';
                    document.getElementById('lubinsky').style.display = 'none';
                    document.getElementById('fortress').style.display = 'none';
                    
                    // Показываем главную страницу
                    document.getElementById('home-page').style.display = 'block';
                    window.scrollTo(0, 0);
                });
            });
            
            // Плавная прокрутка
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    if (this.getAttribute('href') !== '#') {
                        e.preventDefault();
                        const target = document.querySelector(this.getAttribute('href'));
                        if (target) {
                            window.scrollTo({
                                top: target.offsetTop - 80,
                                behavior: 'smooth'
                            });
                        }
                    }
                });
            });
            
            // Фильтрация галереи
            const filterBtns = document.querySelectorAll('.filter-btn');
            const galleryItems = document.querySelectorAll('.gallery-item');
            
            filterBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    // Удаляем активный класс у всех кнопок
                    filterBtns.forEach(b => b.classList.remove('active'));
                    // Добавляем активный класс текущей кнопке
                    btn.classList.add('active');
                    
                    const filter = btn.dataset.filter;
                    
                    galleryItems.forEach(item => {
                        if (filter === 'all' || item.dataset.category === filter) {
                            item.style.display = 'block';
                        } else {
                            item.style.display = 'none';
                        }
                    });
                });
            });
        });
    </script>
</body>
</html>


ссылки для полезных ссылок:
https://admomsk.ru/web/guest/main
https://admomsk.gosuslugi.ru

https://afisha.yandex.ru/omsk
https://www.afisha.ru/omsk/

https://experience.tripster.ru/experience/Omsk/?utm_source=yandex&utm_medium=cpc&utm_campaign=exc_rf_cities_k50_srch&utm_content=116406648_Group-5518509322_Ad-16690967967_PhraseID-53837311952&utm_term=---autotargeting&pid=Yandex_web&c=exc_rf_cities_k50_srch&af_c_id=116406648&is_retargeting=true&af_reengagement_window=3&af_click_lookback=3d&clickid=4752199023587753983&yclid=4752199023587753983

https://gotoomsk.ru/articles/turisticheskie-marshruty-po-omskoj-oblasti/

https://ru.wikipedia.org/wiki/История_Омска

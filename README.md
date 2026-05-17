<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>مشكلتك خليها علينا | الحقني - المساعدة العاجلة على الطريق</title>
    <!-- Fonts & Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Cairo', sans-serif;
            background: radial-gradient(ellipse at 30% 40%, #0a0f1e, #03050b);
            color: #eef5ff;
            scroll-behavior: smooth;
            overflow-x: hidden;
            position: relative;
        }

        /* Stars background dynamic - moving stars */
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
            overflow: hidden;
        }

        .star {
            position: absolute;
            background-color: #fff;
            border-radius: 50%;
            opacity: 0.8;
            box-shadow: 0 0 8px rgba(255,255,200,0.8);
            animation: floatStar linear infinite;
        }

        @keyframes floatStar {
            0% {
                transform: translateY(0vh) translateX(0) rotate(0deg);
                opacity: 0.3;
            }
            50% {
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) translateX(20px) rotate(360deg);
                opacity: 0.2;
            }
        }

        @keyframes twinkle {
            0% { opacity: 0.2; transform: scale(1);}
            100% { opacity: 1; transform: scale(1.3);}
        }

        /* Main content layer */
        .container {
            position: relative;
            z-index: 2;
            max-width: 1400px;
            margin: 0 auto;
            padding: 1rem 2rem;
        }

        /* Glowing text & borders */
        .glow-text {
            text-shadow: 0 0 6px #b0f0ff, 0 0 12px #4effdc, 0 0 20px #00a6c4;
            transition: all 0.3s ease;
        }

        h1, h2, h3, .logo {
            font-weight: 700;
        }

        h2 {
            font-size: 2rem;
            margin-bottom: 1rem;
            border-right: 4px solid #0ff;
            padding-right: 1rem;
            display: inline-block;
            text-shadow: 0 0 5px cyan;
        }

        /* Navigation */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            background: rgba(0,0,0,0.65);
            backdrop-filter: blur(12px);
            border-radius: 60px;
            padding: 0.8rem 2rem;
            margin-bottom: 2rem;
            border: 1px solid rgba(0,255,255,0.2);
            box-shadow: 0 0 20px rgba(0,180,220,0.2);
        }

        .logo i {
            font-size: 2rem;
            color: #0ff;
            margin-left: 0.5rem;
        }

        .nav-links {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .nav-links a {
            color: #eef5ff;
            text-decoration: none;
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 40px;
            transition: 0.2s;
            letter-spacing: 0.5px;
            position: relative;
        }

        .nav-links a:hover, .nav-links a.active {
            background: rgba(0, 255, 255, 0.2);
            text-shadow: 0 0 6px cyan;
            box-shadow: 0 0 10px rgba(0,255,255,0.4);
        }
        
        /* Page sections */
        .page {
            display: none;
            animation: fadeSlide 0.5s ease-out;
            background: rgba(8, 12, 25, 0.55);
            backdrop-filter: blur(2px);
            border-radius: 2rem;
            padding: 2rem;
            margin-top: 1rem;
            border: 1px solid rgba(0, 255, 255, 0.25);
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .active-page {
            display: block;
        }

        @keyframes fadeSlide {
            from { opacity: 0; transform: translateY(15px);}
            to { opacity: 1; transform: translateY(0);}
        }

        /* Cards grid */
        .services-grid, .features-grid, .faq-grid, .solutions-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.8rem;
            margin-top: 2rem;
        }

        .card {
            background: rgba(0, 0, 0, 0.65);
            backdrop-filter: blur(5px);
            border-radius: 1.5rem;
            padding: 1.5rem;
            transition: 0.25s;
            border: 1px solid rgba(0, 255, 255, 0.3);
            box-shadow: 0 8px 20px rgba(0,0,0,0.5);
        }

        .card i {
            font-size: 2.5rem;
            color: #0ff;
            margin-bottom: 1rem;
        }

        .card h3 {
            margin-bottom: 0.8rem;
            font-size: 1.5rem;
        }

        .card p {
            color: #ccddf8;
            line-height: 1.5;
        }

        .card:hover {
            transform: translateY(-8px);
            border-color: #0ff;
            box-shadow: 0 0 25px rgba(0,255,255,0.4);
        }

        /* animated transparent glowing boxes for benefits */
        .benefits-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 1.8rem;
            margin-top: 2rem;
        }
        .benefit-card {
            background: rgba(15, 25, 45, 0.35);
            backdrop-filter: blur(12px);
            border-radius: 1.8rem;
            padding: 1.5rem;
            text-align: center;
            border: 1px solid rgba(0, 255, 255, 0.4);
            transition: all 0.3s cubic-bezier(0.2, 0.9, 0.4, 1.1);
            animation: glowPulse 2.5s infinite ease-in-out;
            box-shadow: 0 0 15px rgba(0, 255, 255, 0.2);
        }
        .benefit-card:hover {
            transform: scale(1.02);
            border-color: #0ff;
            box-shadow: 0 0 35px rgba(0, 255, 255, 0.7);
            animation: none;
        }
        @keyframes glowPulse {
            0% {
                border-color: rgba(0, 255, 255, 0.2);
                box-shadow: 0 0 5px rgba(0, 255, 255, 0.1);
                background: rgba(15, 25, 45, 0.25);
            }
            50% {
                border-color: rgba(0, 255, 255, 0.9);
                box-shadow: 0 0 25px rgba(0, 255, 255, 0.6);
                background: rgba(20, 40, 70, 0.45);
            }
            100% {
                border-color: rgba(0, 255, 255, 0.2);
                box-shadow: 0 0 5px rgba(0, 255, 255, 0.1);
                background: rgba(15, 25, 45, 0.25);
            }
        }
        .benefit-card p {
            font-size: 1rem;
            font-weight: 500;
            letter-spacing: 0.3px;
            color: #eef5ff;
            text-shadow: 0 0 5px rgba(0,255,255,0.5);
        }
        .benefit-card i {
            font-size: 2rem;
            color: #0ff;
            margin-bottom: 0.8rem;
            display: inline-block;
            filter: drop-shadow(0 0 6px cyan);
        }

        /* Buttons */
        .btn {
            background: linear-gradient(95deg, #00b8b0, #0088aa);
            border: none;
            padding: 0.7rem 1.4rem;
            border-radius: 2rem;
            font-family: 'Cairo', sans-serif;
            font-weight: bold;
            color: white;
            cursor: pointer;
            transition: 0.2s;
            box-shadow: 0 0 8px cyan;
            font-size: 1rem;
        }

        .btn-outline {
            background: transparent;
            border: 1px solid #0ff;
            color: #0ff;
        }

        .btn:hover {
            transform: scale(1.02);
            background: #00d4ff;
            color: #010101;
            box-shadow: 0 0 15px cyan;
        }

        /* Form fields */
        .modern-input, .modern-textarea {
            width: 100%;
            padding: 0.9rem 1.5rem;
            margin: 0.8rem 0;
            background: rgba(20, 30, 55, 0.5);
            backdrop-filter: blur(8px);
            border: 1px solid rgba(0, 255, 200, 0.6);
            border-radius: 60px;
            color: #ffffff;
            font-family: 'Cairo', sans-serif;
            font-size: 1rem;
            transition: all 0.3s ease;
            outline: none;
            box-shadow: 0 0 8px rgba(0, 255, 200, 0.2);
        }
        .modern-textarea {
            border-radius: 2rem;
            resize: vertical;
        }
        .modern-input:focus, .modern-textarea:focus {
            border-color: #0ff;
            background: rgba(30, 50, 85, 0.7);
            box-shadow: 0 0 20px rgba(0, 255, 255, 0.5);
            transform: scale(1.01);
        }

        /* footer socials */
        .footer-social {
            margin-top: 3rem;
            background: rgba(0,0,0,0.7);
            backdrop-filter: blur(12px);
            border-radius: 2rem;
            padding: 2rem;
            border: 1px solid rgba(0,255,255,0.3);
            text-align: center;
        }
        .social-icons {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin: 1.5rem 0;
            flex-wrap: wrap;
        }
        .social-icons a {
            color: #0ff;
            font-size: 2rem;
            transition: 0.2s;
            display: inline-block;
        }
        .social-icons a:hover {
            transform: scale(1.2);
            text-shadow: 0 0 15px cyan;
            color: white;
        }
        .contact-info p {
            margin: 0.5rem 0;
            font-size: 1rem;
        }
        hr {
            border-color: rgba(0,255,255,0.3);
            margin: 1rem 0;
        }

        .order-list {
            background: rgba(0,0,0,0.5);
            border-radius: 1rem;
            padding: 1rem;
        }

        .order-item {
            border-bottom: 1px solid cyan;
            padding: 1rem;
            margin-bottom: 0.5rem;
        }

        /* Responsive */
        @media (max-width: 780px) {
            .container { padding: 1rem; }
            nav { flex-direction: column; gap: 1rem; }
            h2 { font-size: 1.6rem; }
        }

        .status-badge {
            display: inline-block;
            padding: 0.2rem 1rem;
            border-radius: 30px;
            font-size: 0.75rem;
            font-weight: bold;
        }
        .status-pending { background: #f0b400; color: #1e1a00; }
        .status-progress { background: #0a6eff; color: white; }
        .status-completed { background: #00cc88; color: #002b1a; }
        .status-cancelled { background: #aa2e4e; color: white; }
        
        /* extra sections */
        .extra-sections {
            margin-top: 3rem;
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }
        .info-block {
            background: rgba(5, 10, 25, 0.7);
            border-radius: 1.8rem;
            padding: 1.8rem;
            border: 1px solid rgba(0, 255, 255, 0.2);
            transition: 0.3s;
        }
        .info-block h3 {
            font-size: 1.8rem;
            margin-bottom: 1rem;
            color: #0ff;
        }
        .solutions-grid div {
            padding: 0.5rem;
            font-size: 1rem;
        }

        /* Developer section */
        .developers-section {
            display: flex;
            justify-content: center;
            gap: 2.5rem;
            flex-wrap: wrap;
            margin: 1.5rem 0;
            padding: 1rem;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 3rem;
            border: 1px dashed rgba(0,255,255,0.4);
        }
        .dev-card {
            display: flex;
            align-items: center;
            gap: 0.8rem;
            background: rgba(0, 20, 40, 0.6);
            backdrop-filter: blur(10px);
            padding: 0.6rem 1.8rem;
            border-radius: 3rem;
            border: 1px solid rgba(0,255,200,0.5);
            transition: 0.2s;
        }
        .dev-card:hover {
            transform: scale(1.05);
            box-shadow: 0 0 20px cyan;
        }
        .fading-star {
            display: inline-block;
            font-size: 1.4rem;
            color: #ffdd44;
            text-shadow: 0 0 8px gold;
            animation: starFade 1.8s infinite ease-in-out;
        }
        @keyframes starFade {
            0% { opacity: 0.2; transform: scale(0.8); text-shadow: 0 0 2px gold;}
            50% { opacity: 1; transform: scale(1.3); text-shadow: 0 0 15px #ffaa33;}
            100% { opacity: 0.2; transform: scale(0.8); text-shadow: 0 0 2px gold;}
        }
        .dev-name {
            font-size: 1.3rem;
            font-weight: 600;
            background: linear-gradient(135deg, #aaffff, #00d4ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            letter-spacing: 0.5px;
        }
        .dev-icon {
            font-size: 1.5rem;
            color: #0ff;
        }
        
        /* Book flip styles (keep for about page) */
        .book-container {
            perspective: 1500px;
            margin: 2rem auto;
            max-width: 900px;
        }
        .book {
            position: relative;
            width: 100%;
            height: 400px;
            transform-style: preserve-3d;
        }
        .page-flip {
            position: absolute;
            width: 100%;
            height: 100%;
            background: rgba(10, 20, 35, 0.85);
            backdrop-filter: blur(12px);
            border-radius: 1rem;
            padding: 2rem;
            border: 1px solid rgba(0, 255, 255, 0.5);
            box-shadow: 0 0 25px rgba(0,255,255,0.3);
            backface-visibility: hidden;
            transition: transform 0.8s cubic-bezier(0.23, 1, 0.32, 1);
            overflow-y: auto;
        }
        .page-front { transform: rotateY(0deg); z-index: 2; }
        .page-back { transform: rotateY(180deg); z-index: 1; }
        .flipped .page-front { transform: rotateY(-180deg); }
        .flipped .page-back { transform: rotateY(0deg); }
        .book-controls { display: flex; justify-content: center; gap: 1.5rem; margin-top: 1.5rem; }
        .book-btn { background: rgba(0, 255, 255, 0.2); border: 1px solid cyan; padding: 0.5rem 1.8rem; border-radius: 40px; cursor: pointer; color: cyan; }
        .book-btn:hover { background: cyan; color: #010101; box-shadow: 0 0 15px cyan; }
        
        /* app showcase */
        .app-showcase { background: rgba(0, 10, 25, 0.6); border-radius: 2rem; padding: 2rem; border: 1px solid rgba(0,255,255,0.4); margin-bottom: 2rem; }
        .download-buttons { display: flex; gap: 1.5rem; justify-content: center; flex-wrap: wrap; margin: 2rem 0; }
        .download-btn { background: linear-gradient(135deg, #1e2a3a, #0a0f1a); border: 1px solid cyan; padding: 0.8rem 2rem; border-radius: 60px; color: white; font-weight: bold; transition: 0.2s; text-decoration: none; display: inline-flex; align-items: center; gap: 0.7rem; }
        .download-btn i { font-size: 1.8rem; color: cyan; }
        .download-btn:hover { transform: scale(1.05); background: #0ff; color: black; }
        .benefits-grid-alt { display: grid; grid-template-columns: repeat(auto-fill, minmax(250px,1fr)); gap: 1.5rem; margin: 2rem 0; }
        .highlight-card { background: rgba(0, 255, 255, 0.08); border-radius: 1.2rem; padding: 1.2rem; text-align: center; border: 1px solid rgba(0,255,255,0.3); }
        
        /* New specific download button style (big and prominent) */
        .promo-download-btn {
            display: block;
            width: 100%;
            max-width: 320px;
            margin: 2rem auto 1rem auto;
            text-align: center;
            background: linear-gradient(115deg, #00c9b7, #005f73);
            border: none;
            padding: 1rem 1.5rem;
            border-radius: 60px;
            font-size: 1.5rem;
            font-weight: bold;
            color: white;
            box-shadow: 0 0 25px rgba(0, 255, 255, 0.7);
            transition: 0.2s;
            text-decoration: none;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            letter-spacing: 1px;
        }
        .promo-download-btn i {
            font-size: 2rem;
            color: #fff;
            filter: drop-shadow(0 0 6px cyan);
        }
        .promo-download-btn:hover {
            transform: scale(1.03);
            background: #00e0cc;
            color: #0a0a0a;
            box-shadow: 0 0 35px cyan;
        }
    </style>
</head>
<body>
<div class="stars" id="starsContainer"></div>
<div class="container">
    <nav>
        <div class="logo glow-text"><i class="fas fa-car-crash"></i> الحقني | مشكلتك خليها علينا</div>
        <div class="nav-links" id="navLinks">
            <a href="#" data-page="home" class="active">🏠 الرئيسية</a>
            <a href="#" data-page="services">🛠️ الخدمات</a>
            <a href="#" data-page="about">📖 نبذة عن الموقع</a>
            <a href="#" data-page="ourapp">📱 تطبيقنا</a>
            <a href="#" data-page="features">✨ الميزات</a>
            <a href="#" data-page="faq">❓ الأسئلة</a>
            <a href="#" data-page="contact">📞 تواصل</a>
        </div>
    </nav>

    <!-- HOME PAGE مع كامل المحتوى المطلوب -->
    <div id="home" class="page active-page">
        <h2 class="glow-text">⭐ مرحباً بك في الحقني - مشكلتك خليها علينا</h2>
        <p style="font-size:1.2rem; margin-top:1rem;">تطبيق المساعدة العاجلة للسيارات والشاحنات في الجزائر — 24 ساعة، سرعة فائقة، خدمات متكاملة. نحن هنا لحل مشكلتك على الطريق.</p>
        <div class="services-grid" style="margin-top:2rem;">
            <div class="card"><i class="fas fa-wrench"></i><h3>ميكانيكي متنقل</h3><p>إصلاح عاجل في موقع العطل.</p></div>
            <div class="card"><i class="fas fa-gas-pump"></i><h3>توصيل وقود</h3><p>نفذ البنزين؟ نوصل لك الوقود أينما كنت.</p></div>
            <div class="card"><i class="fas fa-oil-can"></i><h3>زيوت وقطع غيار</h3><p>توصيل الزيوت المناسبة وقطع الغيار.</p></div>
            <div class="card"><i class="fas fa-truck"></i><h3>ديبناج (سحب)</h3><p>شاحنة رفع لنقل سيارتك إلى أقرب ورشة.</p></div>
        </div>

        <div class="extra-sections">
            <!-- فكرة الموقع ورؤيته -->
            <div class="info-block">
                <h3><i class="fas fa-lightbulb"></i> فكرة الموقع ورؤيته</h3>
                <p>“الحقني” هو منصة جزائرية ذكية تربط السائقين (شاحنات وسيارات) بأسرع مزودي خدمات الطوارئ على الطريق. فكرتنا تنبع من الحاجة الملحة إلى حل سريع ومنظم عند التعطل في المناطق النائية أو الطرق السريعة. نستخدم تقنيات GPS والهز الذكي والواجهة البسيطة لنقل تجربة طلب المساعدة من دقائق مرهقة إلى ثواني سلسة. نسعى لأن تكون تطبيق كل سائق في شمال أفريقيا.</p>
            </div>
            <!-- شرح التطبيق -->
            <div class="info-block">
                <h3><i class="fas fa-mobile-alt"></i> شرح التطبيق</h3>
                <p>تطبيق “الحقني” يعمل كمساعد افتراضي دائم: بمجرد فتح التطبيق، تستطيع اختيار الخدمة المناسبة (ميكانيكي، وقود، زيوت، ديبناج، توجيه إلى ورشة). سيتم تحديد موقعك الجغرافي بدقة فائقة، وإرسال طلبك إلى أقرب مزود خدمة. يمكنك متابعة حالة طلبك (pending, in_progress, completed) من لوحة “طلباتي”. يتميز التطبيق بوضع نهاري/ليلي، وهز الهاتف للتبليغ السريع، وإمكانية نسخ رابط موقعك.</p>
            </div>
            <!-- فوائد التطبيق -->
            <div class="info-block">
                <h3><i class="fas fa-chart-line"></i> فوائد التطبيق</h3>
                <div class="benefits-grid">
                    <div class="benefit-card"><i class="fas fa-bolt"></i><p>سرعة الاستجابة - وصول المساعدة في أقل من 20 دقيقة</p></div>
                    <div class="benefit-card"><i class="fas fa-clock"></i><p>توفير الوقت والجهد - لا حاجة للبحث عن أرقام الورش</p></div>
                    <div class="benefit-card"><i class="fas fa-shield-alt"></i><p>الراحة والأمان - خدمة 24 ساعة طوال أيام الأسبوع</p></div>
                    <div class="benefit-card"><i class="fas fa-map-marker-alt"></i><p>دقة تحديد الموقع عبر GPS وخرائط جوجل</p></div>
                    <div class="benefit-card"><i class="fas fa-concierge-bell"></i><p>تنوع الخدمات - ميكانيكي وقود زيوت ديبناج ورشات</p></div>
                    <div class="benefit-card"><i class="fas fa-gem"></i><p>مجاني بالكامل - جميع الخدمات الأساسية بدون رسوم خفية</p></div>
                    <div class="benefit-card"><i class="fas fa-language"></i><p>واجهة عربية بسيطة ومتابعة حية للطلبات</p></div>
                </div>
            </div>
            <!-- المشكلات التي يعالجها التطبيق -->
            <div class="info-block">
                <h3><i class="fas fa-exclamation-triangle"></i> المشكلات التي يعالجها التطبيق</h3>
                <div class="solutions-grid" style="grid-template-columns: repeat(auto-fill, minmax(240px,1fr)); margin-top:1rem;">
                    <div><i class="fas fa-car-side"></i> تعطل الشاحنات والسيارات في الطريق</div>
                    <div><i class="fas fa-gas-pump"></i> نفاد الوقود في منتصف الرحلة</div>
                    <div><i class="fas fa-oil-can"></i> نقص الزيوت أو تسرب الزيت</div>
                    <div><i class="fas fa-tools"></i> أعطال ميكانيكية مفاجئة (محرك، كهرباء)</div>
                    <div><i class="fas fa-truck"></i> الحاجة إلى سحب السيارة (ديبناج)</div>
                    <div><i class="fas fa-map-marked-alt"></i> صعوبة إيجاد ورشة تصليح قريبة</div>
                    <div><i class="fas fa-location-dot"></i> عدم القدرة على تحديد الموقع بدقة</div>
                    <div><i class="fas fa-clock"></i> بطء طلب المساعدة بالطرق التقليدية</div>
                    <div><i class="fas fa-list-ul"></i> عدم متابعة حالة الطلب</div>
                    <div><i class="fas fa-headset"></i> صعوبة التواصل مع الدعم الفني</div>
                </div>
            </div>
        </div>
    </div>

    <!-- SERVICES PAGE -->
    <div id="services" class="page">
        <h2 class="glow-text">🚛 جميع الخدمات</h2>
        <div class="services-grid">
            <div class="card"><i class="fas fa-tools"></i><h3>إصلاح ميكانيكي</h3><p>ميكانيكي محترف يصل إلى موقعك خلال دقائق.</p></div>
            <div class="card"><i class="fas fa-tint"></i><h3>توصيل الزيوت</h3><p>زيت محرك, ناقل حركة, فرامل حسب الطلب.</p></div>
            <div class="card"><i class="fas fa-charging-station"></i><h3>توصيل الوقود</h3><p>بنزين، ديزل، غاز — نصل لأي مكان.</p></div>
            <div class="card"><i class="fas fa-car-battery"></i><h3>بطارية وقطع غيار</h3><p>توصيل بطاريات، إطارات، قطع غيار أصلية.</p></div>
            <div class="card"><i class="fas fa-map-marked-alt"></i><h3>توجيه إلى ورشات</h3><p>أقرب ورشة تصليح معتمدة.</p></div>
            <div class="card"><i class="fas fa-truck-moving"></i><h3>خدمة السحب</h3><p>سيارة ديبناج مجهزة لسحب جميع أنواع المركبات.</p></div>
        </div>
    </div>

    <!-- ABOUT PAGE (كتاب متحرك) -->
    <div id="about" class="page">
        <h2 class="glow-text">📖 نبذة عن الموقع</h2>
        <div class="book-container">
            <div class="book" id="flipBook">
                <div class="page-flip page-front"><div class="page-content"><h3><i class="fas fa-star-of-life"></i> رؤيتنا</h3><p>“الحقني” منصة ذكية جزائرية 100% تهدف إلى إنقاذ السائقين من عناء البحث عن المساعدة عند تعطل مركباتهم على الطريق. نقدم خدمات الطوارئ المتنقلة بضغطة زر واحدة. نؤمن بأن كل دقيقة تأخير قد تكلفك وقتاً وأعصاباً، لذلك صممنا النظام ليكون فائق السرعة والموثوقية.</p><p>فريقنا يتكون من مهندسين ومطورين جزائريين خبراء في جميع التقنيات لتوجيه أقرب مزود خدمة إليك بدقة خارقة. مشكلتك خليها علينا!</p></div></div>
                <div class="page-flip page-back"><div class="page-content"><h3><i class="fas fa-globe-africa"></i> قصة النجاح والتوسع</h3><p>بدأت فكرة “الحقني” على طرقات الجزائر السريعة حيث يواجه السائقون صعوبة في إيجاد ميكانيكي أو ورشة موثوقة. اليوم، نخدم جميع الولايات، ونخطط للتوسع إلى كامل التراب الوطني. نعمل على تطوير واجهة عربية بسيطة تدعم خاصية هز الهاتف للتبليغ العاجل، وتحديد الموقع التلقائي، ومتابعة الطلب لحظة بلحظة.</p><p>نطمح لأن نكون أول تطبيق عربي رائد في مجال خدمات الطريق، ونقدم تجربة سلسة وآمنة ومجانية تماماً للمستخدمين. مع “الحقني” لن تواجه مشكلة وحدك أبداً.</p></div></div>
            </div>
            <div class="book-controls"><button class="book-btn" id="prevPageBtn">➡️ السابق</button><button class="book-btn" id="nextPageBtn">التالي ⬅️</button></div>
        </div>
    </div>

    <!-- تطبيقنا (تم تعديل العنوان وحذف "في جيبك") -->
    <div id="ourapp" class="page">
        <h2 class="glow-text">📱 تطبيقنا - الحقني</h2>
        <div class="app-showcase">
            <h3><i class="fas fa-mobile-alt"></i> فكرة التطبيق وكيفية حل مشكلاتكم</h3>
            <p>تطبيق "الحقني" ليس مجرد منصة طلب مساعدة، بل هو نظام متكامل يعتمد على الذكاء الجغرافي لربطك بأقرب ميكانيكي أو شاحنة سحب أو مزود وقود في أقل من 30 ثانية. بفضل واجهته البسيطة، يمكنك طلب الخدمة، تحديد موقعك، ومتابعة الحالة (قيد الانتظار، قيد التنفيذ، مكتمل). نحن نحل مشكلة العزلة على الطرقات، صعوبة العثور على ورشة في الليل، ونقص التواصل مع المهنيين الموثوقين. تطبيقنا متاح لجميع السيارات والشاحنات، ويعمل حتى في المناطق ذات التغطية الضعيفة عبر الإرسال الذكي للرسائل. مشكلتك خليها علينا، احنا نوصلو ليك في اي وقت واي مكان.</p>
            <h3 style="margin-top:1.5rem;"><i class="fas fa-download"></i> كيفية تحميل التطبيق</h3>
            <div class="download-buttons"><a href="#" class="download-btn"><i class="fab fa-google-play"></i> تحميل من Google Play</a><a href="#" class="download-btn"><i class="fab fa-apple"></i> تحميل من App Store</a><a href="#" class="download-btn"><i class="fas fa-globe"></i> النسخة الإلكترونية</a></div>
            <div class="benefits-grid-alt">
                <div class="highlight-card"><i class="fas fa-check-circle" style="color:#0ff; font-size:2rem;"></i><h3>سهولة الاستخدام</h3><p>ثلاث خطوات فقط: اختر الخدمة → حدد موقعك → أرسل الطلب</p></div>
                <div class="highlight-card"><i class="fas fa-bell" style="color:#0ff; font-size:2rem;"></i><h3>إشعارات فورية</h3><p>تلقَّ إشعارات بحالة طلبك وتحديثات وصول المساعدة</p></div>
                <div class="highlight-card"><i class="fas fa-shield-virus" style="color:#0ff; font-size:2rem;"></i><h3>أمان تام</h3><p>جميع مزودي الخدمة تمت مراجعتهم ولديهم تقييمات شفافة</p></div>
                <div class="highlight-card"><i class="fas fa-headset" style="color:#0ff; font-size:2rem;"></i><h3>دعم على مدار الساعة</h3><p>فريق متخصص للرد على استفساراتكم وحل أي مشكلة</p></div>
            </div>
            <!-- زر تنزيل التطبيق الجديد - يقع أسفل الصفحة وفوق أيقونات التواصل الاجتماعي -->
            <a href="https://loadly.io/xm2WTzXP" class="promo-download-btn" target="_blank" rel="noopener noreferrer">
                <i class="fas fa-download"></i> تنزيل التطبيق
                <i class="fas fa-arrow-left"></i>
            </a>
        </div>
    </div>

    <!-- FEATURES -->
    <div id="features" class="page">
        <h2 class="glow-text">💎 مميزات التطبيق الفريدة</h2>
        <div class="features-grid">
            <div class="card"><i class="fas fa-bolt"></i><h3>هز الهاتف للتبليغ</h3><p>هز جهازك لفتح طلب مساعدة بسرعة البرق.</p></div>
            <div class="card"><i class="fas fa-moon"></i><h3>وضع ليلي / نهاري</h3><p>واجهة مريحة مع نجوم متلألئة.</p></div>
            <div class="card"><i class="fas fa-chart-line"></i><h3>متابعة الطلبات</h3><p>حالة الطلب: انتظار، تنفيذ، مكتمل، ملغي.</p></div>
            <div class="card"><i class="fas fa-map-pin"></i><h3>GPS دقيق</h3><p>نسخ رابط موقع Google Maps بدقة عالية.</p></div>
            <div class="card"><i class="fas fa-shield-alt"></i><h3>أمان وخصوصية</h3><p>بياناتك مشفرة عبر Supabase.</p></div>
            <div class="card"><i class="fas fa-headset"></i><h3>دعم مباشر 24/7</h3><p>قنوات اتصال سريعة عبر البريد والإبلاغ.</p></div>
        </div>
    </div>

    <!-- FAQ -->
    <div id="faq" class="page">
        <h2 class="glow-text">❓ الأسئلة الشائعة</h2>
        <div class="faq-grid">
            <div class="card"><h3>❓ كيف أطلب المساعدة؟</h3><p>اختر الخدمة من صفحة الطلب، حدد موقعك، ثم أرسل الطلب.</p></div>
            <div class="card"><h3>⏱️ كم سرعة الاستجابة؟</h3><p>فريقنا المنتشر يستجيب خلال 15-30 دقيقة حسب الموقع.</p></div>
            <div class="card"><h3>💰 هل التطبيق مجاني؟</h3><p>نعم، جميع الخدمات الأساسية مجانية، رسوم الخدمات تحددها الجهة المقدمة.</p></div>
            <div class="card"><h3>🔧 ماذا لو احتجت ميكانيكي متخصص؟</h3><p>نوفر ميكانيكيين مدربين مع قطع الغيار إن أمكن.</p></div>
            <div class="card"><h3>🚗 هل تغطون جميع مناطق الجزائر؟</h3><p>نعمل حالياً في كبرى المدن والطرق السريعة، والتوسع مستمر.</p></div>
            <div class="card"><h3>📱 كيف أتابع طلبي؟</h3><p>من صفحة "طلباتي" تجد كل التفاصيل والحالة المحدثة.</p></div>
        </div>
    </div>

    <!-- CONTACT (بدون ابلاغ) -->
    <div id="contact" class="page">
        <h2 class="glow-text">📞 تواصل مع فريق الحقني - مشكلتك خليها علينا</h2>
        <div class="card" style="max-width:700px; margin:1rem auto;">
            <p><i class="fas fa-envelope"></i> البريد الإلكتروني: vixfull516@gmail.com</p>
            <p><i class="fas fa-phone-alt"></i> ارقم الهاتف: 0666302567</p>
            <p><i class="fab fa-whatsapp"></i> واتساب: +213 789 456</p>
            <div class="developers-section">
                <div class="dev-card"><span class="fading-star">⭐</span><i class="fas fa-user-astronaut dev-icon"></i><span class="dev-name">دماني نعيمة</span></div>
                <div class="dev-card"><span class="fading-star">⭐</span><i class="fas fa-user-astronaut dev-icon"></i><span class="dev-name">بلعدل فاطيمة</span></div>
            </div>
        </div>
    </div>

    <div class="footer-social">
        <div class="social-icons">
            <a href="#"><i class="fab fa-facebook-f"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-linkedin-in"></i></a>
            <a href="#"><i class="fab fa-youtube"></i></a>
            <a href="#"><i class="fab fa-tiktok"></i></a>
        </div>
        <div class="contact-info">
            <p><i class="fas fa-map-marker-alt"></i> الجزائر - ولاية الجلفة، الطريق السريع شرق غرب</p>
            <p><i class="fas fa-envelope"></i> Email: vixfull516@gmail.com &nbsp;|&nbsp; <i class="fas fa-phone"></i> الهاتف: +213 555 00 11 22</p>
            <p><i class="fas fa-clock"></i> خدمة العملاء متاحة 24/7 طوال أيام الأسبوع</p>
            <p class="glow-text" style="margin-top:0.5rem;">شعارنا: <strong>مشكلتك خليها علينا</strong> - لأن سلامتكم أولويتنا</p>
        </div>
        <hr>
        <p class="glow-text">© 2026 الحقني — مساعدة الطريق بلا حدود | مشكلتك خليها علينا</p>
    </div>
</div>

<script>
    // Stars background
    function generateMovingStars() {
        const starsDiv = document.getElementById('starsContainer');
        starsDiv.innerHTML = '';
        for(let i = 0; i < 300; i++) {
            let star = document.createElement('div');
            star.classList.add('star');
            let size = Math.random() * 3 + 1;
            star.style.width = size + 'px';
            star.style.height = size + 'px';
            star.style.left = Math.random() * 100 + '%';
            star.style.top = Math.random() * 100 + '%';
            let duration = 8 + Math.random() * 15;
            star.style.animation = `floatStar ${duration}s linear infinite`;
            star.style.animationDelay = `${Math.random() * 10}s`;
            starsDiv.appendChild(star);
        }
        for(let i = 0; i < 150; i++) {
            let glitter = document.createElement('div');
            glitter.classList.add('star');
            glitter.style.width = (Math.random() * 2 + 1) + 'px';
            glitter.style.height = (Math.random() * 2 + 1) + 'px';
            glitter.style.left = Math.random() * 100 + '%';
            glitter.style.top = Math.random() * 100 + '%';
            glitter.style.animation = `twinkle ${1.5 + Math.random() * 4}s infinite alternate`;
            glitter.style.background = '#ffffaa';
            starsDiv.appendChild(glitter);
        }
    }
    generateMovingStars();

    const pages = ['home','services','about','ourapp','features','faq','contact'];
    function showPage(pageId) {
        pages.forEach(p => { const el = document.getElementById(p); if(el) el.classList.remove('active-page'); });
        document.getElementById(pageId).classList.add('active-page');
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.classList.remove('active');
            if(link.getAttribute('data-page') === pageId) link.classList.add('active');
        });
        localStorage.setItem('currentPage', pageId);
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }
    document.querySelectorAll('.nav-links a').forEach(link => {
        link.addEventListener('click', (e) => { e.preventDefault(); const page = link.getAttribute('data-page'); if(page && pages.includes(page)) showPage(page); });
    });
    
    // Book flip logic
    const book = document.getElementById('flipBook');
    if(book) {
        let isFlipped = false;
        document.getElementById('prevPageBtn')?.addEventListener('click', () => { if(isFlipped) { book.classList.remove('flipped'); isFlipped = false; } });
        document.getElementById('nextPageBtn')?.addEventListener('click', () => { if(!isFlipped) { book.classList.add('flipped'); isFlipped = true; } });
    }
    const saved = localStorage.getItem('currentPage');
    if(saved && pages.includes(saved)) showPage(saved); else showPage('home');
    
    // شيك هز الهاتف
    let lastShake = 0;
    if(window.DeviceMotionEvent) {
        window.addEventListener('devicemotion', (e) => {
            let acc = e.accelerationIncludingGravity;
            if(acc && (Math.abs(acc.x) > 15 || Math.abs(acc.y) > 15 || Math.abs(acc.z) > 15)) {
                const now = Date.now();
                if(now - lastShake > 1500) {
                    lastShake = now;
                    if(confirm('🚨 هزاز الهاتف تم تفعيله! هل تريد طلب مساعدة عاجلة؟')) alert('مشكلتك خليها علينا! يمكنك طلب المساعدة من خلال خدماتنا عبر القائمة.');
                }
            }
        });
    }
</script>
</body>
</html>

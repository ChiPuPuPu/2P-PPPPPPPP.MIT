<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>数字博物馆 | 文化遗产数字化展示平台</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Helvetica Neue', Arial, sans-serif;
        }
        
        body {
            background-color: #ffffff;
            color: #333333;
            line-height: 1.6;
        }
        
        header {
            background-color: #fff;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.08);
            padding: 25px 0;
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        
        .container {
            width: 90%;
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 28px;
            font-weight: 700;
            color: #222;
            letter-spacing: 1px;
        }
        
        .logo span {
            color: #8b7355;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 40px;
            position: relative;
        }
        
        nav ul li a {
            text-decoration: none;
            color: #444;
            font-weight: 500;
            font-size: 16px;
            transition: all 0.3s ease;
            padding: 8px 0;
        }
        
        nav ul li a:hover {
            color: #8b7355;
        }
        
        nav ul li a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: #8b7355;
            bottom: 0;
            left: 0;
            transition: width 0.3s;
        }
        
        nav ul li a:hover::after {
            width: 100%;
        }
        
        .hero {
            padding: 80px 0 40px;
            text-align: center;
        }
        
        .hero h1 {
            font-size: 42px;
            margin-bottom: 25px;
            font-weight: 300;
            letter-spacing: 1px;
        }
        
        .hero h1 strong {
            font-weight: 600;
            color: #8b7355;
        }
        
        .hero p {
            font-size: 18px;
            color: #666;
            max-width: 800px;
            margin: 0 auto 50px;
            line-height: 1.8;
        }
        
        .model-container {
            width: 100%;
            height: 70vh;
            min-height: 600px;
            margin: 50px 0;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
            position: relative;
        }
        
        .sketchfab-embed-wrapper {
            width: 100%;
            height: 100%;
        }
        
        .sketchfab-embed-wrapper iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
        
        .about {
            padding: 80px 0;
            text-align: center;
        }
        
        .about h2 {
            font-size: 32px;
            margin-bottom: 30px;
            font-weight: 400;
            color: #444;
        }
        
        .about p {
            font-size: 17px;
            color: #666;
            max-width: 800px;
            margin: 0 auto;
            line-height: 1.8;
        }
        
        footer {
            background-color: #f5f5f5;
            padding: 50px 0 30px;
            margin-top: 80px;
        }
        
        .footer-content {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
        }
        
        .footer-section {
            flex: 1;
            min-width: 250px;
            margin-bottom: 30px;
        }
        
        .footer-section h3 {
            font-size: 18px;
            margin-bottom: 20px;
            color: #444;
            font-weight: 600;
        }
        
        .footer-section p, .footer-section a {
            color: #666;
            margin-bottom: 10px;
            display: block;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-section a:hover {
            color: #8b7355;
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid #e0e0e0;
            margin-top: 30px;
            color: #888;
            font-size: 14px;
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
            }
            
            .logo {
                margin-bottom: 20px;
            }
            
            nav ul {
                width: 100%;
                justify-content: space-around;
            }
            
            nav ul li {
                margin: 0;
            }
            
            .hero h1 {
                font-size: 32px;
            }
            
            .model-container {
                height: 400px;
                min-height: auto;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">数字<span>博物馆</span></div>
                <nav>
                    <ul>
                        <li><a href="#">首页</a></li>
                        <li><a href="#">展品</a></li>
                        <li><a href="#">展讯</a></li>
                        <li><a href="#">联系我们</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>
    
    <main class="container">
        <section class="hero">
            <h1>探索<strong>数字文化遗产</strong>的无限可能</h1>
            <p>通过先进的3D数字化技术，我们将珍贵的文物和艺术品带入您的屏幕，让您足不出户就能近距离欣赏人类文明的瑰宝，体验前所未有的沉浸式观展体验。</p>
        </section>
        
        <div class="model-container">
            <div class="sketchfab-embed-wrapper"> 
                <iframe title="Zui" frameborder="0" allowfullscreen mozallowfullscreen="true" 
                webkitallowfullscreen="true" allow="autoplay; fullscreen; xr-spatial-tracking" 
                xr-spatial-tracking execution-while-out-of-viewport execution-while-not-rendered 
                web-share width="100%" height="100%" 
                src="https://sketchfab.com/models/81762fbab15143c3b8126d5385bd2a72/embed"> 
                </iframe> 
                <p style="font-size: 13px; font-weight: normal; margin: 5px; color: #4A4A4A;"> 
                    Zui by on 
                </p>
            </div>
        </div>
        
        <section class="about">
            <h2>关于数字博物馆</h2>
            <p>我们致力于通过最先进的3D扫描和虚拟现实技术，为全球观众提供高质量的数字化文物展示。我们的团队由文物保护专家、数字技术工程师和艺术史学者组成，共同打造这一不受时空限制的文化遗产展示平台。</p>
        </section>
    </main>
    
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>快速链接</h3>
                    <a href="#">首页</a>
                    <a href="#">展品收藏</a>
                    <a href="#">当前展览</a>
                    <a href="#">即将展出</a>
                </div>
                <div class="footer-section">
                    <h3>关于我们</h3>
                    <a href="#">我们的使命</a>
                    <a href="#">数字技术</a>
                    <a href="#">合作伙伴</a>
                    <a href="#">加入我们</a>
                </div>
                <div class="footer-section">
                    <h3>联系方式</h3>
                    <p>北京市海淀区中关村南大街5号</p>
                    <p>电话: 010-12345678</p>
                    <p>邮箱: info@digitalmuseum.org</p>
                    <p>开放时间: 周二至周日 9:00-17:00</p>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 数字博物馆 版权所有 | 京ICP备12345678号</p>
            </div>
        </div>
    </footer>
</body>
</html>

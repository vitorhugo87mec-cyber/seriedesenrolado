[Desenrolados.html](https://github.com/user-attachments/files/25749989/Desenrolados.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Desenrolados - Grupo de Gravação</title>
    <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Montserrat:wght@300;400;600;800&display=swap" rel="stylesheet">
    <style>
        /* ==========================================
           VARIÁVEIS GLOBAIS
           ========================================== */
        :root {
            --primary: #ff3e3e;
            --secondary: #1a1a1a;
            --accent: #ffd700;
            --success: #28a745;
            --warning: #ffc107;
            --danger: #dc3545;
            --light: #f5f5f5;
            --sidebar-width: 300px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background: var(--secondary);
            color: var(--light);
            overflow-x: hidden;
        }

        /* ==========================================
           SITE PRINCIPAL - VISUALIZAÇÃO PÚBLICA
           ========================================== */
        
        /* Header Cinematográfico */
        #site-view header {
            height: 100vh;
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)),
                        url('https://images.unsplash.com/photo-1485846234645-a62644f84728?w=1920') center/cover;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
            animation: zoomIn 20s ease-in-out infinite alternate;
        }

        @keyframes zoomIn {
            from { transform: scale(1); }
            to { transform: scale(1.1); }
        }

        .clapperboard {
            width: 120px;
            height: 100px;
            background: #000;
            border: 4px solid #fff;
            position: relative;
            margin-bottom: 30px;
            transform: rotate(-5deg);
            animation: clap 2s ease-in-out infinite;
        }

        .clapperboard::before {
            content: '';
            position: absolute;
            top: -15px;
            left: -4px;
            width: 100%;
            height: 30px;
            background: repeating-linear-gradient(45deg, #fff, #fff 10px, #000 10px, #000 20px);
            border: 4px solid #fff;
            transform-origin: left;
            animation: clapTop 2s ease-in-out infinite;
        }

        @keyframes clap {
            0%, 100% { transform: rotate(-5deg); }
            50% { transform: rotate(-2deg); }
        }

        @keyframes clapTop {
            0%, 100% { transform: rotate(0deg); }
            50% { transform: rotate(-25deg); }
        }

        h1 {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 8rem;
            letter-spacing: 0.1em;
            text-shadow: 0 0 30px var(--primary);
            animation: glitch 3s infinite;
        }

        @keyframes glitch {
            0%, 90%, 100% { text-shadow: 0 0 30px var(--primary); }
            92% { text-shadow: -5px 0 #0ff, 5px 0 #f0f; }
            94% { text-shadow: 5px 0 #0ff, -5px 0 #f0f; }
        }

        .tagline {
            font-size: 1.5rem;
            letter-spacing: 0.3em;
            text-transform: uppercase;
            margin-top: 20px;
            opacity: 0.8;
        }

        .scroll-indicator {
            position: absolute;
            bottom: 40px;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(20px); }
        }

        /* Navegação do Site */
        #site-view nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 50px;
            background: rgba(0,0,0,0.9);
            backdrop-filter: blur(10px);
            z-index: 100;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s;
        }

        #site-view nav.scrolled {
            padding: 15px 50px;
            background: rgba(0,0,0,0.95);
        }

        .logo-nav {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 2rem;
            color: var(--primary);
        }

        .nav-links {
            display: flex;
            gap: 40px;
            list-style: none;
        }

        .nav-links a {
            color: var(--light);
            text-decoration: none;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            font-size: 0.9rem;
            position: relative;
            transition: color 0.3s;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .btn-admin-login {
            padding: 10px 20px;
            background: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
            text-decoration: none;
            border-radius: 5px;
            font-weight: 600;
            transition: all 0.3s;
            cursor: pointer;
        }

        .btn-admin-login:hover {
            background: var(--primary);
            color: #fff;
        }

        /* Seções do Site */
        section {
            padding: 100px 10%;
            position: relative;
        }

        .section-title {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 4rem;
            margin-bottom: 50px;
            text-align: center;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 100px;
            height: 4px;
            background: var(--primary);
            margin: 20px auto;
        }

        /* Sobre */
        #sobre {
            background: linear-gradient(135deg, #1a1a1a 0%, #2d2d2d 100%);
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #ccc;
        }

        .about-text p {
            margin-bottom: 20px;
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
            margin-top: 40px;
        }

        .stat-item {
            text-align: center;
            padding: 30px;
            background: rgba(255,255,255,0.05);
            border-radius: 10px;
            border: 1px solid rgba(255,255,255,0.1);
            transition: transform 0.3s, border-color 0.3s;
        }

        .stat-item:hover {
            transform: translateY(-10px);
            border-color: var(--primary);
        }

        .stat-number {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 3rem;
            color: var(--primary);
        }

        .stat-label {
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            margin-top: 10px;
        }

        /* Galeria */
        #projetos {
            background: #0f0f0f;
        }

        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            height: 400px;
            cursor: pointer;
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
        }

        .gallery-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0,0,0,0.9));
            padding: 30px;
            transform: translateY(100%);
            transition: transform 0.3s;
        }

        .gallery-item:hover .gallery-overlay {
            transform: translateY(0);
        }

        .gallery-title {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 1.8rem;
            color: var(--accent);
        }

        /* SEÇÃO SEGURANÇA */
        #seguranca {
            background: linear-gradient(rgba(0,0,0,0.9), rgba(0,0,0,0.9)),
                        url('https://images.unsplash.com/photo-1595590424283-b8f17842773f?w=1920') center/cover fixed;
            border-top: 5px solid var(--primary);
            border-bottom: 5px solid var(--primary);
        }

        .safety-container {
            max-width: 1000px;
            margin: 0 auto;
            background: rgba(20,20,20,0.95);
            padding: 60px;
            border-radius: 20px;
            border: 2px solid var(--primary);
            box-shadow: 0 0 50px rgba(255,62,62,0.3);
        }

        .safety-header {
            text-align: center;
            margin-bottom: 40px;
        }

        .safety-icon {
            font-size: 4rem;
            margin-bottom: 20px;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .safety-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
        }

        .safety-box {
            background: rgba(255,255,255,0.05);
            padding: 30px;
            border-radius: 15px;
            border-left: 5px solid var(--accent);
        }

        .safety-box h3 {
            color: var(--accent);
            font-size: 1.3rem;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .safety-box ul {
            list-style: none;
            line-height: 2;
        }

        .safety-box li::before {
            content: '✓';
            color: var(--primary);
            margin-right: 10px;
            font-weight: bold;
        }

        .disclaimer {
            margin-top: 40px;
            padding: 30px;
            background: rgba(255,62,62,0.1);
            border: 2px dashed var(--primary);
            border-radius: 10px;
            text-align: center;
        }

        .disclaimer h4 {
            color: var(--primary);
            font-size: 1.5rem;
            margin-bottom: 15px;
            text-transform: uppercase;
        }

        .disclaimer p {
            font-size: 1.1rem;
            line-height: 1.8;
        }

        /* Equipe */
        #equipe {
            background: #1a1a1a;
        }

        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .team-member {
            text-align: center;
            padding: 30px;
            background: rgba(255,255,255,0.03);
            border-radius: 15px;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .team-member::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,62,62,0.1), transparent);
            transition: left 0.5s;
        }

        .team-member:hover::before {
            left: 100%;
        }

        .team-member:hover {
            transform: translateY(-10px);
            background: rgba(255,255,255,0.08);
        }

        .member-avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
        }

        .member-name {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 1.8rem;
            margin-bottom: 5px;
        }

        .member-role {
            color: var(--primary);
            text-transform: uppercase;
            letter-spacing: 0.1em;
            font-size: 0.9rem;
        }

        /* Contato */
        #contato {
            background: #0f0f0f;
            text-align: center;
        }

        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 25px;
            text-align: left;
        }

        .form-group label {
            display: block;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            font-size: 0.9rem;
            color: #aaa;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 15px;
            background: rgba(255,255,255,0.05);
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 5px;
            color: var(--light);
            font-family: 'Montserrat', sans-serif;
            transition: all 0.3s;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
            background: rgba(255,255,255,0.1);
        }

        .btn {
            display: inline-block;
            padding: 15px 50px;
            background: var(--primary);
            color: var(--light);
            text-decoration: none;
            text-transform: uppercase;
            letter-spacing: 0.2em;
            font-weight: 600;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
        }

        .btn:hover::before {
            left: 100%;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(255,62,62,0.4);
        }

        /* Footer */
        footer {
            background: #000;
            padding: 40px;
            text-align: center;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-bottom: 30px;
        }

        .social-links a {
            width: 50px;
            height: 50px;
            border: 2px solid rgba(255,255,255,0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--light);
            text-decoration: none;
            transition: all 0.3s;
        }

        .social-links a:hover {
            border-color: var(--primary);
            color: var(--primary);
            transform: rotate(360deg);
        }

        /* Efeito de filme antigo */
        .film-grain {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 9999;
            opacity: 0.03;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)'/%3E%3C/svg%3E");
        }

        /* ==========================================
           PAINEL ADMINISTRATIVO - LOGIN
           ========================================== */
        #admin-login-view {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #1a1a1a 0%, #0f0f0f 100%);
            z-index: 10000;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        #admin-login-view.active {
            display: flex;
        }

        .bg-animation {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.3;
        }

        .bg-animation::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: repeating-linear-gradient(
                0deg,
                transparent,
                transparent 2px,
                rgba(255, 62, 62, 0.03) 2px,
                rgba(255, 62, 62, 0.03) 4px
            );
            animation: scan 8s linear infinite;
        }

        @keyframes scan {
            0% { transform: translateY(0); }
            100% { transform: translateY(50px); }
        }

        .login-container {
            background: rgba(20, 20, 20, 0.95);
            padding: 60px;
            border-radius: 20px;
            border: 1px solid rgba(255, 62, 62, 0.3);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.8),
                        0 0 40px rgba(255, 62, 62, 0.1);
            width: 90%;
            max-width: 450px;
            position: relative;
            overflow: hidden;
        }

        .login-container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, #ff3e3e, #ffd700, #ff3e3e);
            background-size: 200% 100%;
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0% { background-position: -200% 0; }
            100% { background-position: 200% 0; }
        }

        .login-logo {
            text-align: center;
            margin-bottom: 40px;
        }

        .login-logo h1 {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 2.5rem;
            color: #ff3e3e;
            letter-spacing: 0.2em;
            margin-bottom: 10px;
            animation: none;
            text-shadow: none;
        }

        .login-logo p {
            color: #666;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 0.2em;
        }

        .login-form .form-group {
            margin-bottom: 25px;
        }

        .login-form label {
            display: block;
            color: #aaa;
            margin-bottom: 8px;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 0.1em;
        }

        .login-form input {
            width: 100%;
            padding: 15px 20px;
            background: rgba(255, 255, 255, 0.05);
            border: 2px solid rgba(255, 255, 255, 0.1);
            border-radius: 8px;
            color: #fff;
            font-size: 1rem;
            transition: all 0.3s;
            font-family: 'Montserrat', sans-serif;
        }

        .login-form input:focus {
            outline: none;
            border-color: #ff3e3e;
            background: rgba(255, 62, 62, 0.05);
            box-shadow: 0 0 20px rgba(255, 62, 62, 0.2);
        }

        .btn-login {
            width: 100%;
            padding: 18px;
            background: linear-gradient(45deg, #ff3e3e, #ff6b6b);
            border: none;
            border-radius: 8px;
            color: #fff;
            font-size: 1rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.2em;
            cursor: pointer;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
            margin-top: 10px;
        }

        .btn-login:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(255, 62, 62, 0.4);
        }

        .btn-login.loading {
            opacity: 0.8;
            pointer-events: none;
        }

        .error-message {
            background: rgba(255, 62, 62, 0.1);
            border: 1px solid rgba(255, 62, 62, 0.3);
            color: #ff6b6b;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
            display: none;
            align-items: center;
            gap: 10px;
            font-size: 0.9rem;
        }

        .error-message.show {
            display: flex;
            animation: shake 0.5s;
        }

        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-10px); }
            75% { transform: translateX(10px); }
        }

        .back-to-site {
            text-align: center;
            margin-top: 30px;
        }

        .back-to-site a {
            color: #666;
            text-decoration: none;
            font-size: 0.9rem;
            transition: color 0.3s;
            cursor: pointer;
        }

        .back-to-site a:hover {
            color: #ff3e3e;
        }

        /* ==========================================
           DASHBOARD ADMIN
           ========================================== */
        #admin-dashboard {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #0f0f0f;
            z-index: 10000;
        }

        #admin-dashboard.active {
            display: flex;
        }

        .admin-sidebar {
            width: var(--sidebar-width);
            background: linear-gradient(180deg, #1a1a1a 0%, #0f0f0f 100%);
            border-right: 1px solid rgba(255,255,255,0.1);
            height: 100vh;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
        }

        .admin-sidebar-header {
            padding: 30px;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            text-align: center;
        }

        .admin-sidebar-logo {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 1.8rem;
            color: var(--primary);
            letter-spacing: 0.1em;
        }

        .admin-user-info {
            padding: 20px 30px;
            background: rgba(255,62,62,0.05);
            border-bottom: 1px solid rgba(255,255,255,0.1);
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .admin-user-avatar {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
        }

        .admin-user-details h4 {
            font-size: 0.95rem;
            margin-bottom: 3px;
        }

        .admin-user-details span {
            font-size: 0.75rem;
            color: #888;
            text-transform: uppercase;
        }

        .admin-nav {
            flex: 1;
            padding: 20px 0;
        }

        .admin-nav-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 15px 30px;
            color: #aaa;
            text-decoration: none;
            transition: all 0.3s;
            border-left: 3px solid transparent;
            cursor: pointer;
            background: none;
            border: none;
            width: 100%;
            font-family: 'Montserrat', sans-serif;
            font-size: 0.95rem;
        }

        .admin-nav-item:hover, .admin-nav-item.active {
            background: rgba(255,62,62,0.1);
            color: #fff;
            border-left-color: var(--primary);
        }

        .admin-nav-item svg {
            width: 20px;
            height: 20px;
            opacity: 0.7;
        }

        .admin-sidebar-footer {
            padding: 20px 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        .admin-main {
            flex: 1;
            overflow-y: auto;
            padding: 40px;
        }

        .admin-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 40px;
            padding-bottom: 20px;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }

        .admin-header h1 {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 2.5rem;
            animation: none;
            text-shadow: none;
            margin: 0;
        }

        .admin-header p {
            color: #888;
            margin-top: 5px;
        }

        .admin-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .admin-stat-card {
            background: rgba(255,255,255,0.03);
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 15px;
            padding: 25px;
            transition: all 0.3s;
        }

        .admin-stat-card:hover {
            transform: translateY(-5px);
            border-color: rgba(255,62,62,0.3);
        }

        .admin-stat-icon {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            margin-bottom: 15px;
            background: rgba(255,62,62,0.1);
        }

        .admin-stat-value {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 2.5rem;
            margin-bottom: 5px;
        }

        .admin-stat-label {
            color: #888;
            font-size: 0.9rem;
        }

        /* Gerenciamento de Imagens no Admin */
        .admin-section {
            display: none;
        }

        .admin-section.active {
            display: block;
        }

        .image-categories {
            margin-bottom: 30px;
        }

        .category-group {
            margin-bottom: 40px;
        }

        .category-title {
            display: flex;
            align-items: center;
            gap: 10px;
            font-family: 'Bebas Neue', sans-serif;
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: #fff;
        }

        .category-badge {
            background: rgba(255,62,62,0.2);
            color: var(--primary);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-family: 'Montserrat', sans-serif;
        }

        .admin-images-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
        }

        .admin-image-card {
            background: rgba(255,255,255,0.03);
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 15px;
            overflow: hidden;
            transition: all 0.3s;
        }

        .admin-image-card:hover {
            border-color: rgba(255,62,62,0.3);
            transform: translateY(-5px);
            box-shadow: 0 10px 40px rgba(0,0,0,0.5);
        }

        .admin-image-preview {
            height: 180px;
            position: relative;
            overflow: hidden;
            background: #1a1a1a;
        }

        .admin-image-preview img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s;
        }

        .admin-image-card:hover .admin-image-preview img {
            transform: scale(1.05);
        }

        .admin-image-placeholder {
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(45deg, #2a2a2a, #1a1a1a);
            color: #555;
            font-size: 3rem;
        }

        .admin-image-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.7);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 0.3s;
        }

        .admin-image-card:hover .admin-image-overlay {
            opacity: 1;
        }

        .btn-view-image {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(255,255,255,0.2);
            border: 2px solid #fff;
            color: #fff;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .btn-view-image:hover {
            background: var(--primary);
            border-color: var(--primary);
            transform: scale(1.1);
        }

        .admin-image-info {
            padding: 20px;
        }

        .admin-image-info h4 {
            font-size: 1.1rem;
            margin-bottom: 8px;
        }

        .admin-image-info p {
            color: #888;
            font-size: 0.9rem;
            margin-bottom: 15px;
            line-height: 1.4;
        }

        .admin-image-meta {
            display: flex;
            gap: 15px;
            font-size: 0.8rem;
            color: #666;
            margin-bottom: 15px;
        }

        .admin-image-actions {
            display: flex;
            gap: 10px;
        }

        .btn-admin-action {
            flex: 1;
            padding: 10px;
            border: 1px solid rgba(255,255,255,0.1);
            background: rgba(255,255,255,0.05);
            color: #fff;
            border-radius: 8px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            font-size: 0.85rem;
            transition: all 0.3s;
            font-family: 'Montserrat', sans-serif;
        }

        .btn-admin-action:hover {
            background: rgba(255,255,255,0.1);
        }

        .btn-admin-edit {
            border-color: var(--primary);
            color: var(--primary);
        }

        .btn-admin-edit:hover {
            background: rgba(255,62,62,0.1);
        }

        /* Modal de Edição */
        .admin-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.9);
            z-index: 20000;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .admin-modal.active {
            display: flex;
        }

        .admin-modal-content {
            background: #1a1a1a;
            border-radius: 20px;
            width: 90%;
            max-width: 600px;
            max-height: 90vh;
            overflow-y: auto;
            border: 1px solid rgba(255,255,255,0.1);
            animation: modalSlide 0.3s ease;
        }

        @keyframes modalSlide {
            from { opacity: 0; transform: translateY(-50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .admin-modal-header {
            padding: 30px;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .admin-modal-header h2 {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 1.8rem;
        }

        .btn-close-modal {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255,255,255,0.1);
            border: none;
            color: #fff;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .btn-close-modal:hover {
            background: rgba(255,62,62,0.2);
            color: var(--primary);
            transform: rotate(90deg);
        }

        .admin-modal-body {
            padding: 30px;
        }

        .admin-form-group {
            margin-bottom: 25px;
        }

        .admin-form-group label {
            display: block;
            margin-bottom: 10px;
            color: #aaa;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }

        .admin-input {
            width: 100%;
            padding: 12px 15px;
            background: rgba(255,255,255,0.05);
            border: 2px solid rgba(255,255,255,0.1);
            border-radius: 8px;
            color: #fff;
            font-family: 'Montserrat', sans-serif;
            transition: all 0.3s;
        }

        .admin-input:focus {
            outline: none;
            border-color: var(--primary);
            background: rgba(255,62,62,0.05);
        }

        .file-upload-wrapper {
            position: relative;
            overflow: hidden;
            display: inline-block;
            width: 100%;
        }

        .file-upload-wrapper input[type=file] {
            position: absolute;
            left: -9999px;
        }

        .btn-file-upload {
            width: 100%;
            padding: 15px;
            background: rgba(255,255,255,0.05);
            border: 2px dashed rgba(255,255,255,0.2);
            border-radius: 8px;
            color: #aaa;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            transition: all 0.3s;
        }

        .btn-file-upload:hover {
            border-color: var(--primary);
            color: var(--primary);
            background: rgba(255,62,62,0.05);
        }

        .file-selected {
            margin-top: 10px;
            font-size: 0.9rem;
            color: var(--success);
        }

        .image-preview-box {
            margin-top: 20px;
            padding: 20px;
            background: rgba(0,0,0,0.3);
            border-radius: 10px;
            text-align: center;
            min-height: 200px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .image-preview-box img {
            max-width: 100%;
            max-height: 300px;
            border-radius: 8px;
            display: none;
        }

        .image-preview-box img.show {
            display: block;
        }

        .image-preview-box .no-image {
            color: #555;
            font-size: 4rem;
        }

        .admin-modal-footer {
            padding: 20px 30px 30px;
            display: flex;
            gap: 15px;
            justify-content: flex-end;
        }

        /* Notificações */
        .admin-notification {
            position: fixed;
            top: 30px;
            right: 30px;
            background: #1a1a1a;
            border-left: 4px solid var(--primary);
            padding: 20px 25px;
            border-radius: 10px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.5);
            transform: translateX(400px);
            opacity: 0;
            transition: all 0.3s;
            z-index: 30000;
        }

        .admin-notification.show {
            transform: translateX(0);
            opacity: 1;
        }

        .admin-notification.success { border-left-color: var(--success); }
        .admin-notification.error { border-left-color: var(--danger); }

        .notification-content {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .notification-icon {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            background: rgba(255,62,62,0.2);
            color: var(--primary);
        }

        .admin-notification.success .notification-icon {
            background: rgba(40,167,69,0.2);
            color: var(--success);
        }

        /* Lightbox */
        .admin-lightbox {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.95);
            z-index: 25000;
            align-items: center;
            justify-content: center;
            padding: 40px;
        }

        .admin-lightbox.active {
            display: flex;
        }

        .lightbox-content {
            position: relative;
            max-width: 90%;
            max-height: 90%;
        }

        .admin-lightbox img {
            max-width: 100%;
            max-height: 85vh;
            border-radius: 10px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.8);
        }

        .btn-lightbox-close {
            position: absolute;
            top: -50px;
            right: 0;
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border: none;
            border-radius: 50%;
            color: #fff;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .btn-lightbox-close:hover {
            background: var(--primary);
            transform: rotate(90deg);
        }

        .lightbox-caption {
            position: absolute;
            bottom: -50px;
            left: 0;
            right: 0;
            text-align: center;
            color: #aaa;
            font-size: 1.1rem;
        }

        /* Responsivo */
        @media (max-width: 768px) {
            h1 { font-size: 4rem; }
            .nav-links { display: none; }
            .about-content { grid-template-columns: 1fr; }
            .safety-content { grid-template-columns: 1fr; }
            .stats { grid-template-columns: 1fr; }
            
            .admin-sidebar {
                position: fixed;
                transform: translateX(-100%);
                z-index: 10001;
                transition: transform 0.3s;
            }
            
            .admin-sidebar.active {
                transform: translateX(0);
            }
            
            .admin-main {
                margin-left: 0;
            }
            
            .menu-toggle-admin {
                display: flex !important;
            }
        }

        .menu-toggle-admin {
            display: none;
            position: fixed;
            top: 20px;
            left: 20px;
            z-index: 10002;
            width: 45px;
            height: 45px;
            background: rgba(26,26,26,0.95);
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 10px;
            color: #fff;
            cursor: pointer;
            align-items: center;
            justify-content: center;
        }

        /* Utilitários */
        .hidden { display: none !important; }
    </style>
</head>
<body>
    <div class="film-grain"></div>

    <!-- ==========================================
         VISÃO DO SITE (PÚBLICO)
         ========================================== -->
    <div id="site-view">
        <!-- Navegação -->
        <nav id="navbar">
            <div class="logo-nav">DESENROLADOS</div>
            <ul class="nav-links">
                <li><a href="#sobre">Sobre</a></li>
                <li><a href="#projetos">Projetos</a></li>
                <li><a href="#seguranca">⚠️ Segurança</a></li>
                <li><a href="#equipe">Equipe</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>
            <button class="btn-admin-login" onclick="showAdminLogin()">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" style="vertical-align: middle; margin-right: 5px;">
                    <rect x="3" y="11" width="18" height="11" rx="2" ry="2"></rect>
                    <path d="M7 11V7a5 5 0 0 1 10 0v4"></path>
                </svg>
                Admin
            </button>
        </nav>

        <!-- Hero -->
        <header id="hero-section">
            <div class="clapperboard"></div>
            <h1>DESENROLADOS</h1>
            <p class="tagline">Grupo de Gravação de Séries Independentes</p>
            <div class="scroll-indicator">
                <svg width="30" height="30" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2">
                    <path d="M12 5v14M19 12l-7 7-7-7"/>
                </svg>
            </div>
        </header>

        <!-- Sobre -->
        <section id="sobre">
            <h2 class="section-title">Quem Somos</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>O <strong>Desenrolados</strong> é um coletivo de cineastas independentes apaixonados por contar histórias autênticas e envolventes. Desde 2020, produzimos séries de ação, suspense e drama com produção profissional e orçamento criativo.</p>
                    <p>Nossa missão é democratizar a produção audiovisual, provando que histórias incríveis não precisam de grandes estúdios para ganharem vida.</p>
                    <div class="stats">
                        <div class="stat-item">
                            <div class="stat-number">15+</div>
                            <div class="stat-label">Projetos</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-number">50+</div>
                            <div class="stat-label">Membros</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-number">3</div>
                            <div class="stat-label">Anos</div>
                        </div>
                    </div>
                </div>
                <div class="about-image">
                    <div style="background: linear-gradient(45deg, #333, #555); height: 400px; border-radius: 20px; display: flex; align-items: center; justify-content: center; font-size: 4rem;">
                        🎬
                    </div>
                </div>
            </div>
        </section>

        <!-- Projetos -->
        <section id="projetos">
            <h2 class="section-title">Nossos Projetos</h2>
            <div class="gallery">
                <div class="gallery-item" data-image-id="projeto-1">
                    <img src="https://images.unsplash.com/photo-1536440136628-849c177e76a1?w=600" alt="Operação Final">
                    <div class="gallery-overlay">
                        <h3 class="gallery-title">Operação Final</h3>
                        <p>Série de ação - 2023</p>
                    </div>
                </div>
                <div class="gallery-item" data-image-id="projeto-2">
                    <img src="https://images.unsplash.com/photo-1596727147705-54a9d099308d?w=600" alt="Código Zero">
                    <div class="gallery-overlay">
                        <h3 class="gallery-title">Código Zero</h3>
                        <p>Thriller policial - 2024</p>
                    </div>
                </div>
                <div class="gallery-item" data-image-id="projeto-3">
                    <img src="https://images.unsplash.com/photo-1478720568477-152d9b164e26?w=600" alt="Linha de Frente">
                    <div class="gallery-overlay">
                        <h3 class="gallery-title">Linha de Frente</h3>
                        <p>Drama militar - Em produção</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Segurança -->
        <section id="seguranca">
            <div class="safety-container">
                <div class="safety-header">
                    <div class="safety-icon">⚠️</div>
                    <h2 class="section-title" style="margin-bottom: 10px;">Aviso Importante</h2>
                    <p style="color: #aaa; font-size: 1.1rem;">Informações sobre nossas gravações e segurança</p>
                </div>

                <div class="safety-content">
                    <div class="safety-box">
                        <h3>🎬 Cenas de Ação</h3>
                        <ul>
                            <li>Todas as cenas são <strong>fictícias</strong> e para fins de entretenimento</li>
                            <li>Gravações realizadas em locais controlados e autorizados</li>
                            <li>Equipe treinada em protocolos de segurança</li>
                            <li>Sinalização visível durante as gravações</li>
                            <li>Comunicação prévia com autoridades locais</li>
                        </ul>
                    </div>

                    <div class="safety-box">
                        <h3>🔫 Equipamentos de Airsoft/Paintball</h3>
                        <ul>
                            <li>Armas utilizadas são <strong>réplicas de airsoft</strong> (6mm)</li>
                            <li>Equipamentos de paintball para efeitos especiais</li>
                            <li>Todas as armas são desprovidas de capacidade letal</li>
                            <li>Uso obrigatório de proteções (óculos, coletes)</li>
                            <li>Armazenamento seguro e transporte legalizado</li>
                        </ul>
                    </div>
                </div>

                <div class="disclaimer">
                    <h4>⚠️ Atenção</h4>
                    <p><strong>As cenas de violência, tiroteios e confrontos armados exibidas em nossas produções são inteiramente fictícias e realizadas exclusivamente para fins de gravação cinematográfica.</strong></p>
                    <p style="margin-top: 15px; font-size: 0.95rem; color: #888;">
                        Não tentem reproduzir nenhuma das cenas em casa. O uso de réplicas de airsoft e paintball deve seguir todas as leis e regulamentações locais. 
                        Sempre priorizamos a segurança de nossa equipe e do público em todas as produções.
                    </p>
                </div>
            </div>
        </section>

        <!-- Equipe -->
        <section id="equipe">
            <h2 class="section-title">Nossa Equipe</h2>
            <div class="team-grid">
                <div class="team-member">
                    <div class="member-avatar">🎥</div>
                    <h3 class="member-name">Carlos Silva</h3>
                    <p class="member-role">Diretor</p>
                </div>
                <div class="team-member">
                    <div class="member-avatar">📝</div>
                    <h3 class="member-name">Ana Paula</h3>
                    <p class="member-role">Roteirista</p>
                </div>
                <div class="team-member">
                    <div class="member-avatar">🎬</div>
                    <h3 class="member-name">Marcos Oliveira</h3>
                    <p class="member-role">Diretor de Fotografia</p>
                </div>
                <div class="team-member">
                    <div class="member-avatar">💥</div>
                    <h3 class="member-name">Julia Costa</h3>
                    <p class="member-role">Coordenadora de Ação</p>
                </div>
            </div>
        </section>

        <!-- Contato -->
        <section id="contato">
            <h2 class="section-title">Entre em Contato</h2>
            <div class="contact-form">
                <form onsubmit="event.preventDefault(); alert('Mensagem enviada!');">
                    <div class="form-group">
                        <label>Nome</label>
                        <input type="text" placeholder="Seu nome" required>
                    </div>
                    <div class="form-group">
                        <label>Email</label>
                        <input type="email" placeholder="seu@email.com" required>
                    </div>
                    <div class="form-group">
                        <label>Mensagem</label>
                        <textarea rows="5" placeholder="Conte-nos sobre seu projeto..." required></textarea>
                    </div>
                    <button type="submit" class="btn">Enviar Mensagem</button>
                </form>
            </div>
        </section>

        <!-- Footer -->
        <footer>
            <div class="social-links">
                <a href="#">📷</a>
                <a href="#">🎬</a>
                <a href="#">📺</a>
                <a href="#">🎵</a>
            </div>
            <p>&copy; 2024 Desenrolados. Todos os direitos reservados.</p>
            <p style="margin-top: 10px; color: #666; font-size: 0.9rem;">Grupo de Gravação de Séries Independentes</p>
        </footer>
    </div>

    <!-- ==========================================
         LOGIN ADMIN
         ========================================== -->
    <div id="admin-login-view">
        <div class="bg-animation"></div>
        
        <div class="login-container">
            <div class="login-logo">
                <h1>DESENROLADOS</h1>
                <p>Painel Administrativo</p>
            </div>

            <div class="error-message" id="loginError">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <circle cx="12" cy="12" r="10"></circle>
                    <line x1="12" y1="8" x2="12" y2="12"></line>
                    <line x1="12" y1="16" x2="12.01" y2="16"></line>
                </svg>
                <span id="loginErrorText">Credenciais inválidas</span>
            </div>

            <form class="login-form" id="loginForm" onsubmit="handleLogin(event)">
                <div class="form-group">
                    <label for="username">Usuário</label>
                    <input type="text" id="username" name="username" required autocomplete="username">
                </div>

                <div class="form-group">
                    <label for="password">Senha</label>
                    <input type="password" id="password" name="password" required autocomplete="current-password">
                </div>

                <button type="submit" class="btn-login" id="btnLogin">
                    Entrar no Sistema
                </button>
            </form>

            <div class="back-to-site">
                <a onclick="backToSite()">← Voltar para o site</a>
            </div>
        </div>
    </div>

    <!-- ==========================================
         DASHBOARD ADMIN
         ========================================== -->
    <div id="admin-dashboard">
        <button class="menu-toggle-admin" onclick="toggleAdminSidebar()">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <line x1="3" y1="12" x2="21" y2="12"></line>
                <line x1="3" y1="6" x2="21" y2="6"></line>
                <line x1="3" y1="18" x2="21" y2="18"></line>
            </svg>
        </button>

        <aside class="admin-sidebar" id="adminSidebar">
            <div class="admin-sidebar-header">
                <div class="admin-sidebar-logo">DESENROLADOS</div>
                <div style="color: #666; font-size: 0.8rem; text-transform: uppercase; letter-spacing: 0.2em;">Painel Admin</div>
            </div>

            <div class="admin-user-info">
                <div class="admin-user-avatar">👤</div>
                <div class="admin-user-details">
                    <h4 id="adminUsername">Admin</h4>
                    <span id="adminRole">Super Admin</span>
                </div>
            </div>

            <nav class="admin-nav">
                <button class="admin-nav-item active" onclick="showAdminSection('images')">
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <rect x="3" y="3" width="18" height="18" rx="2" ry="2"></rect>
                        <circle cx="8.5" cy="8.5" r="1.5"></circle>
                        <polyline points="21 15 16 10 5 21"></polyline>
                    </svg>
                    Gerenciar Imagens
                </button>
                <button class="admin-nav-item" onclick="showAdminSection('preview')">
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"></path>
                        <circle cx="12" cy="12" r="3"></circle>
                    </svg>
                    Visualizar Site
                </button>
            </nav>

            <div class="admin-sidebar-footer">
                <button class="btn-logout" onclick="logout()">
                    <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M9 21H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h4"></path>
                        <polyline points="16 17 21 12 16 7"></polyline>
                        <line x1="21" y1="12" x2="9" y2="12"></line>
                    </svg>
                    Sair do Sistema
                </button>
            </div>
        </aside>

        <main class="admin-main">
            <!-- Seção: Gerenciar Imagens -->
            <div id="admin-section-images" class="admin-section active">
                <div class="admin-header">
                    <div>
                        <h1>Gerenciamento de Imagens</h1>
                        <p>Atualize as imagens do site em tempo real</p>
                    </div>
                    <button class="btn-primary" onclick="backToSiteFromAdmin()">
                        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                            <polyline points="15 3 21 3 21 9"></polyline>
                        </svg>
                        Ver Site Publicado
                    </button>
                </div>

                <div class="admin-stats">
                    <div class="admin-stat-card">
                        <div class="admin-stat-icon">🖼️</div>
                        <div class="admin-stat-value" id="statTotalImages">5</div>
                        <div class="admin-stat-label">Total de Imagens</div>
                    </div>
                    <div class="admin-stat-card">
                        <div class="admin-stat-icon">✓</div>
                        <div class="admin-stat-value" id="statModifiedImages">0</div>
                        <div class="admin-stat-label">Imagens Alteradas</div>
                    </div>
                    <div class="admin-stat-card">
                        <div class="admin-stat-icon">⚡</div>
                        <div class="admin-stat-value" style="font-size: 1.5rem; margin-top: 10px;">Ao Vivo</div>
                        <div class="admin-stat-label">Atualizações em Tempo Real</div>
                    </div>
                </div>

                <div class="image-categories" id="imageCategories">
                    <!-- Populado via JavaScript -->
                </div>
            </div>

            <!-- Seção: Preview do Site -->
            <div id="admin-section-preview" class="admin-section">
                <div class="admin-header">
                    <div>
                        <h1>Preview do Site</h1>
                        <p>Visualize como o site está aparecendo para os visitantes</p>
                    </div>
                </div>
                <div style="background: #000; border-radius: 15px; overflow: hidden; border: 1px solid rgba(255,255,255,0.1);">
                    <iframe id="sitePreview" style="width: 100%; height: 70vh; border: none;"></iframe>
                </div>
            </div>
        </main>
    </div>

    <!-- ==========================================
         MODAIS E OVERLAYS
         ========================================== -->
    
    <!-- Modal de Edição -->
    <div class="admin-modal" id="editImageModal">
        <div class="admin-modal-content">
            <div class="admin-modal-header">
                <h2>Editar Imagem: <span id="modalImageName"></span></h2>
                <button class="btn-close-modal" onclick="closeEditModal()">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <line x1="18" y1="6" x2="6" y2="18"></line>
                        <line x1="6" y1="6" x2="18" y2="18"></line>
                    </svg>
                </button>
            </div>
            <div class="admin-modal-body">
                <input type="hidden" id="modalImageId">
                
                <div class="admin-form-group">
                    <label>URL da Imagem</label>
                    <input type="text" class="admin-input" id="newImageUrl" placeholder="https://exemplo.com/imagem.jpg">
                </div>

                <div class="admin-form-group">
                    <label>Ou faça upload de arquivo</label>
                    <div class="file-upload-wrapper">
                        <input type="file" id="newImageFile" accept="image/*" onchange="handleFileSelect(this)">
                        <label for="newImageFile" class="btn-file-upload">
                            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                                <polyline points="17 8 12 3 7 8"></polyline>
                                <line x1="12" y1="3" x2="12" y2="15"></line>
                            </svg>
                            Escolher arquivo
                        </label>
                    </div>
                    <div class="file-selected" id="fileSelectedName"></div>
                </div>

                <div class="image-preview-box">
                    <img id="modalImagePreview" src="" alt="Preview">
                    <div class="no-image" id="modalNoImage">🖼️</div>
                </div>
            </div>
            <div class="admin-modal-footer">
                <button class="btn-secondary" onclick="closeEditModal()">Cancelar</button>
                <button class="btn-primary" onclick="saveImageChanges()">
                    <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M19 21H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h11l5 5v11a2 2 0 0 1-2 2z"></path>
                        <polyline points="17 21 17 13 7 13 7 21"></polyline>
                        <polyline points="7 3 7 8 15 8"></polyline>
                    </svg>
                    Salvar Alterações
                </button>
            </div>
        </div>
    </div>

    <!-- Lightbox -->
    <div class="admin-lightbox" id="imageLightbox" onclick="closeLightbox(event)">
        <div class="lightbox-content">
            <button class="btn-lightbox-close" onclick="closeLightboxBtn(event)">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <line x1="18" y1="6" x2="6" y2="18"></line>
                    <line x1="6" y1="6" x2="18" y2="18"></line>
                </svg>
            </button>
            <img id="lightboxImage" src="" alt="">
            <div class="lightbox-caption" id="lightboxCaption"></div>
        </div>
    </div>

    <!-- Notificação -->
    <div class="admin-notification" id="adminNotification">
        <div class="notification-content">
            <div class="notification-icon" id="notifIcon">✓</div>
            <span id="notifText">Operação realizada com sucesso!</span>
        </div>
    </div>

    <!-- ==========================================
         JAVASCRIPT - SISTEMA COMPLETO
         ========================================== -->
    <script>
        // ==========================================
        // CONFIGURAÇÃO E DADOS
        // ==========================================
        
        const CONFIG = {
            admins: [
                { username: 'admin', password: 'desenrolados2024', role: 'superadmin' },
                { username: 'editor', password: 'edit123', role: 'editor' }
            ],
            defaultImages: {
                'hero-bg': {
                    id: 'hero-bg',
                    name: 'Background Hero',
                    current: 'https://images.unsplash.com/photo-1485846234645-a62644f84728?w=1920',
                    category: 'header',
                    description: 'Imagem de fundo da página inicial',
                    selector: '#hero-section',
                    property: 'backgroundImage',
                    prefix: 'linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url("',
                    suffix: '")'
                },
                'projeto-1': {
                    id: 'projeto-1',
                    name: 'Operação Final',
                    current: 'https://images.unsplash.com/photo-1536440136628-849c177e76a1?w=600',
                    category: 'projetos',
                    description: 'Cartaz da série Operação Final',
                    selector: '.gallery-item[data-image-id="projeto-1"] img',
                    attribute: 'src'
                },
                'projeto-2': {
                    id: 'projeto-2',
                    name: 'Código Zero',
                    current: 'https://images.unsplash.com/photo-1596727147705-54a9d099308d?w=600',
                    category: 'projetos',
                    description: 'Cartaz da série Código Zero',
                    selector: '.gallery-item[data-image-id="projeto-2"] img',
                    attribute: 'src'
                },
                'projeto-3': {
                    id: 'projeto-3',
                    name: 'Linha de Frente',
                    current: 'https://images.unsplash.com/photo-1478720568477-152d9b164e26?w=600',
                    category: 'projetos',
                    description: 'Cartaz da série Linha de Frente',
                    selector: '.gallery-item[data-image-id="projeto-3"] img',
                    attribute: 'src'
                },
                'seguranca-bg': {
                    id: 'seguranca-bg',
                    name: 'Background Segurança',
                    current: 'https://images.unsplash.com/photo-1595590424283-b8f17842773f?w=1920',
                    category: 'seguranca',
                    description: 'Imagem de fundo da seção de segurança',
                    selector: '#seguranca',
                    property: 'backgroundImage',
                    prefix: 'linear-gradient(rgba(0,0,0,0.9), rgba(0,0,0,0.9)), url("',
                    suffix: '") center/cover fixed'
                }
            }
        };

        // Estado global
        let currentUser = null;
        let siteImages = {};
        let currentEditId = null;

        // ==========================================
        // INICIALIZAÇÃO
        // ==========================================

        document.addEventListener('DOMContentLoaded', function() {
            initImages();
            checkSession();
            setupEventListeners();
            applyImagesToSite();
        });

        function initImages() {
            const saved = localStorage.getItem('desenrolados_images');
            if (saved) {
                siteImages = JSON.parse(saved);
            } else {
                siteImages = JSON.parse(JSON.stringify(CONFIG.defaultImages));
                saveImages();
            }
            updateStats();
        }

        function saveImages() {
            localStorage.setItem('desenrolados_images', JSON.stringify(siteImages));
        }

        // ==========================================
        // AUTENTICAÇÃO
        // ==========================================

        function checkSession() {
            const session = localStorage.getItem('desenrolados_session');
            if (session) {
                const parsed = JSON.parse(session);
                if (parsed.expires > Date.now()) {
                    currentUser = parsed.user;
                } else {
                    localStorage.removeItem('desenrolados_session');
                }
            }
        }

        function showAdminLogin() {
            document.getElementById('site-view').style.display = 'none';
            document.getElementById('admin-login-view').classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function backToSite() {
            document.getElementById('admin-login-view').classList.remove('active');
            document.getElementById('site-view').style.display = 'block';
            document.body.style.overflow = '';
            document.getElementById('loginForm').reset();
            document.getElementById('loginError').classList.remove('show');
        }

        function handleLogin(e) {
            e.preventDefault();
            
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            const btn = document.getElementById('btnLogin');
            
            btn.classList.add('loading');
            btn.textContent = 'Verificando...';
            
            setTimeout(() => {
                const admin = CONFIG.admins.find(a => a.username === username && a.password === password);
                
                if (admin) {
                    const session = {
                        user: { username: admin.username, role: admin.role },
                        expires: Date.now() + (24 * 60 * 60 * 1000)
                    };
                    localStorage.setItem('desenrolados_session', JSON.stringify(session));
                    currentUser = session.user;
                    
                    enterDashboard();
                } else {
                    document.getElementById('loginErrorText').textContent = 'Credenciais inválidas';
                    document.getElementById('loginError').classList.add('show');
                    btn.classList.remove('loading');
                    btn.textContent = 'Entrar no Sistema';
                }
            }, 800);
        }

        function enterDashboard() {
            document.getElementById('admin-login-view').classList.remove('active');
            document.getElementById('admin-dashboard').classList.add('active');
            
            document.getElementById('adminUsername').textContent = currentUser.username;
            document.getElementById('adminRole').textContent = currentUser.role === 'superadmin' ? 'Super Admin' : 'Editor';
            
            renderImageManager();
            updateStats();
        }

        function logout() {
            localStorage.removeItem('desenrolados_session');
            currentUser = null;
            document.getElementById('admin-dashboard').classList.remove('active');
            document.getElementById('site-view').style.display = 'block';
            document.body.style.overflow = '';
            
            // Resetar formulário de login
            document.getElementById('loginForm').reset();
            document.getElementById('btnLogin').classList.remove('loading');
            document.getElementById('btnLogin').textContent = 'Entrar no Sistema';
        }

        // ==========================================
        // NAVEGAÇÃO ADMIN
        // ==========================================

        function showAdminSection(section) {
            // Atualizar navegação
            document.querySelectorAll('.admin-nav-item').forEach(item => item.classList.remove('active'));
            event.target.closest('.admin-nav-item').classList.add('active');
            
            // Mostrar seção
            document.querySelectorAll('.admin-section').forEach(s => s.classList.remove('active'));
            document.getElementById(`admin-section-${section}`).classList.add('active');
            
            // Fechar sidebar mobile
            if (window.innerWidth <= 768) {
                document.getElementById('adminSidebar').classList.remove('active');
            }
            
            // Se for preview, atualizar iframe
            if (section === 'preview') {
                updateSitePreview();
            }
        }

        function toggleAdminSidebar() {
            document.getElementById('adminSidebar').classList.toggle('active');
        }

        function backToSiteFromAdmin() {
            document.getElementById('admin-dashboard').classList.remove('active');
            document.getElementById('site-view').style.display = 'block';
            document.body.style.overflow = '';
            window.scrollTo(0, 0);
        }

        // ==========================================
        // GERENCIAMENTO DE IMAGENS
        // ==========================================

        function renderImageManager() {
            const container = document.getElementById('imageCategories');
            const categories = {};
            
            // Agrupar por categoria
            Object.values(siteImages).forEach(img => {
                if (!categories[img.category]) {
                    categories[img.category] = [];
                }
                categories[img.category].push(img);
            });
            
            const categoryNames = {
                'header': 'Cabeçalho',
                'projetos': 'Projetos',
                'seguranca': 'Segurança'
            };
            
            const categoryIcons = {
                'header': '🎬',
                'projetos': '🎞️',
                'seguranca': '⚠️'
            };
            
            let html = '';
            
            for (const [cat, images] of Object.entries(categories)) {
                html += `
                    <div class="category-group">
                        <h3 class="category-title">
                            <span>${categoryIcons[cat] || '🖼️'}</span>
                            ${categoryNames[cat] || cat}
                            <span class="category-badge">${images.length}</span>
                        </h3>
                        <div class="admin-images-grid">
                            ${images.map(img => createImageCard(img)).join('')}
                        </div>
                    </div>
                `;
            }
            
            container.innerHTML = html;
        }

        function createImageCard(img) {
            const hasImage = img.current && !img.isGradient;
            const lastMod = img.lastModified ? 
                new Date(img.lastModified).toLocaleDateString('pt-BR') : 
                'Padrão';
            
            return `
                <div class="admin-image-card">
                    <div class="admin-image-preview">
                        ${hasImage ? 
                            `<img src="${img.current}" alt="${img.name}" id="preview-${img.id}">` :
                            `<div class="admin-image-placeholder">🎨</div>`
                        }
                        <div class="admin-image-overlay">
                            <button class="btn-view-image" onclick="viewImage('${img.id}')">
                                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"></path>
                                    <circle cx="12" cy="12" r="3"></circle>
                                </svg>
                            </button>
                        </div>
                    </div>
                    <div class="admin-image-info">
                        <h4>${img.name}</h4>
                        <p>${img.description}</p>
                        <div class="admin-image-meta">
                            <span>🕐 ${lastMod}</span>
                            ${img.fileSize ? `<span>📦 ${img.fileSize}</span>` : ''}
                        </div>
                        <div class="admin-image-actions">
                            <button class="btn-admin-action btn-admin-edit" onclick="openEditModal('${img.id}')">
                                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <path d="M11 4H4a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2v-7"></path>
                                    <path d="M18.5 2.5a2.121 2.121 0 0 1 3 3L12 15l-4 1 1-4 9.5-9.5z"></path>
                                </svg>
                                Alterar
                            </button>
                            <button class="btn-admin-action" onclick="resetImage('${img.id}')" style="${!img.lastModified ? 'opacity: 0.5; pointer-events: none;' : ''}">
                                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <polyline points="1 4 1 10 7 10"></polyline>
                                    <path d="M3.51 15a9 9 0 1 0 2.13-9.36L1 10"></path>
                                </svg>
                                Resetar
                            </button>
                        </div>
                    </div>
                </div>
            `;
        }

        // ==========================================
        // EDIÇÃO DE IMAGENS
        // ==========================================

        function openEditModal(id) {
            currentEditId = id;
            const img = siteImages[id];
            
            document.getElementById('modalImageName').textContent = img.name;
            document.getElementById('modalImageId').value = id;
            document.getElementById('newImageUrl').value = img.current || '';
            document.getElementById('newImageFile').value = '';
            document.getElementById('fileSelectedName').textContent = '';
            
            updateModalPreview(img.current);
            
            document.getElementById('editImageModal').classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeEditModal() {
            document.getElementById('editImageModal').classList.remove('active');
            document.body.style.overflow = '';
            currentEditId = null;
        }

        function handleFileSelect(input) {
            const file = input.files[0];
            if (file) {
                document.getElementById('fileSelectedName').textContent = `📁 ${file.name} (${formatFileSize(file.size)})`;
                
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById('newImageUrl').value = e.target.result;
                    updateModalPreview(e.target.result);
                };
                reader.readAsDataURL(file);
            }
        }

        function updateModalPreview(src) {
            const preview = document.getElementById('modalImagePreview');
            const noImage = document.getElementById('modalNoImage');
            
            if (src) {
                preview.src = src;
                preview.classList.add('show');
                noImage.style.display = 'none';
            } else {
                preview.classList.remove('show');
                noImage.style.display = 'block';
            }
        }

        function saveImageChanges() {
            const url = document.getElementById('newImageUrl').value;
            const fileInput = document.getElementById('newImageFile');
            
            if (!url && !fileInput.files[0]) {
                showNotification('Por favor, forneça uma URL ou selecione um arquivo', 'error');
                return;
            }

            const img = siteImages[currentEditId];
            img.current = url;
            img.lastModified = new Date().toISOString();
            img.modifiedBy = currentUser.username;
            
            if (fileInput.files[0]) {
                img.fileSize = formatFileSize(fileInput.files[0].size);
            }
            
            saveImages();
            applyImagesToSite();
            renderImageManager();
            updateStats();
            closeEditModal();
            showNotification('Imagem atualizada com sucesso!', 'success');
            updateSitePreview();
        }

        function resetImage(id) {
            if (!confirm('Tem certeza que deseja voltar à imagem padrão?')) return;
            
            const defaults = CONFIG.defaultImages;
            if (defaults[id]) {
                siteImages[id].current = defaults[id].current;
                delete siteImages[id].lastModified;
                delete siteImages[id].modifiedBy;
                delete siteImages[id].fileSize;
                
                saveImages();
                applyImagesToSite();
                renderImageManager();
                updateStats();
                showNotification('Imagem restaurada ao padrão!', 'success');
                updateSitePreview();
            }
        }

        // ==========================================
        // APLICAÇÃO DE IMAGENS NO SITE
        // ==========================================

        function applyImagesToSite() {
            Object.values(siteImages).forEach(img => {
                if (!img.current) return;
                
                const element = document.querySelector(img.selector);
                if (!element) return;
                
                if (img.attribute) {
                    element.setAttribute(img.attribute, img.current);
                } else if (img.property) {
                    const value = (img.prefix || '') + img.current + (img.suffix || '');
                    element.style[img.property] = value;
                }
            });
        }

        function updateSitePreview() {
            const iframe = document.getElementById('sitePreview');
            if (iframe && document.getElementById('admin-section-preview').classList.contains('active')) {
                iframe.src = 'about:blank';
                setTimeout(() => {
                    iframe.src = window.location.href;
                }, 100);
            }
        }

        // ==========================================
        // VISUALIZAÇÃO
        // ==========================================

        function viewImage(id) {
            const img = siteImages[id];
            if (!img.current) return;
            
            document.getElementById('lightboxImage').src = img.current;
            document.getElementById('lightboxCaption').textContent = img.name;
            document.getElementById('imageLightbox').classList.add('active');
        }

        function closeLightbox(e) {
            if (e.target.id === 'imageLightbox') {
                document.getElementById('imageLightbox').classList.remove('active');
            }
        }

        function closeLightboxBtn(e) {
            e.stopPropagation();
            document.getElementById('imageLightbox').classList.remove('active');
        }

        // ==========================================
        // ESTATÍSTICAS E UTILITÁRIOS
        // ==========================================

        function updateStats() {
            const total = Object.keys(siteImages).length;
            const modified = Object.values(siteImages).filter(img => img.lastModified).length;
            
            document.getElementById('statTotalImages').textContent = total;
            document.getElementById('statModifiedImages').textContent = modified;
        }

        function showNotification(message, type = 'success') {
            const notif = document.getElementById('adminNotification');
            const icon = document.getElementById('notifIcon');
            const text = document.getElementById('notifText');
            
            text.textContent = message;
            icon.textContent = type === 'success' ? '✓' : '✕';
            
            notif.className = `admin-notification ${type} show`;
            
            setTimeout(() => {
                notif.classList.remove('show');
            }, 3000);
        }

        function formatFileSize(bytes) {
            if (bytes === 0) return '0 Bytes';
            const k = 1024;
            const sizes = ['Bytes', 'KB', 'MB'];
            const i = Math.floor(Math.log(bytes) / Math.log(k));
            return parseFloat((bytes / Math.pow(k, i)).toFixed(2)) + ' ' + sizes[i];
        }

        // ==========================================
        // EVENT LISTENERS
        // ==========================================

        function setupEventListeners() {
            // Navbar scroll effect
            window.addEventListener('scroll', () => {
                const navbar = document.getElementById('navbar');
                if (window.scrollY > 100) {
                    navbar.classList.add('scrolled');
                } else {
                    navbar.classList.remove('scrolled');
                }
            });

            // Smooth scroll
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        target.scrollIntoView({ behavior: 'smooth' });
                    }
                });
            });

            // Fechar modal com ESC
            document.addEventListener('keydown', (e) => {
                if (e.key === 'Escape') {
                    closeEditModal();
                    document.getElementById('imageLightbox').classList.remove('active');
                }
            });

            // Sincronização entre abas
            window.addEventListener('storage', (e) => {
                if (e.key === 'desenrolados_images') {
                    siteImages = JSON.parse(e.newValue);
                    applyImagesToSite();
                    if (document.getElementById('admin-dashboard').classList.contains('active')) {
                        renderImageManager();
                        updateStats();
                    }
                }
            });
        }
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anjali Dasunika | Software Engineering Portfolio</title>
    
    <!-- Google Fonts Import -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600;700&family=Inter:wght@300;400;600&family=Poppins:wght@600;700;800&display=swap" rel="stylesheet">

    <style>
        :root {
            --bg-color: #0d0d0d;
            --bg-secondary: #181818;
            --text-color: #e0e0e0;
            --heading-color: #ffffff;
            --accent-color: #a29bfe;
            --accent-hover: #81ecec;
            --card-bg: #181818;
            --card-shadow: rgba(0, 0, 0, 0.6);
            --nav-bg: rgba(18, 18, 18, 0.95);
            --hero-bg: linear-gradient(135deg, #09090e 0%, #121019 50%, #0d0d0d 100%);
            --tag-bg: #252525;
            --bar-bg: #2a2a2a;
            --bubble-color: rgba(162, 155, 254, 0.1);
            --bubble-border: rgba(162, 155, 254, 0.2);
            --pink-led-color: #ff1493;
            --purple-btn-bg: linear-gradient(135deg, #6c5ce7 0%, #8e44ad 100%);
            --purple-btn-glow: rgba(142, 68, 173, 0.6);
        }

        [data-theme="light"] {
            --bg-color: #fcfcfc;
            --bg-secondary: #f8f9fa;
            --text-color: #333333;
            --heading-color: #2c3e50;
            --accent-color: #6c5ce7;
            --accent-hover: #5b4bc4;
            --card-bg: #ffffff;
            --card-shadow: rgba(0, 0, 0, 0.08);
            --nav-bg: rgba(255, 255, 255, 0.95);
            --hero-bg: linear-gradient(135deg, #e2e8f0 0%, #cbd5e1 100%);
            --tag-bg: #eef2f7;
            --bar-bg: #e0e0e0;
            --bubble-color: rgba(108, 92, 231, 0.15);
            --bubble-border: rgba(108, 92, 231, 0.25);
            --pink-led-color: #d61c6a;
            --purple-btn-bg: linear-gradient(135deg, #8e44ad 0%, #6c5ce7 100%);
            --purple-btn-glow: rgba(108, 92, 231, 0.5);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', sans-serif;
            transition: background-color 0.3s ease, color 0.3s ease;
        }

        h1, h2, h3, .logo {
            font-family: 'Poppins', sans-serif;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--bg-color);
            position: relative;
            overflow-x: hidden;
            padding-top: 70px;
        }

        /* Floating Background Bubbles */
        .bubbles-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
            overflow: hidden;
        }

        .bubble {
            position: absolute;
            bottom: -100px;
            background: var(--bubble-color);
            border: 1px solid var(--bubble-border);
            border-radius: 50%;
            backdrop-filter: blur(2px);
            animation: rise 12s infinite linear;
        }

        @keyframes rise {
            0% { transform: translateY(0) scale(0.8) rotate(0deg); opacity: 0; }
            10% { opacity: 0.8; }
            90% { opacity: 0.8; }
            100% { transform: translateY(-120vh) scale(1.2) rotate(360deg); opacity: 0; }
        }

        header, section, footer {
            position: relative;
            z-index: 1;
        }

        /* Header & Navigation */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 9999;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 8%;
            background-color: var(--nav-bg);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            box-shadow: 0 4px 15px var(--card-shadow);
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--heading-color);
        }

        .logo span {
            color: var(--accent-color);
        }

        .nav-right {
            display: flex;
            align-items: center;
            gap: 2rem;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 1.2rem;
            align-items: center;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-color);
            font-weight: 600;
            display: inline-block;
            padding: 0.5rem 1.1rem;
            border-radius: 8px;
            border: 2px solid transparent;
            transition: transform 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275), color 0.3s ease, border-color 0.3s ease, box-shadow 0.3s ease;
        }

        .nav-links a:hover {
            color: #ffffff;
            transform: scale(1.2);
            border-color: var(--pink-led-color);
            box-shadow: 0 0 12px var(--pink-led-color), inset 0 0 8px rgba(255, 20, 147, 0.4);
            background-color: rgba(255, 20, 147, 0.1);
        }

        .theme-toggle {
            background: var(--purple-btn-bg);
            border: 2px solid #a29bfe;
            color: #ffffff;
            padding: 0.65rem 1.6rem;
            border-radius: 30px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 700;
            letter-spacing: 0.5px;
            box-shadow: 0 4px 15px var(--purple-btn-glow);
            transition: transform 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275), box-shadow 0.3s ease, border-color 0.3s ease;
        }

        .theme-toggle:hover {
            transform: scale(1.1);
            box-shadow: 0 6px 22px var(--purple-btn-glow), 0 0 12px #9b59b6;
            border-color: #ffffff;
        }

        /* Hero Section Container */
        .hero {
            position: relative;
            min-height: calc(100vh - 70px);
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 8%;
            background: var(--hero-bg);
            overflow: hidden;
        }

        .hero-text {
            flex: 1;
            text-align: left;
            z-index: 2;
            padding-right: 2rem;
        }

        .hero-text h1 {
            font-size: 4.8rem;
            font-weight: 800;
            letter-spacing: -1.5px;
            margin-bottom: 1rem;
            color: var(--heading-color);
            line-height: 1.15;
            animation: zoomInStop 1.2s cubic-bezier(0.25, 1, 0.5, 1) forwards;
        }

        @keyframes zoomInStop {
            0% { opacity: 0; transform: scale(0.2); }
            100% { opacity: 1; transform: scale(1); }
        }

        .water-wave-text {
            background: linear-gradient(-45deg, #00d2ff, #3a7bd5, #00c6ff, #0072ff, #7F00FF);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: waterFlow 5s ease-in-out infinite alternate;
            display: inline-block;
        }

        @keyframes waterFlow {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .highlight {
            background: linear-gradient(135deg, #a29bfe 0%, #74b9ff 50%, #e84393 100%);
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientShift 4s ease infinite;
            display: inline-block;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .hero-text p {
            font-size: 1.45rem;
            font-weight: 300;
            line-height: 1.8;
            margin-bottom: 2rem;
            opacity: 0.95;
            min-height: 70px;
        }

        .cursor {
            display: inline-block;
            color: var(--accent-color);
            font-weight: 600;
            animation: blink 0.7s infinite;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        .btn-pink-border {
            position: relative;
            display: inline-block;
            padding: 2px;
            color: var(--heading-color);
            font-size: 1.15rem;
            font-weight: 700;
            text-decoration: none;
            letter-spacing: 0.5px;
            background: transparent;
            border-radius: 30px;
            z-index: 1;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .btn-pink-border::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(transparent 70%, #c71585 85%, #ff1493 95%, #ff69b4 100%);
            animation: rotateBorder 3.5s linear infinite;
            z-index: -2;
        }

        .btn-pink-border span {
            display: block;
            padding: 0.85rem 2.2rem;
            background: transparent;
            border-radius: 28px;
            backdrop-filter: blur(8px);
            -webkit-backdrop-filter: blur(8px);
        }

        @keyframes rotateBorder {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .btn-pink-border:hover {
            transform: scale(1.05);
            box-shadow: 0 0 15px rgba(255, 20, 147, 0.5);
            color: #ffffff;
        }

        /* HERO PURE CSS AVATAR PLACEHOLDER (NO IMAGE REQUIRED) */
        .hero-avatar-wrapper {
            flex: 1;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 2;
        }

        .hero-avatar-card {
            width: 320px;
            height: 320px;
            border-radius: 50%;
            background: linear-gradient(135deg, rgba(162, 155, 254, 0.2), rgba(255, 20, 147, 0.2));
            border: 3px solid rgba(162, 155, 254, 0.4);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            backdrop-filter: blur(10px);
            box-shadow: 0 0 40px rgba(162, 155, 254, 0.2), inset 0 0 20px rgba(255, 20, 147, 0.15);
            animation: pulseGlow 4s ease-in-out infinite alternate;
        }

        @keyframes pulseGlow {
            0% { transform: scale(1); box-shadow: 0 0 30px rgba(162, 155, 254, 0.2); }
            100% { transform: scale(1.04); box-shadow: 0 0 50px rgba(255, 20, 147, 0.4); }
        }

        .hero-avatar-icon {
            font-size: 5.5rem;
            margin-bottom: 0.5rem;
            filter: drop-shadow(0 4px 8px rgba(0,0,0,0.5));
        }

        .hero-avatar-tag {
            font-family: 'Fira Code', monospace;
            font-size: 1.1rem;
            font-weight: 700;
            color: #a29bfe;
            background: rgba(0, 0, 0, 0.4);
            padding: 4px 14px;
            border-radius: 12px;
            border: 1px solid rgba(162, 155, 254, 0.3);
        }

        .section {
            padding: 5rem 8%;
            text-align: center;
        }

        .bg-secondary {
            background-color: var(--bg-secondary);
        }

        .section h2 {
            font-size: 2.2rem;
            margin-bottom: 2rem;
            color: var(--heading-color);
        }

        /* About Section */
        .about-layout-container {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 3rem;
        }

        .about-col-left {
            flex: 1;
            text-align: left;
        }

        .id-outer-container {
            flex: 1;
            height: 380px;
            border: none;
            background: transparent;
            display: flex;
            align-items: center;
            justify-content: flex-start;
            padding: 20px;
            position: relative;
            overflow: hidden;
        }

        .student-id-card {
            width: 310px;
            background: linear-gradient(145deg, #1f1c2c, #928dab);
            border: 2px solid var(--accent-color);
            border-radius: 16px;
            padding: 20px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.5), 0 0 15px rgba(162, 155, 254, 0.4);
            position: relative;
            overflow: hidden;
            animation: floatLeftRight 6s ease-in-out infinite alternate;
        }

        @keyframes floatLeftRight {
            0% { transform: translateX(0px) rotate(-1deg); }
            50% { transform: translateX(calc(100% - 70px)) rotate(1deg); }
            100% { transform: translateX(0px) rotate(-1deg); }
        }

        .id-stripe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 8px;
            background: linear-gradient(90deg, #ff1493, #6c5ce7, #00d2ff, #ff1493);
            background-size: 300% 100%;
            animation: stripeAnimation 3s linear infinite;
        }

        @keyframes stripeAnimation {
            0% { background-position: 0% 0%; }
            100% { background-position: 100% 0%; }
        }

        .id-scan-line {
            position: absolute;
            top: -100%;
            left: 0;
            width: 100%;
            height: 40%;
            background: linear-gradient(to bottom, transparent, rgba(255, 20, 147, 0.25), transparent);
            animation: scanLine 3.5s ease-in-out infinite;
            pointer-events: none;
        }

        @keyframes scanLine {
            0% { top: -40%; }
            50% { top: 100%; }
            100% { top: -40%; }
        }

        .id-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.2);
            padding-bottom: 10px;
            margin-bottom: 15px;
            margin-top: 5px;
        }

        .id-header h4 {
            font-size: 1.1rem;
            font-weight: 800;
            color: #ffffff;
            letter-spacing: 1.5px;
        }

        .id-badge {
            background: #ff1493;
            color: #ffffff;
            font-size: 0.65rem;
            font-weight: 700;
            padding: 3px 8px;
            border-radius: 10px;
            text-transform: uppercase;
        }

        .id-body { text-align: left; }
        .id-name { font-size: 1.15rem; font-weight: 700; color: #ffffff; margin-bottom: 4px; }
        .id-uni { font-size: 0.95rem; color: #81ecec; font-weight: 600; margin-bottom: 8px; }

        .id-details {
            font-size: 0.85rem;
            color: #e0e0e0;
            line-height: 1.5;
            background: rgba(0, 0, 0, 0.25);
            padding: 10px;
            border-radius: 8px;
            border-left: 3px solid #a29bfe;
        }

        .id-details span { display: block; }

        .about-discord-outline {
            font-family: 'Fira Code', monospace !important;
            font-size: 2.2rem !important;
            font-weight: 700;
            letter-spacing: 3px;
            color: transparent;
            -webkit-text-stroke: 2px #d8b4fe;
            text-shadow: 0 0 10px rgba(181, 23, 158, 0.8), 0 0 20px rgba(114, 9, 183, 0.6);
            text-transform: uppercase;
            margin-bottom: 2rem !important;
        }

        .about-heading-cursor {
            display: inline-block;
            color: #d8b4fe;
            font-weight: 700;
            text-shadow: 0 0 8px #b5179e;
            animation: blink 0.7s infinite;
        }

        .about-text {
            font-family: 'Fira Code', monospace !important;
            font-size: 1.05rem;
            line-height: 1.8;
            opacity: 0;
            transform: translateY(50px);
            transition: opacity 1.2s ease-out, transform 1.2s cubic-bezier(0.25, 1, 0.5, 1);
            color: var(--text-color);
        }

        .about-text.slide-up {
            opacity: 1;
            transform: translateY(0);
        }

        /* SPLIT SECTION LAYOUT */
        .skills-cert-wrapper {
            display: flex;
            align-items: stretch;
            justify-content: space-between;
            gap: 3rem;
        }

        .skills-cert-col {
            flex: 1;
            text-align: left;
        }

        .skills-fancy-title {
            font-family: 'Poppins', sans-serif !important;
            font-size: 1.8rem !important;
            font-weight: 700;
            letter-spacing: 1.5px;
            color: #ffb6c1;
            text-shadow: 0 0 8px #ff69b4, 0 0 20px #ff1493;
            margin-bottom: 2rem !important;
            text-transform: uppercase;
        }

        /* PURPLE LASER BORDER CERTIFICATE CARD */
        .cert-card-outer {
            position: relative;
            background: rgba(18, 18, 28, 0.85);
            border-radius: 20px;
            padding: 2rem;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-height: 440px;
            border: 1px solid rgba(142, 68, 173, 0.3);
            backdrop-filter: blur(10px);
        }

        .cert-card-outer::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(transparent 70%, #8e44ad 85%, #d8b4fe 95%, #9b59b6 100%);
            animation: rotatePurpleLaser 4s linear infinite;
            z-index: 0;
        }

        .cert-card-outer::after {
            content: '';
            position: absolute;
            inset: 3px;
            background: var(--card-bg);
            border-radius: 17px;
            z-index: 1;
        }

        @keyframes rotatePurpleLaser {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .cert-card-content {
            position: relative;
            z-index: 2;
            display: flex;
            flex-direction: column;
            height: 100%;
            align-items: center;
        }

        .cert-title {
            font-size: 1.6rem;
            font-weight: 800;
            color: #d8b4fe;
            text-shadow: 0 0 10px rgba(142, 68, 173, 0.7);
            margin-bottom: 1.5rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            text-align: center;
        }

        /* FLOATING EMOJIS */
        .cert-emojis-direct-container {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 2.5rem;
            margin: 1.5rem 0 2rem 0;
        }

        .direct-emoji {
            font-size: 3.8rem;
            line-height: 1;
            filter: drop-shadow(0 6px 12px rgba(0,0,0,0.5));
            transition: transform 0.3s ease;
        }

        .direct-emoji:hover {
            transform: scale(1.25) !important;
        }

        .float-anim-1 { animation: floatEmojiOne 3.2s ease-in-out infinite alternate; }
        .float-anim-2 { animation: floatEmojiTwo 3.8s ease-in-out infinite alternate; }
        .float-anim-3 { animation: floatEmojiThree 3.5s ease-in-out infinite alternate; }

        @keyframes floatEmojiOne {
            0% { transform: translateY(0px) rotate(-6deg); }
            100% { transform: translateY(-16px) rotate(8deg); }
        }

        @keyframes floatEmojiTwo {
            0% { transform: translateY(-14px) rotate(6deg); }
            100% { transform: translateY(8px) rotate(-6deg); }
        }

        @keyframes floatEmojiThree {
            0% { transform: translateY(6px) rotate(-8deg); }
            100% { transform: translateY(-14px) rotate(5deg); }
        }

        .btn-view-certs {
            margin-top: 0.5rem;
            background: linear-gradient(135deg, #8e44ad 0%, #6c5ce7 100%);
            color: #ffffff;
            font-weight: 700;
            padding: 0.75rem 1.8rem;
            border-radius: 30px;
            text-decoration: none;
            font-size: 0.95rem;
            letter-spacing: 0.5px;
            box-shadow: 0 0 15px rgba(142, 68, 173, 0.6);
            border: 1px solid #d8b4fe;
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .btn-view-certs:hover {
            transform: scale(1.08);
            box-shadow: 0 0 25px rgba(216, 180, 254, 0.8), 0 0 10px #8e44ad;
        }

        /* SCHOOL & WALKING STUDENT TRACK */
        .school-walk-track-container {
            margin-top: auto;
            width: 100%;
            padding-top: 1rem;
            border-top: 1px dashed rgba(216, 180, 254, 0.2);
            position: relative;
            height: 75px;
            display: flex;
            align-items: center;
            overflow: hidden;
        }

        .school-icon-left {
            font-size: 2.5rem;
            position: absolute;
            left: 10px;
            bottom: 10px;
            z-index: 2;
            filter: drop-shadow(0 2px 8px rgba(0,0,0,0.6));
        }

        .student-walking-emoji {
            position: absolute;
            right: 10px;
            bottom: 12px;
            font-size: 2.3rem;
            animation: walkToSchool 6s linear infinite;
            filter: drop-shadow(0 2px 6px rgba(0,0,0,0.5));
        }

        @keyframes walkToSchool {
            0% { right: 15px; opacity: 1; transform: translateY(0px) rotate(0deg); }
            25% { transform: translateY(-4px) rotate(-4deg); }
            50% { transform: translateY(0px) rotate(4deg); }
            75% { transform: translateY(-4px) rotate(-4deg); }
            85% { right: calc(100% - 65px); opacity: 1; }
            92% { opacity: 0; }
            100% { right: 15px; opacity: 0; }
        }

        /* BLACK OVERLAY MODAL PAGE FOR CERTIFICATES */
        .cert-modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(5, 5, 5, 0.95);
            backdrop-filter: blur(15px);
            z-index: 99999;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.4s ease;
        }

        .cert-modal-overlay.active {
            opacity: 1;
            pointer-events: auto;
        }

        .modal-close-btn {
            position: absolute;
            top: 25px;
            right: 35px;
            font-size: 2.2rem;
            color: #ff4757;
            cursor: pointer;
            background: transparent;
            border: none;
            font-weight: 800;
            transition: transform 0.3s ease, color 0.3s ease;
        }

        .modal-close-btn:hover {
            transform: scale(1.2) rotate(90deg);
            color: #ff6b81;
        }

        /* MAROON / DARK RED LASER BORDER CERTIFICATE CARD */
        .maroon-laser-card {
            position: relative;
            width: 90%;
            max-width: 650px;
            background: #0d0608;
            border-radius: 20px;
            padding: 2.5rem 2rem;
            overflow: hidden;
            box-shadow: 0 0 35px rgba(128, 0, 32, 0.6), 0 0 15px rgba(255, 0, 50, 0.3);
            text-align: center;
        }

        .maroon-laser-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(transparent 70%, #800020 85%, #ff003c 95%, #b00020 100%);
            animation: rotateMaroonLaser 3.5s linear infinite;
            z-index: 0;
        }

        .maroon-laser-card::after {
            content: '';
            position: absolute;
            inset: 3px;
            background: #120509;
            border-radius: 17px;
            z-index: 1;
        }

        @keyframes rotateMaroonLaser {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .maroon-card-content {
            position: relative;
            z-index: 2;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .maroon-card-title {
            font-size: 1.8rem;
            font-weight: 800;
            color: #ff4d6d;
            text-shadow: 0 0 12px rgba(255, 0, 60, 0.7);
            margin-bottom: 0.3rem;
            text-transform: uppercase;
            letter-spacing: 1.5px;
        }

        .maroon-card-subtitle {
            font-size: 1.15rem;
            font-weight: 600;
            color: #ff85a1;
            margin-bottom: 1.2rem;
        }

        .certificate-holder-box {
            width: 100%;
            height: 260px;
            border: 2px dashed rgba(255, 77, 109, 0.4);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(40, 0, 15, 0.4);
            color: #ffb3c1;
            font-size: 0.95rem;
            overflow: hidden;
            padding: 10px;
        }

        #certCanvas {
            max-width: 100%;
            max-height: 100%;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
        }

        .cert-nav-btns {
            margin-top: 1.2rem;
            display: flex;
            gap: 1rem;
            justify-content: center;
        }

        /* Skills Progress Bar */
        .skills-container { width: 100%; text-align: left; }
        .skill-item { margin-bottom: 1.5rem; }
        .skill-info { display: flex; justify-content: space-between; margin-bottom: 0.5rem; font-weight: 600; }
        .skill-name-math-script { font-family: 'Fira Code', monospace; font-size: 1.05rem; font-weight: 600; color: var(--heading-color); }
        .progress-bar { width: 100%; height: 10px; background-color: var(--bar-bg); border-radius: 5px; overflow: hidden; }
        .progress { height: 100%; background-color: var(--accent-color); width: 0%; transition: width 1.5s ease-in-out; }

        /* 3D CIRCULAR CAROUSEL PROJECTS SECTION */
        .carousel-wrapper {
            position: relative;
            width: 100%;
            height: 380px;
            margin-top: 2rem;
            display: flex;
            justify-content: center;
            align-items: center;
            perspective: 1000px;
            overflow: visible;
        }

        .project-card {
            position: absolute;
            width: 380px;
            min-height: 260px;
            background: var(--card-bg);
            padding: 2rem;
            border-radius: 16px;
            box-shadow: 0 10px 30px var(--card-shadow);
            text-align: left;
            border: 1px solid rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(8px);
            cursor: pointer;
            user-select: none;
            transition: transform 0.6s cubic-bezier(0.25, 1, 0.5, 1), opacity 0.6s ease, z-index 0.6s ease, box-shadow 0.6s ease, border-color 0.6s ease;
        }

        /* Center / Focused Active Card */
        .project-card.active {
            transform: translateX(0) scale(1.15) translateZ(50px);
            z-index: 10;
            opacity: 1;
            border-color: var(--accent-color);
            box-shadow: 0 15px 35px rgba(162, 155, 254, 0.35), 0 0 15px rgba(162, 155, 254, 0.2);
        }

        /* Left Side Cards */
        .project-card.left {
            transform: translateX(-340px) scale(0.85) translateZ(-50px) rotateY(15deg);
            z-index: 5;
            opacity: 0.55;
        }

        /* Right Side Cards */
        .project-card.right {
            transform: translateX(340px) scale(0.85) translateZ(-50px) rotateY(-15deg);
            z-index: 5;
            opacity: 0.55;
        }

        /* Hidden Cards (if more than 3 cards added) */
        .project-card.hidden {
            transform: translateX(0) scale(0.5) translateZ(-100px);
            z-index: 1;
            opacity: 0;
            pointer-events: none;
        }

        .project-card:hover {
            opacity: 1;
        }

        .project-card h3 { 
            margin-bottom: 0.8rem; 
            color: var(--heading-color); 
            font-size: 1.3rem;
        }
        
        .tags { margin-top: 1.2rem; }
        .tags span { 
            display: inline-block; 
            background: var(--tag-bg); 
            color: var(--accent-color); 
            padding: 0.3rem 0.8rem; 
            font-size: 0.85rem; 
            border-radius: 20px; 
            margin-right: 0.5rem; 
            margin-bottom: 0.5rem; 
        }

        /* Contact Section with CSS Gradient Background */
        #contact {
            position: relative;
            background: linear-gradient(135deg, rgba(24, 24, 24, 0.95), rgba(13, 13, 13, 0.98)),
                        radial-gradient(circle at top right, rgba(162, 155, 254, 0.15), transparent);
            border: 1px solid rgba(255, 255, 255, 0.08);
            color: #ffffff;
            border-radius: 16px;
            margin: 2rem 8%;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }

        #contact h2 {
            color: #ffffff;
            text-shadow: 0 0 10px rgba(0, 210, 255, 0.5);
        }

        .contact-info p { margin: 0.8rem 0; font-size: 1.1rem; }
        .contact-info a { color: #81ecec; text-decoration: none; font-weight: 600; transition: color 0.3s ease; }
        .contact-info a:hover { color: #a29bfe; text-decoration: underline; }

        footer { padding: 1.5rem; background-color: var(--bg-secondary); color: var(--text-color); text-align: center; font-size: 0.9rem; border-top: 1px solid var(--bar-bg); }

        @media (max-width: 900px) {
            .hero { padding: 4rem 5%; flex-direction: column; justify-content: center; }
            .hero-text { padding-right: 0; text-align: center; }
            .hero-text h1 { font-size: 3.2rem; }
            .hero-text p { font-size: 1.2rem; }
            .hero-avatar-wrapper { margin-top: 2rem; width: 100%; }
            .about-layout-container, .skills-cert-wrapper { flex-direction: column; }
            .id-outer-container { width: 100%; }
            .project-card { width: 290px; }
            .project-card.left { transform: translateX(-160px) scale(0.8); }
            .project-card.right { transform: translateX(160px) scale(0.8); }
            #contact { margin: 2rem 4%; }
        }
    </style>
</head>
<body>

    <div class="bubbles-container" id="bubblesContainer"></div>

    <header>
        <nav class="navbar">
            <div class="logo">Anjali<span>.dev</span></div>
            <div class="nav-right">
                <ul class="nav-links">
                    <li><a href="#about">About</a></li>
                    <li><a href="#skills">Skills & Certs</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <button class="theme-toggle" id="themeToggle">☀️ Light Mode</button>
            </div>
        </nav>
    </header>

    <section id="hero" class="hero">
        <div class="hero-text">
            <h1>
                <span class="water-wave-text">Hi, I'm</span> <br>
                <span class="highlight">Anjali Dasunika</span>
            </h1>
            <p><span id="typing-text"></span><span class="cursor">|</span></p>
            <a href="#projects" class="btn-pink-border">
                <span>View My Work</span>
            </a>
        </div>

        <div class="hero-avatar-wrapper">
            <div class="hero-avatar-card">
                <span class="hero-avatar-icon">👩‍💻</span>
                <span class="hero-avatar-tag">&lt;SoftwareEngineer /&gt;</span>
            </div>
        </div>
    </section>

    <!-- About Me Section -->
    <section id="about" class="section">
        <div class="about-layout-container">
            <div class="about-col-left">
                <h2 class="about-discord-outline">
                    <span id="aboutTopicTyped"></span><span class="about-heading-cursor" id="aboutTopicCursor">|</span>
                </h2>
                <p class="about-text" id="aboutText">
                    I am a Software Engineering undergraduate dedicated to writing clean, maintainable code and developing responsive web applications. With practical experience building database-driven web platforms and interactive user applications, I enjoy bringing designs to life and solving real-world engineering challenges.
                </p>
            </div>

            <div class="id-outer-container">
                <div class="student-id-card">
                    <div class="id-stripe"></div>
                    <div class="id-scan-line"></div>
                    <div class="id-header">
                        <h4>STUDENT ID</h4>
                        <span class="id-badge">VERIFIED</span>
                    </div>
                    <div class="id-body">
                        <div class="id-name">Anjali Dasunika Thathsarani</div>
                        <div class="id-uni">KIU University</div>
                        <div class="id-details">
                            <span><strong>Program:</strong> Software Engineering</span>
                            <span><strong>Academic Year:</strong> 2nd Year Student</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Split Section: MY CERTIFICATES & TECHNICAL PROFICIENCY -->
    <section id="skills" class="section bg-secondary">
        <div class="skills-cert-wrapper">
            
            <!-- LEFT COLUMN: CERTIFICATES CARD WITH SCHOOL & WALKING STUDENT ANIMATION -->
            <div class="skills-cert-col">
                <div class="cert-card-outer">
                    <div class="cert-card-content">
                        <h2 class="cert-title">MY CERTIFICATES</h2>
                        
                        <!-- FLOATING REAL EMOJIS -->
                        <div class="cert-emojis-direct-container">
                            <span class="direct-emoji float-anim-1" title="Papers">📜</span>
                            <span class="direct-emoji float-anim-2" title="Certificate">🎓</span>
                            <span class="direct-emoji float-anim-3" title="Books">📚</span>
                        </div>

                        <!-- Action Button (Opens Black Page Overlay) -->
                        <button class="btn-view-certs" id="openCertModal">View My Certificates</button>

                        <!-- Bottom Track: School on Left, Walking Student Animated to School -->
                        <div class="school-walk-track-container">
                            <span class="school-icon-left" title="School">🏫</span>
                            <span class="student-walking-emoji" title="Student Walking">🚶‍♀️</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- RIGHT COLUMN: FEATURED TECHNICAL PROFICIENCY -->
            <div class="skills-cert-col">
                <h2 class="skills-fancy-title">FEATURED TECHNICAL PROFICIENCY</h2>
                
                <div class="skills-container">
                    <div class="skill-item">
                        <div class="skill-info">
                            <span class="skill-name-math-script">HTML5 / CSS3 / JavaScript</span>
                            <span>90%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress" data-width="90%"></div>
                        </div>
                    </div>

                    <div class="skill-item">
                        <div class="skill-info">
                            <span class="skill-name-math-script">Python</span>
                            <span>85%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress" data-width="85%"></div>
                        </div>
                    </div>

                    <div class="skill-item">
                        <div class="skill-info">
                            <span class="skill-name-math-script">PHP & MySQL</span>
                            <span>80%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress" data-width="80%"></div>
                        </div>
                    </div>

                    <div class="skill-item">
                        <div class="skill-info">
                            <span class="skill-name-math-script">Java</span>
                            <span>75%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress" data-width="75%"></div>
                        </div>
                    </div>
                </div>
            </div>

        </div>
    </section>

    <!-- BLACK PAGE CERTIFICATE MODAL OVERLAY -->
    <div class="cert-modal-overlay" id="certModal">
        <button class="modal-close-btn" id="closeCertModal">&times;</button>
        <div class="maroon-laser-card">
            <div class="maroon-card-content">
                <h3 class="maroon-card-title" id="certTitle">Moratuwa University</h3>
                <h4 class="maroon-card-subtitle" id="certSubtitle">(DP Education)</h4>
                
                <div class="certificate-holder-box">
                    <canvas id="certCanvas" width="500" height="300"></canvas>
                </div>

                <div class="cert-nav-btns">
                    <button class="btn-view-certs" id="prevCertBtn" style="padding: 0.4rem 1.2rem; font-size: 0.85rem;">&larr; Prev</button>
                    <button class="btn-view-certs" id="nextCertBtn" style="padding: 0.4rem 1.2rem; font-size: 0.85rem;">Next &rarr;</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Projects Section (3D Circular Horizontal Carousel) -->
    <section id="projects" class="section">
        <h2>Featured Projects</h2>
        <div class="carousel-wrapper" id="carouselWrapper">
            <div class="project-card">
                <h3>Chop & Chill Restaurant Website</h3>
                <p>Full-stack restaurant application integrated with a backend database. Includes functional form handling, dynamic menu display, and online contact workflows.</p>
                <div class="tags"><span>PHP</span><span>MySQL</span><span>HTML5</span><span>CSS3</span></div>
            </div>
            <div class="project-card">
                <h3>Python Desktop Calculator</h3>
                <p>Functional desktop application implementing arithmetic calculation routines along with persistent session history tracking and clean GUI layouts.</p>
                <div class="tags"><span>Python</span><span>GUI</span><span>Algorithms</span></div>
            </div>
            <div class="project-card">
                <h3>Interactive Web Portfolios & Apps</h3>
                <p>Custom single-page applications engineered with dynamic light/dark UI themes, responsive progress indicators, and client-side interactions.</p>
                <div class="tags"><span>JavaScript</span><span>DOM API</span><span>CSS Grid</span></div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section">
        <h2>Get In Touch</h2>
        <p>Currently open to software engineering internships, open-source projects, and collaborative opportunities.</p>
        <br>
        <div class="contact-info">
            <p><strong>Email:</strong> <a href="mailto:anjalidthathsarani11@gmail.com">anjalidthathsarani11@gmail.com</a></p>
            <p><strong>GitHub:</strong> <a href="https://github.com/anjali-thathsarani" target="_blank" rel="noopener noreferrer">github.com/anjali-thathsarani</a></p>
            <p><strong>LinkedIn:</strong> <a href="https://linkedin.com/in/anjali-dasunika" target="_blank" rel="noopener noreferrer">linkedin.com/in/anjali-dasunika</a></p>
        </div>
    </section>

    <footer>
        <p>&copy; 2026 Anjali Dasunika. Built with HTML, CSS, and JavaScript.</p>
    </footer>

    <script>
        // Floating Bubbles
        const bubblesContainer = document.getElementById('bubblesContainer');
        for (let i = 0; i < 18; i++) {
            const bubble = document.createElement('div');
            bubble.classList.add('bubble');
            const size = Math.random() * 60 + 20;
            bubble.style.width = `${size}px`;
            bubble.style.height = `${size}px`;
            bubble.style.left = `${Math.random() * 100}%`;
            bubble.style.animationDuration = `${Math.random() * 10 + 8}s`;
            bubble.style.animationDelay = `${Math.random() * 8}s`;
            bubblesContainer.appendChild(bubble);
        }

        // Theme Toggle
        const toggleBtn = document.getElementById('themeToggle');
        toggleBtn.addEventListener('click', () => {
            const currentTheme = document.documentElement.getAttribute('data-theme');
            if (currentTheme === 'light') {
                document.documentElement.removeAttribute('data-theme');
                toggleBtn.textContent = '☀️ Light Mode';
            } else {
                document.documentElement.setAttribute('data-theme', 'light');
                toggleBtn.textContent = '🌙 Dark Mode';
            }
        });

        // Certificate Data Array
        const certificates = [
            {
                title: "University of Moratuwa",
                subtitle: "(DP Education - Python Coding)",
                certName: "Certificate of Completion",
                field: "Python Programming"
            },
            {
                title: "Full-Stack Web Development",
                subtitle: "(Interactive Applications & PHP)",
                certName: "Certificate of Achievement",
                field: "Web Development"
            }
        ];

        let currentCertIndex = 0;

        const certModal = document.getElementById('certModal');
        const openCertModalBtn = document.getElementById('openCertModal');
        const closeCertModalBtn = document.getElementById('closeCertModal');
        const certTitle = document.getElementById('certTitle');
        const certSubtitle = document.getElementById('certSubtitle');
        const certCanvas = document.getElementById('certCanvas');
        const prevCertBtn = document.getElementById('prevCertBtn');
        const nextCertBtn = document.getElementById('nextCertBtn');

        function drawCertificateCanvas() {
            const ctx = certCanvas.getContext('2d');
            const data = certificates[currentCertIndex];

            // Background
            ctx.fillStyle = "#1a0810";
            ctx.fillRect(0, 0, 500, 300);

            // Border
            ctx.strokeStyle = "#ff4d6d";
            ctx.lineWidth = 6;
            ctx.strokeRect(15, 15, 470, 270);
            
            ctx.strokeStyle = "#8e44ad";
            ctx.lineWidth = 2;
            ctx.strokeRect(22, 22, 456, 256);

            // Text Rendering
            ctx.fillStyle = "#ff85a1";
            ctx.font = "bold 16px 'Poppins', sans-serif";
            ctx.textAlign = "center";
            ctx.fillText(data.title.toUpperCase(), 250, 65);

            ctx.fillStyle = "#d8b4fe";
            ctx.font = "13px 'Inter', sans-serif";
            ctx.fillText(data.subtitle, 250, 90);

            ctx.fillStyle = "#ffffff";
            ctx.font = "bold 22px 'Poppins', sans-serif";
            ctx.fillText(data.certName, 250, 150);

            ctx.fillStyle = "#a29bfe";
            ctx.font = "14px 'Fira Code', monospace";
            ctx.fillText("Specialization: " + data.field, 250, 185);

            ctx.fillStyle = "#ff4d6d";
            ctx.font = "bold 12px 'Inter', sans-serif";
            ctx.fillText("AWARDED TO: ANJALI DASUNIKA", 250, 235);
        }

        function updateCertificateView() {
            certTitle.textContent = certificates[currentCertIndex].title;
            certSubtitle.textContent = certificates[currentCertIndex].subtitle;
            drawCertificateCanvas();
        }

        openCertModalBtn.addEventListener('click', () => {
            updateCertificateView();
            certModal.classList.add('active');
        });

        closeCertModalBtn.addEventListener('click', () => {
            certModal.classList.remove('active');
        });

        certModal.addEventListener('click', (e) => {
            if (e.target === certModal) {
                certModal.classList.remove('active');
            }
        });

        prevCertBtn.addEventListener('click', () => {
            currentCertIndex = (currentCertIndex - 1 + certificates.length) % certificates.length;
            updateCertificateView();
        });

        nextCertBtn.addEventListener('click', () => {
            currentCertIndex = (currentCertIndex + 1) % certificates.length;
            updateCertificateView();
        });

        // Skill Bar Animation
        const progressBars = document.querySelectorAll('.progress');
        const animatedSkills = () => {
            progressBars.forEach(bar => {
                const rect = bar.getBoundingClientRect();
                if (rect.top < window.innerHeight && rect.bottom >= 0) {
                    bar.style.width = bar.getAttribute('data-width');
                }
            });
        };

        // Hero Typing Effect
        const textArray = [
            "Undergraduate Software Engineering Student passionate about full-stack web development.",
            "Specializing in modern software architecture & clean code design.",
            "Building responsive web apps and interactive UI experiences."
        ];
        let arrayIndex = 0, charIndex = 0;
        const typingTextElement = document.getElementById("typing-text");

        function type() {
            if (charIndex < textArray[arrayIndex].length) {
                typingTextElement.textContent += textArray[arrayIndex].charAt(charIndex);
                charIndex++;
                setTimeout(type, 50);
            } else {
                setTimeout(erase, 2200);
            }
        }

        function erase() {
            if (charIndex > 0) {
                typingTextElement.textContent = textArray[arrayIndex].substring(0, charIndex - 1);
                charIndex--;
                setTimeout(erase, 25);
            } else {
                arrayIndex = (arrayIndex + 1) % textArray.length;
                setTimeout(type, 400);
            }
        }

        // About Section Typing Animation
        const aboutTextString = "ABOUT ME";
        let topicCharIdx = 0, aboutSectionStarted = false;
        const aboutTopicTyped = document.getElementById('aboutTopicTyped');
        const aboutTopicCursor = document.getElementById('aboutTopicCursor');
        const aboutTextElem = document.getElementById('aboutText');

        function typeAboutTopic() {
            if (topicCharIdx < aboutTextString.length) {
                aboutTopicTyped.textContent += aboutTextString.charAt(topicCharIdx);
                topicCharIdx++;
                setTimeout(typeAboutTopic, 120);
            } else {
                setTimeout(() => { aboutTopicCursor.style.display = 'none'; }, 800);
            }
        }

        const handleAboutScroll = () => {
            const rect = aboutTextElem.getBoundingClientRect();
            if (rect.top < window.innerHeight - 80 && !aboutSectionStarted) {
                aboutSectionStarted = true;
                typeAboutTopic();
                aboutTextElem.classList.add('slide-up');
            }
        };

        // 3D CIRCULAR CAROUSEL INTERACTION SCRIPT
        const cards = document.querySelectorAll('.carousel-wrapper .project-card');
        let activeIndex = 0;

        function updateCarousel() {
            const total = cards.length;
            cards.forEach((card, index) => {
                card.classList.remove('active', 'left', 'right', 'hidden');
                
                if (index === activeIndex) {
                    card.classList.add('active');
                } else if (index === (activeIndex - 1 + total) % total) {
                    card.classList.add('left');
                } else if (index === (activeIndex + 1) % total) {
                    card.classList.add('right');
                } else {
                    card.classList.add('hidden');
                }
            });
        }

        cards.forEach((card, index) => {
            card.addEventListener('mouseenter', () => {
                activeIndex = index;
                updateCarousel();
            });
            card.addEventListener('click', () => {
                activeIndex = index;
                updateCarousel();
            });
        });

        // Initialize Carousel Position
        updateCarousel();

        window.addEventListener('scroll', () => {
            animatedSkills();
            handleAboutScroll();
        });

        window.addEventListener('load', () => {
            animatedSkills();
            handleAboutScroll();
        });

        document.addEventListener("DOMContentLoaded", type);
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Paul Lee - Industrial Engineering Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            background: #0a0a0a;
            color: #ffffff;
            line-height: 1.6;
            overflow-x: hidden;
        }

        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(10, 10, 10, 0.9);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            z-index: 1000;
            padding: 20px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        nav .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        nav .logo {
            font-size: 22px;
            font-weight: 700;
            letter-spacing: -0.5px;
            background: linear-gradient(135deg, #00d9ff 0%, #a855f7 50%, #ff0080 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 35px;
            align-items: center;
        }

        nav a {
            text-decoration: none;
            color: #ffffff;
            font-size: 14px;
            transition: color 0.3s;
            position: relative;
        }

        nav a:hover {
            color: #00d9ff;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, #00d9ff 0%, #a855f7 100%);
            transition: width 0.3s;
        }

        nav a:hover::after {
            width: 100%;
        }

        .download-btn {
            padding: 10px 24px;
            background: linear-gradient(135deg, #00d9ff 0%, #a855f7 100%);
            color: white !important;
            border-radius: 25px;
            font-weight: 600;
            transition: transform 0.3s, box-shadow 0.3s;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .download-btn::after {
            display: none;
        }

        .download-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(0, 217, 255, 0.4);
            color: white !important;
        }

        .hero {
            margin-top: 80px;
            padding: 140px 40px 100px;
            text-align: center;
            max-width: 1200px;
            margin-left: auto;
            margin-right: auto;
            position: relative;
        }

        .hero-background {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at 20% 20%, rgba(168, 85, 247, 0.15) 0%, transparent 50%),
                        radial-gradient(circle at 80% 80%, rgba(0, 217, 255, 0.15) 0%, transparent 50%);
            z-index: -1;
            animation: pulse-bg 8s ease-in-out infinite;
        }

        @keyframes pulse-bg {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }

        .hero h1 {
            font-size: 72px;
            font-weight: 800;
            letter-spacing: -3px;
            margin-bottom: 20px;
            line-height: 1.1;
            background: linear-gradient(135deg, #00d9ff 0%, #a855f7 50%, #ff0080 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradient-shift 5s ease infinite;
            background-size: 200% 200%;
        }

        @keyframes gradient-shift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .hero p {
            font-size: 24px;
            color: #b4b4b4;
            font-weight: 400;
            max-width: 700px;
            margin: 0 auto 40px;
        }

        .availability-badge {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 12px 24px;
            background: rgba(0, 217, 255, 0.1);
            border: 1px solid rgba(0, 217, 255, 0.3);
            border-radius: 50px;
            font-size: 14px;
            color: #00d9ff;
            margin-top: 20px;
            backdrop-filter: blur(10px);
        }

        .availability-dot {
            width: 10px;
            height: 10px;
            background: #00d9ff;
            border-radius: 50%;
            animation: pulse-dot 2s infinite;
            box-shadow: 0 0 10px #00d9ff;
        }

        @keyframes pulse-dot {
            0%, 100% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.2); opacity: 0.7; }
        }

        .about {
            background: rgba(255, 255, 255, 0.02);
            padding: 100px 40px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .about-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .about-title {
            font-size: 52px;
            font-weight: 800;
            letter-spacing: -2px;
            margin-bottom: 30px;
            text-align: center;
            background: linear-gradient(135deg, #00d9ff 0%, #ffffff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .about-intro {
            font-size: 20px;
            line-height: 1.8;
            color: #b4b4b4;
            text-align: center;
            max-width: 900px;
            margin: 0 auto 80px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
            margin-bottom: 80px;
        }

        .skill-category {
            background: linear-gradient(135deg, rgba(168, 85, 247, 0.1) 0%, rgba(0, 217, 255, 0.1) 100%);
            padding: 40px;
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: transform 0.3s, box-shadow 0.3s, border-color 0.3s;
            position: relative;
            overflow: hidden;
        }

        .skill-category::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.05) 0%, transparent 70%);
            opacity: 0;
            transition: opacity 0.3s;
        }

        .skill-category:hover::before {
            opacity: 1;
        }

        .skill-category:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(0, 217, 255, 0.3);
            border-color: rgba(0, 217, 255, 0.5);
        }

        .skill-category h3 {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 25px;
            letter-spacing: -0.5px;
            color: #00d9ff;
        }

        .skill-category ul {
            list-style: none;
        }

        .skill-category li {
            font-size: 16px;
            color: #e0e0e0;
            padding: 12px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            transition: padding-left 0.3s, color 0.3s;
        }

        .skill-category li:hover {
            padding-left: 10px;
            color: #00d9ff;
        }

        .skill-category li:last-child {
            border-bottom: none;
        }

        .stats {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 50px;
            padding: 80px 0 0;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .stat {
            text-align: center;
            position: relative;
        }

        .stat-number {
            font-size: 64px;
            font-weight: 800;
            letter-spacing: -2px;
            background: linear-gradient(135deg, #00d9ff 0%, #a855f7 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            display: block;
        }

        .stat-label {
            font-size: 14px;
            color: #b4b4b4;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .story-section {
            max-width: 1000px;
            margin: 120px auto;
            padding: 0 40px;
        }

        .story-title {
            font-size: 48px;
            font-weight: 800;
            letter-spacing: -2px;
            margin-bottom: 40px;
            text-align: center;
            background: linear-gradient(135deg, #ff0080 0%, #a855f7 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .story-content {
            font-size: 19px;
            line-height: 1.9;
            color: #d0d0d0;
            text-align: center;
        }

        .timeline {
            max-width: 1100px;
            margin: 120px auto;
            padding: 0 40px;
        }

        .timeline-title {
            font-size: 48px;
            font-weight: 800;
            letter-spacing: -2px;
            margin-bottom: 80px;
            text-align: center;
            background: linear-gradient(135deg, #00d9ff 0%, #ffffff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .timeline-items {
            position: relative;
            padding-left: 50px;
        }

        .timeline-items::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 3px;
            background: linear-gradient(180deg, #00d9ff 0%, #a855f7 50%, #ff0080 100%);
            box-shadow: 0 0 20px rgba(0, 217, 255, 0.5);
        }

        .timeline-item {
            position: relative;
            padding-bottom: 60px;
            margin-left: 30px;
        }

        .timeline-dot {
            position: absolute;
            left: -42px;
            top: 5px;
            width: 16px;
            height: 16px;
            background: #00d9ff;
            border-radius: 50%;
            border: 4px solid #0a0a0a;
            box-shadow: 0 0 20px #00d9ff;
            animation: pulse-dot 2s infinite;
        }

        .timeline-year {
            font-size: 14px;
            color: #00d9ff;
            font-weight: 700;
            margin-bottom: 8px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .timeline-content h3 {
            font-size: 24px;
            margin-bottom: 10px;
            color: #ffffff;
        }

        .timeline-content p {
            font-size: 16px;
            color: #b4b4b4;
            line-height: 1.6;
        }

        .certifications {
            background: rgba(255, 255, 255, 0.02);
            padding: 100px 40px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .cert-title {
            font-size: 48px;
            font-weight: 800;
            letter-spacing: -2px;
            margin-bottom: 60px;
            text-align: center;
            background: linear-gradient(135deg, #a855f7 0%, #ff0080 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .cert-grid {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 30px;
        }

        .cert-badge {
            background: rgba(255, 255, 255, 0.03);
            padding: 40px 30px;
            border-radius: 20px;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s, border-color 0.3s;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .cert-badge:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 60px rgba(168, 85, 247, 0.4);
            border-color: rgba(168, 85, 247, 0.5);
        }

        .cert-icon {
            font-size: 56px;
            margin-bottom: 20px;
            filter: drop-shadow(0 0 10px rgba(168, 85, 247, 0.5));
        }

        .cert-name {
            font-size: 17px;
            font-weight: 600;
            color: #ffffff;
        }

        .companies {
            padding: 120px 40px;
        }

        .companies-title {
            font-size: 16px;
            text-align: center;
            color: #b4b4b4;
            margin-bottom: 60px;
            text-transform: uppercase;
            letter-spacing: 3px;
        }

        .company-logos {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-wrap: wrap;
            gap: 70px;
        }

        .company-logo {
            font-size: 28px;
            font-weight: 800;
            color: #4a4a4a;
            opacity: 0.5;
            transition: opacity 0.3s, color 0.3s, transform 0.3s;
        }

        .company-logo:hover {
            opacity: 1;
            color: #00d9ff;
            transform: scale(1.1);
        }

        .case-studies {
            max-width: 1300px;
            margin: 120px auto;
            padding: 0 40px;
        }

        .case-title {
            font-size: 48px;
            font-weight: 800;
            letter-spacing: -2px;
            margin-bottom: 70px;
            text-align: center;
            background: linear-gradient(135deg, #00d9ff 0%, #a855f7 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .case-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
            gap: 40px;
        }

        .case-card {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 24px;
            padding: 45px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: transform 0.3s, box-shadow 0.3s, border-color 0.3s;
            position: relative;
            overflow: hidden;
        }

        .case-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #00d9ff 0%, #a855f7 50%, #ff0080 100%);
            opacity: 0;
            transition: opacity 0.3s;
        }

        .case-card:hover::before {
            opacity: 1;
        }

        .case-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 70px rgba(0, 217, 255, 0.3);
            border-color: rgba(0, 217, 255, 0.4);
        }

        .case-label {
            display: inline-block;
            font-size: 11px;
            font-weight: 700;
            color: #00d9ff;
            background: rgba(0, 217, 255, 0.15);
            padding: 8px 16px;
            border-radius: 20px;
            margin-bottom: 25px;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            border: 1px solid rgba(0, 217, 255, 0.3);
        }

        .case-card h3 {
            font-size: 26px;
            font-weight: 700;
            margin-bottom: 25px;
            color: #ffffff;
        }

        .case-section {
            margin-bottom: 22px;
        }

        .case-section-title {
            font-size: 12px;
            font-weight: 700;
            color: #a855f7;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            margin-bottom: 10px;
        }

        .case-section-content {
            font-size: 16px;
            color: #d0d0d0;
            line-height: 1.7;
        }

        .case-result {
            background: linear-gradient(135deg, rgba(0, 217, 255, 0.1) 0%, rgba(168, 85, 247, 0.1) 100%);
            padding: 25px;
            border-radius: 16px;
            margin-top: 25px;
            border: 1px solid rgba(0, 217, 255, 0.2);
        }

        .case-result-number {
            font-size: 36px;
            font-weight: 800;
            background: linear-gradient(135deg, #00d9ff 0%, #a855f7 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 8px;
        }

        .testimonials {
            background: rgba(255, 255, 255, 0.02);
            padding: 120px 40px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .testimonials-title {
            font-size: 48px;
            font-weight: 800;
            letter-spacing: -2px;
            margin-bottom: 70px;
            text-align: center;
            background: linear-gradient(135deg, #ff0080 0%, #00d9ff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .testimonial-slider {
            max-width: 1000px;
            margin: 0 auto;
            position: relative;
        }

        .testimonial {
            text-align: center;
            padding: 50px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 24px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .testimonial-quote {
            font-size: 26px;
            line-height: 1.7;
            color: #ffffff;
            margin-bottom: 35px;
            font-style: italic;
            font-weight: 300;
        }

        .testimonial-author {
            font-size: 18px;
            font-weight: 700;
            color: #00d9ff;
        }

        .testimonial-role {
            font-size: 15px;
            color: #b4b4b4;
            margin-top: 8px;
        }

        .testimonial-dots {
            display: flex;
            justify-content: center;
            gap: 12px;
            margin-top: 40px;
        }

        .dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.2);
            cursor: pointer;
            transition: background 0.3s, transform 0.3s, box-shadow 0.3s;
        }

        .dot.active {
            background: #00d9ff;
            transform: scale(1.4);
            box-shadow: 0 0 15px #00d9ff;
        }

        .free-resource {
            background: linear-gradient(135deg, rgba(0, 217, 255, 0.1) 0%, rgba(168, 85, 247, 0.1) 100%);
            padding: 100px 40px;
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .resource-title {
            font-size: 48px;
            font-weight: 800;
            letter-spacing: -2px;
            margin-bottom: 25px;
            background: linear-gradient(135deg, #00d9ff 0%, #a855f7 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .resource-description {
            font-size: 19px;
            margin-bottom: 45px;
            color: #d0d0d0;
            max-width: 750px;
            margin-left: auto;
            margin-right: auto;
        }

        .resource-download {
            display: inline-flex;
            align-items: center;
            gap: 12px;
            padding: 20px 50px;
            background: linear-gradient(135deg, #00d9ff 0%, #a855f7 100%);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-size: 18px;
            font-weight: 700;
            transition: transform 0.3s, box-shadow 0.3s;
            box-shadow: 0 10px 40px rgba(0, 217, 255, 0.4);
        }

        .resource-download:hover {
            transform: translateY(-3px) scale(1.03);
            box-shadow: 0 15px 60px rgba(0, 217, 255, 0.6);
        }

        .projects {
            max-width: 1300px;
            margin: 120px auto;
            padding: 0 40px;
        }

        .section-title {
            font-size: 48px;
            font-weight: 800;
            letter-spacing: -2px;
            margin-bottom: 70px;
            text-align: center;
            background: linear-gradient(135deg, #a855f7 0%, #ff0080 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
            gap: 40px;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 24px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: transform 0.3s, box-shadow 0.3s, border-color 0.3s;
            cursor: pointer;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 70px rgba(168, 85, 247, 0.4);
            border-color: rgba(168, 85, 247, 0.5);
        }

        .project-image {
            width: 100%;
            height: 280px;
            background: linear-gradient(135deg, #00d9ff 0%, #a855f7 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 56px;
            position: relative;
            overflow: hidden;
        }

        .project-image::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.2) 0%, transparent 70%);
            animation: rotate 10s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .project-card:nth-child(2) .project-image {
            background: linear-gradient(135deg, #a855f7 0%, #ff0080 100%);
        }

        .project-card:nth-child(3) .project-image {
            background: linear-gradient(135deg, #ff0080 0%, #00d9ff 100%);
        }

        .project-card:nth-child(4) .project-image {
            background: linear-gradient(135deg, #00d9ff 0%, #ff0080 100%);
        }

        .project-content {
            padding: 35px;
        }

        .project-title {
            font-size: 26px;
            font-weight: 700;
            margin-bottom: 12px;
            letter-spacing: -0.5px;
            color: #ffffff;
        }

        .project-description {
            font-size: 16px;
            color: #b4b4b4;
            line-height: 1.7;
        }

        .contact {
            background: rgba(255, 255, 255, 0.02);
            padding: 120px 40px;
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .contact h2 {
            font-size: 56px;
            font-weight: 800;
            letter-spacing: -2px;
            margin-bottom: 25px;
            background: linear-gradient(135deg, #00d9ff 0%, #a855f7 50%, #ff0080 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .contact p {
            font-size: 20px;
            color: #b4b4b4;
            margin-bottom: 50px;
        }

        .contact-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        .contact-email {
            display: inline-block;
            padding: 20px 50px;
            background: linear-gradient(135deg, #00d9ff 0%, #a855f7 100%);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-size: 18px;
            font-weight: 700;
            transition: transform 0.3s, box-shadow 0.3s;
            box-shadow: 0 10px 40px rgba(0, 217, 255, 0.4);
        }

        .contact-email:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 60px rgba(0, 217, 255, 0.6);
        }

        .contact-secondary {
            display: inline-block;
            padding: 20px 50px;
            background: transparent;
            color: #00d9ff;
            text-decoration: none;
            border-radius: 50px;
            font-size: 18px;
            font-weight: 700;
            border: 2px solid #00d9ff;
            transition: background 0.3s, color 0.3s, transform 0.3s, box-shadow 0.3s;
        }

        .contact-secondary:hover {
            background: #00d9ff;
            color: #0a0a0a;
            transform: translateY(-3px);
            box-shadow: 0 10px 40px rgba(0, 217, 255, 0.4);
        }

        footer {
            background: #000000;
            padding: 50px 40px;
            text-align: center;
            color: #6e6e73;
            font-size: 14px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 42px;
            }

            .hero p {
                font-size: 18px;
            }

            nav ul {
                gap: 15px;
                font-size: 12px;
            }

            nav .logo {
                font-size: 18px;
            }

            .download-btn {
                padding: 8px 16px;
                font-size: 12px;
            }

            .about-title, .story-title, .timeline-title, .cert-title, .case-title, .testimonials-title, .resource-title, .section-title {
                font-size: 36px;
            }

            .companies-title {
                font-size: 14px;
            }

            .company-logos {
                gap: 30px;
            }

            .company-logo {
                font-size: 20px;
            }

            .about-intro, .story-content {
                font-size: 17px;
            }

            .testimonial-quote {
                font-size: 20px;
                padding: 30px;
            }

            .skills-grid, .cert-grid, .case-grid, .project-grid {
                grid-template-columns: 1fr;
            }

            .stat-number {
                font-size: 48px;
            }

            .contact h2 {
                font-size: 40px;
            }

            .contact-buttons {
                flex-direction: column;
                align-items: center;
            }

            .contact-email, .contact-secondary {
                width: 100%;
                max-width: 300px;
            }

            .timeline-items {
                padding-left: 30px;
            }

            .timeline-dot {
                left: -32px;
            }
        }

        html {
            scroll-behavior: smooth;
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <div class="hero-background"></div>
    
    <nav>
        <div class="container">
            <div class="logo">PAUL LEE</div>
            <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#journey">Journey</a></li>
                <li><a href="#cases">Case Studies</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
                <li>
                    <a href="#" class="download-btn" download="Paul_Lee_Resume.pdf">
                        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5">
                            <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                            <polyline points="7 10 12 15 17 10"></polyline>
                            <line x1="12" y1="15" x2="12" y2="3"></line>
                        </svg>
                        Resume
                    </a>
                </li>
            </ul>
        </div>
    </nav>

    <section class="hero">
        <h1>Hi, I'm Paul Lee</h1>
        <p>Industrial engineer passionate about optimizing processes, improving efficiency, and driving innovation through data-driven solutions.</p>
        <div class="availability-badge">
            <span class="availability-dot"></span>
            Available for Consulting Projects
        </div>
    </section>

    <section class="about" id="about">
        <div class="about-container">
            <div class="about-content">
                <h2 class="about-title">Expertise & Skills</h2>
                <p class="about-intro">Industrial engineer specializing in process optimization, lean manufacturing, and supply chain excellence. I combine analytical rigor with creative problem-solving to deliver measurable results that drive operational efficiency and bottom-line impact.</p>
                
                <div class="skills-grid">
                    <div class="skill-category">
                        <h3>Technical Expertise</h3>
                        <ul>
                            <li>Process Optimization & Simulation</li>
                            <li>Lean Six Sigma Methodologies</li>
                            <li>Statistical Analysis & Quality Control</li>
                            <li>Operations Research & Analytics</li>
                        </ul>
                    </div>
                    
                    <div class="skill-category">
                        <h3>Tools & Technologies</h3>
                        <ul>
                            <li>Python, R, MATLAB</li>
                            <li>AutoCAD, SolidWorks</li>
                            <li>Arena, Simio Simulation</li>
                            <li>SQL, Tableau, Excel</li>
                        </ul>
                    </div>
                    
                    <div class="skill-category">
                        <h3>Core Strengths</h3>
                        <ul>
                            <li>Cost Reduction Strategies</li>
                            <li>Workflow Design & Layout Planning</li>
                            <li>Data-Driven Decision Making</li>
                            <li>Cross-Functional Team Leadership</li>
                        </ul>
                    </div>
                </div>

                <div class="stats">
                    <div class="stat">
                        <span class="stat-number" data-target="35">0</span>%
                        <div class="stat-label">Average Efficiency Gain</div>
                    </div>
                    <div class="stat">
                        <span class="stat-number" data-target="2">0</span>M+
                        <div class="stat-label">Cost Savings Delivered</div>
                    </div>
                    <div class="stat">
                        <span class="stat-number" data-target="15">0</span>+
                        <div class="stat-label">Projects Completed</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="story-section" id="journey">
        <h2 class="story-title">My Journey</h2>
        <div class="story-content">
            <p>My passion for industrial engineering began when I witnessed firsthand how small process improvements could create massive ripple effects across entire organizations. What started as curiosity about "how things work" evolved into a career dedicated to making systems work better, faster, and smarter.</p>
            <br>
            <p>Today, I combine technical expertise with business acumen to help organizations unlock hidden potential, eliminate waste, and build competitive advantages through operational excellence.</p>
        </div>
    </section>

    <section class="timeline">
        <h2 class="timeline-title">Career Milestones</h2>
        <div class="timeline-items">
            <div class="timeline-item">
                <div class="timeline-dot"></div>
                <div class="timeline-content">
                    <div class="timeline-year">2024</div>
                    <h3>Senior Industrial Engineer</h3>
                    <p>Leading enterprise-wide optimization initiatives, achieving $2M+ in cost savings</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-dot"></div>
                <div class="timeline-content">
                    <div class="timeline-year">2022</div>
                    <h3>Lean Six Sigma Black Belt Certification</h3>
                    <p>Advanced expertise in process improvement and statistical analysis</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-dot"></div>
                <div class="timeline-content">
                    <div class="timeline-year">2021</div>
                    <h3>Industrial Engineering Consultant</h3>
                    <p>Delivered transformative solutions across manufacturing, logistics, and healthcare sectors</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-dot"></div>
                <div class="timeline-content">
                    <div class="timeline-year">2019</div>
                    <h3>Master's in Industrial Engineering</h3>
                    <p>Specialized in operations research and supply chain optimization</p>
                </div>
            </div>
        </div>
    </section>

    <section class="certifications">
        <h2 class="cert-title">Certifications & Recognition</h2>
        <div class="cert-grid">
            <div class="cert-badge">
                <div class="cert-icon">🏆</div>
                <div class="cert-name">Lean Six Sigma Black Belt</div>
            </div>
            <div class="cert-badge">
                <div class="cert-icon">📊</div>
                <div class="cert-name">PMP Certified</div>
            </div>
            <div class="cert-badge">
                <div class="cert-icon">⚙️</div>
                <div class="cert-name">APICS CSCP</div>
            </div>
            <div class="cert-badge">
                <div class="cert-icon">🎓</div>
                <div class="cert-name">Master's in IE</div>
            </div>
        </div>
    </section>

    <section class="companies">
        <div class="companies-title">Trusted by Industry Leaders</div>
        <div class="company-logos">
            <div class="company-logo">BOEING</div>
            <div class="company-logo">AMAZON</div>
            <div class="company-logo">TESLA</div>
            <div class="company-logo">SIEMENS</div>
            <div class="company-logo">3M</div>
        </div>
    </section>

    <section class="case-studies" id="cases">
        <h2 class="case-title">Case Studies</h2>
        <div class="case-grid">
            <div class="case-card">
                <span class="case-label">Manufacturing</span>
                <h3>Assembly Line Optimization</h3>
                <div class="case-section">
                    <div class="case-section-title">Problem</div>
                    <div class="case-section-content">Production bottlenecks causing 40% capacity underutilization and missed delivery deadlines</div>
                </div>
                <div class="case-section">
                    <div class="case-section-title">Solution</div>
                    <div class="case-section-content">Implemented value stream mapping, redesigned workstation layouts, and deployed real-time monitoring systems</div>
                </div>
                <div class="case-result">
                    <div class="case-result-number">42%</div>
                    <div class="case-section-content">Increase in throughput with 28% reduction in cycle time</div>
                </div>
            </div>

            <div class="case-card">
                <span class="case-label">Supply Chain</span>
                <h3>Inventory Optimization</h3>
                <div class="case-section">
                    <div class="case-section-title">Problem</div>
                    <div class="case-section-content">High inventory carrying costs and frequent stockouts impacting customer satisfaction</div>
                </div>
                <div class="case-section">
                    <div class="case-section-title">Solution</div>
                    <div class="case-section-content">Developed predictive models and implemented demand forecasting with safety stock optimization</div>
                </div>
                <div class="case-result">
                    <div class="case-result-number">$850K</div>
                    <div class="case-section-content">Annual cost savings with 95% service level achievement</div>
                </div>
            </div>

            <div class="case-card">
                <span class="case-label">Quality Control</span>
                <h3>Defect Reduction Initiative</h3>
                <div class="case-section">
                    <div class="case-section-title">Problem</div>
                    <div class="case-section-content">Defect rates exceeding 8% causing warranty claims and brand reputation damage</div>
                </div>
                <div class="case-section">
                    <div class="case-section-title">Solution</div>
                    <div class="case-section-content">Applied DMAIC methodology with statistical process control and root cause analysis</div>
                </div>
                <div class="case-result">
                    <div class="case-result-number">73%</div>
                    <div class="case-section-content">Defect reduction achieving industry-leading quality standards</div>
                </div>
            </div>
        </div>
    </section>

    <section class="testimonials">
        <h2 class="testimonials-title">What Clients Say</h2>
        <div class="testimonial-slider">
            <div class="testimonial" id="testimonial-1">
                <div class="testimonial-quote">"Paul's analytical approach and attention to detail transformed our production line. The efficiency gains exceeded our expectations and the ROI was remarkable."</div>
                <div class="testimonial-author">Sarah Chen</div>
                <div class="testimonial-role">Director of Operations, TechManufacturing Inc.</div>
            </div>
            <div class="testimonial hidden" id="testimonial-2">
                <div class="testimonial-quote">"Working with Paul was a game-changer for our supply chain. His data-driven insights helped us reduce costs while improving delivery performance."</div>
                <div class="testimonial-author">Michael Rodriguez</div>
                <div class="testimonial-role">VP Supply Chain, Global Logistics Corp</div>
            </div>
            <div class="testimonial hidden" id="testimonial-3">
                <div class="testimonial-quote">"Paul's expertise in lean methodologies helped us eliminate waste and streamline operations. His collaborative approach made implementation seamless."</div>
                <div class="testimonial-author">Jennifer Park</div>
                <div class="testimonial-role">Plant Manager, Automotive Solutions LLC</div>
            </div>
            <div class="testimonial-dots">
                <span class="dot active" onclick="showTestimonial(1)"></span>
                <span class="dot" onclick="showTestimonial(2)"></span>
                <span class="dot" onclick="showTestimonial(3)"></span>
            </div>
        </div>
    </section>

    <section class="free-resource">
        <h2 class="resource-title">Free Resource</h2>
        <p class="resource-description">Download my comprehensive Process Optimization Checklist - a practical guide to identifying inefficiencies and implementing improvements in your operations.</p>
        <a href="#" class="resource-download" download="Process_Optimization_Checklist.pdf">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5">
                <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                <polyline points="7 10 12 15 17 10"></polyline>
                <line x1="12" y1="15" x2="12" y2="3"></line>
            </svg>
            Download Free Checklist
        </a>
    </section>

    <section class="projects" id="projects">
        <h2 class="section-title">Featured Projects</h2>
        <div class="project-grid">
            <div class="project-card">
                <div class="project-image">📊</div>
                <div class="project-content">
                    <h3 class="project-title">Process Optimization</h3>
                    <p class="project-description">Streamlined manufacturing workflow resulting in 35% efficiency improvement and reduced cycle time.</p>
                </div>
            </div>

            <div class="project-card">
                <div class="project-image">🏭</div>
                <div class="project-content">
                    <h3 class="project-title">Supply Chain Analysis</h3>
                    <p class="project-description">Comprehensive supply chain redesign that decreased inventory costs by 28% while improving delivery times.</p>
                </div>
            </div>

            <div class="project-card">
                <div class="project-image">⚙️</div>
                <div class="project-content">
                    <h3 class="project-title">Quality Control System</h3>
                    <p class="project-description">Implemented statistical process control methods reducing defect rates by 42% across production lines.</p>
                </div>
            </div>

            <div class="project-card">
                <div class="project-image">📈</div>
                <div class="project-content">
                    <h3 class="project-title">Lean Manufacturing</h3>
                    <p class="project-description">Applied lean principles to eliminate waste and optimize resource allocation in automotive assembly.</p>
                </div>
            </div>
        </div>
    </section>

    <section class="contact" id="contact">
        <h2>Let's Work Together</h2>
        <p>Ready to optimize your operations and drive measurable results?</p>
        <div class="contact-buttons">
            <a href="mailto:paul.lee@example.com" class="contact-email">Get in Touch</a>
            <a href="https://linkedin.com/in/paullee" class="contact-secondary">View LinkedIn</a>
        </div>
    </section>

    <footer>
        <p>© 2025 Paul Lee. All rights reserved.</p>
    </footer>

    <script>
        // Smooth scroll for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                if (this.getAttribute('href') !== '#') {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        target.scrollIntoView({
                            behavior: 'smooth',
                            block: 'start'
                        });
                    }
                }
            });
        });

        // Animated counter for stats
        function animateCounter(element) {
            const target = parseInt(element.getAttribute('data-target'));
            const duration = 2000;
            const increment = target / (duration / 16);
            let current = 0;

            const timer = setInterval(() => {
                current += increment;
                if (current >= target) {
                    element.textContent = target;
                    clearInterval(timer);
                } else {
                    element.textContent = Math.floor(current);
                }
            }, 16);
        }

        // Intersection Observer for stats animation
        const statsObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting && !entry.target.classList.contains('animated')) {
                    entry.target.classList.add('animated');
                    animateCounter(entry.target);
                }
            });
        }, { threshold: 0.5 });

        document.querySelectorAll('.stat-number').forEach(stat => {
            statsObserver.observe(stat);
        });

        // Fade-in animation on scroll for cards
        const cardObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.project-card, .case-card, .skill-category').forEach((card, index) => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = `opacity 0.6s ease ${index * 0.1}s, transform 0.6s ease ${index * 0.1}s`;
            cardObserver.observe(card);
        });

        // Testimonial slider
        let currentTestimonial = 1;

        function showTestimonial(num) {
            // Hide all testimonials
            for (let i = 1; i <= 3; i++) {
                document.getElementById(`testimonial-${i}`).classList.add('hidden');
                document.querySelectorAll('.dot')[i - 1].classList.remove('active');
            }
            
            // Show selected testimonial
            document.getElementById(`testimonial-${num}`).classList.remove('hidden');
            document.querySelectorAll('.dot')[num - 1].classList.add('active');
            currentTestimonial = num;
        }

        // Auto-rotate testimonials
        setInterval(() => {
            currentTestimonial = currentTestimonial >= 3 ? 1 : currentTestimonial + 1;
            showTestimonial(currentTestimonial);
        }, 5000);
    </script>
</body>
</html>

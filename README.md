Евген, [31.10.2025 09:25]
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KazakhIT - IT Компания</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="icon" href="https://i.postimg.cc/vZfhnyMc/photo.jpg" type="image/jpg">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        :root {
            --primary: #2563eb;
            --primary-dark: #1d4ed8;
            --secondary: #06b6d4;
            --dark: #111827;
            --darker: #030712;
            --gray: #374151;
            --light-gray: #6b7280;
            --white: #ffffff;
        }
        html {
            scroll-behavior: smooth;
            font-size: 16px;
        }
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: var(--white);
            line-height: 1.6;
            position: relative;
            min-height: 100vh;
            background-color: #ff0000; /* Красный фон */
        }
        /* Фоновое изображение */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.6);
            z-index: -1;
        }
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        header {
            background-color: rgba(3, 7, 18, 0.9);
            backdrop-filter: blur(8px);
            border-bottom: 1px solid rgba(59, 130, 246, 0.2);
            padding: 8px 0; /* Уменьшено в 2 раза */
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 100;
            transition: transform 0.3s ease;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .header-content {
            display: flex;
            flex-direction: row;
            align-items: center;
            justify-content: space-between;
            width: 100%;
            gap: 16px;
        }
        .logo-container {
            display: flex;
            align-items: center;
            gap: 8px; /* Уменьшено */
            cursor: pointer;
        }
        .logo-image {
            width: 24px; /* Уменьшено */
            height: 24px; /* Уменьшено */
            border-radius: 50%;
            object-fit: cover;
        }
        .logo-text h1 {
            font-size: 14px; /* Уменьшено */
            font-weight: 800;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        .logo-text p {
            color: var(--light-gray);
            font-size: 8px; /* Уменьшено */
            margin-top: 1px; /* Уменьшено */
        }
        nav a {
            color: var(--white);
            text-decoration: none;
            margin: 0 4px; /* Уменьшено */
            font-weight: 500;
            font-size: 12px; /* Уменьшено */
            transition: color 0.3s ease;
        }
        nav a:hover {
            color: var(--primary);
        }
        .top-right-widgets {
            position: fixed;
            top: 10px;
            right: 10px;
            z-index: 200;
            display: flex;
            gap: 8px;
        }
        .currency-selector, .language-selector {
            position: relative;
        }
        .currency-btn, .lang-btn {
            background: rgba(37, 99, 235, 0.5);
            border: none;
            color: white;
            padding: 6px 10px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 12px;
            transition: background 0.3s;
        }
        .currency-btn.active, .lang-btn.active {

Евген, [31.10.2025 09:25]
background: var(--primary);
        }
        .dropdown-menu {
            position: absolute;
            top: 100%;
            right: 0;
            background: rgba(3, 7, 18, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 8px;
            padding: 8px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
            display: none;
            flex-direction: column;
            gap: 4px;
            z-index: 1000;
            animation: slideDown 0.3s ease forwards;
        }
        .dropdown-menu.closing {
            animation: slideUp 0.3s ease forwards;
        }
        @keyframes slideDown {
            from { opacity: 0; transform: translateY(-10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        @keyframes slideUp {
            from { opacity: 1; transform: translateY(0); }
            to { opacity: 0; transform: translateY(-10px); }
        }
        .dropdown-item {
            background: rgba(37, 99, 235, 0.3);
            border: none;
            color: white;
            padding: 6px 10px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 12px;
            transition: background 0.3s;
            text-align: center;
        }
        .dropdown-item:hover {
            background: var(--primary);
        }
        .hero {
            position: relative;
            padding: 120px 0 60px; /* Уменьшено */
        }
        .hero-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 32px;
        }
        .hero-text {
            max-width: 600px;
            text-align: center;
            padding: 0 10px;
        }
        .hero-text h2 {
            font-size: 36px;
            font-weight: 800;
            line-height: 1.2;
            margin-bottom: 20px;
        }
        .hero-text h2 span {
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        .hero-text p {
            font-size: 18px;
            color: #d1d5db;
            margin-bottom: 24px;
        }
        .hero-buttons {
            display: flex;
            flex-direction: column;
            gap: 12px;
            width: 100%;
            max-width: 300px;
        }
        .btn {
            padding: 12px 20px;
            border-radius: 8px;
            font-weight: 600;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            text-align: center;
        }
        .btn-primary {
            background: var(--primary);
            color: white;
        }
        .btn-primary:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
        }
        .btn-outline {
            border: 2px solid var(--primary);
            color: var(--primary);
            background: transparent;
        }
        .btn-outline:hover {
            background: rgba(37, 99, 235, 0.1);
            transform: translateY(-2px);
        }
        .hero-image {
            position: relative;
            max-width: 500px;
            width: 100%;
        }
        .hero-image img {
            width: 100%;
            border-radius: 16px;
            box-shadow: 0 15px 30px -10px rgba(0, 0, 0, 0.5);
        }
        .section-header {
            text-align: center;
            margin-bottom: 48px;
            padding: 0 10px;
        }
        .section-header h2 {
            font-size: 32px;
            font-weight: 800;
            margin-bottom: 12px;
        }
        .section-header p {
            font-size: 16px;
            color: var(--light-gray);
            max-width: 500px;
            margin: 0 auto;
        }
        /* Products */
        .products, .team, .contact, .reviews, .addresses {
            padding: 60px 0;
        }

Евген, [31.10.2025 09:25]
.products-grid, .team-grid, .reviews-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 24px;
        }
        .product-card, .team-member, .review-card {
            background: rgba(55, 65, 81, 0.65);
            backdrop-filter: blur(6px);
            border-radius: 16px;
            overflow: hidden;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        .product-card:hover, .team-member:hover, .review-card:hover {
            background: rgba(49, 62, 81, 0.75);
            transform: translateY(-4px);
        }
        .product-image {
            width: 100%;
            height: 160px;
            position: relative;
            overflow: hidden;
        }
        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }
        .product-info {
            padding: 16px;
        }
        .product-info h3 {
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 6px;
            text-align: center;
        }
        .product-info .price {
            color: var(--secondary);
            font-weight: 600;
            font-size: 16px;
            margin-bottom: 10px;
            text-align: center;
        }
        .product-info .summary {
            color: #d1d5db;
            font-size: 13px;
            margin-bottom: 12px;
            display: -webkit-box;
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;
            overflow: hidden;
            text-align: center;
        }
        .product-rating {
            display: flex;
            justify-content: center;
            margin-bottom: 10px;
        }
        .product-rating .stars {
            color: #fbbf24;
            font-size: 16px;
        }
        .product-rating .rating-value {
            color: #d1d5db;
            font-size: 14px;
            margin-left: 8px;
        }
        .btn-details {
            width: 100%;
            padding: 10px;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: background 0.3s;
            font-size: 15px;
            margin-bottom: 8px;
        }
        .btn-details:hover {
            background: var(--primary-dark);
        }
        .btn-comments {
            width: 100%;
            padding: 10px;
            background: rgba(37, 99, 235, 0.3);
            color: white;
            border: none;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: background 0.3s;
            font-size: 15px;
        }
        .btn-comments:hover {
            background: rgba(29, 78, 216, 0.5);
        }
        /* Team */
        .member-image-container {
            width: 100%;
            height: 220px;
            background: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .member-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }
        .member-info {
            padding: 20px;
        }
        .member-info h3 {
            font-size: 20px;
            font-weight: 700;
            margin-bottom: 6px;
            text-align: center;
        }
        .member-info .role {
            color: var(--primary);
            font-weight: 600;
            margin-bottom: 12px;
            display: block;
            font-size: 14px;
            text-align: center;
        }
        .member-info p {
            color: #d1d5db;
            font-size: 13px;
            line-height: 1.5;
            text-align: center;
        }
        /* Reviews */
        .review-card {
            padding: 20px;
        }
        .review-header {
            display: flex;
            justify-content: space-between;

Евген, [31.10.2025 09:25]
align-items: center;
            margin-bottom: 12px;
        }
        .reviewer-name {
            font-weight: 700;
            font-size: 16px;
        }
        .review-rating {
            color: #fbbf24;
            font-size: 18px;
        }
        .review-text {
            color: #d1d5db;
            font-size: 14px;
            line-height: 1.5;
        }
        /* Show More Button */
        .show-more {
            display: block;
            width: 100%;
            max-width: 300px;
            margin: 20px auto;
            padding: 12px 20px;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 8px;
            font-weight: 600;
            font-size: 16px;
            cursor: pointer;
            transition: background 0.3s;
        }
        .show-more:hover {
            background: var(--primary-dark);
        }
        /* Contact */
        .contact-content {
            display: flex;
            flex-direction: column;
            gap: 32px;
        }
        .contact-item {
            display: flex;
            align-items: flex-start;
            gap: 12px;
        }
        .contact-icon {
            width: 40px;
            height: 40px;
            background: var(--primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }
        .contact-icon i {
            font-size: 16px;
        }
        .contact-details h3 {
            font-size: 18px;
            font-weight: 600;
            margin-bottom: 4px;
        }
        .contact-details p {
            color: var(--light-gray);
            font-size: 14px;
        }
        .contact-form {
            background: rgba(55, 65, 81, 0.65);
            padding: 24px;
            border-radius: 16px;
            backdrop-filter: blur(6px);
        }
        .form-group {
            margin-bottom: 16px;
        }
        .form-group label {
            display: block;
            margin-bottom: 6px;
            font-weight: 500;
            font-size: 14px;
        }
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 10px 14px;
            background: rgba(17, 24, 39, 0.6);
            border: 1px solid #4b5563;
            border-radius: 8px;
            color: white;
            font-size: 15px;
        }
        .form-group textarea {
            min-height: 100px;
            resize: vertical;
        }
        /* Addresses */
        .addresses-content {
            display: flex;
            flex-direction: column;
            gap: 32px;
        }
        .address-info {
            display: flex;
            flex-direction: column;
            gap: 16px;
        }
        .address-title {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 8px;
        }
        .address-text {
            font-size: 18px;
            color: #d1d5db;
            margin-bottom: 16px;
        }
        .address-shop {
            font-size: 20px;
            font-weight: 700;
            color: var(--secondary);
        }
        .map-container {
            width: 100%;
            height: 400px;
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.3);
        }
        .map {
            width: 100%;
            height: 100%;
            border: none;
        }
        /* Footer */
        footer {
            background: rgba(3, 7, 18, 0.9);
            backdrop-filter: blur(8px);
            border-top: 1px solid rgba(59, 130, 246, 0.2);
            padding: 32px 0;
            margin-top: 60px;
        }
        .footer-logo {
            display: flex;
            align-items: center;
            gap: 12px;
            justify-content: center;
        }
        .footer-logo .logo-image {
            width: 40px;
            height: 40px;
            border-radius: 50%;

Евген, [31.10.2025 09:25]
object-fit: cover;
        }
        .footer-logo h3 {
            font-size: 18px;
            font-weight: 700;
        }
        .footer-logo p {
            color: var(--light-gray);
            font-size: 13px;
        }
        .copyright {
            color: var(--light-gray);
            text-align: center;
            font-size: 13px;
            margin-top: 16px;
        }
        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7); /* Полупрозрачный фон */
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        .modal-content {
            background: rgba(3, 7, 18, 0.5); /* Прозрачность 50% */
            width: 95%;
            max-width: 700px;
            padding: 24px;
            border-radius: 16px;
            backdrop-filter: blur(10px);
            position: relative;
            max-height: 90vh;
            overflow-y: auto;
        }
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 16px;
        }
        .modal-header h2 {
            font-size: 24px;
            text-align: center;
            flex-grow: 1;
        }
        .close-modal {
            background: none;
            border: none;
            color: white;
            font-size: 24px;
            cursor: pointer;
            padding: 0;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: absolute;
            top: 16px; /* Ближе к верху */
            right: 16px; /* Ближе к правому краю */
            z-index: 1001;
        }
        .specs-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 10px;
        }
        .spec-item {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            padding: 8px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        .spec-label {
            font-weight: 600;
            color: var(--primary);
            text-align: center;
            margin-bottom: 4px;
        }
        .spec-value {
            color: #d1d5db;
            text-align: center;
        }
        /* Comments Modal */
        .comments-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        .comments-modal-content {
            background: rgba(3, 7, 18, 0.5); /* Прозрачность 50% */
            width: 95%;
            max-width: 700px;
            padding: 24px;
            border-radius: 16px;
            backdrop-filter: blur(10px);
            position: relative;
            max-height: 90vh;
            overflow-y: auto;
        }
        .comments-modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 16px;
        }
        .comments-modal-header h2 {
            font-size: 24px;
            text-align: center;
            flex-grow: 1;
        }
        .close-comments-modal {
            background: none;
            border: none;
            color: white;
            font-size: 24px;
            cursor: pointer;
            padding: 0;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: absolute;
            top: 16px; /* Ближе к верху */
            right: 16px; /* Ближе к правому краю */
            z-index: 1001;
        }
        .comments-list {
            max-height: 400px;

Евген, [31.10.2025 09:25]
overflow-y: auto;
            padding-right: 10px;
        }
        .comment-item {
            background: rgba(55, 65, 81, 0.65);
            padding: 16px;
            border-radius: 12px;
            margin-bottom: 16px;
        }
        .comment-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 8px;
        }
        .comment-author {
            font-weight: 700;
            font-size: 16px;
        }
        .comment-rating {
            color: #fbbf24;
            font-size: 16px;
        }
        .comment-text {
            color: #d1d5db;
            font-size: 14px;
            line-height: 1.5;
        }
        /* Review Form */
        .review-form {
            background: rgba(55, 65, 81, 0.65);
            padding: 24px;
            border-radius: 16px;
            backdrop-filter: blur(6px);
            margin-top: 32px;
        }
        .form-row {
            display: flex;
            gap: 16px;
            margin-bottom: 16px;
        }
        .form-group {
            flex: 1;
        }
        .form-group-full {
            width: 100%;
        }
        .form-group label {
            display: block;
            margin-bottom: 6px;
            font-weight: 500;
            font-size: 14px;
        }
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 10px 14px;
            background: rgba(17, 24, 39, 0.6);
            border: 1px solid #4b5563;
            border-radius: 8px;
            color: white;
            font-size: 15px;
        }
        .form-group textarea {
            min-height: 100px;
            resize: vertical;
        }
        .rating-selection {
            display: flex;
            justify-content: center;
            gap: 8px;
            margin: 16px 0;
        }
        .rating-star {
            font-size: 24px;
            color: #4b5563;
            cursor: pointer;
            transition: color 0.3s;
        }
        .rating-star.active {
            color: #fbbf24;
        }
        .submit-review {
            width: 100%;
            padding: 12px;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: background 0.3s;
            font-size: 16px;
        }
        .submit-review:hover {
            background: var(--primary-dark);
        }
        /* Site Rating */
        .site-rating {
            text-align: center;
            margin-bottom: 24px;
        }
        .site-rating-stars {
            font-size: 24px;
            color: #fbbf24;
            margin-bottom: 8px;
        }
        .site-rating-value {
            color: #d1d5db;
            font-size: 18px;
        }
        /* Mobile styles */
        @media (max-width: 767px) {
            .header-content {
                padding: 0 10px;
                flex-direction: column;
                gap: 8px;
            }
            .logo-container {
                flex-direction: row;
                text-align: left;
            }
            .nav-container {
                width: 100%;
                display: flex;
                justify-content: center;
            }
            nav a {
                margin: 0 4px;
                font-size: 12px;
            }
            .logo-image {
                width: 20px;
                height: 20px;
            }
            .logo-text h1 {
                font-size: 12px;
            }
            .logo-text p {
                font-size: 7px;
            }
            .hero {
                padding: 100px 0 60px;
            }
            .hero-content {
                gap: 24px;
            }
            .hero-text h2 {
                font-size: 28px;
            }
            .hero-text p {
                font-size: 16px;
            }
            .section-header h2 {
                font-size: 28px;
            }

Евген, [31.10.2025 09:25]
.contact-content {
                gap: 24px;
            }
            .contact-item {
                flex-direction: column;
                align-items: center;
                text-align: center;
            }
            .contact-details {
                text-align: center;
            }
            .specs-grid {
                grid-template-columns: 1fr;
            }
            .reviews-grid {
                grid-template-columns: 1fr;
            }
            .btn-details, .btn-comments {
                width: 100%;
                margin-bottom: 8px;
            }
            .form-row {
                flex-direction: column;
                gap: 16px;
            }
            .addresses-content {
                gap: 24px;
            }
            .modal-content, .comments-modal-content {
                width: 95%;
                max-width: 95%;
                padding: 16px;
                margin: 10px;
                max-height: calc(100vh - 20px);
            }
            .modal-header, .comments-modal-header {
                margin-bottom: 30px;
            }
            .modal-header h2, .comments-modal-header h2 {
                font-size: 20px;
                margin-top: 20px;
            }
            .close-modal, .close-comments-modal {
                position: fixed;
                top: 15px; /* Ближе к верху */
                right: 15px; /* Ближе к правому краю */
                font-size: 24px; /* Уменьшен размер */
                width: 28px;
                height: 28px;
            }
        }
        /* Desktop styles */
        @media (min-width: 768px) {
            html {
                font-size: 16px;
            }
            header {
                padding: 12px 0;
            }
            .header-content {
                flex-direction: row;
                gap: 20px;
            }
            .logo-image {
                width: 24px;
                height: 24px;
            }
            .logo-text h1 {
                font-size: 14px;
            }
            .logo-text p {
                font-size: 8px;
            }
            nav a {
                margin: 0 6px;
                font-size: 12px;
            }
            .hero {
                padding: 140px 0 80px;
            }
            .hero-content {
                flex-direction: row;
                align-items: flex-start;
                text-align: left;
                gap: 50px;
            }
            .hero-text {
                max-width: none;
                text-align: left;
                padding: 0;
            }
            .hero-text h2 {
                font-size: 48px;
            }
            .hero-text p {
                font-size: 20px;
            }
            .hero-buttons {
                flex-direction: row;
                gap: 16px;
                justify-content: flex-start;
                max-width: none;
            }
            .hero-image {
                max-width: 600px;
            }
            .hero-image img {
                border-radius: 20px;
                box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
            }
            .section-header h2 {
                font-size: 40px;
            }
            .section-header p {
                font-size: 20px;
            }
            .products-grid, .team-grid, .reviews-grid {
                grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
                gap: 32px;
            }
            .product-image {
                height: 180px;
            }
            .member-image-container {
                height: 256px;
            }
            .contact-content {
                flex-direction: row;
                gap: 48px;
            }
            .modal-content, .comments-modal-content {
                width: 90%;
                max-width: 800px;
                padding: 32px;
            }
            .specs-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            .spec-item {
                flex-direction: row;

Евген, [31.10.2025 09:25]
justify-content: space-between;
            }
            .spec-label {
                text-align: left;
                margin-bottom: 0;
            }
            .spec-value {
                text-align: right;
            }
        }
        @media (min-width: 1024px) {
            .hero-content {
                gap: 64px;
            }
        }
        /* Анимированные картинки */
        .animated-images-container {
            position: relative;
            width: 100%;
            height: 300px; /* Увеличен размер */
            overflow: hidden;
            border-radius: 16px;
            border: 2px solid var(--primary);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
        }
        .animated-images-wrapper {
            display: flex;
            height: 100%;
            transition: transform 0.5s ease-in-out;
        }
        .animated-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 16px;
            flex-shrink: 0;
            opacity: 0;
            transition: opacity 0.5s ease;
        }
        .animated-image.active {
            opacity: 1;
        }
        .carousel-controls {
            position: absolute;
            top: 50%;
            left: 0;
            right: 0;
            display: flex;
            justify-content: space-between;
            transform: translateY(-50%);
            z-index: 10;
        }
        .carousel-control {
            background: rgba(3, 7, 18, 0.7);
            color: white;
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 20px;
            transition: background 0.3s;
        }
        .carousel-control:hover {
            background: var(--primary);
        }
        .carousel-indicators {
            position: absolute;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 8px;
        }
        .carousel-indicator {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.5);
            cursor: pointer;
            transition: background 0.3s;
        }
        .carousel-indicator.active {
            background: var(--primary);
        }
        /* Flag styles */
        .flag {
            width: 24px;
            height: 24px;
            border-radius: 50%;
            object-fit: cover;
            cursor: pointer;
            transition: transform 0.3s;
        }
        .flag:hover {
            transform: scale(1.1);
        }
        .flags-container {
            display: flex;
            gap: 6px;
        }
    </style>
</head>
<body>
    <header id="header">
        <div class="container">
            <div class="header-content">
                <div class="logo-container" onclick="scrollToSection('home')">
                    <img src="https://i.postimg.cc/8jPC5nX7/37a79315-54e3-4833-870a-3b09e5a6d073.jpg" alt="KazakhIT Логотип" class="logo-image">
                    <div class="logo-text">
                        <h1 data-translate="logo-title">KazakhIT </h1>
                        <p data-translate="logo-subtitle">Технологии будущего</p>
                    </div>
                </div>
                <div class="nav-container">
                    <nav>
                        <a href="#" data-target="home" class="nav-link" data-translate="nav-home">Главная</a>
                        <a href="#" data-target="products" class="nav-link" data-translate="nav-products">Товары</a>
                        <a href="#" data-target="team" class="nav-link" data-translate="nav-team">Команда</a>
                        <a href="#" data-target="reviews" class="nav-link" data-translate="nav-reviews">Отзывы</a>

Евген, [31.10.2025 09:25]
<a href="#" data-target="addresses" class="nav-link" data-translate="nav-addresses">Адреса</a>
                        <a href="#" data-target="contact" class="nav-link" data-translate="nav-contact">Контакты</a>
                    </nav>
                </div>
            </div>
        </div>
    </header>
    <div class="top-right-widgets">
        <div class="currency-selector">
            <button class="currency-btn active" data-currency="RUB" data-translate="currency-rub">₽</button>
            <div class="dropdown-menu" id="currency-menu">
                <button class="dropdown-item" data-currency="RUB" data-translate="currency-rub-full">₽ Рубль</button>
                <button class="dropdown-item" data-currency="USD" data-translate="currency-usd-full">$ Доллар</button>
                <button class="dropdown-item" data-currency="CNY" data-translate="currency-cny-full">¥ Юань</button>
            </div>
        </div>
        <div class="language-selector">
            <button class="lang-btn active" data-lang="ru" data-translate="lang-ru">RU</button>
            <div class="dropdown-menu" id="language-menu">
                <button class="dropdown-item" data-lang="ru" data-translate="lang-ru-full">Русский</button>
                <button class="dropdown-item" data-lang="en" data-translate="lang-en-full">English</button>
                <button class="dropdown-item" data-lang="zh" data-translate="lang-zh-full">中文</button>
                <button class="dropdown-item" data-lang="ky" data-translate="lang-ky-full">Кыргызча</button>
            </div>
        </div>
        <div class="flags-container">
            <img src="https://flagcdn.com/ru.svg" alt="Русский" class="flag" data-lang="ru">
            <img src="https://flagcdn.com/us.svg" alt="English" class="flag" data-lang="en">
            <img src="https://flagcdn.com/cn.svg" alt="中文" class="flag" data-lang="zh">
            <img src="https://flagcdn.com/kg.svg" alt="Кыргызча" class="flag" data-lang="ky">
        </div>
    </div>
    <section id="home" class="hero">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h2><span data-translate="hero-title">KazakhIT — </span> <span data-translate="hero-subtitle">ваш надежный партнер</span></h2>
                    <p data-translate="hero-text">Мы создаем инновационные решения, которые меняют бизнес и повседневную жизнь.</p>
                    <div class="hero-buttons">
                        <a href="#" class="btn btn-primary" data-target="contact" data-translate="btn-contact">Связаться</a>
                        <a href="#" class="btn btn-outline" data-target="products" data-translate="btn-products">Товары</a>
                    </div>
                </div>
                <div class="hero-image">
                    <!-- Анимированные картинки -->
                    <div class="animated-images-container">
                        <div class="animated-images-wrapper" id="animated-images-wrapper">
                            <img src="https://i.postimg.cc/FFMD0yxj/amd.webp" alt="AMD" class="animated-image">
                            <img src="https://i.postimg.cc/k5gc7fnX/apple-m4.jpg" alt="Apple M4" class="animated-image">
                            <img src="https://i.postimg.cc/wvScczD9/intel.webp" alt="Intel" class="animated-image">
                            <img src="https://i.postimg.cc/jSs6hZnK/snap.webp" alt="Snapdragon" class="animated-image">
                        </div>
                        <div class="carousel-controls">
                            <button class="carousel-control" id="prev-btn"><</button>
                            <button class="carousel-control" id="next-btn">></button>
                        </div>
                        <div class="carousel-indicators" id="carousel-indicators"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <section id="products" class="products">
        <div class="container">

Евген, [31.10.2025 09:25]
<div class="section-header">
                <h2 data-translate="products-title">Наши ноутбуки</h2>
                <p data-translate="products-subtitle">Широкий выбор моделей для работы, учёбы и игр</p>
            </div>
            <div class="products-grid" id="products-grid"></div>
        </div>
    </section>
    <section id="team" class="team">
        <div class="container">
            <div class="section-header">
                <h2 data-translate="team-title">Наша команда</h2>
                <p data-translate="team-subtitle">Профессионалы своего дела</p>
            </div>
            <div class="team-grid">
                <div class="team-member">
                    <div class="member-image-container">
                        <img src="https://iimg.su/i/cuEYcO" alt="Евгений" class="member-image">
                    </div>
                    <div class="member-info">
                        <h3>Евгений</h3>
                        <span class="role" data-translate="role-ceo">Генеральный директор</span>
                        <p data-translate="role-ceo-desc">Лидер команды с 15-летним опытом в IT-индустрии.</p>
                    </div>
                </div>
                <div class="team-member">
                    <div class="member-image-container">
                        <img src="https://i.postimg.cc/d3t2gdCQ/z.jpg" alt="Захар" class="member-image">
                    </div>
                    <div class="member-info">
                        <h3>Захар</h3>
                        <span class="role" data-translate="role-director">Директор</span>
                        <p data-translate="role-director-desc">Организатор процессов и управления проектами.</p>
                    </div>
                </div>
                <div class="team-member">
                    <div class="member-image-container">
                        <img src="" alt="Кирилл" class="member-image">
                    </div>
                    <div class="member-info">
                        <h3>Кирил Мамбет</h3>
                        <span class="role" data-translate="role-accountant">Бухгалтер</span>
                        <p data-translate="role-accountant-desc">Финансовый эксперт, гарантирует стабильность.</p>
                    </div>
                </div>
                <div class="team-member">
                    <div class="member-image-container">
                        <img src="https://iimg.su/i/gc4q3N" alt="Костя" class="member-image">
                    </div>
                    <div class="member-info">
                        <h3>Костя</h3>
                        <span class="role" data-translate="role-cleaner">Уборщик</span>
                        <p data-translate="role-cleaner-desc">Зелёный гоблин с болота, поддерживает чистоту.</p>
                    </div>
                </div>
                <div class="team-member">
                    <div class="member-image-container">
                        <img src="https://i.postimg.cc/BncvPzk0/m.jpg" alt="Марлэс" class="member-image">
                    </div>
                    <div class="member-info">
                        <h3>Марлэс Назармбетов</h3>
                        <span class="role" data-translate="role-consultant">Консультант</span>
                        <p data-translate="role-consultant-desc">Классный парень, хороший тип!</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <section id="reviews" class="reviews">
        <div class="container">
            <div class="section-header">
                <div class="site-rating">
                    <div class="site-rating-stars">★★★★★</div>
                    <div class="site-rating-value">4.9 из 5</div>
                </div>
                <h2 data-translate="reviews-title">Отзывы клиентов</h2>
                <p data-translate="reviews-subtitle">Что говорят наши клиенты о нас</p>
            </div>
            <div class="reviews-grid" id="reviews-grid"></div>

Евген, [31.10.2025 09:25]
<button class="show-more" id="showMoreBtn" data-translate="btn-show-more">Показать ещё</button>
            <div class="review-form">
                <h3 data-translate="review-form-title">Оставить отзыв</h3>
                <form id="review-form">
                    <div class="form-row">
                        <div class="form-group">
                            <label for="first-name" data-translate="form-first-name">Имя</label>
                            <input type="text" id="first-name" placeholder="Ваше имя" required>
                        </div>
                        <div class="form-group">
                            <label for="last-name" data-translate="form-last-name">Фамилия</label>
                            <input type="text" id="last-name" placeholder="Ваша фамилия" required>
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="email" data-translate="form-email">Email</label>
                        <input type="email" id="email" placeholder="Ваш email" required>
                    </div>
                    <div class="form-group">
                        <label data-translate="form-rating">Оценка</label>
                        <div class="rating-selection">
                            <span class="rating-star" data-rating="1">★</span>
                            <span class="rating-star" data-rating="2">★</span>
                            <span class="rating-star" data-rating="3">★</span>
                            <span class="rating-star" data-rating="4">★</span>
                            <span class="rating-star" data-rating="5">★</span>
                        </div>
                    </div>
                    <div class="form-group form-group-full">
                        <label for="review-text" data-translate="form-review">Отзыв</label>
                        <textarea id="review-text" placeholder="Ваш отзыв" required></textarea>
                    </div>
                    <button type="submit" class="submit-review" data-translate="btn-submit-review">Отправить отзыв</button>
                </form>
            </div>
        </div>
    </section>
    <section id="addresses" class="addresses">
        <div class="container">
            <div class="section-header">
                <h2 data-translate="addresses-title">Наши адреса</h2>
                <p data-translate="addresses-subtitle">Посетите наши магазины в удобное для вас время</p>
            </div>
            <div class="addresses-content">
                <div class="address-info">
                    <div class="address-title" data-translate="address-title">Адрес</div>
                    <div class="address-text">г. Волгоград, ул. 64-й Армии, 117</div>
                    <div class="address-shop">Магазин электроники "KazakhIT"</div>
                </div>
                <div class="map-container">
                    <iframe class="map" src="https://yandex.ru/map-widget/v1/?um=constructor%3A498286b9ae2782994d80e523f4c55490e1388505e72ae1bab1cc23630b6b58be&amp;source=constructor" width="600" height="380" frameborder="0"></iframe>
                </div>
            </div>
        </div>
    </section>
    <section id="contact" class="contact">
        <div class="container">
            <div class="section-header">
                <h2 data-translate="contact-title">Свяжитесь с нами</h2>
                <p data-translate="contact-subtitle">Напишите нам — ответим в ближайшее время</p>
            </div>
            <div class="contact-content">
                <div class="contact-info">
                    <div class="contact-item">
                        <div class="contact-icon"><i class="fas fa-phone"></i></div>
                        <div class="contact-details"><h3 data-translate="contact-phone">Телефон</h3><p>+7 (993) 322-51-69</p></div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon"><i class="fas fa-envelope"></i></div>

Евген, [31.10.2025 09:25]
<div class="contact-details"><h3 data-translate="contact-email">Email</h3><p>sinxays3@mail.ru</p></div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon"><i class="fas fa-map-marker-alt"></i></div>
                        <div class="contact-details"><h3 data-translate="contact-address">Адрес</h3><p>г. Волгоград, ул. 64-й Армии, 117</p></div>
                    </div>
                </div>
                <div class="contact-form">
                    <form>
                        <div class="form-group"><label for="name" data-translate="form-name">Имя</label><input type="text" id="name" placeholder="Ваше имя" required></div>
                        <div class="form-group"><label for="email" data-translate="form-email">Email</label><input type="email" id="email" placeholder="Ваш email" required></div>
                        <div class="form-group"><label for="message" data-translate="form-message">Сообщение</label><textarea id="message" placeholder="Ваше сообщение" required></textarea></div>
                        <button type="submit" class="btn btn-primary" style="width: 100%;" data-translate="btn-send">Отправить</button>
                    </form>
                </div>
            </div>
        </div>
    </section>
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-logo">
                    <img src="https://i.postimg.cc/8jPC5nX7/37a79315-54e3-4833-870a-3b09e5a6d073.jpg" alt="KazakhIT Логотип" class="logo-image">
                    <div>
                        <h3 data-translate="footer-title">KazakhIT</h3>
                        <p data-translate="footer-subtitle">Технологии будущего</p>
                    </div>
                </div>
                <div class="copyright" data-translate="footer-copyright">© 2025 KazakhIT. Все права защищены.</div>
            </div>
        </div>
    </footer>
    <div class="modal" id="productModal">
        <div class="modal-content">
            <button class="close-modal" id="closeModal">&times;</button>
            <div class="modal-header">
                <h2 id="modal-title" data-translate="modal-title">Ноутбук</h2>
            </div>
            <div class="specs-grid" id="modal-specs"></div>
        </div>
    </div>
    <div class="comments-modal" id="commentsModal">
        <div class="comments-modal-content">
            <button class="close-comments-modal" id="closeCommentsModal">&times;</button>
            <div class="comments-modal-header">
                <h2 id="comments-modal-title" data-translate="comments-modal-title">Отзывы</h2>
            </div>
            <div class="comments-list" id="comments-list"></div>
        </div>
    </div>
    <script>
        const laptopModels = [
            { brand: 'Dell', model: 'XPS 13', image: 'https://i.postimg.cc/SKTNDhDR/Dell-XPS-13.webp' },
            { brand: 'HP', model: 'Spectre x360', image: 'https://i.postimg.cc/sDXmN9jy/HP-Spectre-x360.jpg' },
            { brand: 'Lenovo', model: 'ThinkPad X1', image: 'https://i.postimg.cc/25VfjB7C/Lenovo-Think-Pad-X1.jpg' },
            { brand: 'Asus', model: 'ZenBook Pro', image: 'https://i.postimg.cc/G90WqMWp/Asus-Zen-Book-Pro.webp' },
            { brand: 'Acer', model: 'Swift 5', image: 'https://i.postimg.cc/G2LhjpFp/Acer-Swift-5.jpg' },
            { brand: 'MSI', model: 'GS66 Stealth', image: 'https://i.postimg.cc/vBfkD7gb/MSI-GS66-Stealth.webp' },
            { brand: 'Apple', model: 'MacBook Pro', image: 'https://i.postimg.cc/pr9v05yG/Apple-Mac-Book-Pro.jpg' },
            { brand: 'Samsung', model: 'Galaxy Book3', image: 'https://i.postimg.cc/L66QMFVc/Samsung-Galaxy-Book3.webp' },
            { brand: 'Razer', model: 'Blade 15', image: 'https://i.postimg.cc/fRyPYQt7/razer-blade-15.jpg' },
            { brand: 'Microsoft', model: 'Surface Laptop 5', image: 'https://i.postimg.cc/sggkKZ86/Microsoft-Surface-Laptop-5.png' },

Евген, [31.10.2025 09:25]
{ brand: 'Alienware', model: 'm18', image: 'https://i.postimg.cc/D0DvFdRD/alienware-m18.jpg' },
            { brand: 'HP', model: 'Victus 15', image: 'https://i.postimg.cc/43dXK0sg/HP-Victus-15.webp' },
            { brand: 'Lenovo', model: 'Legion Pro 7i', image: 'https://i.postimg.cc/02sxGjPL/Lenovo-Legion-Pro-7i.jpg' },
            { brand: 'Asus', model: 'ROG Zephyrus G14', image: 'https://i.postimg.cc/2jJr1GK5/Asus-ROG-Zephyrus-G14.webp' },
            { brand: 'Dell', model: 'Latitude 5430', image: 'https://i.postimg.cc/W1V34SdL/Dell-Latitude-5430.webp' },
            { brand: 'Acer', model: 'Predator Helios', image: 'https://i.postimg.cc/tCwJHpjn/Acer-Predator-Helios.webp' },
            { brand: 'MSI', model: 'Katana 15', image: 'https://i.postimg.cc/Kc7C2NhV/MSI-Katana-15.jpg' },
            { brand: 'Apple', model: 'MacBook Air M2', image: 'https://i.postimg.cc/ZKBYH2dN/Apple-Mac-Book-Air-M2.webp' },
            { brand: 'Samsung', model: 'Galaxy Book4 Pro', image: 'https://i.postimg.cc/Cx9cDBV8/Samsung-Galaxy-Book4-Pro.jpg' },
            { brand: 'Huawei', model: 'MateBook X Pro', image: 'https://i.postimg.cc/Y9LkRm4p/Huawei-Mate-Book-X-Pro.png' },
            { brand: 'Xiaomi', model: 'RedmiBook Pro 15', image: 'https://i.postimg.cc/gjcsd33H/Xiaomi-Redmi-Book-Pro-15.jpg' },
            { brand: 'Gigabyte', model: 'Aero 16 OLED', image: 'https://i.postimg.cc/dt2sgd5L/Gigabyte-Aero-16-OLED.png' },
            { brand: 'Asus', model: 'VivoBook 15', image: 'https://i.postimg.cc/QMXr2yHz/Asus-Vivo-Book-15.webp' },
            { brand: 'Lenovo', model: 'Yoga Slim 7 Pro', image: 'https://i.postimg.cc/WzmBYmsR/Lenovo-Yoga-Slim-7-Pro.webp' }
        ];
        const processors = ['Intel Core i5-1240P', 'Intel Core i7-1260P', 'AMD Ryzen 7 6800U', 'Apple M2', 'Intel Core i9-12900H', 'AMD Ryzen 9 7940HS', 'Intel Core Ultra 7'];
        const rams = ['8 ГБ', '16 ГБ', '32 ГБ', '64 ГБ'];
        const storages = ['256 ГБ SSD', '512 ГБ SSD', '1 ТБ SSD', '2 ТБ SSD'];
        const screens = ['13.3" FHD', '14" QHD', '15.6" FHD', '16" 4K', '14.5" OLED 2.8K', '18" QHD+ 240Hz'];
        const gpus = ['Intel Iris Xe', 'NVIDIA RTX 3050', 'NVIDIA RTX 4060', 'AMD Radeon 680M', 'Apple M2 GPU', 'NVIDIA RTX 4080', 'GeForce RTX 4090'];
        const laptops = [];
        // Генерация отзывов для каждого ноутбука
        const generateReviews = (laptopId) => {
            const laptopReviews = [];
            const reviewCount = Math.floor(Math.random() * 7) + 1; // От 1 до 7 отзывов
            for (let i = 0; i < reviewCount; i++) {
                const rating = (Math.random() * 0.5 + 4.5).toFixed(1); // Оценка от 4.5 до 5.0
                const reviewers = ['Алексей Петров', 'Мария Сидорова', 'Дмитрий Иванов', 'Елена Козлова', 'Андрей Николаев', 'Ольга Морозова', 'Михаил Федоров', 'Татьяна Волкова', 'Сергей Павлов', 'Наталья Орлова', 'Иван Семенов', 'Анна Лебедева', 'Константин Волков', 'Ирина Назарова', 'Роман Кузнецов', 'Екатерина Фролова', 'Александр Медведев', 'Виктория Сорокина', 'Артем Григорьев', 'Дарья Беляева', 'Павел Зайцев', 'Юлия Яковлева', 'Максим Гусев', 'Алина Осипова', 'Владимир Фомин', 'Евгения Новикова', 'Антон Виноградов', 'Оксана Крылова', 'Борис Максимов', 'Светлана Алексеева', 'Роман Соколов', 'Анна Михайлова', 'Денис Белов', 'Марина Семенова', 'Алексей Герасимов', 'Елена Егорова', 'Игорь Поляков', 'Нина Дмитриева', 'Андрей Тимофеев', 'Татьяна Казакова', 'Виктор Степанов', 'Ксения Орехова', 'Григорий Назаров', 'Валерия Савельева'];
                const texts = [
                    'Отличный сервис! Быстро оформили заказ, доставили вовремя. Ноутбук работает отлично, спасибо!',
                    'Очень довольна покупкой. Консультант помог выбрать подходящую модель, всё объяснил. Рекомендую!',
                    'Работаю на ноутбуке уже полгода - всё отлично. Не греется, быстро запускается, батарея держит долго.',
                    'Быстрая доставка, качественный товар. Сотрудники вежливые и компетентные. Спасибо за отличный сервис!',

Евген, [31.10.2025 09:25]
'Цены радуют, ассортимент большой. Выбрал себе ноутбук для работы, работает безотказно.',
                    'Очень довольна покупкой! Качество на высоте, сервис отличный. Обязательно буду обращаться снова.',
                    'Рекомендую эту компанию. Быстро, надежно, качественно. Ноутбук работает как часы.',
                    'Прекрасный выбор ноутбуков, консультанты знают свое дело. Спасибо за помощь в выборе.',
                    'Отличное качество, быстрая доставка. Работаю на этом ноутбуке каждый день - всё устраивает.',
                    'Покупкой довольна. Ноутбук работает исправно, дизайн приятный, цена радует.',
                    'Очень доволен сервисом. Быстро оформили заказ, доставили вовремя. Рекомендую!',
                    'Отличный выбор техники, профессиональные консультанты. Покупкой полностью довольна.',
                    'Работаю на ноутбуке уже несколько месяцев - всё отлично. Рекомендую всем!',
                    'Очень приятно удивлена качеством обслуживания. Спасибо за отличный сервис!',
                    'Быстро, удобно, надежно. Ноутбук работает отлично, рекомендую эту компанию.',
                    'Прекрасный выбор, быстрая доставка. Спасибо за отличный сервис и качественный товар.',
                    'Работаю на этом ноутбуке каждый день - всё устраивает. Рекомендую!',
                    'Очень довольна покупкой. Качество, сервис и доставка на высшем уровне.',
                    'Отличный выбор техники, всё работает исправно. Рекомендую всем друзьям.',
                    'Прекрасный сервис, вежливые сотрудники. Покупкой полностью довольна.',
                    'Быстрая доставка, качественный товар. Работаю на ноутбуке каждый день.',
                    'Отличный выбор, приятные цены. Спасибо за помощь в выборе и быструю доставку.',
                    'Рекомендую эту компанию. Все на высшем уровне - сервис, качество, цены.',
                    'Очень довольна покупкой. Ноутбук работает отлично, спасибо за отличный сервис!',
                    'Работаю на ноутбуке уже несколько месяцев - всё устраивает. Рекомендую!',
                    'Прекрасный выбор техники, профессиональные консультанты. Спасибо!',
                    'Быстрая доставка, отличное качество. Работаю на ноутбуке каждый день.',
                    'Очень довольна покупкой. Сервис на высшем уровне, рекомендую всем!',
                    'Рекомендую эту компанию. Быстро, надежно, качественно. Спасибо!',
                    'Прекрасный выбор, отличный сервис. Покупкой полностью довольна.',
                    'Работаю на ноутбуке каждый день - всё устраивает. Рекомендую!',
                    'Очень приятно удивлена качеством обслуживания. Спасибо за отличный сервис!',
                    'Быстро, удобно, надежно. Ноутбук работает отлично, рекомендую эту компанию.',
                    'Прекрасный выбор техники, быстрая доставка. Спасибо за отличный сервис!',
                    'Работаю на этом ноутбуке каждый день - всё устраивает. Рекомендую!',
                    'Очень довольна покупкой. Качество, сервис и доставка на высшем уровне.',
                    'Отличный выбор техники, всё работает исправно. Рекомендую всем друзьям.',
                    'Прекрасный сервис, вежливые сотрудники. Покупкой полностью довольна.',
                    'Быстрая доставка, качественный товар. Работаю на ноутбуке каждый день.',
                    'Отличный выбор, приятные цены. Спасибо за помощь в выборе и быструю доставку.',
                    'Рекомендую эту компанию. Все на высшем уровне - сервис, качество, цены.',
                    'Очень довольна покупкой. Ноутбук работает отлично, спасибо за отличный сервис!',
                    'Работаю на ноутбуке уже несколько месяцев - всё устраивает. Рекомендую!',
                    'Прекрасный выбор техники, профессиональные консультанты. Спасибо!'
                ];
                laptopReviews.push({
                    id: laptopId * 100 + i,
                    laptopId: laptopId,

Евген, [31.10.2025 09:25]
name: reviewers[Math.floor(Math.random() * reviewers.length)],
                    text: texts[Math.floor(Math.random() * texts.length)],
                    rating: parseFloat(rating)
                });
            }
            return laptopReviews;
        };
        for (let i = 0; i < laptopModels.length; i++) {
            const laptopModel = laptopModels[i];
            const processor = processors[Math.floor(Math.random() * processors.length)];
            const ram = rams[Math.floor(Math.random() * rams.length)];
            const storage = storages[Math.floor(Math.random() * storages.length)];
            const screen = screens[Math.floor(Math.random() * screens.length)];
            const gpu = gpus[Math.floor(Math.random() * gpus.length)];
            const price = Math.floor(Math.random() * 400000) + 50000;
            const rating = (Math.random() * 0.2 + 4.8).toFixed(1); // Оценка от 4.8 до 5.0
            laptops.push({
                id: i + 1,
                name: ${laptopModel.brand} ${laptopModel.model},
                price: price,
                summary: ${screen}, ${processor}, ${ram} RAM,
                image: laptopModel.image,
                rating: rating,
                specs: {
                    'Модель': ${laptopModel.brand} ${laptopModel.model},
                    'Процессор': processor,
                    'Оперативная память': ram,
                    'Накопитель': storage,
                    'Экран': screen,
                    'Видеокарта': gpu,
                    'Операционная система': 'Windows 11 Pro',
                    'Вес': '1.3 кг',
                    'Батарея': 'до 12 часов',
                    'Порты': '2x USB-C, 1x USB-A, HDMI, аудио',
                    'Wi-Fi': 'Wi-Fi 6E',
                    'Bluetooth': 'Bluetooth 5.2',
                    'Камера': '1080p HD',
                    'Микрофон': 'Да, с шумоподавлением',
                    'Клавиатура': 'С подсветкой',
                    'Цвет': 'Серый / Серебристый',
                    'Гарантия': '2 года',
                    'Страна сборки': 'Китай',
                    'Дата выхода': '2024'
                },
                reviews: generateReviews(i + 1) // Генерируем отзывы для каждого ноутбука
            });
        }
        // Курсы обмена
        const exchangeRates = {
            RUB: 1,
            USD: 0.012, // Условный курс
            CNY: 0.088  // Условный курс
        };
        // Текущая валюта
        let currentCurrency = 'RUB';
        // Текущий язык
        let currentLanguage = 'ru';
        // Словарь переводов
        const translations = {
            ru: {
                'logo-title': 'KazakhIT',
                'logo-subtitle': 'Технологии будущего',
                'nav-home': 'Главная',
                'nav-products': 'Товары',
                'nav-team': 'Команда',
                'nav-reviews': 'Отзывы',
                'nav-addresses': 'Адреса',
                'nav-contact': 'Контакты',
                'currency-rub': '₽',
                'currency-usd': '$',
                'currency-cny': '¥',
                'currency-rub-full': '₽ Рубль',
                'currency-usd-full': '$ Доллар',
                'currency-cny-full': '¥ Юань',
                'lang-ru': 'RU',
                'lang-en': 'EN',
                'lang-zh': 'ZH',
                'lang-ky': 'KG',
                'lang-ru-full': 'Русский',
                'lang-en-full': 'English',
                'lang-zh-full': '中文',
                'lang-ky-full': 'Кыргызча',
                'hero-title': 'KazakhIT',
                'hero-subtitle': '— ваш надежный партнер',
                'hero-text': 'Мы создаем инновационные решения, которые меняют бизнес и повседневную жизнь.',
                'btn-contact': 'Связаться',
                'btn-products': 'Товары',
                'products-title': 'Наши ноутбуки',
                'products-subtitle': 'Широкий выбор моделей для работы, учёбы и игр',
                'team-title': 'Наша команда',
                'team-subtitle': 'Профессионалы своего дела',

Евген, [31.10.2025 09:25]
'role-ceo': 'Генеральный директор',
                'role-ceo-desc': 'Лидер команды с 15-летним опытом в IT-индустрии.',
                'role-director': 'Директор',
                'role-director-desc': 'Организатор процессов и управления проектами.',
                'role-accountant': 'Бухгалтер',
                'role-accountant-desc': 'Финансовый эксперт, гарантирует стабильность.',
                'role-cleaner': 'Уборщик',
                'role-cleaner-desc': 'Зелёный гоблин с болота, поддерживает чистоту.',
                'role-consultant': 'Консультант',
                'role-consultant-desc': 'Классный парень, хороший тип!',
                'reviews-title': 'Отзывы клиентов',
                'reviews-subtitle': 'Что говорят наши клиенты о нас',
                'btn-show-more': 'Показать ещё',
                'review-form-title': 'Оставить отзыв',
                'form-first-name': 'Имя',
                'form-last-name': 'Фамилия',
                'form-email': 'Email',
                'form-rating': 'Оценка',
                'form-review': 'Отзыв',
                'btn-submit-review': 'Отправить отзыв',
                'addresses-title': 'Наши адреса',
                'addresses-subtitle': 'Посетите наши магазины в удобное для вас время',
                'address-title': 'Адрес',
                'contact-title': 'Свяжитесь с нами',
                'contact-subtitle': 'Напишите нам — ответим в ближайшее время',
                'contact-phone': 'Телефон',
                'contact-email': 'Email',
                'contact-address': 'Адрес',
                'form-name': 'Имя',
                'form-message': 'Сообщение',
                'btn-send': 'Отправить',
                'footer-title': 'KazakhIT',
                'footer-subtitle': 'Технологии будущего',
                'footer-copyright': '© 2025 KazakhIT. Все права защищены.',
                'modal-title': 'Ноутбук',
                'comments-modal-title': 'Отзывы',
                'btn-details': 'Подробнее',
                'btn-comments': 'Отзывы'
            },
            en: {
                'logo-title': 'KazakhIT',
                'logo-subtitle': 'Future Technologies',
                'nav-home': 'Home',
                'nav-products': 'Products',
                'nav-team': 'Team',
                'nav-reviews': 'Reviews',
                'nav-addresses': 'Addresses',
                'nav-contact': 'Contact',
                'currency-rub': '₽',
                'currency-usd': '$',
                'currency-cny': '¥',
                'currency-rub-full': '₽ Ruble',
                'currency-usd-full': '$ Dollar',
                'currency-cny-full': '¥ Yuan',
                'lang-ru': 'RU',
                'lang-en': 'EN',
                'lang-zh': 'ZH',
                'lang-ky': 'KG',
                'lang-ru-full': 'Русский',
                'lang-en-full': 'English',
                'lang-zh-full': '中文',
                'lang-ky-full': 'Кыргызча',
                'hero-title': 'KazakhIT',
                'hero-subtitle': '— your reliable partner',
                'hero-text': 'We create innovative solutions that change business and everyday life.',
                'btn-contact': 'Contact',
                'btn-products': 'Products',
                'products-title': 'Our Laptops',
                'products-subtitle': 'Wide selection of models for work, study, and gaming',
                'team-title': 'Our Team',
                'team-subtitle': 'Professionals in their field',
                'role-ceo': 'CEO',
                'role-ceo-desc': 'Team leader with 15 years of experience in the IT industry.',
                'role-director': 'Director',
                'role-director-desc': 'Process and project management organizer.',
                'role-accountant': 'Accountant',
                'role-accountant-desc': 'Financial expert, guarantees stability.',
                'role-cleaner': 'Cleaner',
                'role-cleaner-desc': 'Green goblin from the swamp, maintains cleanliness.',

Евген, [31.10.2025 09:25]
'role-consultant': 'Consultant',
                'role-consultant-desc': 'Cool guy, good type!',
                'reviews-title': 'Customer Reviews',
                'reviews-subtitle': 'What our customers say about us',
                'btn-show-more': 'Show More',
                'review-form-title': 'Leave a Review',
                'form-first-name': 'First Name',
                'form-last-name': 'Last Name',
                'form-email': 'Email',
                'form-rating': 'Rating',
                'form-review': 'Review',
                'btn-submit-review': 'Submit Review',
                'addresses-title': 'Our Addresses',
                'addresses-subtitle': 'Visit our stores at your convenience',
                'address-title': 'Address',
                'contact-title': 'Contact Us',
                'contact-subtitle': 'Write to us — we will respond as soon as possible',
                'contact-phone': 'Phone',
                'contact-email': 'Email',
                'contact-address': 'Address',
                'form-name': 'Name',
                'form-message': 'Message',
                'btn-send': 'Send',
                'footer-title': 'KazakhIT',
                'footer-subtitle': 'Future Technologies',
                'footer-copyright': '© 2025 KazakhIT. All rights reserved.',
                'modal-title': 'Laptop',
                'comments-modal-title': 'Reviews',
                'btn-details': 'Details',
                'btn-comments': 'Reviews'
            },
            zh: {
                'logo-title': 'KazakhIT',
                'logo-subtitle': '未来技术',
                'nav-home': '首页',
                'nav-products': '产品',
                'nav-team': '团队',
                'nav-reviews': '评价',
                'nav-addresses': '地址',
                'nav-contact': '联系',
                'currency-rub': '₽',
                'currency-usd': '$',
                'currency-cny': '¥',
                'currency-rub-full': '₽ 卢布',
                'currency-usd-full': '$ 美元',
                'currency-cny-full': '¥ 元',
                'lang-ru': 'RU',
                'lang-en': 'EN',
                'lang-zh': 'ZH',
                'lang-ky': 'KG',
                'lang-ru-full': 'Русский',
                'lang-en-full': 'English',
                'lang-zh-full': '中文',
                'lang-ky-full': 'Кыргызча',
                'hero-title': 'KazakhIT',
                'hero-subtitle': '— 您可靠的合作伙伴',
                'hero-text': '我们创造改变商业和日常生活的创新解决方案。',
                'btn-contact': '联系',
                'btn-products': '产品',
                'products-title': '我们的笔记本电脑',
                'products-subtitle': '工作、学习和游戏的广泛型号选择',
                'team-title': '我们的团队',
                'team-subtitle': '各自领域的专业人士',
                'role-ceo': '首席执行官',
                'role-ceo-desc': '拥有15年IT行业经验的团队领导者。',
                'role-director': '总监',
                'role-director-desc': '流程和项目管理组织者。',
                'role-accountant': '会计',
                'role-accountant-desc': '财务专家，保证稳定。',
                'role-cleaner': '清洁工',
                'role-cleaner-desc': '来自沼泽的绿色哥布林，保持清洁。',
                'role-consultant': '顾问',
                'role-consultant-desc': '酷家伙，好人！',
                'reviews-title': '客户评价',
                'reviews-subtitle': '客户对我们的评价',
                'btn-show-more': '显示更多',
                'review-form-title': '留下评价',
                'form-first-name': '名字',
                'form-last-name': '姓氏',
                'form-email': '邮箱',
                'form-rating': '评分',
                'form-review': '评价',
                'btn-submit-review': '提交评价',
                'addresses-title': '我们的地址',
                'addresses-subtitle': '在方便的时候访问我们的商店',
                'address-title': '地址',
                'contact-title': '联系我们',
                'contact-subtitle': '写信给我们 — 我们将尽快回复',
                'contact-phone': '电话',
                'contact-email': '邮箱',
                'contact-address': '地址',
                'form-name': '姓名',
                'form-message': '消息',

Евген, [31.10.2025 09:25]
'btn-send': '发送',
                'footer-title': 'KazakhIT',
                'footer-subtitle': '未来技术',
                'footer-copyright': '© 2025 KazakhIT. 版权所有。',
                'modal-title': '笔记本电脑',
                'comments-modal-title': '评价',
                'btn-details': '详情',
                'btn-comments': '评价'
            },
            ky: {
                'logo-title': 'KazakhIT',
                'logo-subtitle': 'Келечек технологиялары',
                'nav-home': 'Башкы',
                'nav-products': 'Продукттар',
                'nav-team': 'Команда',
                'nav-reviews': 'Пикирлер',
                'nav-addresses': 'Даректер',
                'nav-contact': 'Байланыш',
                'currency-rub': '₽',
                'currency-usd': '$',
                'currency-cny': '¥',
                'currency-rub-full': '₽ Рубль',
                'currency-usd-full': '$ Доллар',
                'currency-cny-full': '¥ Юань',
                'lang-ru': 'RU',
                'lang-en': 'EN',
                'lang-zh': 'ZH',
                'lang-ky': 'KG',
                'lang-ru-full': 'Русский',
                'lang-en-full': 'English',
                'lang-zh-full': '中文',
                'lang-ky-full': 'Кыргызча',
                'hero-title': 'KazakhIT',
                'hero-subtitle': '— сендин ишенчүү өнөктөшүң',
                'hero-text': 'Биз бизнес жана күнүмдүк өмүрдү өзгөртө турган инновациялык чечимдер жаратабыз.',
                'btn-contact': 'Байланышуу',
                'btn-products': 'Продукттар',
                'products-title': 'Биздин ноутбуктар',
                'products-subtitle': 'Жумуш, окуу жана оюн үчүн кеңири модельдөрдүн тандоосу',
                'team-title': 'Биздин команда',
                'team-subtitle': 'Өз ишинин профессионалы',
                'role-ceo': 'Башкаруучу директор',
                'role-ceo-desc': 'IT-сфера бойынча 15 жылдык тажрыйбага ээ команданын жетекчиси.',
                'role-director': 'Директор',
                'role-director-desc': 'Процесс жана долбоор башкаруунун уюштуруучусу.',
                'role-accountant': 'Бухгалтер',
                'role-accountant-desc': 'Карыздыкты камсыздай турган финанстык эксперт.',
                'role-cleaner': 'Тазалоочу',
                'role-cleaner-desc': 'Батыштан жашыл гоблин, тазалыкты сактайт.',
                'role-consultant': 'Консультант',
                'role-consultant-desc': 'Керемет пацан, жакшы тип!',
                'reviews-title': 'Кардарлардын пикирлери',
                'reviews-subtitle': 'Кардарлар биз жөнүндө эмне айтат',
                'btn-show-more': 'Дагы көрсөтүү',
                'review-form-title': 'Пикир калтыруу',
                'form-first-name': 'Атыңыз',
                'form-last-name': 'Фамилияңыз',
                'form-email': 'Email',
                'form-rating': 'Рейтинг',
                'form-review': 'Пикир',
                'btn-submit-review': 'Пикир жөнөтүү',
                'addresses-title': 'Биздин даректер',
                'addresses-subtitle': 'Дүкөнөбүзгө ыңгайлуу убакта келгиле',
                'address-title': 'Дарек',
                'contact-title': 'Биз менен байланышыңыз',
                'contact-subtitle': 'Бизге жазыңыз — жакын арада жооп беремиз',
                'contact-phone': 'Телефон',
                'contact-email': 'Email',
                'contact-address': 'Дарек',
                'form-name': 'Аты',
                'form-message': 'Билдирүү',
                'btn-send': 'Жөнөтүү',
                'footer-title': 'KazakhIT',
                'footer-subtitle': 'Келечек технологиялары',
                'footer-copyright': '© 2025 KazakhIT. Бардык укуктар корголгон.',
                'modal-title': 'Ноутбук',
                'comments-modal-title': 'Пикирлер',
                'btn-details': 'Чоо-жайы',
                'btn-comments': 'Пикирлер'
            }
        };
        // Функция для форматирования цены в зависимости от валюты
        function formatPrice(price, currency) {

Евген, [31.10.2025 09:25]
const rate = exchangeRates[currency];
            const convertedPrice = price * rate;
            switch(currency) {
                case 'RUB':
                    return convertedPrice.toLocaleString('ru-RU') + ' ₽';
                case 'USD':
                    return '$' + convertedPrice.toFixed(2);
                case 'CNY':
                    return '¥' + convertedPrice.toFixed(2);
                default:
                    return convertedPrice.toLocaleString('ru-RU') + ' ₽';
            }
        }
        // Функция для обновления цен на странице
        function updatePrices() {
            document.querySelectorAll('.price').forEach((element, index) => {
                const laptop = laptops[index];
                if (laptop) {
                    element.textContent = formatPrice(laptop.price, currentCurrency);
                }
            });
        }
        // Функция для обновления языка
        function updateLanguage() {
            // Обновляем все элементы с атрибутом data-translate
            const elements = document.querySelectorAll('[data-translate]');
            elements.forEach(element => {
                const key = element.getAttribute('data-translate');
                if (translations[currentLanguage][key]) {
                    if (element.tagName === 'INPUT'  element.tagName === 'TEXTAREA') {
                        element.placeholder = translations[currentLanguage][key];
                    } else {
                        element.textContent = translations[currentLanguage][key];
                    }
                }
            });
            // Обновляем тексты на кнопках в карточках товаров
            document.querySelectorAll('.btn-details').forEach(btn => {
                btn.textContent = translations[currentLanguage]['btn-details'];
            });
            document.querySelectorAll('.btn-comments').forEach(btn => {
                // Сохраняем количество отзывов, если оно было добавлено после загрузки
                const reviewCountMatch = btn.textContent.match(/\(\d+\)/);
                const reviewCount = reviewCountMatch ? reviewCountMatch[0] : '';
                btn.textContent = translations[currentLanguage]['btn-comments'] + ' ' + reviewCount;
            });
        }
        const productsGrid = document.getElementById('products-grid');
        laptops.forEach(laptop => {
            const productCard = document.createElement('div');
            productCard.className = 'product-card';
            productCard.innerHTML = `
                <div class="product-image">
                    <img src="${laptop.image}" alt="${laptop.name}">
                </div>
                <div class="product-info">
                    <h3>${laptop.name}</h3>
                    <div class="product-rating">
                        <div class="stars">${'★'.repeat(5)}</div>
                        <div class="rating-value">${laptop.rating}</div>
                    </div>
                    <div class="price">${formatPrice(laptop.price, currentCurrency)}</div>
                    <div class="summary">${laptop.summary}</div>
                    <button class="btn-details" onclick="showProductDetails(${laptop.id})" data-translate="btn-details">Подробнее</button>
                    <button class="btn-comments" onclick="showComments(${laptop.id})" data-translate="btn-comments">Отзывы (${laptop.reviews.length})</button>
                </div>
            `;
            productsGrid.appendChild(productCard);
        });
        function showProductDetails(id) {
            const laptop = laptops.find(l => l.id === id);
            if (laptop) {
                document.getElementById('modal-title').textContent = laptop.name;
                const modalSpecs = document.getElementById('modal-specs');
                modalSpecs.innerHTML = '';
                Object.entries(laptop.specs).forEach(([key, value]) => {
                    const specItem = document.createElement('div');
                    specItem.className = 'spec-item';
                    specItem.innerHTML

Евген, [31.10.2025 09:25]
= `<span class="spec-label">${key}:</span><span class="spec-value">${value}</span>`;
                    modalSpecs.appendChild(specItem);
                });
                document.getElementById('productModal').style.display = 'flex';
            }
        }
        function showComments(laptopId) {
            const laptop = laptops.find(l => l.id === laptopId);
            if (laptop) {
                document.getElementById('comments-modal-title').textContent = `Отзывы о ${laptop.name}`;
                const commentsList = document.getElementById('comments-list');
                commentsList.innerHTML = '';
                laptop.reviews.forEach(review => {
                    const commentItem = document.createElement('div');
                    commentItem.className = 'comment-item';
                    commentItem.innerHTML = `
                        <div class="comment-header">
                            <div class="comment-author">${review.name}</div>
                            <div class="comment-rating">${'★'.repeat(Math.floor(review.rating))}${review.rating % 1 !== 0 ? '★' : ''}</div>
                        </div>
                        <div class="comment-text">${review.text}</div>
                    `;
                    commentsList.appendChild(commentItem);
                });
                document.getElementById('commentsModal').style.display = 'flex';
            }
        }
        document.getElementById('closeModal').addEventListener('click', () => {
            document.getElementById('productModal').style.display = 'none';
        });
        document.getElementById('closeCommentsModal').addEventListener('click', () => {
            document.getElementById('commentsModal').style.display = 'none';
        });
        window.addEventListener('click', (e) => {
            if (e.target.id === 'productModal') {
                document.getElementById('productModal').style.display = 'none';
            }
            if (e.target.id === 'commentsModal') {
                document.getElementById('commentsModal').style.display = 'none';
            }
        });
        document.querySelector('.contact-form form').addEventListener('submit', (e) => {
            e.preventDefault();
            alert('Сообщение отправлено!');
            e.target.reset();
        });
        // Обработчики для навигации
        document.querySelectorAll('a[data-target]').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('data-target');
                scrollToSection(targetId);
            });
        });
        // Обработчики для валют
        document.querySelectorAll('.currency-btn').forEach(btn => {
            btn.addEventListener('click', function() {
                const menu = document.getElementById('currency-menu');
                menu.style.display = 'flex';
                menu.classList.remove('closing');
            });
        });
        document.querySelectorAll('.dropdown-item[data-currency]').forEach(item => {
            item.addEventListener('click', function() {
                const currency = this.getAttribute('data-currency');
                document.querySelectorAll('.currency-btn').forEach(b => b.classList.remove('active'));
                document.querySelector('.currency-btn').classList.add('active');
                document.querySelector('.currency-btn').textContent = this.textContent.charAt(0); // Отображаем только символ
                currentCurrency = currency;
                updatePrices();
                // Закрываем меню с анимацией
                const menu = document.getElementById('currency-menu');
                menu.classList.add('closing');
                setTimeout(() => {
                    menu.style.display = 'none';
                    menu.classList.remove('closing');
                }, 300);
            });
        });
        // Обработчики для языков
        document.querySelectorAll('.lang-btn').forEach(btn => {

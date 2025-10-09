<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ООО "Kazakh IT" — Ноутбуки</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f5f5f5;
            color: #333;
            line-height: 1.6;
        }

        header {
            background: url('https://i.imgur.com/2Gq7YzO.jpg') no-repeat center center;
            background-size: cover;
            padding: 25px 15px;
            text-align: center;
            color: white;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            position: relative;
        }

        .logo {
            max-width: 300px;
            margin: 0 auto 15px;
            display: block;
            filter: drop-shadow(0 2px 4px rgba(0,0,0,0.3));
        }

        h1 {
            font-size: 1.8em;
            margin-bottom: 8px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        p.subtitle {
            font-size: 1em;
            opacity: 0.9;
            text-shadow: 1px 1px 3px rgba(0,0,0,0.5);
        }

        .container {
            max-width: 1200px;
            margin: 20px auto;
            padding: 15px;
        }

        section {
            margin-bottom: 30px;
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
        }

        h2 {
            color: #007acc;
            border-bottom: 2px solid #007acc;
            padding-bottom: 5px;
            margin-bottom: 15px;
            font-size: 1.4em;
        }

        ol {
            padding-left: 20px;
            font-size: 0.95em;
        }

        li {
            margin-bottom: 8px;
        }

        /* Сотрудники как кнопки */
        .employee-card {
            background: #f9f9f9;
            padding: 12px;
            margin: 8px 0;
            border-left: 4px solid #007acc;
            border-radius: 5px;
            font-size: 0.95em;
            cursor: pointer;
            transition: background 0.2s, transform 0.1s;
            user-select: none;
        }

        .employee-card:active {
            background: #e0f0ff;
            transform: scale(0.98);
        }

        /* Товары как кнопки */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 15px;
        }

        .product-item {
            border: 1px solid #ddd;
            padding: 15px;
            text-align: center;
            border-radius: 8px;
            background: white;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
            user-select: none;
            overflow: hidden;
        }

        .product-item:hover {
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .product-item:active {
            transform: scale(0.97);
            background: #f0f8ff;
        }

        .product-item img {
            max-width: 100%;
            height: auto;
            border-radius: 5px;
            margin-bottom: 10px;
        }

        .product-title {
            font-weight: bold;
            margin-bottom: 5px;
            font-size: 1em;
            color: #007acc;
        }

        .product-specs {
            font-size: 0.85em;
            color: #555;
            line-height: 1.4;
        }

        footer {
            text-align: center;
            padding: 15px;
            background: #333;
            color: white;
            margin-top: 20px;
            font-size: 0.9em;
        }

        /* Адаптивность */
        @media (max-width: 768px) {
            .logo { max-width: 250px; }
            h1 { font-size: 1.5em; }
            .container { padding: 10px; margin: 10px; }
            section { padding: 15px; margin-bottom: 20px; }
            h2 { font-size: 1.2em; }
            .products-grid { grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 10px; }
            .product-item { padding: 12px; font-size: 0.85em; }
            .employee-card { padding: 10px; font-size: 0.9em; }
            .product-title { font-size: 0.9em; }
            .product-specs { font-size: 0.8em; }
        }

        @media (max-width: 480px) {
            header { padding: 20px 10px; }
            h1 { font-size: 1.3em; }
            .products-grid { grid-template-columns: 1fr; }
            .product-item { padding: 12px; font-size: 0.8em; }
            .employee-card { font-size: 0.85em; padding: 8px; }
            footer { padding: 10px; font-size: 0.8em; }
        }

        /* Модальное окно */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.7);
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background: white;
            padding: 20px;
            border-radius: 8px;
            max-width: 90%;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 0 5px 20px rgba(0,0,0,0.3);
            position: relative;
        }

        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
        }

        .close:hover {
            color: black;
        }

        .spec-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 15px;
            font-size: 0.85em;
        }

        .spec-table th, .spec-table td {
            border: 1px solid #ccc;
            padding: 6px;
            text-align: left;
        }

        .spec-table th {
            background: #f0f0f0;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <header>
        <img src="https://i.imgur.com/2Gq7YzO.jpg" alt="Логотип KazakhIT" class="logo">
        <h1>ООО "Kazakh IT"</h1>
        <p class="subtitle">Технологии будущего — сегодня</p>
    </header>

    <div class="container">

        <!-- Правила -->
        <section id="rules">
            <h2>Правила компании</h2>
            <ol>
                <li><strong>Не ругаться</strong> — поддерживаем уважительную атмосферу.</li>
                <li><strong>Быть вежливым</strong> — вежливость открывает двери.</li>
                <li><strong>Уважать всех работников</strong> — каждый важен для успеха компании.</li>
                <li><strong>Перерыв два раза в день</strong> — отдых — залог продуктивности.</li>
                <li><strong>Не опаздывать</strong> — время — деньги, и ваше, и компании.</li>
                <li><strong>Соблюдать технику безопасности</strong> — ваша безопасность — наш приоритет.</li>
                <li><strong>Не засорять чат</strong> — чистый чат = эффективная коммуникация.</li>
            </ol>
        </section>

        <!-- Сотрудники -->
        <section id="employees">
            <h2>Наша команда</h2>
            <div class="employee-card" data-name="Евгений" data-role="Владелец">Евгений — Владелец</div>
            <div class="employee-card" data-name="Захар" data-role="Директор">Захар — Директор</div>
            <div class="employee-card" data-name="Константин" data-role="Уборщик">Константин — Уборщик</div>
            <div class="employee-card" data-name="Кирилл" data-role="Бухгалтер">Кирилл — Бухгалтер</div>
        </section>

        <!-- Товары — Ноутбуки -->
        <section id="products">
            <h2>Наши товары — Ноутбуки</h2>
            <div class="products-grid">

                <!-- Dell XPS 13 9315 -->
                <div class="product-item" data-model="Dell XPS 13 9315">
                    <img src="https://via.placeholder.com/250x150?text=Dell+XPS+13" alt="Dell XPS 13 9315">
                    <div class="product-title">Dell XPS 13 9315</div>
                    <div class="product-specs">
                        Intel i7-1250U • 16 ГБ LPDDR5 • 512 ГБ SSD<br>
                        Intel Iris Xe • 13.4" 1920×1200 IPS
                    </div>
                </div>

                <!-- MacBook Air M2 -->
                <div class="product-item" data-model="MacBook Air M2">
                    <img src="https://via.placeholder.com/250x150?text=MacBook+Air+M2" alt="MacBook Air M2">
                    <div class="product-title">MacBook Air M2</div>
                    <div class="product-specs">
                        Apple M2 • 16 ГБ Unified • 512 ГБ SSD<br>
                        M2 GPU • 13.6" 2560×1664 Liquid Retina
                    </div>
                </div>

                <!-- ThinkPad X1 Carbon -->
                <div class="product-item" data-model="ThinkPad X1 Carbon">
                    <img src="https://via.placeholder.com/250x150?text=ThinkPad+X1" alt="ThinkPad X1 Carbon">
                    <div class="product-title">ThinkPad X1 Carbon</div>
                    <div class="product-specs">
                        Intel i7-1365U • 16 ГБ LPDDR5 • 1 ТБ SSD<br>
                        Intel Iris Xe • 14.0" 1920×1200 IPS
                    </div>
                </div>

                <!-- HP Spectre x360 14 -->
                <div class="product-item" data-model="HP Spectre x360 14">
                    <img src="https://via.placeholder.com/250x150?text=HP+Spectre" alt="HP Spectre x360 14">
                    <div class="product-title">HP Spectre x360 14</div>
                    <div class="product-specs">
                        Intel i7-1355U • 16 ГБ LPDDR5 • 1 ТБ SSD<br>
                        Intel Iris Xe • 13.5" 3000×2000 OLED
                    </div>
                </div>

                <!-- ASUS ZenBook 14X -->
                <div class="product-item" data-model="ASUS ZenBook 14X">
                    <img src="https://via.placeholder.com/250x150?text=ZenBook+14X" alt="ASUS ZenBook 14X">
                    <div class="product-title">ASUS ZenBook 14X</div>
                    <div class="product-specs">
                        Intel i9-13900H • 32 ГБ DDR5 • 1 ТБ SSD<br>
                        RTX 3050 • 14.5" 2880×1800 OLED
                    </div>
                </div>

                <!-- Acer Swift 3 -->
                <div class="product-item" data-model="Acer Swift 3">
                    <img src="https://via.placeholder.com/250x150?text=Acer+Swift+3" alt="Acer Swift 3">
                    <div class="product-title">Acer Swift 3</div>
                    <div class="product-specs">
                        AMD Ryzen 7 7730U • 16 ГБ DDR4 • 512 ГБ SSD<br>
                        Radeon • 14.0" 1920×1080 IPS
                    </div>
                </div>

                <!-- Surface Laptop 5 -->
                <div class="product-item" data-model="Surface Laptop 5">
                    <img src="https://via.placeholder.com/250x150?text=Surface+Laptop+5" alt="Surface Laptop 5">
                    <div class="product-title">Surface Laptop 5</div>
                    <div class="product-specs">
                        Intel i7-1255U • 16 ГБ LPDDR5 • 512 ГБ SSD<br>
                        Intel Iris Xe • 13.5" 2256×1504 PixelSense
                    </div>
                </div>

                <!-- MSI Summit E13 Flip -->
                <div class="product-item" data-model="MSI Summit E13 Flip">
                    <img src="https://via.placeholder.com/250x150?text=MSI+Summit" alt="MSI Summit E13 Flip">
                    <div class="product-title">MSI Summit E13 Flip</div>
                    <div class="product-specs">
                        Intel i7-1260P • 16 ГБ LPDDR5 • 1 ТБ SSD<br>
                        Intel Iris Xe • 13.3" 1920×1080 IPS
                    </div>
                </div>

                <!-- Lenovo Yoga 9i -->
                <div class="product-item" data-model="Lenovo Yoga 9i">
                    <img src="https://via.placeholder.com/250x150?text=Yoga+9i" alt="Lenovo Yoga 9i">
                    <div class="product-title">Lenovo Yoga 9i</div>
                    <div class="product-specs">
                        Intel i7-1360P • 16 ГБ LPDDR5 • 1 ТБ SSD<br>
                        Intel Iris Xe • 14.0" 3840×2400 OLED
                    </div>
                </div>

                <!-- Dell Inspiron 16 Plus -->
                <div class="product-item" data-model="Dell Inspiron 16 Plus">
                    <img src="https://via.placeholder.com/250x150?text=Inspiron+16+" alt="Dell Inspiron 16 Plus">
                    <div class="product-title">Dell Inspiron 16 Plus</div>
                    <div class="product-specs">
                        Intel i7-13620H • 32 ГБ DDR5 • 1 ТБ SSD<br>
                        RTX 4060 • 16.0" 3072×1920 IPS
                    </div>
                </div>

            </div>
        </section>

    </div>

    <footer>
        &copy; 2025 ООО "Kazakh IT". Все права защищены.
    </footer>

    <!-- Модальное окно -->
    <div id="modal" class="modal">
        <div class="modal-content">
            <span class="close">&times;</span>
            <h3 id="modal-title">Модель</h3>
            <div id="modal-specs"></div>
        </div>
    </div>

    <script>
        // Данные по моделям (из вашей таблицы)
        const laptops = {
            "Dell XPS 13 9315": {
                model: "Dell XPS 13 9315",
                processor: "Intel Core i7-1250U",
                cores: "10/12",
                freq: "3.1",
                ram: "16",
                ramType: "LPDDR5",
                storage: "SSD",
                ssd: "512",
                hdd: "-",
                gpu: "Intel Iris Xe",
                vram: "-",
                diagonal: "13.4",
                resolution: "1920×1200",
                matrix: "IPS",
                refresh: "60",
                os: "Windows 11",
                weight: "1.2",
                battery: "55",
                ports: "USB-C, Thunderbolt 4",
                extra: "Сенсорный экран"
            },
            "MacBook Air M2": {
                model: "MacBook Air M2",
                processor: "Apple M2",
                cores: "8/8",
                freq: "3.5",
                ram: "16",
                ramType: "Unified",
                storage: "SSD",
                ssd: "512",
                hdd: "-",
                gpu: "Apple M2 GPU",
                vram: "8",
                diagonal: "13.6",
                resolution: "2560×1664",
                matrix: "Liquid Retina",
                refresh: "60",
                os: "macOS",
                weight: "1.24",
                battery: "52.6",
                ports: "USB-C (2)",
                extra: "Безвентиляторный"
            },
            "ThinkPad X1 Carbon": {
                model: "ThinkPad X1 Carbon",
                processor: "Intel Core i7-1365U",
                cores: "10/12",
                freq: "3.6",
                ram: "16",
                ramType: "LPDDR5",
                storage: "SSD",
                ssd: "1024",
                hdd: "-",
                gpu: "Intel Iris Xe",
                vram: "-",
                diagonal: "14.0",
                resolution: "1920×1200",
                matrix: "IPS",
                refresh: "60",
                os: "Windows 11",
                weight: "1.12",
                battery: "57",
                ports: "USB-C, HDMI, RJ45",
                extra: "MIL-STD-810H"
            },
            "HP Spectre x360 14": {
                model: "HP Spectre x360 14",
                processor: "Intel Core i7-1355U",
                cores: "10/12",
                freq: "3.7",
                ram: "16",
                ramType: "LPDDR5",
                storage: "SSD",
                ssd: "1024",
                hdd: "-",
                gpu: "Intel Iris Xe",
                vram: "-",
                diagonal: "13.5",
                resolution: "3000×2000",
                matrix: "OLED",
                refresh: "60",
                os: "Windows 11",
                weight: "1.49",
                battery: "66",
                ports: "USB-C, HDMI, microSD",
                extra: "2-в-1"
            },
            "ASUS ZenBook 14X": {
                model: "ASUS ZenBook 14X",
                processor: "Intel Core i9-13900H",
                cores: "14/20",
                freq: "2.6",
                ram: "32",
                ramType: "DDR5",
                storage: "SSD",
                ssd: "1024",
                hdd: "-",
                gpu: "RTX 3050",
                vram: "6",
                diagonal: "14.5",
                resolution: "2880×1800",
                matrix: "OLED",
                refresh: "90",
                os: "Windows 11",
                weight: "1.7",
                battery: "70",
                ports: "USB-C, HDMI 2.1",
                extra: "Цифровая клавиатура"
            },
            "Acer Swift 3": {
                model: "Acer Swift 3",
                processor: "AMD Ryzen 7 7730U",
                cores: "8/16",
                freq: "2.0",
                ram: "16",
                ramType: "DDR4",
                storage: "SSD",
                ssd: "512",
                hdd: "-",
                gpu: "AMD Radeon",
                vram: "-",
                diagonal: "14.0",
                resolution: "1920×1080",
                matrix: "IPS",
                refresh: "60",
                os: "Windows 11",
                weight: "1.21",
                battery: "56",
                ports: "USB-C, USB-A, HDMI",
                extra: "Алюминий"
            },
            "Surface Laptop 5": {
                model: "Surface Laptop 5",
                processor: "Intel Core i7-1255U",
                cores: "10/12",
                freq: "3.7",
                ram: "16",
                ramType: "LPDDR5",
                storage: "SSD",
                ssd: "512",
                hdd: "-",
                gpu: "Intel Iris Xe",
                vram: "-",
                diagonal: "13.5",
                resolution: "2256×1504",
                matrix: "PixelSense",
                refresh: "60",
                os: "Windows 11",
                weight: "1.27",
                battery: "47.4",
                ports: "USB-C, USB-A",
                extra: "Сенсорный экран"
            },
            "MSI Summit E13 Flip": {
                model: "MSI Summit E13 Flip",
                processor: "Intel Core i7-1260P",
                cores: "12/16",
                freq: "2.1",
                ram: "16",
                ramType: "LPDDR5",
                storage: "SSD",
                ssd: "1024",
                hdd: "-",
                gpu: "Intel Iris Xe",
                vram: "-",
                diagonal: "13.3",
                resolution: "1920×1080",
                matrix: "IPS",
                refresh: "60",
                os: "Windows 11",
                weight: "1.5",
                battery: "62",
                ports: "USB-C, HDMI, microSD",
                extra: "2-в-1"
            },
            "Lenovo Yoga 9i": {
                model: "Lenovo Yoga 9i",
                processor: "Intel Core i7-1360P",
                cores: "12/16",
                freq: "2.2",
                ram: "16",
                ramType: "LPDDR5",
                storage: "SSD",
                ssd: "1024",
                hdd: "-",
                gpu: "Intel Iris Xe",
                vram: "-",
                diagonal: "14.0",
                resolution: "3840×2400",
                matrix: "OLED",
                refresh: "90",
                os: "Windows 11",
                weight: "1.58",
                battery: "71",
                ports: "USB-C, HDMI",
                extra: "Вращающийся экран"
            },
            "Dell Inspiron 16 Plus": {
                model: "Dell Inspiron 16 Plus",
                processor: "Intel Core i7-13620H",
                cores: "10/16",
                freq: "2.4",
                ram: "32",
                ramType: "DDR5",
                storage: "SSD",
                ssd: "1024",
                hdd: "-",
                gpu: "RTX 4060",
                vram: "8",
                diagonal: "16.0",
                resolution: "3072×1920",
                matrix: "IPS",
                refresh: "60",
                os: "Windows 11",
                weight: "2.05",
                battery: "86",
                ports: "USB-C, HDMI 2.1",
                extra: "Цветной экран"
            }
        };

        // Обработка кликов по сотрудникам
        document.querySelectorAll('.employee-card').forEach(card => {
            card.addEventListener('click', () => {
                const name = card.getAttribute('data-name');
                const role = card.getAttribute('data-role');
                alert(`👤 ${name}\nДолжность: ${role}`);
            });
        });

        // Обработка кликов по товарам
        document.querySelectorAll('.product-item').forEach(item => {
            item.addEventListener('click', () => {
                const model = item.getAttribute('data-model');
                showProductDetails(model);
            });
        });

        // Функция отображения деталей
        function showProductDetails(modelName) {
            const modal = document.getElementById('modal');
            const modalTitle = document.getElementById('modal-title');
            const modalSpecs = document.getElementById('modal-specs');

            const laptop = laptops[modelName];

            if (!laptop) return;

            modalTitle.textContent = laptop.model;

            let specsHTML = `
                <table class="spec-table">
                    <tr><th>Процессор</th><td>${laptop.processor}</td></tr>
                    <tr><th>Ядра/Потоки</th><td>${laptop.cores}</td></tr>
                    <tr><th>Частота (ГГц)</th><td>${laptop.freq}</td></tr>
                    <tr><th>ОЗУ (ГБ)</th><td>${laptop.ram} ${laptop.ramType}</td></tr>
                    <tr><th>Накопитель</th><td>${laptop.storage} ${laptop.ssd} ГБ</td></tr>
                    <tr><th>Видеокарта</th><td>${laptop.gpu} (${laptop.vram ? laptop.vram + ' ГБ' : '—'})</td></tr>
                    <tr><th>Диагональ (")</th><td>${laptop.diagonal}"</td></tr>
                    <tr><th>Разрешение</th><td>${laptop.resolution}</td></tr>
                    <tr><th>Тип матрицы</th><td>${laptop.matrix}</td></tr>
                    <tr><th>Частота (Гц)</th><td>${laptop.refresh}</td></tr>
                    <tr><th>ОС</th><td>${laptop.os}</td></tr>
                    <tr><th>Вес (кг)</th><td>${laptop.weight}</td></tr>
                    <tr><th>Батарея (Вт·ч)</th><td>${laptop.battery}</td></tr>
                    <tr><th>Порты</th><td>${laptop.ports}</td></tr>
                    <tr><th>Дополнительно</th><td>${laptop.extra}</td></tr>
                </table>
            `;

            modalSpecs.innerHTML = specsHTML;
            modal.style.display = "flex";
        }

        // Закрытие модального окна
        document.querySelector('.close').addEventListener('click', () => {
            document.getElementById('modal').style.display = "none";
        });

        window.addEventListener('click', (e) => {
            if (e.target === document.getElementById('modal')) {
                document.getElementById('modal').style.display = "none";
            }
        });
    </script>

</body>
</html>

```html
<!DOCTYPE html>
<html lang="id" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EcoPaws Cafe & Green Living Hub</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <style>
        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background-color: #fdfbf7;
            color: #1c1917;
        }

        .glass-nav {
            background: rgba(255, 255, 255, 0.92);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
        }

        .cat-card-shadow {
            box-shadow: 0 10px 30px -10px rgba(5, 150, 105, 0.1);
        }

        .cat-card-shadow:hover {
            box-shadow: 0 20px 40px -15px rgba(5, 150, 105, 0.2);
        }

        /* Custom Range Slider */
        input[type=range] {
            -webkit-appearance: none;
            width: 100%;
            background: #047857;
            height: 8px;
            border-radius: 999px;
            outline: none;
        }

        input[type=range]::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            width: 22px;
            height: 22px;
            border-radius: 50%;
            background: #f59e0b;
            cursor: pointer;
            border: 3px solid #ffffff;
            box-shadow: 0 2px 6px rgba(0,0,0,0.3);
            transition: transform 0.1s ease;
        }

        input[type=range]::-webkit-slider-thumb:hover {
            transform: scale(1.15);
        }

        /* Custom Modal Animation */
        .modal-enter {
            opacity: 0;
            transform: scale(0.95) translateY(10px);
            transition: opacity 0.25s ease-out, transform 0.25s ease-out;
        }

        .modal-enter-active {
            opacity: 1;
            transform: scale(1) translateY(0);
        }
    </style>
</head>
<body class="antialiased selection:bg-emerald-200 text-stone-800">

    <nav class="sticky top-0 z-50 glass-nav border-b border-stone-200 transition-all duration-300">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 py-3.5 flex justify-between items-center">
            <!-- Brand Logo -->
            <a href="#about" class="flex items-center gap-2.5 group">
                <div class="w-10 h-10 bg-emerald-600 rounded-full flex items-center justify-center text-white font-bold text-xl shadow-md group-hover:bg-emerald-700 transition">
                    🐾
                </div>
                <div>
                    <span class="font-extrabold text-xl tracking-tight text-emerald-950 block leading-none">EcoPaws</span>
                    <span class="text-[10px] text-amber-700 font-bold tracking-wider uppercase">Cat Cafe & Eco Hub</span>
                </div>
            </a>
            
            <!-- Desktop Nav Links -->
            <div class="hidden md:flex items-center gap-7 font-semibold text-stone-600 text-sm">
                <a href="#about" class="hover:text-emerald-700 transition">Tentang</a>
                <a href="#calculator" class="hover:text-emerald-700 transition">Kalkulator Eco</a>
                <a href="#cats" class="hover:text-emerald-700 transition">Kucing Kami</a>
                <a href="#menu" class="hover:text-emerald-700 transition">Menu Cafe</a>
                <a href="#tips" class="hover:text-emerald-700 transition">Aksi Hijau</a>
            </div>

            <!-- Action CTA Button & Mobile Toggle -->
            <div class="flex items-center gap-3">
                <a href="#booking" class="bg-emerald-700 hover:bg-emerald-800 text-white text-xs md:text-sm font-bold px-5 py-2.5 rounded-full transition shadow-md hover:shadow-lg active:scale-95">
                    Reservasi Meja ✨
                </a>
                <button onclick="toggleMobileMenu()" class="md:hidden text-stone-700 text-2xl p-1 focus:outline-none" aria-label="Toggle Menu">
                    <i class="fa-solid fa-bars" id="menu-icon"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Menu Drawer -->
        <div id="mobile-drawer" class="hidden md:hidden bg-white border-b border-stone-200 px-6 py-4 space-y-3 text-sm font-semibold shadow-xl">
            <a href="#about" onclick="toggleMobileMenu()" class="block py-2 text-stone-700 hover:text-emerald-700 border-b border-stone-100">Tentang Kami</a>
            <a href="#calculator" onclick="toggleMobileMenu()" class="block py-2 text-stone-700 hover:text-emerald-700 border-b border-stone-100">Kalkulator Eco 📊</a>
            <a href="#cats" onclick="toggleMobileMenu()" class="block py-2 text-stone-700 hover:text-emerald-700 border-b border-stone-100">Kucing Kami 🐱</a>
            <a href="#menu" onclick="toggleMobileMenu()" class="block py-2 text-stone-700 hover:text-emerald-700 border-b border-stone-100">Menu Cafe ☕</a>
            <a href="#tips" onclick="toggleMobileMenu()" class="block py-2 text-stone-700 hover:text-emerald-700 border-b border-stone-100">Aksi Hijau 🌿</a>
            <a href="#booking" onclick="toggleMobileMenu()" class="block py-2 text-emerald-700 font-bold">Reservasi Meja 📅</a>
        </div>
    </nav>

    <section id="about" class="relative py-12 md:py-20 overflow-hidden">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 grid md:grid-cols-2 gap-10 items-center">
            <div class="space-y-6 text-center md:text-left">
                <span class="inline-flex items-center gap-2 px-3.5 py-1.5 bg-amber-100 text-amber-900 rounded-full text-xs font-extrabold tracking-wide uppercase border border-amber-200">
                    🌱 100% Zero-Waste & Pet Rescue Hub
                </span>
                <h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold text-stone-900 leading-tight">
                    Bersantai Bareng <span class="text-emerald-600">Anabul</span>, Menjaga <span class="text-amber-600">Bumi</span>.
                </h1>
                <p class="text-stone-600 text-base sm:text-lg leading-relaxed">
                    EcoPaws Cafe adalah kafe kucing ramah lingkungan pertama tempat kamu bisa menikmati racikan kopi organik, bersantai dengan kucing-kucing adopsi, serta belajar gaya hidup *zero-waste*.
                </p>
                <div class="flex flex-col sm:flex-row gap-4 justify-center md:justify-start pt-2">
                    <a href="#cats" class="bg-amber-600 text-white font-bold px-7 py-3.5 rounded-full hover:bg-amber-700 transition text-center shadow-lg hover:shadow-xl active:scale-95">
                        Lihat Kucing Adopsi 🐱
                    </a>
                    <a href="#calculator" class="border border-stone-300 bg-white text-stone-700 font-bold px-7 py-3.5 rounded-full hover:bg-stone-100 transition text-center active:scale-95">
                        Hitung Jejak Hijaumu 📊
                    </a>
                </div>

                <!-- Stats Badge -->
                <div class="pt-6 grid grid-cols-3 gap-4 border-t border-stone-200/80">
                    <div>
                        <p class="text-2xl sm:text-3xl font-extrabold text-emerald-800">35+</p>
                        <p class="text-xs text-stone-500 font-semibold mt-0.5">Kucing Teradopsi</p>
                    </div>
                    <div>
                        <p class="text-2xl sm:text-3xl font-extrabold text-emerald-800">100%</p>
                        <p class="text-xs text-stone-500 font-semibold mt-0.5">Bahan Organik</p>
                    </div>
                    <div>
                        <p class="text-2xl sm:text-3xl font-extrabold text-emerald-800">0 Plastik</p>
                        <p class="text-xs text-stone-500 font-semibold mt-0.5">Komitmen Kami</p>
                    </div>
                </div>
            </div>

            <!-- Hero Feature Image Card -->
            <div class="relative flex justify-center">
                <div class="w-full max-w-md h-[360px] sm:h-[400px] bg-gradient-to-tr from-emerald-600 to-amber-500 rounded-3xl p-3 shadow-2xl relative group">
                    <img src="https://images.unsplash.com/photo-1514888286974-6c03e2ca1dba?auto=format&fit=crop&w=800&q=80" 
                         onerror="this.src='https://placehold.co/800x600/059669/ffffff?text=EcoPaws+Cat'" 
                         alt="Cat at EcoPaws Cafe" 
                         class="w-full h-full object-cover rounded-2xl group-hover:scale-[1.02] transition duration-500">
                    <div class="absolute bottom-6 left-6 right-6 bg-white/90 backdrop-blur-md p-4 rounded-2xl border border-white/50 shadow-lg flex items-center gap-3">
                        <span class="text-2xl">🐾</span>
                        <p class="text-xs text-stone-800 font-bold leading-snug">Dukung penyelamatan anabul jalanan sambil menikmati hidangan organik!</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="calculator" class="py-14 bg-emerald-900 text-white relative overflow-hidden">
        <div class="max-w-5xl mx-auto px-4 sm:px-6">
            <div class="text-center space-y-3 mb-10">
                <span class="text-emerald-300 text-xs font-extrabold uppercase tracking-widest bg-emerald-950/60 px-3.5 py-1 rounded-full border border-emerald-800">
                    Simulasi Interaktif
                </span>
                <h2 class="text-3xl sm:text-4xl font-extrabold">Hitung Dampak Hijau Kunjunganmu</h2>
                <p class="text-emerald-100/90 text-xs sm:text-sm max-w-xl mx-auto">
                    Setiap cangkir kopi organik dan waktu bersantai kamu di EcoPaws berkontribusi langsung mengurangi sampah plastik tanah air!
                </p>
            </div>

            <div class="bg-emerald-800/80 border border-emerald-700/80 p-6 sm:p-10 rounded-3xl shadow-2xl grid md:grid-cols-2 gap-8 items-center">
                <!-- Sliders -->
                <div class="space-y-6">
                    <div>
                        <div class="flex justify-between text-xs font-bold mb-2.5">
                            <span class="text-emerald-100">Estimasi Kunjungan Per Bulan:</span>
                            <span id="slider-visits-val" class="text-amber-300 text-sm font-extrabold">4 kali</span>
                        </div>
                        <input type="range" id="slider-visits" min="1" max="15" value="4" oninput="runEcoCalc()">
                    </div>

                    <div>
                        <div class="flex justify-between text-xs font-bold mb-2.5">
                            <span class="text-emerald-100">Cangkir Minuman Per Kunjungan:</span>
                            <span id="slider-cups-val" class="text-amber-300 text-sm font-extrabold">2 cangkir</span>
                        </div>
                        <input type="range" id="slider-cups" min="1" max="6" value="2" oninput="runEcoCalc()">
                    </div>
                </div>

                <!-- Display Results -->
                <div class="bg-emerald-950/80 p-6 rounded-2xl text-center border border-emerald-800/80 space-y-4">
                    <p class="text-xs text-emerald-300 font-bold uppercase tracking-wider">Kontribusi Pertahun Kamu:</p>
                    <div class="grid grid-cols-2 gap-4">
                        <div class="bg-emerald-900/60 p-4 rounded-xl border border-emerald-800/80">
                            <span id="calc-res-cups" class="text-3xl font-extrabold text-amber-300 block">96</span>
                            <span class="text-[11px] text-stone-300 font-medium">Gelas Plastik Dihemat</span>
                        </div>
                        <div class="bg-emerald-900/60 p-4 rounded-xl border border-emerald-800/80">
                            <span id="calc-res-co2" class="text-3xl font-extrabold text-emerald-300 block">24 kg</span>
                            <span class="text-[11px] text-stone-300 font-medium">Emisi CO2 Dikurangi</span>
                        </div>
                    </div>
                    <p class="text-xs text-emerald-200/90 italic pt-1">
                        🌳 Setara dengan menanam <strong id="calc-res-trees" class="text-amber-300">4</strong> pohon baru setiap tahun!
                    </p>
                </div>
            </div>
        </div>
    </section>

    <section id="cats" class="py-16 bg-white border-y border-stone-200">
        <div class="max-w-6xl mx-auto px-4 sm:px-6">
            <div class="text-center max-w-2xl mx-auto mb-10 space-y-3">
                <span class="bg-amber-100 text-amber-800 text-xs font-extrabold px-3 py-1 rounded-full uppercase">
                    Anabul Rescue Hub
                </span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-stone-900">Kucing Kami di EcoPaws</h2>
                <p class="text-stone-600 text-sm">
                    Semua kucing dirawat dengan penuh kasih sayang. Klik foto kucing untuk melihat profil lengkap & mengajukan adopsi!
                </p>
                
                <!-- Filter Buttons -->
                <div class="flex flex-wrap justify-center gap-2.5 pt-4">
                    <button onclick="filterCats('all', this)" class="filter-btn active bg-emerald-700 text-white px-5 py-2 rounded-full text-xs font-bold shadow transition cursor-pointer">
                        Semua Kucing
                    </button>
                    <button onclick="filterCats('adoptable', this)" class="filter-btn bg-stone-100 text-stone-700 hover:bg-emerald-100 px-5 py-2 rounded-full text-xs font-bold transition cursor-pointer">
                        Siap Diadopsi 🏡
                    </button>
                    <button onclick="filterCats('resident', this)" class="filter-btn bg-stone-100 text-stone-700 hover:bg-emerald-100 px-5 py-2 rounded-full text-xs font-bold transition cursor-pointer">
                        Penghuni Cafe ☕
                    </button>
                </div>
            </div>

            <!-- Cat Cards Grid -->
            <div class="grid md:grid-cols-3 gap-8" id="cats-grid">
                <!-- Cat Card 1 -->
                <div onclick="openCatModal('Milo 🧡', 'Domestik Mix', '1.5 Tahun', 'Siap Diadopsi', 'Milo adalah kucing rescue yang sangat ramah dan suka tidur di pangkuan pengunjung saat menikmati kopi. Sudah divaksinasi lengkap & steril.', 'https://images.unsplash.com/photo-1573865526739-10659fec78a5?auto=format&fit=crop&w=600&q=80')" 
                     class="cat-item adoptable bg-stone-50 rounded-2xl overflow-hidden border border-stone-200 cat-card-shadow transition duration-300 cursor-pointer transform hover:-translate-y-1.5 flex flex-col">
                    <div class="relative h-52 bg-stone-200">
                        <span class="absolute top-3 left-3 bg-amber-100 text-amber-800 text-[11px] font-extrabold px-3 py-1 rounded-full shadow">Siap Diadopsi</span>
                        <img src="https://images.unsplash.com/photo-1573865526739-10659fec78a5?auto=format&fit=crop&w=600&q=80" 
                             onerror="this.src='https://placehold.co/600x400/f59e0b/ffffff?text=Milo'" 
                             alt="Milo" class="w-full h-full object-cover">
                    </div>
                    <div class="p-5 flex-1 flex flex-col justify-between space-y-3">
                        <div>
                            <div class="flex justify-between items-center mb-1">
                                <h3 class="text-xl font-extrabold text-stone-900">Milo 🧡</h3>
                            </div>
                            <p class="text-xs text-stone-500 font-bold mb-2">Ras: Domestik Mix • 1.5 Tahun</p>
                            <p class="text-xs text-stone-600 leading-relaxed">Ramah banget, suka duduk di pangkuan pengunjung. (Klik untuk detail)</p>
                        </div>
                        <button class="w-full py-2 bg-white border border-stone-300 rounded-xl text-xs font-bold text-emerald-800 group-hover:bg-emerald-50 transition">
                            Lihat Profil & Adopsi 🐾
                        </button>
                    </div>
                </div>

                <!-- Cat Card 2 -->
                <div onclick="openCatModal('Luna 🤍', 'Persian Rescue', '3 Tahun', 'Penghuni Cafe', 'Luna adalah ratu di cafe kami! Suka tidur di dekat jendela sambil berjemur matahari pagi. Menjadi maskot kesayangan pengunjung.', 'https://images.unsplash.com/photo-1533738363-b7f9aef128ce?auto=format&fit=crop&w=600&q=80')" 
                     class="cat-item resident bg-stone-50 rounded-2xl overflow-hidden border border-stone-200 cat-card-shadow transition duration-300 cursor-pointer transform hover:-translate-y-1.5 flex flex-col">
                    <div class="relative h-52 bg-stone-200">
                        <span class="absolute top-3 left-3 bg-emerald-100 text-emerald-800 text-[11px] font-extrabold px-3 py-1 rounded-full shadow">Penghuni Cafe</span>
                        <img src="https://images.unsplash.com/photo-1533738363-b7f9aef128ce?auto=format&fit=crop&w=600&q=80" 
                             onerror="this.src='https://placehold.co/600x400/059669/ffffff?text=Luna'" 
                             alt="Luna" class="w-full h-full object-cover">
                    </div>
                    <div class="p-5 flex-1 flex flex-col justify-between space-y-3">
                        <div>
                            <div class="flex justify-between items-center mb-1">
                                <h3 class="text-xl font-extrabold text-stone-900">Luna 🤍</h3>
                            </div>
                            <p class="text-xs text-stone-500 font-bold mb-2">Ras: Persian Rescue • 3 Tahun</p>
                            <p class="text-xs text-stone-600 leading-relaxed">Ratu cafe! Suka berjemur santai di dekat jendela utama. (Klik untuk detail)</p>
                        </div>
                        <button class="w-full py-2 bg-white border border-stone-300 rounded-xl text-xs font-bold text-emerald-800 group-hover:bg-emerald-50 transition">
                            Lihat Profil Complete 🐾
                        </button>
                    </div>
                </div>

                <!-- Cat Card 3 -->
                <div onclick="openCatModal('Oreo 🖤', 'Tuxedo Cat', '8 Bulan', 'Siap Diadopsi', 'Oreo sangat lincah, penuh energi, dan senang bermain mengejar bola kertas daur ulang. Sangat cocok untuk keluarga aktif.', 'https://images.unsplash.com/photo-1543852786-1cf6624b9987?auto=format&fit=crop&w=600&q=80')" 
                     class="cat-item adoptable bg-stone-50 rounded-2xl overflow-hidden border border-stone-200 cat-card-shadow transition duration-300 cursor-pointer transform hover:-translate-y-1.5 flex flex-col">
                    <div class="relative h-52 bg-stone-200">
                        <span class="absolute top-3 left-3 bg-amber-100 text-amber-800 text-[11px] font-extrabold px-3 py-1 rounded-full shadow">Siap Diadopsi</span>
                        <img src="https://images.unsplash.com/photo-1543852786-1cf6624b9987?auto=format&fit=crop&w=600&q=80" 
                             onerror="this.src='https://placehold.co/600x400/1c1917/ffffff?text=Oreo'" 
                             alt="Oreo" class="w-full h-full object-cover">
                    </div>
                    <div class="p-5 flex-1 flex flex-col justify-between space-y-3">
                        <div>
                            <div class="flex justify-between items-center

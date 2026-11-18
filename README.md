<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pesan Perdamaian &amp; Voucher Jajanan 📩🍫</title>

    <!-- Google Fonts: Quicksand (Judul) & Plus Jakarta Sans (Isi Teks) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:ital,wght@0,400;0,500;0,600;0,700;0,800;1,400&family=Quicksand:wght@600;700&display=swap" rel="stylesheet">

    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        heading: ['Quicksand', 'sans-serif'],
                        body: ['"Plus Jakarta Sans"', 'sans-serif'],
                    },
                    colors: {
                        blush: {
                            bg: '#FFF5F7',
                            100: '#FFE8EE',
                            200: '#FFD1DC',
                            300: '#FFB3C6',
                        },
                        cream: '#FFFDF9',
                        choco: {
                            DEFAULT: '#4E2A1E',
                            medium: '#6B3E2E',
                            light: '#8D5B4C',
                            soft: '#F5EBE6',
                        },
                        roseaccent: {
                            DEFAULT: '#FF6B8B',
                            hover: '#F25477',
                            light: '#FF94AC',
                        }
                    }
                }
            }
        }
    </script>

    <style>
        /* Palet Dasar: Blush Pink Lembut (#FFF5F7), Krem Hangat (#FFFDF9), Coklat Manis (#4E2A1E) */
        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background: radial-gradient(circle at top right, #FFE6EC 0%, #FFF5F7 48%, #FFFDF9 100%);
            min-height: 100dvh;
            overflow-x: hidden;
            color: #4E2A1E;
            -webkit-tap-highlight-color: transparent;
        }

        h1, h2, h3, .font-heading {
            font-family: 'Quicksand', sans-serif;
        }

        /* Layer Partikel Latar Belakang: Dijamin tidak pernah menghalangi klik */
        #bg-particles-container {
            position: fixed;
            inset: 0;
            pointer-events: none;
            z-index: 0;
            overflow: hidden;
        }

        .bg-particle {
            position: absolute;
            bottom: -45px;
            pointer-events: none;
            user-select: none;
            animation: floatParticle linear infinite;
            opacity: 0;
        }

        @keyframes floatParticle {
            0% {
                transform: translateY(0) rotate(0deg) scale(0.85);
                opacity: 0;
            }
            15% {
                opacity: 0.65;
            }
            85% {
                opacity: 0.55;
            }
            100% {
                transform: translateY(-112vh) rotate(28deg) scale(1.1);
                opacity: 0;
            }
        }

        /* Animasi Maskot Mengayun Lembut */
        @keyframes gentleSway {
            0%, 100% { transform: rotate(-2deg) translateY(0px); }
            50% { transform: rotate(2deg) translateY(-4px); }
        }

        .mascot-sway {
            animation: gentleSway 3.2s ease-in-out infinite;
            transform-origin: bottom center;
        }

        /* Animasi Bendera Putih Kecil Berkibar */
        @keyframes whiteFlagWave {
            0%, 100% { transform: rotate(0deg); }
            50% { transform: rotate(-7deg); }
        }

        .white-flag-wave {
            animation: whiteFlagWave 1.9s ease-in-out infinite;
            transform-origin: 54px 132px;
        }

        /* Transisi Antar Tahap */
        .stage-section {
            display: none;
            opacity: 0;
            transform: translateY(14px);
            transition: opacity 0.4s cubic-bezier(0.22, 1, 0.36, 1), transform 0.4s cubic-bezier(0.22, 1, 0.36, 1);
        }

        .stage-section.active {
            display: block;
            opacity: 1;
            transform: translateY(0);
        }

        /* =================================================================
           ANIMASI AMPLOP INTERAKTIF TAHAP 1 (700ms SAAT DIKLIK)
           ================================================================= */
        .hero-envelope {
            position: relative;
            width: 224px;
            height: 138px;
            margin: 0 auto;
            perspective: 900px;
            cursor: pointer;
            user-select: none;
            transition: transform 0.25s ease;
        }

        .hero-envelope:hover {
            transform: translateY(-3px) scale(1.02);
        }

        .hero-envelope:active {
            transform: scale(0.98);
        }

        /* Kertas Surat di Dalam Amplop yang Naik ke Atas */
        .hero-letter-sheet {
            position: absolute;
            left: 14px;
            right: 14px;
            top: 14px;
            height: 108px;
            background: #FFFDF9;
            border: 1.5px solid #FFD1DC;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(78, 42, 30, 0.08);
            z-index: 2;
            transition: transform 0.55s cubic-bezier(0.22, 1, 0.36, 1) 0.14s, box-shadow 0.4s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: flex-start;
            padding-top: 12px;
        }

        .hero-envelope.is-opening .hero-letter-sheet {
            transform: translateY(-54px);
            box-shadow: 0 10px 24px rgba(255, 107, 139, 0.22);
        }

        /* Tutup Segitiga Atas Amplop */
        .hero-envelope-flap {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 78px;
            transform-origin: top center;
            transform-style: preserve-3d;
            z-index: 4;
            transition: transform 0.52s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .hero-envelope.is-opening .hero-envelope-flap {
            transform: rotateX(180deg);
            z-index: 1;
        }

        /* Segel Stiker Bintang & Coklat pada Amplop */
        .envelope-seal {
            position: absolute;
            top: 52px;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 5;
            transition: transform 0.3s ease, opacity 0.25s ease;
        }

        .hero-envelope.is-opening .envelope-seal {
            transform: translate(-50%, -50%) scale(1.35);
            opacity: 0;
        }

        /* Cahaya Lembut pada Tombol Utama Coral-Rose */
        @keyframes rosePulse {
            0%, 100% { box-shadow: 0 8px 24px rgba(255, 107, 139, 0.30); }
            50% { box-shadow: 0 12px 32px rgba(255, 107, 139, 0.48); }
        }

        .btn-rose-glow {
            animation: rosePulse 2.4s infinite;
        }

        /* Kartu Jajanan Interaktif */
        .treat-card {
            transition: all 0.25s cubic-bezier(0.22, 1, 0.36, 1);
        }

        .treat-card:hover {
            transform: translateY(-2px);
        }

        .treat-card:active {
            transform: scale(0.97);
        }

        .treat-card.tasted {
            background: linear-gradient(145deg, #FFF5F7 0%, #FFE8EE 100%);
            border-color: #FF6B8B;
            box-shadow: 0 6px 18px rgba(255, 107, 139, 0.16);
        }

        /* Desain Tiket Kupon Berlubang Samping */
        .ticket-voucher {
            position: relative;
            transition: all 0.25s cubic-bezier(0.22, 1, 0.36, 1);
        }

        .ticket-voucher::before,
        .ticket-voucher::after {
            content: '';
            position: absolute;
            top: 50%;
            width: 18px;
            height: 18px;
            background-color: #FFFDF9;
            border: 2px solid #EAD7D1;
            border-radius: 9999px;
            transform: translateY(-50%);
            z-index: 10;
            transition: border-color 0.25s ease;
        }

        .ticket-voucher::before {
            left: -11px;
        }

        .ticket-voucher::after {
            right: -11px;
        }

        .ticket-voucher.selected {
            background: linear-gradient(135deg, #FFF5F7 0%, #FFE8EE 100%);
            border-color: #FF6B8B;
            box-shadow: 0 8px 20px rgba(255, 107, 139, 0.18);
        }

        .ticket-voucher.selected::before,
        .ticket-voucher.selected::after {
            border-color: #FF6B8B;
        }

        /* Tombol Lincah & Tombol Positif Membesar */
        #btn-runaway {
            transition: left 0.24s cubic-bezier(0.34, 1.56, 0.64, 1),
                        top 0.24s cubic-bezier(0.34, 1.56, 0.64, 1),
                        transform 0.2s ease,
                        background-color 0.2s ease;
        }

        #btn-forgive {
            transition: transform 0.32s cubic-bezier(0.34, 1.56, 0.64, 1), box-shadow 0.3s ease;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #FFF5F7;
        }
        ::-webkit-scrollbar-thumb {
            background: #E6C7C2;
            border-radius: 9999px;
        }
    </style>
</head>
<body class="relative flex items-center justify-center p-4 sm:p-6 selection:bg-blush-200 selection:text-choco">

    <!-- Canvas Perayaan Konfeti Bintang, Sakura, Coklat & Mochi (Tahap 3) -->
    <canvas id="celebration-canvas" class="fixed inset-0 pointer-events-none z-40"></canvas>

    <!-- Kontainer Partikel Melayang di Latar Belakang (pointer-events: none; z-index: 0) -->
    <div id="bg-particles-container" aria-hidden="true"></div>

    <!-- Notifikasi Toast Lembut -->
    <div id="toast-notification" class="fixed top-5 left-1/2 -translate-x-1/2 z-50 pointer-events-none opacity-0 transition-all duration-300 transform -translate-y-3">
        <div class="bg-cream/95 backdrop-blur-md border border-roseaccent-light text-choco px-4 py-2.5 rounded-full shadow-lg flex items-center gap-2 text-xs sm:text-sm font-bold">
            <span id="toast-icon">✨</span>
            <span id="toast-text">Pesan berhasil disalin!</span>
        </div>
    </div>

    <!-- =====================================================================
         KARTU UTAMA SINGLE-PAGE INTERAKTIF (TANPA OVERFLOW TERPOTONG)
         ===================================================================== -->
    <main class="relative z-10 w-full max-w-md mx-auto my-auto">

        <!-- Indikator Progres 3 Tahap -->
        <div class="flex items-center justify-center gap-2 mb-3">
            <span id="stage-dot-1" class="h-2 w-8 rounded-full bg-roseaccent transition-all duration-300"></span>
            <span id="stage-dot-2" class="h-2 w-2.5 rounded-full bg-[#E8C8CE] transition-all duration-300"></span>
            <span id="stage-dot-3" class="h-2 w-2.5 rounded-full bg-[#E8C8CE] transition-all duration-300"></span>
        </div>

        <!-- Kontainer Kartu Utama (overflow: visible agar animasi surat & tombol tidak terpotong) -->
        <div class="bg-cream/95 backdrop-blur-md border-2 border-[#F5D5DC] rounded-[2rem] shadow-[0_20px_50px_rgba(78,42,30,0.12)] p-5 sm:p-7 relative">

            <!-- Lapisan Dekorasi Sudut Pastel (Terisolasi agar tidak memotong konten) -->
            <div class="absolute inset-0 rounded-[2rem] overflow-hidden pointer-events-none" aria-hidden="true">
                <div class="absolute -top-12 -right-12 w-32 h-32 rounded-full bg-blush-100/80"></div>
                <div class="absolute -bottom-14 -left-14 w-36 h-36 rounded-full bg-choco-soft/80"></div>
            </div>

            <!-- ===============================================================
                 TAHAP 1: LAYAR PEMBUKA & AMPLOP INTERAKTIF
                 =============================================================== -->
            <section id="stage-1" class="stage-section active relative z-10 text-center">
                <div class="inline-flex items-center gap-1.5 px-3.5 py-1 rounded-full bg-blush-100 border border-blush-200 text-choco text-xs font-extrabold tracking-wide mb-2">
                    <span>Misi Perdamaian ✨</span>
                </div>

                <!-- Ilustrasi SVG Maskot Menggemaskan + Bendera Putih + Keranjang Beryl's, Nabati, Mochi -->
                <div class="w-48 h-40 mx-auto my-1 mascot-sway">
                    <svg viewBox="0 0 260 220" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-full h-full drop-shadow-sm">
                        <ellipse cx="135" cy="204" rx="72" ry="10" fill="#F3D3DB" opacity="0.75"/>

                        <!-- Bendera Putih Kecil -->
                        <g class="white-flag-wave">
                            <line x1="56" y1="142" x2="34" y2="56" stroke="#8D5B4C" stroke-width="4" stroke-linecap="round"/>
                            <path d="M35 58C22 54 11 61 1 56V86C11 91 22 84 35 88V58Z" fill="#FFFDF9" stroke="#D9B6BE" stroke-width="2.2" stroke-linejoin="round"/>
                            <path d="M19 66L20.4 69.6L24 71L20.4 72.4L19 76L17.6 72.4L14 71L17.6 69.6L19 66Z" fill="#FF6B8B"/>
                        </g>

                        <!-- Telinga Maskot -->
                        <path d="M92 64C84 39 98 27 115 44" fill="#FFFFFF" stroke="#D8B4BC" stroke-width="3.5" stroke-linecap="round" stroke-linejoin="round"/>
                        <path d="M97 59C92 44 100 38 110 48" fill="#FFD1DC"/>

                        <path d="M178 64C186 39 172 27 155 44" fill="#FFFFFF" stroke="#D8B4BC" stroke-width="3.5" stroke-linecap="round" stroke-linejoin="round"/>
                        <path d="M173 59C178 44 170 38 160 48" fill="#FFD1DC"/>

                        <!-- Badan & Kepala Maskot -->
                        <path d="M92 128C88 162 102 192 135 192C168 192 182 162 178 128C175 108 158 100 135 100C112 100 95 108 92 128Z" fill="#FFFFFF" stroke="#D8B4BC" stroke-width="3.5"/>
                        <ellipse cx="135" cy="82" rx="52" ry="43" fill="#FFFFFF" stroke="#D8B4BC" stroke-width="3.5"/>

                        <!-- Ekspresi Ramah & Sopan -->
                        <path d="M107 67C111 64 117 64 121 67" stroke="#6B3E2E" stroke-width="2.6" stroke-linecap="round"/>
                        <path d="M163 67C159 64 153 64 149 67" stroke="#6B3E2E" stroke-width="2.6" stroke-linecap="round"/>

                        <circle cx="114" cy="80" r="7.2" fill="#4E2A1E"/>
                        <circle cx="111.5" cy="77.5" r="2.6" fill="#FFFFFF"/>
                        <circle cx="116.5" cy="82.5" r="1.2" fill="#FFFFFF"/>

                        <circle cx="156" cy="80" r="7.2" fill="#4E2A1E"/>
                        <circle cx="153.5" cy="77.5" r="2.6" fill="#FFFFFF"/>
                        <circle cx="158.5" cy="82.5" r="1.2" fill="#FFFFFF"/>

                        <ellipse cx="100" cy="89" rx="8.5" ry="4.5" fill="#FFB3C6" opacity="0.75"/>
                        <ellipse cx="170" cy="89" rx="8.5" ry="4.5" fill="#FFB3C6" opacity="0.75"/>

                        <ellipse cx="135" cy="87" rx="3.8" ry="2.6" fill="#8D5B4C"/>
                        <path d="M127 94C131 99 139 99 143 94" stroke="#6B3E2E" stroke-width="2.6" stroke-linecap="round"/>

                        <!-- Keranjang Jajanan Favorit -->
                        <g transform="translate(82, 112)">
                            <path d="M16 32C16 8 90 8 90 32" stroke="#A47148" stroke-width="4" stroke-linecap="round" fill="none"/>

                            <!-- Coklat Beryl's -->
                            <g transform="translate(12, 12) rotate(-10)">
                                <rect x="0" y="0" width="32" height="36" rx="4" fill="#9B1C31" stroke="#D4AF37" stroke-width="1.8"/>
                                <rect x="3" y="4" width="26" height="12" rx="2" fill="#D4AF37"/>
                                <text x="16" y="12.5" text-anchor="middle" fill="#4E2A1E" font-size="6.5" font-weight="bold" font-family="serif">Beryl's</text>
                                <circle cx="16" cy="24" r="4.5" fill="#4E2A1E"/>
                            </g>

                            <!-- Nabati Coklat -->
                            <g transform="translate(38, 6)">
                                <rect x="0" y="4" width="30" height="38" rx="4" fill="#C81E1E" stroke="#4E2A1E" stroke-width="1.6"/>
                                <rect x="2" y="13" width="26" height="11" rx="3" fill="#FACC15"/>
                                <text x="15" y="21" text-anchor="middle" fill="#9B1C1C" font-size="6.5" font-weight="900" font-family="sans-serif">nabati</text>
                                <rect x="17" y="-3" width="9" height="10" rx="1.5" transform="rotate(12 17 -3)" fill="#D97706" stroke="#4E2A1E" stroke-width="1"/>
                                <line x1="17" y1="1" x2="25" y2="3" stroke="#4E2A1E" stroke-width="1.5"/>
                            </g>

                            <!-- Mochi Puncak -->
                            <g transform="translate(64, 14) rotate(9)">
                                <rect x="0" y="6" width="32" height="28" rx="4" fill="#FDE68A" stroke="#B45309" stroke-width="1.6"/>
                                <rect x="0" y="16" width="32" height="12" fill="#FF6B8B"/>
                                <text x="16" y="24" text-anchor="middle" fill="#FFFDF9" font-size="5.5" font-weight="bold">MOCHI</text>
                                <circle cx="10" cy="6" r="5.5" fill="#FFFDF9" stroke="#E5D3C8" stroke-width="1.2"/>
                                <circle cx="21" cy="6" r="5.5" fill="#FFFDF9" stroke="#E5D3C8" stroke-width="1.2"/>
                                <circle cx="10" cy="5" r="0.8" fill="#8D5B4C"/>
                                <circle cx="21" cy="5" r="0.8" fill="#8D5B4C"/>
                            </g>

                            <!-- Badan Keranjang -->
                            <path d="M8 32H98L90 68C89 73 84 76 79 76H27C22 76 17 73 16 68L8 32Z" fill="#C68B59" stroke="#6B3E2E" stroke-width="2.5" stroke-linejoin="round"/>
                            <path d="M11 44H95M14 56H92M30 32L34 76M53 32V76M76 32L72 76" stroke="#8D5B4C" stroke-width="1.6" stroke-linecap="round"/>
                            <circle cx="53" cy="48" r="5" fill="#FF6B8B"/>
                            <path d="M53 48L43 42V54L53 48ZM53 48L63 42V54L53 48Z" fill="#FF6B8B" stroke="#4E2A1E" stroke-width="1.2" stroke-linejoin="round"/>
                        </g>

                        <ellipse cx="94" cy="146" rx="11" ry="8.5" transform="rotate(-15 94 146)" fill="#FFFFFF" stroke="#D8B4BC" stroke-width="3"/>
                        <ellipse cx="176" cy="146" rx="11" ry="8.5" transform="rotate(15 176 146)" fill="#FFFFFF" stroke="#D8B4BC" stroke-width="3"/>
                    </svg>
                </div>

                <h1 class="text-xl sm:text-2xl font-bold text-choco leading-snug">
                    Hai, <span class="display-nickname text-roseaccent">Kamu</span>! Jangan bad mood lagi ya...
                </h1>

                <p class="text-choco-medium text-xs sm:text-sm leading-relaxed mt-1.5 px-1">
                    Aku titip pesan kecil bareng jajanan favoritmu. Ketuk amplop atau tombol di bawah untuk membukanya ya!
                </p>

                <!-- ===========================================================
                     AMPLOP SURAT INTERAKTIF (BISA DIKLIK LANGSUNG)
                     =========================================================== -->
                <div class="mt-6 mb-4 pt-2">
                    <div id="stage1-envelope" role="button" tabindex="0" aria-label="Buka Amplop Pesan"
                        onclick="openEnvelopeAndAdvance()"
                        onkeydown="if(event.key==='Enter'||event.key===' '){event.preventDefault();openEnvelopeAndAdvance();}"
                        class="hero-envelope group">

                        <!-- Bagian Belakang Amplop -->
                        <div class="absolute inset-0 rounded-2xl bg-[#F6BCC9] border-2 border-[#E39FAE] shadow-md z-1"></div>

                        <!-- Kertas Surat di Dalam yang Naik ke Atas saat Diklik -->
                        <div class="hero-letter-sheet">
                            <span class="text-[11px] font-heading font-bold text-roseaccent">
                                Untuk <span class="display-nickname">Kamu</span> ✨
                            </span>
                            <div class="w-24 h-1.5 bg-blush-200 rounded-full mt-1.5"></div>
                            <div class="w-16 h-1.5 bg-choco-soft rounded-full mt-1"></div>
                        </div>

                        <!-- Saku Depan Amplop (Kiri, Kanan, Bawah) -->
                        <svg viewBox="0 0 224 138" class="absolute inset-0 w-full h-full pointer-events-none z-3">
                            <path d="M2 135L112 72L222 135H2Z" fill="#FFE8EE" stroke="#E39FAE" stroke-width="2" stroke-linejoin="round"/>
                            <path d="M2 4L94 72L2 135V4Z" fill="#FFD6E0" stroke="#E39FAE" stroke-width="2" stroke-linejoin="round"/>
                            <path d="M222 4L130 72L222 135V4Z" fill="#FFD6E0" stroke="#E39FAE" stroke-width="2" stroke-linejoin="round"/>
                        </svg>

                        <!-- Tutup Segitiga Atas Amplop -->
                        <div class="hero-envelope-flap pointer-events-none">
                            <svg viewBox="0 0 224 78" class="w-full h-full">
                                <path d="M2 2L112 73L222 2H2Z" fill="#F9B5C4" stroke="#DC94A4" stroke-width="2" stroke-linejoin="round"/>
                            </svg>
                        </div>

                        <!-- Segel Stiker Bintang & Coklat -->
                        <div class="envelope-seal pointer-events-none">
                            <div class="w-11 h-11 rounded-full bg-cream border-2 border-roseaccent shadow-md flex items-center justify-center text-base group-hover:scale-110 transition-transform">
                                <span>✨🍫</span>
                            </div>
                        </div>
                    </div>
                    <p class="text-[11px] text-choco-light font-semibold mt-2">
                        Ketuk amplop di atas atau tekan tombol di bawah 👇
                    </p>
                </div>

                <div>
                    <button id="btn-open-stage2" type="button" onclick="openEnvelopeAndAdvance()"
                        class="w-full py-3.5 px-6 rounded-2xl bg-gradient-to-r from-roseaccent to-roseaccent-hover hover:from-roseaccent-hover hover:to-roseaccent text-white font-heading font-bold text-base sm:text-lg btn-rose-glow transition-all duration-200 active:scale-[0.98] flex items-center justify-center gap-2 cursor-pointer">
                        <span>Buka Pesannya 📩</span>
                    </button>
                </div>
            </section>

            <!-- ===============================================================
                 TAHAP 2: KARTU SURAT, LEVEL MOOD ADEM & MENU JAJANAN FAVORIT
                 =============================================================== -->
            <section id="stage-2" class="stage-section relative z-10">

                <!-- Kartu Surat Bersih & Mudah Dibaca -->
                <div class="bg-blush-bg border border-blush-200 rounded-2xl p-4 sm:p-5 shadow-xs text-left">
                    <div class="flex items-center justify-between border-b border-blush-200/80 pb-2.5 mb-3">
                        <h2 class="font-heading font-bold text-choco text-base sm:text-lg">
                            Hai, <span class="display-nickname text-roseaccent">Kamu</span>! ✨
                        </h2>
                        <span class="text-[11px] font-bold text-choco bg-cream border border-blush-200 px-2.5 py-0.5 rounded-full">
                            Pesan Tulus 📩
                        </span>
                    </div>

                    <p id="display-apology-message" class="text-xs sm:text-[13.5px] text-choco-medium leading-relaxed whitespace-pre-line">
                        Maaf banget ya kalau ucapan atau sikapku kemarin sempat bikin kamu kurang nyaman atau bad mood. Niatku sama sekali nggak ke sana. Karena kita baru kenal, aku pengen banget jaga suasana tetap asyik dan bikin kamu nyaman ngobrol. Boleh ya kita baikan lagi?
                    </p>
                </div>

                <!-- Indikator Level Mood Adem & 3 Kartu Jajanan Favorit -->
                <div class="mt-4 bg-choco-soft/75 border border-[#E6CFC7] rounded-2xl p-3.5">
                    <div class="flex items-center justify-between mb-1.5">
                        <h3 class="font-heading font-bold text-xs sm:text-sm text-choco">
                            Level Mood Adem ✨
                        </h3>
                        <span id="meter-percent-badge" class="text-[11px] font-extrabold text-roseaccent bg-cream px-2.5 py-0.5 rounded-full border border-blush-200">
                            0%
                        </span>
                    </div>

                    <!-- Progress Bar Level Mood Adem (0% -> 100%) -->
                    <div class="w-full h-3 bg-cream rounded-full overflow-hidden border border-[#E5C7C0] p-0.5 mb-3">
                        <div id="meter-fill-bar" class="h-full w-0 rounded-full bg-gradient-to-r from-roseaccent-light via-roseaccent to-[#E11D48] transition-all duration-500 ease-out"></div>
                    </div>

                    <!-- 3 Kartu Jajanan Favorit dengan Ilustrasi SVG Khusus -->
                    <div class="grid grid-cols-3 gap-2">
                        <!-- 1) Coklat Beryl's -->
                        <button type="button" onclick="tasteTreat('beryls')" id="treat-card-beryls"
                            class="treat-card bg-cream border-2 border-[#EAD4CE] rounded-xl p-2 flex flex-col items-center text-center cursor-pointer relative">
                            <span id="badge-beryls" class="hidden absolute -top-1.5 -right-1.5 w-5 h-5 rounded-full bg-roseaccent text-white text-[10px] font-bold items-center justify-center shadow-xs">✓</span>
                            <div class="w-16 h-14 mb-1">
                                <!-- Ilustrasi SVG Kotak Coklat Beryl's Tiramisu/Almond -->
                                <svg viewBox="0 0 110 86" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-full h-full">
                                    <rect x="10" y="10" width="66" height="64" rx="7" fill="#9B1C31" stroke="#D4AF37" stroke-width="2.5"/>
                                    <rect x="15" y="15" width="56" height="54" rx="4" stroke="#F3D06B" stroke-width="1" stroke-dasharray="3 2"/>
                                    <path d="M54 10L76 32V42L44 10H54Z" fill="#D4AF37"/>
                                    <rect x="18" y="28" width="50" height="24" rx="4" fill="#FFFDF9" stroke="#D4AF37" stroke-width="1.4"/>
                                    <text x="43" y="41" text-anchor="middle" fill="#9B1C31" font-size="11" font-weight="bold" font-family="Georgia, serif">Beryl's</text>
                                    <text x="43" y="48.5" text-anchor="middle" fill="#4E2A1E" font-size="5" font-weight="800" letter-spacing="0.8">TIRAMISU</text>
                                    <!-- Butir Coklat Almond -->
                                    <ellipse cx="86" cy="64" rx="14" ry="11" fill="#4E2A1E" stroke="#2D160E" stroke-width="1.5"/>
                                    <path d="M78 61C82 57 90 57 94 61" stroke="#8D5B4C" stroke-width="1.8" stroke-linecap="round"/>
                                    <circle cx="91" cy="49" r="9" fill="#6B3E2E" stroke="#4E2A1E" stroke-width="1.5"/>
                                    <path d="M87 46C89 44 93 44 95 46" stroke="#D4AF37" stroke-width="1.4" stroke-linecap="round"/>
                                </svg>
                            </div>
                            <span class="font-heading font-bold text-[11px] sm:text-xs text-choco leading-tight">Coklat Beryl's</span>
                        </button>

                        <!-- 2) Nabati Coklat -->
                        <button type="button" onclick="tasteTreat('nabati')" id="treat-card-nabati"
                            class="treat-card bg-cream border-2 border-[#EAD4CE] rounded-xl p-2 flex flex-col items-center text-center cursor-pointer relative">
                            <span id="badge-nabati" class="hidden absolute -top-1.5 -right-1.5 w-5 h-5 rounded-full bg-roseaccent text-white text-[10px] font-bold items-center justify-center shadow-xs">✓</span>
                            <div class="w-16 h-14 mb-1">
                                <!-- Ilustrasi SVG Wafer Coklat Renyah Nabati -->
                                <svg viewBox="0 0 110 86" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-full h-full">
                                    <g transform="rotate(-8 42 44)">
                                        <rect x="10" y="14" width="54" height="58" rx="6" fill="url(#nabatiGrad)" stroke="#4E2A1E" stroke-width="2"/>
                                        <ellipse cx="37" cy="36" rx="21" ry="11" fill="#FACC15" stroke="#B91C1C" stroke-width="1.8"/>
                                        <text x="37" y="40" text-anchor="middle" fill="#B91C1C" font-size="11" font-weight="900" font-family="sans-serif">nabati</text>
                                        <text x="37" y="56" text-anchor="middle" fill="#FFFDF9" font-size="6.5" font-weight="bold">RICHOCO</text>
                                    </g>
                                    <g transform="translate(56, 36)">
                                        <rect x="4" y="14" width="38" height="22" rx="3" fill="#EAB308" stroke="#4E2A1E" stroke-width="1.5"/>
                                        <rect x="4" y="19" width="38" height="4" fill="#4E2A1E"/>
                                        <rect x="4" y="27" width="38" height="4" fill="#4E2A1E"/>
                                        <line x1="14" y1="14" x2="14" y2="19" stroke="#B45309" stroke-width="1"/>
                                        <line x1="24" y1="14" x2="24" y2="19" stroke="#B45309" stroke-width="1"/>
                                        <line x1="34" y1="14" x2="34" y2="19" stroke="#B45309" stroke-width="1"/>
                                        <rect x="10" y="2" width="34" height="14" rx="2.5" transform="rotate(-14 10 2)" fill="#F59E0B" stroke="#4E2A1E" stroke-width="1.5"/>
                                        <line x1="11" y1="8" x2="43" y2="0" stroke="#4E2A1E" stroke-width="3"/>
                                    </g>
                                    <defs>
                                        <linearGradient id="nabatiGrad" x1="10" y1="14" x2="64" y2="72" gradientUnits="userSpaceOnUse">
                                            <stop stop-color="#DC2626"/>
                                            <stop offset="1" stop-color="#5C2D1E"/>
                                        </linearGradient>
                                    </defs>
                                </svg>
                            </div>
                            <span class="font-heading font-bold text-[11px] sm:text-xs text-choco leading-tight">Nabati Coklat</span>
                        </button>

                        <!-- 3) Mochi Puncak -->
                        <button type="button" onclick="tasteTreat('mochi')" id="treat-card-mochi"
                            class="treat-card bg-cream border-2 border-[#EAD4CE] rounded-xl p-2 flex flex-col items-center text-center cursor-pointer relative">
                            <span id="badge-mochi" class="hidden absolute -top-1.5 -right-1.5 w-5 h-5 rounded-full bg-roseaccent text-white text-[10px] font-bold items-center justify-center shadow-xs">✓</span>
                            <div class="w-16 h-14 mb-1">
                                <!-- Ilustrasi SVG Kotak Mochi Lembut Bertabur Kacang/Wijen -->
                                <svg viewBox="0 0 110 86" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-full h-full">
                                    <rect x="12" y="34" width="86" height="40" rx="6" fill="#F3D9B1" stroke="#8D5B4C" stroke-width="2"/>
                                    <rect x="12" y="46" width="86" height="18" fill="#FF6B8B"/>
                                    <text x="55" y="57.5" text-anchor="middle" fill="#FFFDF9" font-size="7.5" font-weight="900" letter-spacing="0.5">MOCHI PUNCAK</text>
                                    <ellipse cx="32" cy="31" rx="14" ry="11" fill="#FFFDF9" stroke="#DFC7B8" stroke-width="1.8"/>
                                    <ellipse cx="55" cy="28" rx="15" ry="12" fill="#FFFFFF" stroke="#DFC7B8" stroke-width="1.8"/>
                                    <ellipse cx="78" cy="31" rx="14" ry="11" fill="#FFFDF9" stroke="#DFC7B8" stroke-width="1.8"/>
                                    <ellipse cx="30" cy="28" rx="1.4" ry="0.9" fill="#8D5B4C"/>
                                    <ellipse cx="35" cy="30" rx="1.4" ry="0.9" fill="#8D5B4C"/>
                                    <ellipse cx="52" cy="24" rx="1.5" ry="1" fill="#8D5B4C"/>
                                    <ellipse cx="58" cy="26" rx="1.5" ry="1" fill="#8D5B4C"/>
                                    <ellipse cx="55" cy="29" rx="1.4" ry="0.9" fill="#8D5B4C"/>
                                    <ellipse cx="76" cy="28" rx="1.4" ry="0.9" fill="#8D5B4C"/>
                                    <ellipse cx="81" cy="30" rx="1.4" ry="0.9" fill="#8D5B4C"/>
                                    <path d="M48 11L49.5 14L52.5 15.5L49.5 17L48 20L46.5 17L43.5 15.5L46.5 14L48 11Z" fill="#FF6B8B"/>
                                </svg>
                            </div>
                            <span class="font-heading font-bold text-[11px] sm:text-xs text-choco leading-tight">Mochi Puncak</span>
                        </button>
                    </div>

                    <!-- Kotak Balasan Sopan Saat Jajanan Diklik -->
                    <div id="treat-reply-box" class="hidden mt-3 bg-cream border border-roseaccent-light rounded-xl p-2.5 text-xs sm:text-[13px] text-choco leading-relaxed shadow-xs">
                        <p id="treat-reply-text" class="font-semibold"></p>
                    </div>
                </div>

                <!-- Dua Tombol Pilihan di Bawah Kartu -->
                <div class="mt-4 text-center">
                    <h3 class="text-base sm:text-lg font-bold text-choco leading-snug">
                        Jadi... udah nggak bad mood lagi kan? 😊
                    </h3>
                    <p id="runaway-helper-text" class="text-[11px] sm:text-xs text-choco-light mt-1 min-h-[18px]">
                        Ketuk jajanan di atas dulu biar makin adem, lalu pilih jawabanmu 👇
                    </p>

                    <!-- Arena Tombol Interaktif -->
                    <div id="button-arena" class="relative w-full h-44 sm:h-48 mt-2 rounded-2xl bg-blush-bg border border-dashed border-[#E2B8C2] flex flex-col items-center justify-start pt-4 px-3 select-none">
                        <!-- Tombol Positif (Membesar perlahan jika tombol satunya dihindari) -->
                        <button id="btn-forgive" type="button" onclick="acceptApology()"
                            class="relative z-20 py-3 px-7 rounded-2xl bg-gradient-to-r from-roseaccent to-roseaccent-hover text-white font-heading font-bold text-base sm:text-lg btn-rose-glow active:scale-95 cursor-pointer">
                            Oke, dimaafin ✨
                        </button>

                        <!-- Tombol Lincah: Masih kesel 😤 -->
                        <button id="btn-runaway" type="button"
                            class="z-10 mt-5 py-2.5 px-5 rounded-xl bg-cream border border-[#DFC1B9] text-choco-medium font-heading font-bold text-xs sm:text-sm shadow-xs hover:bg-blush-100 cursor-pointer whitespace-nowrap">
                            Masih kesel 😤
                        </button>
                    </div>
                </div>
            </section>

            <!-- ===============================================================
                 TAHAP 3: PERAYAAN & 4 TIKET KUPON KLAIM KE WHATSAPP
                 =============================================================== -->
            <section id="stage-3" class="stage-section relative z-10 text-center">
                <!-- Ilustrasi Maskot Ceria Membawa Kotak Hadiah Jajanan -->
                <div class="w-24 h-20 mx-auto mb-1 mascot-sway">
                    <svg viewBox="0 0 180 145" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-full h-full">
                        <!-- Bintang & Bunga Sakura -->
                        <path d="M34 26L36.5 32L42.5 34.5L36.5 37L34 43L31.5 37L25.5 34.5L31.5 32L34 26Z" fill="#FACC15"/>
                        <circle cx="146" cy="34" r="4" fill="#FFB3C6"/>
                        <circle cx="152" cy="38" r="4" fill="#FF94AC"/>
                        <circle cx="149" cy="44" r="4" fill="#FFB3C6"/>
                        <circle cx="143" cy="42" r="4" fill="#FF94AC"/>
                        <circle cx="147.5" cy="39" r="2.2" fill="#FACC15"/>

                        <path d="M54 50C48 30 59 20 72 33" fill="#FFFFFF" stroke="#D8B4BC" stroke-width="3.5" stroke-linecap="round"/>
                        <path d="M126 50C132 30 121 20 108 33" fill="#FFFFFF" stroke="#D8B4BC" stroke-width="3.5" stroke-linecap="round"/>

                        <ellipse cx="90" cy="74" rx="45" ry="37" fill="#FFFFFF" stroke="#D8B4BC" stroke-width="3.5"/>
                        <path d="M65 71C68 65 75 65 78 71" stroke="#4E2A1E" stroke-width="3" stroke-linecap="round"/>
                        <path d="M102 71C105 65 112 65 115 71" stroke="#4E2A1E" stroke-width="3" stroke-linecap="round"/>
                        <ellipse cx="60" cy="80" rx="8" ry="4.5" fill="#FFB3C6" opacity="0.8"/>
                        <ellipse cx="120" cy="80" rx="8" ry="4.5" fill="#FFB3C6" opacity="0.8"/>
                        <path d="M82 83C85 89 95 89 98 83" stroke="#4E2A1E" stroke-width="2.8" stroke-linecap="round"/>

                        <rect x="70" y="96" width="40" height="30" rx="5" fill="#FF6B8B" stroke="#4E2A1E" stroke-width="1.8"/>
                        <rect x="87" y="96" width="6" height="30" fill="#FACC15"/>
                        <rect x="70" y="108" width="40" height="6" fill="#FACC15"/>
                        <ellipse cx="70" cy="113" rx="10" ry="8" transform="rotate(-20 70 113)" fill="#FFFFFF" stroke="#D8B4BC" stroke-width="3"/>
                        <ellipse cx="110" cy="113" rx="10" ry="8" transform="rotate(20 110 113)" fill="#FFFFFF" stroke="#D8B4BC" stroke-width="3"/>
                    </svg>
                </div>

                <h2 class="text-xl sm:text-2xl font-bold text-choco leading-snug">
                    Yeay! Makasih banyak udah mau maafin 🙌✨
                </h2>

                <p class="text-xs sm:text-sm text-choco-medium mt-1.5 leading-relaxed">
                    Sebagai tanda terima kasih karena udah bikin suasana adem lagi, pilih tiket jajanan di bawah ini buat langsung diklaim ke WhatsApp:
                </p>

                <!-- 4 Tiket Kupon Berlubang Samping -->
                <div class="mt-3.5 space-y-2.5 text-left px-1" id="vouchers-container">

                    <!-- Tiket 1: 1 Box Coklat Beryl's 🍫 -->
                    <button type="button" onclick="claimVoucher(this, '1 Box Coklat Beryl\'s 🍫')"
                        class="w-full text-left ticket-voucher cursor-pointer rounded-2xl border-2 border-[#EAD7D1] bg-blush-bg hover:border-roseaccent flex items-stretch">
                        <div class="w-16 shrink-0 border-r-2 border-dashed border-[#DFC3BC] flex flex-col items-center justify-center p-2 text-center">
                            <span class="text-xl">🍫</span>
                            <span class="text-[9px] font-extrabold tracking-wider text-choco-light mt-0.5">TIKET #01</span>
                        </div>
                        <div class="flex-1 p-2.5 sm:p-3 flex items-center justify-between gap-2 min-w-0">
                            <div class="min-w-0">
                                <h3 class="font-heading font-bold text-xs sm:text-[13.5px] text-choco leading-snug">
                                    1 Box Coklat Beryl's 🍫
                                </h3>
                                <p class="text-[11px] text-choco-light leading-tight mt-0.5">
                                    Coklat manis buat balikin semangat hari ini
                                </p>
                            </div>
                            <span class="px-2.5 py-1 rounded-full bg-cream border border-blush-200 text-roseaccent text-[10px] font-extrabold shrink-0">
                                Klaim 💬
                            </span>
                        </div>
                    </button>

                    <!-- Tiket 2: Paket Nabati Coklat 🧇 -->
                    <button type="button" onclick="claimVoucher(this, 'Paket Nabati Coklat 🧇')"
                        class="w-full text-left ticket-voucher cursor-pointer rounded-2xl border-2 border-[#EAD7D1] bg-blush-bg hover:border-roseaccent flex items-stretch">
                        <div class="w-16 shrink-0 border-r-2 border-dashed border-[#DFC3BC] flex flex-col items-center justify-center p-2 text-center">
                            <span class="text-xl">🧇</span>
                            <span class="text-[9px] font-extrabold tracking-wider text-choco-light mt-0.5">TIKET #02</span>
                        </div>
                        <div class="flex-1 p-2.5 sm:p-3 flex items-center justify-between gap-2 min-w-0">
                            <div class="min-w-0">
                                <h3 class="font-heading font-bold text-xs sm:text-[13.5px] text-choco leading-snug">
                                    Paket Nabati Coklat 🧇
                                </h3>
                                <p class="text-[11px] text-choco-light leading-tight mt-0.5">
                                    Wafer coklat renyah buat teman santai
                                </p>
                            </div>
                            <span class="px-2.5 py-1 rounded-full bg-cream border border-blush-200 text-roseaccent text-[10px] font-extrabold shrink-0">
                                Klaim 💬
                            </span>
                        </div>
                    </button>

                    <!-- Tiket 3: 1 Kotak Mochi Puncak Hangat 🍡 -->
                    <button type="button" onclick="claimVoucher(this, '1 Kotak Mochi Puncak Hangat 🍡')"
                        class="w-full text-left ticket-voucher cursor-pointer rounded-2xl border-2 border-[#EAD7D1] bg-blush-bg hover:border-roseaccent flex items-stretch">
                        <div class="w-16 shrink-0 border-r-2 border-dashed border-[#DFC3BC] flex flex-col items-center justify-center p-2 text-center">
                            <span class="text-xl">🍡</span>
                            <span class="text-[9px] font-extrabold tracking-wider text-choco-light mt-0.5">TIKET #03</span>
                        </div>
                        <div class="flex-1 p-2.5 sm:p-3 flex items-center justify-between gap-2 min-w-0">
                            <div class="min-w-0">
                                <h3 class="font-heading font-bold text-xs sm:text-[13.5px] text-choco leading-snug">
                                    1 Kotak Mochi Puncak Hangat 🍡
                                </h3>
                                <p class="text-[11px] text-choco-light leading-tight mt-0.5">
                                    Mochi lembut khas Puncak yang bikin adem
                                </p>
                            </div>
                            <span class="px-2.5 py-1 rounded-full bg-cream border border-blush-200 text-roseaccent text-[10px] font-extrabold shrink-0">
                                Klaim 💬
                            </span>
                        </div>
                    </button>

                    <!-- Tiket 4: Paket Komplit (Semua Jajanan) ✨ -->
                    <button type="button" onclick="claimVoucher(this, 'Paket Komplit (Semua Jajanan) ✨')"
                        class="w-full text-left ticket-voucher cursor-pointer rounded-2xl border-2 border-[#EAD7D1] bg-blush-bg hover:border-roseaccent flex items-stretch">
                        <div class="w-16 shrink-0 border-r-2 border-dashed border-[#DFC3BC] flex flex-col items-center justify-center p-2 text-center">
                            <span class="text-xl">✨</span>
                            <span class="text-[9px] font-extrabold tracking-wider text-roseaccent mt-0.5">KOMPLIT</span>
                        </div>
                        <div class="flex-1 p-2.5 sm:p-3 flex items-center justify-between gap-2 min-w-0">
                            <div class="min-w-0">
                                <h3 class="font-heading font-bold text-xs sm:text-[13.5px] text-choco leading-snug">
                                    Paket Komplit (Semua Jajanan) ✨
                                </h3>
                                <p class="text-[11px] text-choco-light leading-tight mt-0.5">
                                    Coklat Beryl's + Nabati + Mochi Puncak sekaligus!
                                </p>
                            </div>
                            <span class="px-2.5 py-1 rounded-full bg-cream border border-blush-200 text-roseaccent text-[10px] font-extrabold shrink-0">
                                Klaim 💬
                            </span>
                        </div>
                    </button>
                </div>

                <p class="text-[11px] text-choco-light font-semibold mt-3">
                    Ketuk salah satu tiket di atas untuk langsung klaim via WhatsApp 😊
                </p>
            </section>

        </div>

        <!-- Footer Kecil -->
        <p class="text-center text-[11px] text-choco-light mt-3 font-semibold">
            Dibuat khusus untuk mencairkan suasana bareng <span class="display-nickname text-choco">Kamu</span> 🍫🌸
        </p>
    </main>

    <!-- =====================================================================
         TOMBOL KUSTOMISASI CEPAT (POJOK KANAN BAWAH)
         ===================================================================== -->
    <button id="btn-open-settings" type="button" onclick="openSettingsModal()" title="Kustomisasi Pesan & WA"
        aria-label="Kustomisasi Pesan dan WA"
        class="fixed bottom-4 right-4 z-30 px-3.5 py-2.5 rounded-full bg-cream/95 backdrop-blur-md border border-[#E6C7C2] shadow-md hover:shadow-lg text-choco hover:text-roseaccent flex items-center gap-1.5 text-xs font-heading font-bold transition-all duration-200 active:scale-95 cursor-pointer">
        <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 text-roseaccent" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M12 20h9"></path>
            <path d="M16.5 3.5a2.121 2.121 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"></path>
        </svg>
        <span class="hidden sm:inline">Kustomisasi</span>
    </button>

    <!-- =====================================================================
         MODAL PENGATURAN / KUSTOMISASI (display: none saat tertutup)
         ===================================================================== -->
    <div id="settings-modal" style="display: none;" class="fixed inset-0 z-50 items-center justify-center p-4 bg-choco/40 backdrop-blur-xs">
        <div class="bg-cream border-2 border-blush-200 rounded-3xl w-full max-w-sm p-6 shadow-2xl relative">
            <div class="flex items-center justify-between border-b border-blush-200 pb-3 mb-4">
                <div class="flex items-center gap-2">
                    <span class="text-lg">✏️</span>
                    <h3 class="font-heading font-bold text-base text-choco">Pengaturan Pesan &amp; WA</h3>
                </div>
                <button type="button" onclick="closeSettingsModal()" class="w-8 h-8 rounded-full bg-blush-100 text-choco hover:bg-blush-200 flex items-center justify-center text-sm font-bold cursor-pointer">
                    ✕
                </button>
            </div>

            <div class="space-y-3.5 text-left">
                <div>
                    <label for="input-nickname" class="block text-xs font-bold text-choco mb-1">
                        Nama Panggilan
                    </label>
                    <input type="text" id="input-nickname" placeholder="Default: Kamu"
                        class="w-full px-3.5 py-2.5 rounded-xl bg-blush-bg border border-blush-200 focus:border-roseaccent focus:outline-none text-sm text-choco">
                </div>

                <div>
                    <label for="input-message" class="block text-xs font-bold text-choco mb-1">
                        Pesan Permintaan Maaf
                    </label>
                    <textarea id="input-message" rows="3" placeholder="Kosongkan untuk menggunakan pesan default yang ramah & sopan..."
                        class="w-full px-3.5 py-2 rounded-xl bg-blush-bg border border-blush-200 focus:border-roseaccent focus:outline-none text-sm text-choco resize-none"></textarea>
                </div>

                <div>
                    <label for="input-wa" class="block text-xs font-bold text-choco mb-1">
                        Nomor WhatsApp (Format 628...)
                    </label>
                    <input type="tel" id="input-wa" placeholder="Contoh: 6281234567890"
                        class="w-full px-3.5 py-2.5 rounded-xl bg-blush-bg border border-blush-200 focus:border-roseaccent focus:outline-none text-sm text-choco">
                </div>
            </div>

            <div class="mt-5 space-y-2">
                <button type="button" onclick="saveSettings()"
                    class="w-full py-3 px-4 rounded-xl bg-gradient-to-r from-roseaccent to-roseaccent-hover text-white font-heading font-bold text-sm shadow-md active:scale-98 cursor-pointer">
                    Simpan Perubahan
                </button>

                <button type="button" onclick="copyShareableLink()"
                    class="w-full py-2.5 px-4 rounded-xl bg-blush-100 hover:bg-blush-200 text-choco font-heading font-bold text-xs flex items-center justify-center gap-1.5 transition-colors cursor-pointer">
                    <span>Salin Link Khusus 🔗</span>
                </button>
            </div>
        </div>
    </div>

    <!-- =====================================================================
         MODAL MINI FALLBACK WHATSAPP (display: none saat tertutup)
         ===================================================================== -->
    <div id="wa-fallback-modal" style="display: none;" class="fixed inset-0 z-50 items-center justify-center p-4 bg-choco/45 backdrop-blur-xs">
        <div class="bg-cream border-2 border-blush-200 rounded-3xl w-full max-w-sm p-5 shadow-2xl text-left">
            <div class="flex items-center justify-between border-b border-blush-200 pb-2.5 mb-3">
                <h3 class="font-heading font-bold text-base text-choco flex items-center gap-1.5">
                    <span>💬</span>
                    <span>Kirim Klaim Tiket</span>
                </h3>
                <button type="button" onclick="closeWaFallbackModal()" class="w-7 h-7 rounded-full bg-blush-100 text-choco hover:bg-blush-200 flex items-center justify-center text-xs font-bold cursor-pointer">
                    ✕
                </button>
            </div>

            <p class="text-xs text-choco-medium leading-relaxed mb-3">
                Masukkan nomor WhatsApp tujuan (format <span class="font-bold">628...</span>) untuk langsung mengirim pilihan tiketmu, atau salin teks pesannya:
            </p>

            <div class="space-y-2.5">
                <div>
                    <input type="tel" id="fallback-wa-input" placeholder="Contoh: 6281234567890"
                        class="w-full px-3.5 py-2.5 rounded-xl bg-blush-bg border border-blush-200 focus:border-roseaccent focus:outline-none text-sm text-choco">
                </div>

                <button type="button" onclick="submitFallbackWaNumber()"
                    class="w-full py-3 px-4 rounded-xl bg-gradient-to-r from-[#25D366] to-[#1EBE5D] text-white font-heading font-bold text-xs sm:text-sm shadow-md active:scale-98 flex items-center justify-center gap-1.5 cursor-pointer">
                    <span>Lanjut ke WhatsApp 💬</span>
                </button>

                <button type="button" onclick="copyClaimMessageOnly()"
                    class="w-full py-2.5 px-4 rounded-xl bg-blush-100 hover:bg-blush-200 text-choco font-heading font-bold text-xs flex items-center justify-center gap-1.5 transition-colors cursor-pointer">
                    <span>📋</span>
                    <span>Salin Teks Pesan Klaim</span>
                </button>
            </div>
        </div>
    </div>

    <!-- =====================================================================
         LOGIKA JAVASCRIPT INTERAKTIF (BEBAS BUG & RESPONSIF)
         ===================================================================== -->
    <script>
        const STORAGE_KEY = 'pesan_perdamaian_jajanan_v2';

        const DEFAULT_APOLOGY_MESSAGE =
            "Maaf banget ya kalau ucapan atau sikapku kemarin sempat bikin kamu kurang nyaman atau bad mood. Niatku sama sekali nggak ke sana. Karena kita baru kenal, aku pengen banget jaga suasana tetap asyik dan bikin kamu nyaman ngobrol. Boleh ya kita baikan lagi?";

        // State Utama Aplikasi
        const appState = {
            currentStage: 1,
            isOpeningEnvelope: false,
            nickname: 'Kamu',
            apologyMessage: '',
            whatsappNumber: '',
            tastedTreats: new Set(),
            runawayCount: 0,
            forgiveScale: 1,
            lastClaimedVoucher: '1 Box Coklat Beryl\'s 🍫'
        };

        // Balasan Sopan & Hangat untuk 3 Jajanan Favorit
        const treatSweetReplies = {
            beryls: "Manisnya Coklat Beryl's semoga bisa langsung balikin senyum dan semangat kamu hari ini! 🍫✨",
            nabati: "Renyah dan lumer kayak Nabati Coklat, semoga bad mood-nya langsung ikutan lumer ya! 🧇✨",
            mochi: "Lembutnya Mochi Puncak siap nemenin waktu santai kamu biar nggak cemberut lagi! 🍡✨"
        };

        // Daftar Teks Lucu & Sopan untuk Tombol Lincah ("Masih kesel 😤")
        const runawayPhrases = [
            "Jangan kesel lama-lama dong 😅",
            "Tambah Coklat Beryl's nih? 🍫",
            "Mochi Puncak-nya udah siap lho 🍡",
            "Eits, tombolnya geser sendiri ✨",
            "Nabati Coklat-nya ikut nungguin 🧇",
            "Klik yang sebelah aja ya 😊"
        ];

        // =====================================================================
        // INISIALISASI SAAT HALAMAN DIMUAT
        // =====================================================================
        window.addEventListener('DOMContentLoaded', () => {
            loadSavedSettings();
            updateUIContent();
            createBackgroundParticles();
            setupRunawayButton();
            resizeCelebrationCanvas();
        });

        window.addEventListener('resize', () => {
            resizeCelebrationCanvas();
            if (appState.currentStage === 2 && appState.runawayCount > 0) {
                moveRunawayButton();
            }
        });

        // =====================================================================
        // NAVIGASI TAHAP 1 -> TAHAP 2 (ANIMASI AMPLOP 700ms) -> TAHAP 3
        // =====================================================================
        function openEnvelopeAndAdvance() {
            if (appState.isOpeningEnvelope || appState.currentStage !== 1) return;
            appState.isOpeningEnvelope = true;

            const envelopeEl = document.getElementById('stage1-envelope');
            const openBtn = document.getElementById('btn-open-stage2');

            if (envelopeEl) {
                envelopeEl.classList.add('is-opening');
            }
            if (openBtn) {
                openBtn.disabled = true;
                openBtn.classList.add('opacity-85');
            }

            // Jalankan animasi tutup amplop terbuka dan surat naik ke atas selama 700ms, lalu pindah ke Tahap 2
            setTimeout(() => {
                goToStage(2);
                appState.isOpeningEnvelope = false;
            }, 700);
        }

        function goToStage(stageNumber) {
            appState.currentStage = stageNumber;

            // Sembunyikan semua tahap terlebih dahulu
            document.querySelectorAll('.stage-section').forEach(sec => {
                sec.classList.remove('active');
            });

            // Tampilkan tahap tujuan dengan transisi mulus
            const targetSection = document.getElementById(`stage-${stageNumber}`);
            if (targetSection) {
                targetSection.classList.add('active');
            }

            // Perbarui indikator titik tahap di atas kartu
            for (let i = 1; i <= 3; i++) {
                const dot = document.getElementById(`stage-dot-${i}`);
                if (!dot) continue;
                if (i === stageNumber) {
                    dot.classList.remove('w-2.5', 'bg-[#E8C8CE]');
                    dot.classList.add('w-8', 'bg-roseaccent');
                } else if (i < stageNumber) {
                    dot.classList.remove('w-8', 'bg-[#E8C8CE]');
                    dot.classList.add('w-2.5', 'bg-roseaccent-light');
                } else {
                    dot.classList.remove('w-8', 'bg-roseaccent', 'bg-roseaccent-light');
                    dot.classList.add('w-2.5', 'bg-[#E8C8CE]');
                }
            }

            // Gulir lembut ke atas agar seluruh kartu terlihat utuh di layar HP
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // =====================================================================
        // MUAT & SIMPAN PENGATURAN (LOCALSTORAGE & PARAMETER URL)
        // =====================================================================
        function loadSavedSettings() {
            try {
                const rawSaved = localStorage.getItem(STORAGE_KEY);
                if (rawSaved) {
                    const parsed = JSON.parse(rawSaved);
                    if (parsed.nickname) appState.nickname = parsed.nickname;
                    if (typeof parsed.apologyMessage === 'string') appState.apologyMessage = parsed.apologyMessage;
                    if (parsed.whatsappNumber) appState.whatsappNumber = parsed.whatsappNumber;
                }
            } catch (err) {
                console.warn('Tidak dapat membaca localStorage:', err);
            }

            try {
                const params = new URLSearchParams(window.location.search);
                if (params.get('nama')) appState.nickname = params.get('nama').trim();
                if (params.get('pesan')) appState.apologyMessage = params.get('pesan').trim();
                if (params.get('wa')) appState.whatsappNumber = formatTo62(params.get('wa').trim());
            } catch (err) {
                console.warn('Tidak dapat membaca parameter URL:', err);
            }
        }

        function formatTo62(rawPhone) {
            if (!rawPhone) return '';
            let digits = rawPhone.replace(/\D/g, '');
            if (digits.startsWith('0')) {
                digits = '62' + digits.slice(1);
            } else if (digits.startsWith('8')) {
                digits = '62' + digits;
            }
            return digits;
        }

        function updateUIContent() {
            const safeNick = (appState.nickname || '').trim() || 'Kamu';
            document.querySelectorAll('.display-nickname').forEach(el => {
                el.textContent = safeNick;
            });

            const msgEl = document.getElementById('display-apology-message');
            if (msgEl) {
                const customMsg = (appState.apologyMessage || '').trim();
                msgEl.textContent = customMsg || DEFAULT_APOLOGY_MESSAGE;
            }

            const inputNick = document.getElementById('input-nickname');
            const inputMsg = document.getElementById('input-message');
            const inputWa = document.getElementById('input-wa');

            if (inputNick) inputNick.value = safeNick === 'Kamu' ? '' : safeNick;
            if (inputMsg) inputMsg.value = appState.apologyMessage || '';
            if (inputWa) inputWa.value = appState.whatsappNumber || '';
        }

        // =====================================================================
        // PARTIKEL MELAYANG DI LATAR BELAKANG (BINTANG, SAKURA, COKLAT, MOCHI)
        // =====================================================================
        function createBackgroundParticles() {
            const container = document.getElementById('bg-particles-container');
            if (!container) return;

            const particles = ['✨', '🌸', '🍫', '🍡'];
            const total = 16;

            for (let i = 0; i < total; i++) {
                const item = document.createElement('div');
                item.className = 'bg-particle';
                item.textContent = particles[i % particles.length];

                item.style.left = `${Math.random() * 96}vw`;
                item.style.animationDuration = `${9 + Math.random() * 8}s`;
                item.style.animationDelay = `${Math.random() * 9}s`;
                item.style.fontSize = `${14 + Math.random() * 10}px`;

                container.appendChild(item);
            }
        }

        // =====================================================================
        // TAHAP 2: MENU JAJANAN FAVORIT & LEVEL MOOD ADEM (0% -> 100%)
        // =====================================================================
        function tasteTreat(treatKey) {
            appState.tastedTreats.add(treatKey);

            const card = document.getElementById(`treat-card-${treatKey}`);
            const badge = document.getElementById(`badge-${treatKey}`);
            if (card) card.classList.add('tasted');
            if (badge) {
                badge.classList.remove('hidden');
                badge.classList.add('flex');
            }

            const count = appState.tastedTreats.size;
            let percent = 0;
            if (count === 1) percent = 33;
            else if (count === 2) percent = 66;
            else if (count >= 3) percent = 100;

            const fillBar = document.getElementById('meter-fill-bar');
            const percentBadge = document.getElementById('meter-percent-badge');

            if (fillBar) fillBar.style.width = `${percent}%`;
            if (percentBadge) percentBadge.textContent = `${percent}%`;

            const replyBox = document.getElementById('treat-reply-box');
            const replyText = document.getElementById('treat-reply-text');
            if (replyBox && replyText) {
                replyText.textContent = treatSweetReplies[treatKey];
                replyBox.classList.remove('hidden');
            }
        }

        // =====================================================================
        // TAHAP 2: TOMBOL LINCAH ("MASIH KESEL 😤") & TOMBOL POSITIF MEMBESAR
        // =====================================================================
        function setupRunawayButton() {
            const btnRunaway = document.getElementById('btn-runaway');
            if (!btnRunaway) return;

            // Desktop hover
            btnRunaway.addEventListener('mouseenter', () => {
                moveRunawayButton();
            });

            // Mobile touch
            btnRunaway.addEventListener('touchstart', (e) => {
                e.preventDefault();
                moveRunawayButton();
            }, { passive: false });

            // Fallback click
            btnRunaway.addEventListener('click', (e) => {
                e.preventDefault();
                moveRunawayButton();
            });
        }

        function moveRunawayButton() {
            const arena = document.getElementById('button-arena');
            const btnRunaway = document.getElementById('btn-runaway');
            const btnForgive = document.getElementById('btn-forgive');
            const helperText = document.getElementById('runaway-helper-text');

            if (!arena || !btnRunaway || !btnForgive) return;

            // Ganti teks tombol lincah secara bergantian
            const phrase = runawayPhrases[appState.runawayCount % runawayPhrases.length];
            btnRunaway.textContent = phrase;
            appState.runawayCount++;

            // Perbesar tombol "Oke, dimaafin ✨" perlahan
            appState.forgiveScale = Math.min(1.36, 1 + appState.runawayCount * 0.075);
            btnForgive.style.transform = `scale(${appState.forgiveScale})`;

            if (helperText) {
                helperText.textContent = appState.runawayCount >= 3
                    ? "Tombol pink-nya udah makin besar tuh, pencet yang itu aja ya 😊✨"
                    : "Eits, geser! Coba pencet tombol yang sebelah aja ya 😉";
            }

            // Ubah ke posisi absolut di dalam arena agar bebas berpindah dengan aman
            btnRunaway.style.position = 'absolute';
            btnRunaway.style.marginTop = '0px';

            const arenaWidth = arena.clientWidth;
            const arenaHeight = arena.clientHeight;
            const runWidth = btnRunaway.offsetWidth;
            const runHeight = btnRunaway.offsetHeight;

            // Hitung batas aman di bawah tombol "Oke, dimaafin ✨"
            const forgiveBottom = btnForgive.offsetTop + (btnForgive.offsetHeight * appState.forgiveScale);
            const padding = 10;

            const minX = padding;
            const maxX = Math.max(minX, arenaWidth - runWidth - padding);

            const minY = Math.min(
                Math.max(padding, arenaHeight - runHeight - padding),
                Math.round(forgiveBottom + 10)
            );
            const maxY = Math.max(minY, arenaHeight - runHeight - padding);

            const randomX = minX + Math.random() * (maxX - minX);
            const randomY = minY + Math.random() * (maxY - minY);

            btnRunaway.style.left = `${Math.round(randomX)}px`;
            btnRunaway.style.top = `${Math.round(randomY)}px`;
        }

        // =====================================================================
        // TAHAP 3: PERAYAAN & KLAIM TIKET KUPON KE WHATSAPP
        // =====================================================================
        function acceptApology() {
            goToStage(3);
            startCelebrationConfetti();
        }

        function claimVoucher(cardEl, voucherName) {
            appState.lastClaimedVoucher = voucherName;

            document.querySelectorAll('.ticket-voucher').forEach(el => {
                el.classList.remove('selected');
            });
            if (cardEl) {
                cardEl.classList.add('selected');
            }

            const cleanWa = formatTo62(appState.whatsappNumber);
            if (!cleanWa) {
                openWaFallbackModal();
                return;
            }

            openWhatsAppWithNumber(cleanWa, voucherName);
        }

        function buildClaimWhatsAppMessage(voucherName) {
            const chosen = voucherName || appState.lastClaimedVoucher;
            return `Halo! Aku udah baca pesannya dan udah dimaafin kok 😊 Aku mau klaim tiket jajanannya: *${chosen}* ya!`;
        }

        function openWhatsAppWithNumber(formatted62Number, voucherName) {
            const msg = buildClaimWhatsAppMessage(voucherName);
            const encoded = encodeURIComponent(msg);
            const waUrl = `https://wa.me/${formatted62Number}?text=${encoded}`;
            window.open(waUrl, '_blank', 'noopener,noreferrer');
        }

        // Modal Mini Fallback WA (strictly display: none saat tertutup)
        function openWaFallbackModal() {
            const modal = document.getElementById('wa-fallback-modal');
            if (modal) modal.style.display = 'flex';
        }

        function closeWaFallbackModal() {
            const modal = document.getElementById('wa-fallback-modal');
            if (modal) modal.style.display = 'none';
        }

        document.getElementById('wa-fallback-modal').addEventListener('click', (e) => {
            if (e.target.id === 'wa-fallback-modal') closeWaFallbackModal();
        });

        function submitFallbackWaNumber() {
            const rawInput = document.getElementById('fallback-wa-input').value.trim();
            const formatted = formatTo62(rawInput);

            if (!formatted || formatted.length < 10) {
                showToast('Masukkan nomor WhatsApp yang valid ya (628...) 📱', '⚠️');
                return;
            }

            appState.whatsappNumber = formatted;
            persistToLocalStorage();
            updateUIContent();
            closeWaFallbackModal();
            openWhatsAppWithNumber(formatted, appState.lastClaimedVoucher);
        }

        function copyClaimMessageOnly() {
            const msg = buildClaimWhatsAppMessage(appState.lastClaimedVoucher);
            copyTextToClipboard(msg, 'Teks klaim tiket berhasil disalin! 📋');
            closeWaFallbackModal();
        }

        // =====================================================================
        // MODAL PENGATURAN / KUSTOMISASI (strictly display: none saat tertutup)
        // =====================================================================
        function openSettingsModal() {
            const modal = document.getElementById('settings-modal');
            if (modal) modal.style.display = 'flex';
        }

        function closeSettingsModal() {
            const modal = document.getElementById('settings-modal');
            if (modal) modal.style.display = 'none';
        }

        document.getElementById('settings-modal').addEventListener('click', (e) => {
            if (e.target.id === 'settings-modal') closeSettingsModal();
        });

        function persistToLocalStorage() {
            try {
                localStorage.setItem(STORAGE_KEY, JSON.stringify({
                    nickname: appState.nickname,
                    apologyMessage: appState.apologyMessage,
                    whatsappNumber: appState.whatsappNumber
                }));
            } catch (err) {
                console.warn('Gagal menyimpan ke localStorage:', err);
            }
        }

        function saveSettings() {
            const nick = document.getElementById('input-nickname').value.trim();
            const message = document.getElementById('input-message').value.trim();
            const wa = document.getElementById('input-wa').value.trim();

            appState.nickname = nick || 'Kamu';
            appState.apologyMessage = message;
            appState.whatsappNumber = formatTo62(wa);

            persistToLocalStorage();
            updateUIContent();
            closeSettingsModal();
            showToast('Perubahan berhasil disimpan! ✨', '🍫');
        }

        function copyShareableLink() {
            const nick = document.getElementById('input-nickname').value.trim() || 'Kamu';
            const message = document.getElementById('input-message').value.trim();
            const wa = formatTo62(document.getElementById('input-wa').value.trim());

            appState.nickname = nick;
            appState.apologyMessage = message;
            appState.whatsappNumber = wa;

            persistToLocalStorage();
            updateUIContent();

            const shareUrl = new URL(window.location.href.split('?')[0]);
            if (nick && nick !== 'Kamu') shareUrl.searchParams.set('nama', nick);
            if (message) shareUrl.searchParams.set('pesan', message);
            if (wa) shareUrl.searchParams.set('wa', wa);

            copyTextToClipboard(shareUrl.toString(), 'Link khusus berhasil disalin! 🔗');
        }

        function copyTextToClipboard(text, successMessage) {
            try {
                const textarea = document.createElement('textarea');
                textarea.value = text;
                textarea.style.position = 'fixed';
                textarea.style.opacity = '0';
                document.body.appendChild(textarea);
                textarea.focus();
                textarea.select();
                document.execCommand('copy');
                document.body.removeChild(textarea);
                showToast(successMessage, '✨');
            } catch (err) {
                showToast('Gagal menyalin otomatis, silakan salin manual.', '⚠️');
            }
        }

        let toastTimer;
        function showToast(text, icon = '✨') {
            const toast = document.getElementById('toast-notification');
            document.getElementById('toast-text').textContent = text;
            document.getElementById('toast-icon').textContent = icon;

            toast.classList.remove('opacity-0', '-translate-y-3');
            toast.classList.add('opacity-100', 'translate-y-0');

            clearTimeout(toastTimer);
            toastTimer = setTimeout(() => {
                toast.classList.remove('opacity-100', 'translate-y-0');
                toast.classList.add('opacity-0', '-translate-y-3');
            }, 2800);
        }

        // =====================================================================
        // ANIMASI CANVAS KONFETI PERAYAAN (BINTANG, SAKURA, COKLAT, MOCHI)
        // =====================================================================
        const canvas = document.getElementById('celebration-canvas');
        const ctx = canvas.getContext('2d');
        let confettiItems = [];
        let animId = null;

        function resizeCelebrationCanvas() {
            if (!canvas) return;
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }

        function startCelebrationConfetti() {
            resizeCelebrationCanvas();
            confettiItems = [];

            const types = ['star', 'sakura', 'choco', 'mochi', 'ribbon'];
            const ribbonColors = ['#FF6B8B', '#FFB3C6', '#D4AF37', '#8D5B4C', '#FACC15'];

            for (let i = 0; i < 85; i++) {
                confettiItems.push({
                    x: Math.random() * canvas.width,
                    y: Math.random() * -canvas.height - 20,
                    size: 9 + Math.random() * 8,
                    speedY: 2.3 + Math.random() * 3.4,
                    speedX: (Math.random() - 0.5) * 2.6,
                    rotation: Math.random() * 360,
                    rotationSpeed: (Math.random() - 0.5) * 6,
                    type: types[i % types.length],
                    color: ribbonColors[i % ribbonColors.length]
                });
            }

            if (animId) cancelAnimationFrame(animId);
            renderCelebrationFrame();
        }

        function drawParticleItem(p) {
            ctx.save();
            ctx.translate(p.x, p.y);
            ctx.rotate((p.rotation * Math.PI) / 180);

            if (p.type === 'star') {
                const r = p.size * 0.7;
                ctx.fillStyle = '#FACC15';
                ctx.beginPath();
                ctx.moveTo(0, -r);
                ctx.quadraticCurveTo(0, 0, r, 0);
                ctx.quadraticCurveTo(0, 0, 0, r);
                ctx.quadraticCurveTo(0, 0, -r, 0);
                ctx.quadraticCurveTo(0, 0, 0, -r);
                ctx.fill();
            } else if (p.type === 'sakura') {
                const r = p.size * 0.35;
                ctx.fillStyle = '#FF94AC';
                for (let k = 0; k < 5; k++) {
                    const angle = (k * 2 * Math.PI) / 5;
                    ctx.beginPath();
                    ctx.arc(Math.cos(angle) * r, Math.sin(angle) * r, r * 0.75, 0, Math.PI * 2);
                    ctx.fill();
                }
                ctx.fillStyle = '#FACC15';
                ctx.beginPath();
                ctx.arc(0, 0, r * 0.45, 0, Math.PI * 2);
                ctx.fill();
            } else if (p.type === 'choco') {
                ctx.fillStyle = '#4E2A1E';
                ctx.strokeStyle = '#8D5B4C';
                ctx.lineWidth = 1.2;
                ctx.fillRect(-p.size / 2, -p.size / 2.5, p.size, p.size * 0.8);
                ctx.strokeRect(-p.size / 2, -p.size / 2.5, p.size, p.size * 0.8);
            } else if (p.type === 'mochi') {
                ctx.fillStyle = '#FFFDF9';
                ctx.strokeStyle = '#E5D1C8';
                ctx.lineWidth = 1.4;
                ctx.beginPath();
                ctx.arc(0, 0, p.size * 0.55, 0, Math.PI * 2);
                ctx.fill();
                ctx.stroke();
                ctx.fillStyle = '#6B3E2E';
                ctx.fillRect(-1.5, -1.5, 2, 1.5);
                ctx.fillRect(1.5, 1, 2, 1.5);
            } else {
                ctx.fillStyle = p.color;
                ctx.fillRect(-p.size / 2, -p.size / 4, p.size, p.size * 0.45);
            }

            ctx.restore();
        }

        function renderCelebrationFrame() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            let stillVisible = 0;
            confettiItems.forEach(p => {
                p.y += p.speedY;
                p.x += p.speedX + Math.sin(p.y * 0.025) * 0.7;
                p.rotation += p.rotationSpeed;

                if (p.y < canvas.height + 35) {
                    stillVisible++;
                    drawParticleItem(p);
                }
            });

            if (stillVisible > 0) {
                animId = requestAnimationFrame(renderCelebrationFrame);
            } else {
                ctx.clearRect(0, 0, canvas.width, canvas.height);
            }
        }
    </script>
</body>
</html>

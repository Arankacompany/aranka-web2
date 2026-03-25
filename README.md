# aranka-web2
<!DOCTYPE html>
<html lang="cs" class="scroll-smooth scroll-pt-24">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ubytování Aranka Žatec | Prémiové apartmány — Rezervace online</title>
    
    <!-- SEO OPTIMALIZACE: Rozšířená klíčová slova dle návrhu SEO specialisty -->
    <meta name="description" content="Prémiové ubytování Aranka v Žatci a okolí od 550 Kč/noc. Čisté, klidné apartmány a dlouhodobé ubytování blízko centra Žatce s privátní zahradou.">
    <meta name="theme-color" content="#2C241B">
    <link rel="canonical" href="https://arankacompany.eu/">
    
    <!-- Open Graph -->
    <meta property="og:title" content="Ubytování Aranka | Prémiové apartmány Žatec">
    <meta property="og:description" content="Designové apartmány s klidem a stylem v srdci Žatce. Rezervujte svůj pobyt online.">
    <!-- TODO [AGENTURA]: Změnit obrázek za finální a zajistit kompresi do formátu WebP -->
    <meta property="og:image" content="https://images.unsplash.com/photo-1611892440504-42a792e24d32?auto=format&fit=crop&w=1200&q=80">
    
    <!-- SEO: Strukturovaná data (Schema.org) pro lepší zobrazení v Google vyhledávání -->
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "Hotel",
      "name": "Ubytování Aranka Žatec",
      "description": "Prémiové ubytování a apartmány v Žatci s privátní zahradou a pergolou.",
      "image": "https://images.unsplash.com/photo-1611892440504-42a792e24d32?auto=format&fit=crop&w=1200&q=80",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "Francouzská 1398",
        "addressLocality": "Žatec",
        "postalCode": "438 01",
        "addressCountry": "CZ"
      },
      "telephone": "+420776604006",
      "url": "https://arankacompany.eu/",
      "priceRange": "$$"
    }
    </script>

    <!-- Fonty -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&family=Cinzel:wght@400;500;600;700&display=swap" rel="stylesheet">
    
    <!-- Tailwind CSS & Lucide Icons -->
    <script src="https://cdn.tailwindcss.com?plugins=forms,typography,aspect-ratio"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            caramel: '#c28e62', 
                            dark: '#2C241B', 
                            light: '#fdfbf9',
                            sand: '#f5f2eb', 
                            text: '#4A423C', 
                            muted: '#8c7e71'
                        }
                    },
                    fontFamily: {
                        sans: ['Montserrat', 'sans-serif'],
                        serif: ['Cinzel', 'serif'],
                    },
                    boxShadow: {
                        'premium': '0 25px 50px -12px rgba(44, 36, 27, 0.15)',
                        'premium-hover': '0 35px 60px -15px rgba(44, 36, 27, 0.25)',
                        'glow': '0 0 40px -10px rgba(194, 142, 98, 0.4)',
                    },
                    animation: {
                        'fade-in': 'fadeIn 1s ease-out forwards',
                        'slide-up': 'slideUp 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards',
                    },
                    keyframes: {
                        fadeIn: { '0%': { opacity: '0' }, '100%': { opacity: '1' } },
                        slideUp: { '0%': { opacity: '0', transform: 'translateY(40px)' }, '100%': { opacity: '1', transform: 'translateY(0)' } }
                    }
                }
            }
        };
    </script>

    <style>
        /* Base & Animations */
        body { -webkit-font-smoothing: antialiased; background-color: #fdfbf9; color: #4A423C; overflow-x: hidden; }
        .reveal { opacity: 0; transform: translateY(40px); transition: all 1s cubic-bezier(0.16, 1, 0.3, 1); will-change: transform, opacity; }
        .reveal.active { opacity: 1; transform: translateY(0); }
        #scroll-progress { position: fixed; top: 0; left: 0; height: 3px; background: #c28e62; z-index: 99999; transition: width 0.1s ease-out; }

        /* Ochrana heslem - VIP Brána */
        #password-protection { transition: opacity 0.8s ease, visibility 0.8s ease; background: rgba(44, 36, 27, 0.98); backdrop-filter: blur(20px); }
        .pwd-input-line { border-bottom: 2px solid rgba(255,255,255,0.2); transition: border-color 0.4s ease; }
        .pwd-input-line:focus-within { border-color: #c28e62; }

        /* Modals & Overlays */
        .overlay { visibility: hidden; opacity: 0; transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1); position: fixed; inset: 0; z-index: 9000; background: rgba(44, 36, 27, 0.85); backdrop-filter: blur(8px); display: flex; align-items: center; justify-content: center; padding: 1rem; }
        .overlay.active { visibility: visible; opacity: 1; }
        .modal-content { max-height: 95vh; overflow-y: auto; width: 100%; border-radius: 20px; box-shadow: 0 40px 80px -20px rgba(0,0,0,0.7); background-color: #fdfbf9; scrollbar-width: none; transform: scale(0.95); transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1); }
        .overlay.active .modal-content { transform: scale(1); }
        .modal-content::-webkit-scrollbar { display: none; }

        /* Navigation */
        #site-nav { transform: translateY(-100%); transition: all 0.5s cubic-bezier(0.16, 1, 0.3, 1); background: rgba(253, 251, 249, 0.95); backdrop-filter: blur(20px); border-bottom: 1px solid rgba(194, 142, 98, 0.05); }
        #site-nav.nav-visible { transform: translateY(0); }
        #site-nav.nav-scrolled { box-shadow: 0 10px 40px -10px rgba(44, 36, 27, 0.08); padding-top: 1rem !important; padding-bottom: 1rem !important; }
        
        /* Buttons & Forms */
        .b2b-field { border-bottom: 1px solid #cfcac1; padding: 12px 0; background: transparent; outline: none; transition: border-color 0.3s; font-size: 1rem; color: #2C241B; width: 100%; border-top: none; border-left: none; border-right: none; }
        .b2b-field:focus { border-color: #c28e62; box-shadow: none; }
        .b2b-label { font-size: 0.65rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.15em; color: #8c7e71; display: block; margin-bottom: 4px; }
        .btn-premium { background-color: #2C241B; color: #fff; transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1); border: 1px solid #2C241B; display: inline-flex; align-items: center; justify-content: center; gap: 0.5rem;}
        .btn-premium:hover { background-color: #c28e62; border-color: #c28e62; transform: translateY(-3px); box-shadow: 0 15px 30px -5px rgba(194, 142, 98, 0.4); }
        .btn-outline { border: 1px solid #c28e62; color: #c28e62; background: transparent; transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1); }
        .btn-outline:hover { background-color: #c28e62; color: white; transform: translateY(-3px); box-shadow: 0 15px 30px -5px rgba(194, 142, 98, 0.4); }

        .no-scrollbar::-webkit-scrollbar { display: none; }
        .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }

        /* Room Cards */
        .mood-card { transition: all 0.6s cubic-bezier(0.16, 1, 0.3, 1); cursor: pointer; border-radius: 20px; overflow: hidden; position: relative; display: flex; flex-direction: column; justify-content: flex-end; background-color: #2C241B; aspect-ratio: 4/5; transform: translateZ(0); }
        .mood-card:hover { transform: translateY(-12px); box-shadow: 0 40px 60px -15px rgba(44, 36, 27, 0.4); z-index: 10; }
        .mood-card img { transition: transform 1.5s cubic-bezier(0.16, 1, 0.3, 1); width: 100%; height: 100%; object-fit: cover; position: absolute; inset: 0; opacity: 0.75; }
        .mood-card:hover img { transform: scale(1.05); opacity: 0.9; }
        .card-gradient { background: linear-gradient(to top, rgba(44, 36, 27, 0.98) 0%, rgba(44, 36, 27, 0.4) 50%, transparent 100%); position: absolute; inset: 0; pointer-events: none; transition: opacity 0.5s ease; }
        .mood-card:hover .card-gradient { opacity: 1; }
        .card-content { transition: transform 0.5s cubic-bezier(0.16, 1, 0.3, 1); transform: translateY(10px); }
        .mood-card:hover .card-content { transform: translateY(0); }

        /* Filter Widget */
        .filter-input { background: transparent; border: none; border-bottom: 1px solid rgba(255,255,255,0.2); border-radius: 0; color: white; padding: 0.5rem 0; transition: border-color 0.3s ease; }
        .filter-input:focus { border-color: #c28e62; box-shadow: none; outline: none; }
        .filter-input option { background: #2C241B; color: white; }
        .filter-input::-webkit-calendar-picker-indicator { filter: invert(1) opacity(0.7); cursor: pointer; transition: opacity 0.3s; }
        .filter-input::-webkit-calendar-picker-indicator:hover { opacity: 1; }

        /* Slider Gallery */
        .slider-container { display: flex; overflow-x: auto; scroll-snap-type: x mandatory; scrollbar-width: none; gap: 24px; padding: 20px 0; scroll-behavior: smooth; }
        .slider-container::-webkit-scrollbar { display: none; }
        .slider-item { flex: 0 0 clamp(280px, 30vw, 450px); scroll-snap-align: center; aspect-ratio: 4/3; cursor: zoom-in; position: relative; border-radius: 16px; overflow: hidden; background-color: #2C241B; box-shadow: 0 10px 30px rgba(44, 36, 27, 0.1); transition: transform 0.5s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.5s ease; }
        .slider-item:hover { transform: scale(1.02); box-shadow: 0 20px 40px rgba(44, 36, 27, 0.2); z-index: 10; }
        .slider-item img { width: 100%; height: 100%; object-fit: cover; transition: transform 1.2s cubic-bezier(0.16, 1, 0.3, 1); opacity: 0.9; }
        .slider-item:hover img { transform: scale(1.08); opacity: 1; }

        /* Hero Video Container */
        .hero-video-container { position: absolute; inset: 0; overflow: hidden; z-index: 0; background-color: #2C241B; }
        .hero-video-container video { position: absolute; top: 50%; left: 50%; width: 100vw; height: 100vh; object-fit: cover; transform: translate(-50%, -50%); opacity: 0.6; pointer-events: none; }

        /* Cookie Banner */
        #cookie-banner { position: fixed; bottom: 0; left: 0; right: 0; z-index: 9999; transform: translateY(100%); transition: transform 0.6s cubic-bezier(0.16, 1, 0.3, 1); }
        #cookie-banner.show { transform: translateY(0); }
    </style>
</head>
<body class="font-sans text-brand-text overflow-x-hidden overflow-y-auto bg-brand-light">

    <!-- Progress Bar -->
    <div id="scroll-progress"></div>

    <!-- 1. VIP HESLO -->
    <div id="password-protection" class="fixed inset-0 z-[100000] flex flex-col items-center justify-center">
        <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1600210492486-724fe5c67fb0?auto=format&fit=crop&w=1920&q=80')] bg-cover bg-center opacity-10"></div>
        <div class="relative z-10 w-full max-w-md px-8 text-center reveal active">
            <span class="font-serif text-5xl md:text-6xl text-brand-caramel mb-6 block tracking-[0.25em]">ARANKA</span>
            <p class="text-white/60 text-xs tracking-[0.3em] uppercase mb-16 font-light">Diskrétní zóna</p>
            
            <div class="pwd-input-line w-full flex items-center mb-8 px-2 pb-2">
                <i data-lucide="lock" class="w-5 h-5 text-brand-caramel shrink-0"></i>
                <input type="password" id="site-password" class="w-full bg-transparent border-none text-white text-center text-lg tracking-[0.3em] focus:ring-0 placeholder-white/20 outline-none" placeholder="HESLO" onkeypress="if(event.key === 'Enter') checkPassword()">
            </div>
            
            <button onclick="checkPassword()" class="w-full bg-brand-caramel/90 backdrop-blur-md text-white hover:bg-white hover:text-brand-dark px-8 py-5 font-bold uppercase tracking-[0.2em] text-[0.75rem] rounded-full transition-all duration-500 shadow-glow">Vstoupit do rezidence</button>
            <p id="password-error" class="text-red-400 text-xs mt-6 opacity-0 transition-opacity font-medium tracking-widest">Neplatné heslo. Zkuste to prosím znovu.</p>
        </div>
    </div>

    <!-- Cookie Banner -->
    <div id="cookie-banner" class="bg-brand-dark text-white p-6 md:p-8 shadow-premium border-t border-brand-caramel/20">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center justify-between gap-6">
            <div class="text-sm font-light leading-relaxed max-w-3xl">
                <p class="mb-2"><strong class="font-serif text-brand-caramel tracking-widest text-base">Vážíme si vašeho soukromí</strong></p>
                K poskytování těch nejlepších služeb používáme my a naši partneři technologie, jako jsou soubory cookies. Vaše volba nám umožní vylepšovat náš web a nabídnout vám služby šité na míru. Svůj souhlas můžete kdykoliv změnit v nastavení.
            </div>
            <div class="flex flex-col sm:flex-row gap-3 w-full md:w-auto shrink-0">
                <button onclick="acceptCookies('all')" class="bg-brand-caramel text-white hover:bg-white hover:text-brand-dark px-6 py-3 text-xs font-bold uppercase tracking-widest rounded-full transition-colors shadow-glow whitespace-nowrap">Přijmout vše</button>
                <button onclick="acceptCookies('necessary')" class="bg-transparent border border-white/30 text-white hover:bg-white/10 px-6 py-3 text-xs font-bold uppercase tracking-widest rounded-full transition-colors whitespace-nowrap">Pouze nezbytné</button>
            </div>
        </div>
    </div>

    <!-- 2. NAVIGACE -->
    <header id="site-nav" class="fixed top-0 left-0 w-full z-50 py-5 px-6 flex justify-between items-center">
        <div class="max-w-7xl mx-auto w-full flex justify-between items-center">
            <a href="#" class="font-serif text-2xl md:text-3xl font-bold tracking-[0.25em] text-brand-dark hover:text-brand-caramel transition-colors" onclick="window.scrollTo({top:0, behavior:'smooth'})" aria-label="Zpět nahoru">ARANKA</a>
            <nav class="hidden lg:flex items-center gap-8" aria-label="Hlavní menu">
                <a href="#o-nas" class="text-[0.65rem] font-bold uppercase tracking-[0.2em] text-brand-dark hover:text-brand-caramel transition-colors">Příběh</a>
                <a href="#ubytovani" class="text-[0.65rem] font-bold uppercase tracking-[0.2em] text-brand-dark hover:text-brand-caramel transition-colors">Apartmány</a>
                <a href="#zahrada" class="text-[0.65rem] font-bold uppercase tracking-[0.2em] text-brand-dark hover:text-brand-caramel transition-colors">Zahrada</a>
                <a href="#hodnoceni" class="text-[0.65rem] font-bold uppercase tracking-[0.2em] text-brand-dark hover:text-brand-caramel transition-colors">Recenze</a>
                <button onclick="openBooking('all')" class="bg-brand-dark text-white px-8 py-3.5 rounded-full text-[0.65rem] font-bold uppercase tracking-[0.2em] hover:bg-brand-caramel transition-all shadow-lg hover:shadow-glow transform hover:-translate-y-0.5">Ověřit termín</button>
            </nav>
            <button class="lg:hidden text-brand-dark hover:text-brand-caramel transition-colors p-2" onclick="toggleMobileMenu()" aria-label="Otevřít menu"><i data-lucide="menu" class="w-8 h-8"></i></button>
        </div>
    </header>

    <nav id="mobile-menu" class="overlay flex-col space-y-10 text-center text-white bg-brand-dark/98 z-[5000]">
        <button onclick="toggleMobileMenu()" class="absolute top-8 right-8 text-white/50 hover:text-white transition-colors p-2" aria-label="Zavřít menu"><i data-lucide="x" class="w-10 h-10"></i></button>
        <span class="font-serif text-4xl text-brand-caramel mb-6 tracking-[0.4em]">ARANKA</span>
        <div class="w-12 h-px bg-brand-caramel/30 mb-6 mx-auto"></div>
        <a href="#o-nas" onclick="toggleMobileMenu()" class="text-lg font-serif tracking-[0.2em] hover:text-brand-caramel transition-colors">Náš Příběh</a>
        <a href="#ubytovani" onclick="toggleMobileMenu()" class="text-lg font-serif tracking-[0.2em] hover:text-brand-caramel transition-colors">Apartmány a studia</a>
        <a href="#zahrada" onclick="toggleMobileMenu()" class="text-lg font-serif tracking-[0.2em] hover:text-brand-caramel transition-colors">Zahrada & Galerie</a>
        <a href="#faq" onclick="toggleMobileMenu()" class="text-lg font-serif tracking-[0.2em] hover:text-brand-caramel transition-colors">Časté dotazy</a>
        <button onclick="openBooking('all'); toggleMobileMenu()" class="mt-10 bg-brand-caramel px-12 py-5 font-bold uppercase tracking-widest text-[0.8rem] rounded-full hover:bg-white hover:text-brand-dark transition-all shadow-glow">Rezervovat online</button>
    </nav>

    <!-- 3. MODÁLNÍ OKNA -->
    
    <!-- Lightbox pro galerii -->
    <div id="lightboxOverlay" class="overlay" role="dialog" aria-modal="true" aria-label="Prohlížeč obrázků">
        <button onclick="closeAllOverlays()" class="absolute top-6 right-6 text-white/50 hover:text-white z-[6000] p-2" aria-label="Zavřít galerii"><i data-lucide="x" class="w-10 h-10"></i></button>
        <div class="w-full max-w-7xl flex items-center justify-between relative text-white">
            <button onclick="prevImage()" class="p-4 bg-black/40 hover:bg-brand-caramel rounded-full transition-all backdrop-blur-sm transform hover:scale-110" aria-label="Předchozí obrázek"><i data-lucide="chevron-left" class="w-8 h-8"></i></button>
            <div class="flex-1 flex flex-col items-center justify-center px-4">
                <img id="lightboxImg" src="" class="max-w-full max-h-[85vh] object-contain rounded-xl shadow-2xl transition-opacity duration-300" alt="Detailní fotografie">
                <div class="mt-6 text-center">
                    <p id="lightboxCaption" class="font-serif tracking-[0.3em] uppercase text-sm mb-1 text-brand-caramel"></p>
                    <p id="lightboxCounter" class="text-white/40 text-xs tracking-widest font-bold"></p>
                </div>
            </div>
            <button onclick="nextImage()" class="p-4 bg-black/40 hover:bg-brand-caramel rounded-full transition-all backdrop-blur-sm transform hover:scale-110" aria-label="Další obrázek"><i data-lucide="chevron-right" class="w-8 h-8"></i></button>
        </div>
    </div>

    <!-- Pergola Info -->
    <div id="pergolaOverlay" class="overlay" role="dialog" aria-modal="true" aria-labelledby="pergola-title">
        <div class="modal-content max-w-2xl bg-white shadow-2xl relative border border-brand-sand">
            <button onclick="closeAllOverlays()" class="absolute top-6 right-6 text-brand-dark hover:text-brand-caramel transition-colors p-2" aria-label="Zavřít"><i data-lucide="x" class="w-8 h-8"></i></button>
            <div class="p-10 md:p-16 text-center border-t-4 border-brand-caramel">
                <div class="w-20 h-20 bg-brand-sand rounded-full flex items-center justify-center mx-auto mb-8 shadow-inner"><i data-lucide="leaf" class="w-10 h-10 text-brand-caramel"></i></div>
                <h3 id="pergola-title" class="font-serif text-3xl md:text-4xl mb-4 text-brand-dark">Exkluzivně pro hosty</h3>
                <p class="text-brand-muted mb-10 leading-relaxed font-light text-sm md:text-base">Zahrada a prosklená pergola s krbem jsou pečlivě udržovány a určeny výhradně pro ubytované hosty. Zaručujeme tak naprostý klid, ticho a soukromí po celou dobu Vašeho pobytu.</p>
                <div class="flex flex-col sm:flex-row gap-4 justify-center">
                    <button onclick="openBooking('all')" class="btn-premium px-10 py-4 rounded-full font-bold text-[0.7rem] uppercase tracking-widest">Rezervovat pobyt</button>
                    <button onclick="closeAllOverlays(); if(typeof Tawk_API !== 'undefined'){Tawk_API.maximize();}" class="btn-outline px-10 py-4 rounded-full font-bold text-[0.7rem] uppercase tracking-widest">Kontaktovat recepci</button>
                </div>
            </div>
        </div>
    </div>

    <!-- B2B Formulář -->
    <div id="b2bOverlay" class="overlay" role="dialog" aria-modal="true" aria-labelledby="b2b-title">
        <div class="modal-content max-w-4xl bg-white shadow-2xl flex flex-col border border-brand-sand relative">
            <div class="p-6 md:p-8 flex justify-between items-center border-b border-[#e5e0d8] bg-brand-light sticky top-0 z-10 rounded-t-20">
                <div class="flex items-center gap-4"><span id="b2b-title" class="font-serif text-xl md:text-2xl font-bold text-brand-dark tracking-wide">ARANKA <span class="text-brand-caramel font-light">CORPORATE</span></span></div>
                <button onclick="closeAllOverlays()" class="text-brand-dark hover:text-brand-caramel transition-colors p-2" aria-label="Zavřít formulář"><i data-lucide="x" class="w-6 h-6 md:w-8 md:h-8"></i></button>
            </div>
            <div class="p-6 md:p-12">
                <h3 class="font-serif text-2xl md:text-3xl mb-2 text-brand-dark">Specifikace ubytování</h3>
                <p class="text-sm text-brand-muted mb-8 font-light">Vyplňte prosím data pro vytvoření firemní nabídky na míru. Ozveme se Vám s přesnou kalkulací do 24 hodin.</p>
                
                <form id="b2bForm" onsubmit="submitB2BForm(event)" class="space-y-10">
                    <div class="space-y-4">
                        <p class="text-[0.65rem] font-bold uppercase text-brand-caramel tracking-[0.2em] border-b border-brand-sand pb-2">1. Kontaktní údaje</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 md:gap-8">
                            <div><label class="b2b-label" for="b2b-company">Firma / IČO *</label><input type="text" id="b2b-company" required class="b2b-field focus:border-brand-caramel" placeholder="Např. Stavo s.r.o."></div>
                            <div><label class="b2b-label" for="b2b-email">E-mail pro kalkulaci *</label><input type="email" id="b2b-email" required class="b2b-field focus:border-brand-caramel" placeholder="nakup@firma.cz"></div>
                            <div class="md:col-span-2"><label class="b2b-label" for="b2b-phone">Telefon</label><input type="tel" id="b2b-phone" class="b2b-field focus:border-brand-caramel" placeholder="+420 ..."></div>
                        </div>
                    </div>
                    
                    <div class="space-y-4">
                        <p class="text-[0.65rem] font-bold uppercase text-brand-caramel tracking-[0.2em] border-b border-brand-sand pb-2">2. Termín a kapacity</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 md:gap-8">
                            <div><label class="b2b-label" for="b2b-date">Nástup</label><input type="date" id="b2b-date" class="b2b-field text-brand-dark focus:border-brand-caramel"></div>
                            <div>
                                <label class="b2b-label" for="b2b-length">Délka pobytu</label>
                                <select id="b2b-length" class="b2b-field text-brand-dark cursor-pointer focus:border-brand-caramel">
                                    <option>Krátkodobě (do 14 dní)</option>
                                    <option>Střednědobě (1 – 3 měsíce)</option>
                                    <option>Dlouhodobě (3+ měsíců)</option>
                                </select>
                            </div>
                            <div><label class="b2b-label" for="b2b-persons">Počet osob</label><input type="number" id="b2b-persons" min="1" class="b2b-field focus:border-brand-caramel" placeholder="Např. 6"></div>
                            <div><label class="b2b-label" for="b2b-rooms">Počet pokojů</label><input type="number" id="b2b-rooms" min="1" class="b2b-field focus:border-brand-caramel" placeholder="Např. 2"></div>
                        </div>
                    </div>
                    
                    <div class="space-y-4">
                        <p class="text-[0.65rem] font-bold uppercase text-brand-caramel tracking-[0.2em] border-b border-brand-sand pb-2">3. Specifické požadavky</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 text-brand-dark">
                            <label class="flex items-center gap-4 bg-brand-sand/40 p-4 rounded-xl border border-transparent hover:border-brand-caramel/50 cursor-pointer transition-colors"><input type="checkbox" class="w-5 h-5 accent-brand-caramel rounded-sm"> <span class="text-sm font-medium">Oddělená lůžka (Twin)</span></label>
                            <label class="flex items-center gap-4 bg-brand-sand/40 p-4 rounded-xl border border-transparent hover:border-brand-caramel/50 cursor-pointer transition-colors"><input type="checkbox" class="w-5 h-5 accent-brand-caramel rounded-sm"> <span class="text-sm font-medium">Parkování nadrozměrných dodávek</span></label>
                            <label class="flex items-center gap-4 bg-brand-sand/40 p-4 rounded-xl border border-transparent hover:border-brand-caramel/50 cursor-pointer transition-colors md:col-span-2"><input type="checkbox" class="w-5 h-5 accent-brand-caramel rounded-sm"> <span class="text-sm font-medium">Pravidelný úklid a častější výměna prádla</span></label>
                        </div>
                        <div class="mt-4"><label class="b2b-label" for="b2b-note">Doplňující poznámka</label><textarea id="b2b-note" class="b2b-field h-20 resize-none focus:border-brand-caramel" placeholder="Specifikujte další detaily (např. preferovaný způsob fakturace)..."></textarea></div>
                    </div>
                    
                    <div class="pt-6 text-center">
                        <button type="submit" class="btn-premium px-12 py-5 rounded-full shadow-lg text-[0.75rem] uppercase tracking-widest font-bold w-full md:w-auto">Odeslat nezávaznou poptávku</button>
                        <p class="mt-5 text-brand-muted text-[0.65rem] uppercase tracking-widest font-bold flex items-center justify-center gap-2"><i data-lucide="shield-check" class="w-4 h-4 text-brand-caramel"></i> Jsme plátci DPH. Fakturujeme spolehlivě.</p>
                    </div>
                </form>
            </div>
        </div>
    </div>

    <!-- Trevlix Rezervace -->
    <div id="bookingOverlay" class="overlay" role="dialog" aria-modal="true" aria-label="Rezervační systém">
        <div class="modal-content max-w-6xl bg-brand-light shadow-2xl rounded-2xl overflow-hidden flex flex-col h-[90vh]">
            <div class="p-4 md:p-5 flex justify-between items-center border-b border-[#e5e0d8] bg-white shrink-0 shadow-sm z-10">
                <span class="font-serif text-xl md:text-2xl font-bold tracking-widest text-brand-dark">ARANKA <span class="text-brand-caramel font-light">RESERVE</span></span>
                <button onclick="closeAllOverlays()" class="flex items-center gap-2 text-brand-dark hover:text-brand-caramel font-bold uppercase text-[0.65rem] tracking-widest transition-colors p-2">Zavřít <i data-lucide="x" class="w-5 h-5 md:w-6 md:h-6"></i></button>
            </div>
            <div class="flex-1 relative bg-white">
                <iframe id="trevlixIframe" src="" loading="lazy" class="w-full h-full border-none" title="Rezervační formulář"></iframe>
            </div>
        </div>
    </div>

    <!-- 4. HLAVNÍ OBSAH -->
    <main>
        <!-- HERO -->
        <section class="relative w-full flex flex-col items-center justify-center min-h-screen bg-brand-dark overflow-hidden">
            <div class="hero-video-container">
                <!-- TODO [AGENTURA]: Nahradit iFrame za lokální MP4/WebM video pro lepší výkon na mobilu -->
                <video autoplay loop muted playsinline>
                    <source src="vase-video.mp4" type="video/mp4">
                    <!-- Záložní fallback pokud se nenačte video -->
                </video>
            </div>
            <div class="absolute inset-0 bg-gradient-to-b from-brand-dark/75 via-brand-dark/40 to-brand-dark/90 z-0"></div>
            
            <div class="relative z-10 w-full max-w-6xl mx-auto px-6 text-center pb-12 pt-24 flex flex-col items-center animate-fade-in">
                <span class="text-brand-caramel uppercase tracking-[0.4em] font-bold text-[0.65rem] mb-6 block animate-slide-up" style="animation-delay: 0.2s">Rezidence s historií</span>
                <h1 class="font-serif text-5xl md:text-7xl lg:text-[7.5rem] mb-6 tracking-[0.05em] text-white drop-shadow-2xl leading-tight animate-slide-up" style="animation-delay: 0.4s">Ubytování<br><span class="text-brand-caramel italic font-light">Aranka</span></h1>
                <p class="text-white/80 text-lg md:text-2xl font-light max-w-2xl mx-auto drop-shadow-md leading-relaxed mb-16 animate-slide-up" style="animation-delay: 0.6s">
                    Vaše prémiové útočiště v srdci Žatce. Spojení naprostého soukromí, moderního designu a rodinné pohostinnosti.
                </p>
                
                <nav aria-label="Rychlá navigace" class="flex flex-nowrap overflow-x-auto justify-start lg:justify-center items-center gap-3 w-full no-scrollbar snap-x px-2 pb-6 animate-slide-up" style="animation-delay: 0.8s">
                    <a href="#o-nas" class="snap-center shrink-0 px-8 py-4 rounded-full border border-white/20 bg-white/5 backdrop-blur-md text-[0.7rem] font-bold uppercase tracking-[0.2em] text-white hover:bg-brand-caramel hover:border-brand-caramel hover:shadow-glow transition-all duration-300">Příběh</a>
                    <a href="#ubytovani" class="snap-center shrink-0 px-8 py-4 rounded-full border border-white/20 bg-white/5 backdrop-blur-md text-[0.7rem] font-bold uppercase tracking-[0.2em] text-white hover:bg-brand-caramel hover:border-brand-caramel hover:shadow-glow transition-all duration-300">Pokoje</a>
                    <a href="#pro-firmy" class="snap-center shrink-0 px-8 py-4 rounded-full border border-white/20 bg-white/5 backdrop-blur-md text-[0.7rem] font-bold uppercase tracking-[0.2em] text-white hover:bg-brand-caramel hover:border-brand-caramel hover:shadow-glow transition-all duration-300">Pro firmy</a>
                    <button onclick="openBooking('all')" class="snap-center shrink-0 px-10 py-4 rounded-full border border-brand-caramel bg-brand-caramel text-white text-[0.7rem] font-bold uppercase tracking-[0.2em] hover:bg-white hover:text-brand-dark hover:border-white transition-all duration-300 shadow-glow ml-0 lg:ml-2 flex items-center gap-2">Rezervovat <i data-lucide="calendar" class="w-4 h-4"></i></button>
                </nav>
            </div>
            
            <a href="#o-nas" aria-label="Pokračovat dolů" class="absolute bottom-10 z-10 text-white/40 hover:text-brand-caramel transition-colors animate-bounce">
                <i data-lucide="chevron-down" class="w-10 h-10"></i>
            </a>
        </section>

        <!-- O NÁS PŘÍBĚH -->
        <section id="o-nas" class="py-24 md:py-32 bg-brand-light text-brand-dark relative border-b border-[#e5e0d8] overflow-hidden">
            <div class="absolute top-0 right-0 w-[600px] h-[600px] bg-brand-sand rounded-full blur-[120px] opacity-60 pointer-events-none -z-10 translate-x-1/3 -translate-y-1/3"></div>
            
            <div class="max-w-7xl mx-auto px-6 grid grid-cols-1 lg:grid-cols-2 gap-16 lg:gap-24 items-center">
                <div class="relative reveal">
                    <div class="aspect-[4/5] rounded-2xl overflow-hidden shadow-premium relative">
                        <img src="https://images.unsplash.com/photo-1600210492486-724fe5c67fb0?auto=format&fit=crop&w=1000&q=80" class="w-full h-full object-cover hover:scale-105 transition-transform duration-1000" alt="Zahrada ubytování Aranka s pergolou" loading="lazy">
                    </div>
                    <div class="absolute -bottom-8 -right-8 bg-brand-caramel text-white p-8 shadow-xl rounded-2xl text-center hidden md:block transform hover:-translate-y-2 transition-transform duration-500">
                        <span class="font-serif text-5xl font-bold block mb-2">2007</span>
                        <span class="text-[0.65rem] uppercase tracking-widest font-bold">Založení tradice</span>
                    </div>
                </div>
                <div class="reveal lg:pl-4">
                    <span class="text-brand-caramel uppercase tracking-[0.3em] font-bold text-[0.65rem] mb-4 block flex items-center gap-3">
                        <div class="w-8 h-px bg-brand-caramel"></div> Náš příběh
                    </span>
                    <h2 class="font-serif text-4xl md:text-5xl mb-8 leading-tight text-brand-dark">Více než ubytování.<br>Pocit, že jste opravdu vítáni.</h2>
                    <div class="space-y-6 text-brand-text text-base font-light leading-relaxed mb-10 text-justify">
                        <p><strong>Aranka je rodinný projekt, který staví na osobním přístupu.</strong> Už od roku 2007 budujeme v podhradí královského města Žatce místo, kde se snoubí moderní design s domáckou atmosférou. Každý pokoj prošel našima rukama a nese v sobě kus naší vášně pro detail.</p>
                        <p>Naším cílem nikdy nebylo vybudovat obří hotel. Chtěli jsme vytvořit klidné útočiště – oázu s privátní zahradou, kam se hosté budou rádi a s důvěrou vracet. Ať už přijíždíte za romantikou, rodinným výletem do památek UNESCO, nebo pracovně, Aranka je připravena poskytnout Vám dokonalé zázemí.</p>
                    </div>
                    
                    <div class="grid grid-cols-2 gap-8 border-t border-[#e5e0d8] pt-8 mt-8">
                        <div class="flex gap-4 items-start">
                            <i data-lucide="key" class="w-6 h-6 text-brand-caramel shrink-0 mt-1"></i>
                            <div><strong class="block text-brand-dark font-serif text-lg mb-1">Naprosté soukromí</strong><span class="text-xs text-brand-muted font-light leading-relaxed block">Diskrétní přístup a tichá lokalita</span></div>
                        </div>
                        <div class="flex gap-4 items-start">
                            <i data-lucide="sparkles" class="w-6 h-6 text-brand-caramel shrink-0 mt-1"></i>
                            <div><strong class="block text-brand-dark font-serif text-lg mb-1">Prémiová čistota</strong><span class="text-xs text-brand-muted font-light leading-relaxed block">Standardy, ze kterých neslevujeme</span></div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- SLUŽBY V KOSTCE (Přehled vybavení) -->
        <section class="py-16 bg-white border-b border-[#e5e0d8] relative z-20">
            <div class="max-w-7xl mx-auto px-6">
                <div class="grid grid-cols-2 md:grid-cols-4 gap-8 text-center reveal">
                    <div class="flex flex-col items-center">
                        <div class="w-16 h-16 rounded-full bg-brand-sand flex items-center justify-center mb-4 text-brand-caramel transition-transform hover:scale-110 duration-300"><i data-lucide="wifi" class="w-7 h-7"></i></div>
                        <h4 class="font-serif text-base text-brand-dark mb-1 font-bold">Rychlá Wi-Fi</h4>
                        <p class="text-xs text-brand-muted font-light">Zdarma v celém areálu</p>
                    </div>
                    <div class="flex flex-col items-center">
                        <div class="w-16 h-16 rounded-full bg-brand-sand flex items-center justify-center mb-4 text-brand-caramel transition-transform hover:scale-110 duration-300"><i data-lucide="car" class="w-7 h-7"></i></div>
                        <h4 class="font-serif text-base text-brand-dark mb-1 font-bold">Parkování</h4>
                        <p class="text-xs text-brand-muted font-light">Bezpečně zajištěno</p>
                    </div>
                    <div class="flex flex-col items-center">
                        <div class="w-16 h-16 rounded-full bg-brand-sand flex items-center justify-center mb-4 text-brand-caramel transition-transform hover:scale-110 duration-300"><i data-lucide="coffee" class="w-7 h-7"></i></div>
                        <h4 class="font-serif text-base text-brand-dark mb-1 font-bold">Vlastní kuchyňka</h4>
                        <p class="text-xs text-brand-muted font-light">Plně vybavená pro Vás</p>
                    </div>
                    <div class="flex flex-col items-center">
                        <div class="w-16 h-16 rounded-full bg-brand-sand flex items-center justify-center mb-4 text-brand-caramel transition-transform hover:scale-110 duration-300"><i data-lucide="smartphone" class="w-7 h-7"></i></div>
                        <h4 class="font-serif text-base text-brand-dark mb-1 font-bold">Smart Check-in</h4>
                        <p class="text-xs text-brand-muted font-light">Pohodlně a bezkontaktně</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- SJEDNOCENÁ SEKCE: APARTMÁNY A STUDIA (Zjednodušený filtr + Karty) -->
        <section id="ubytovani" class="pt-24 pb-32 bg-brand-sand text-brand-dark border-b border-[#e5e0d8] relative z-10">
            <div class="max-w-7xl mx-auto px-6 w-full">
                
                <div class="mb-16 text-center reveal">
                    <span class="text-brand-caramel uppercase tracking-[0.3em] font-bold text-[0.65rem] mb-4 block">Ubytování na míru</span>
                    <h2 class="font-serif text-4xl md:text-5xl lg:text-6xl tracking-tight text-brand-dark">Naše apartmány & studia</h2>
                </div>

                <!-- 1. CHYTRÝ FILTR ZJEDNODUŠENÝ -->
                <div class="bg-brand-dark rounded-[2rem] shadow-premium-hover p-8 md:p-12 mb-20 reveal relative overflow-hidden text-white border border-[#332e2a]">
                    <div class="absolute top-[-30%] right-[-20%] w-[600px] h-[600px] bg-brand-caramel/15 blur-[120px] rounded-full pointer-events-none"></div>
                    
                    <div class="relative z-10">
                        <div class="text-center mb-10">
                            <h3 class="font-serif text-2xl md:text-3xl text-white mb-2">Najděte svůj ideální prostor</h3>
                            <p class="text-white/60 font-light text-sm max-w-xl mx-auto">Vyberte pouze termín a pro kolik osob pokoj hledáte. O zbytek se postaráme.</p>
                        </div>
                        
                        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-x-8 gap-y-8 items-end text-left mb-10 bg-white/5 p-6 rounded-2xl border border-white/10 max-w-4xl mx-auto">
                            
                            <!-- Příjezd -->
                            <div class="border-b border-white/20 pb-2 relative">
                                <label for="filter-checkin" class="block text-[0.6rem] font-bold uppercase tracking-[0.2em] text-brand-caramel mb-2">Příjezd</label>
                                <input type="date" id="filter-checkin" class="filter-input w-full font-serif text-lg appearance-none cursor-pointer bg-transparent">
                            </div>

                            <!-- Odjezd -->
                            <div class="border-b border-white/20 pb-2 relative">
                                <label for="filter-checkout" class="block text-[0.6rem] font-bold uppercase tracking-[0.2em] text-brand-caramel mb-2">Odjezd</label>
                                <input type="date" id="filter-checkout" class="filter-input w-full font-serif text-lg appearance-none cursor-pointer bg-transparent">
                            </div>

                            <!-- ÚPRAVA UX: Zvětšeny tap targets (w-11 h-11) pro tlačítka + a - pro lepší ovládání na mobilu -->
                            <!-- Osoby -->
                            <div class="border-b border-white/20 pb-2">
                                <label class="block text-[0.6rem] font-bold uppercase tracking-[0.2em] text-brand-caramel mb-2">Hosté</label>
                                <div class="flex items-center justify-between pb-1">
                                    <button onclick="updatePeople(-1)" class="w-11 h-11 rounded-full border border-white/30 text-white flex items-center justify-center hover:bg-brand-caramel hover:border-brand-caramel transition-all" aria-label="Odebrat osobu"><i data-lucide="minus" class="w-5 h-5"></i></button>
                                    <span id="people-val" class="font-serif text-xl font-medium" aria-live="polite">2</span>
                                    <button onclick="updatePeople(1)" class="w-11 h-11 rounded-full border border-white/30 text-white flex items-center justify-center hover:bg-brand-caramel hover:border-brand-caramel transition-all" aria-label="Přidat osobu"><i data-lucide="plus" class="w-5 h-5"></i></button>
                                </div>
                            </div>

                            <!-- Pokoje -->
                            <div class="border-b border-white/20 pb-2">
                                <label class="block text-[0.6rem] font-bold uppercase tracking-[0.2em] text-brand-caramel mb-2">Pokoje</label>
                                <div class="flex items-center justify-between pb-1">
                                    <button onclick="updateRooms(-1)" class="w-11 h-11 rounded-full border border-white/30 text-white flex items-center justify-center hover:bg-brand-caramel hover:border-brand-caramel transition-all" aria-label="Odebrat pokoj"><i data-lucide="minus" class="w-5 h-5"></i></button>
                                    <span id="rooms-val" class="font-serif text-xl font-medium" aria-live="polite">1</span>
                                    <button onclick="updateRooms(1)" class="w-11 h-11 rounded-full border border-white/30 text-white flex items-center justify-center hover:bg-brand-caramel hover:border-brand-caramel transition-all" aria-label="Přidat pokoj"><i data-lucide="plus" class="w-5 h-5"></i></button>
                                </div>
                            </div>
                        </div>
                        
                        <div class="text-center">
                            <button onclick="runSmartFilter()" class="bg-brand-caramel text-white hover:bg-white hover:text-brand-dark px-12 py-4 text-[0.75rem] font-bold uppercase tracking-[0.2em] rounded-full shadow-glow transition-all duration-300 w-full sm:w-auto transform hover:-translate-y-1 flex items-center justify-center mx-auto gap-2">
                                <i data-lucide="search" class="w-4 h-4"></i> Najít ubytování
                            </button>
                        </div>

                        <div id="filter-results" class="hidden mt-10 pt-10 border-t border-white/10" aria-live="polite"></div>
                    </div>
                </div>

                <!-- 2. KARTY KATEGORIÍ (Fallback) -->
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 lg:gap-8">
                    <div onclick="openBooking('8308,8310,8311,8312,8313,8314,8315,8316,8317,8318')" class="mood-card reveal group" role="button" tabindex="0" aria-label="Zobrazit nadstandardní mezonety">
                        <img src="https://images.unsplash.com/photo-1600596542815-ffad4c1539a9?auto=format&fit=crop&w=800&q=80" alt="Luxusní interiér prémiového mezonetu" loading="lazy">
                        <div class="card-gradient"></div>
                        <div class="absolute top-6 left-6 bg-brand-dark/80 backdrop-blur-md text-brand-caramel text-[0.6rem] uppercase tracking-widest px-4 py-2 rounded-full border border-brand-caramel/30 z-20 font-bold shadow-lg">Větší prostor</div>
                        <div class="absolute bottom-0 left-0 p-8 w-full z-10 text-white card-content">
                            <h3 class="font-serif text-3xl mb-2">Nadstandardní mezonety</h3>
                            <p class="text-sm text-[#d8d3ca] font-light mb-6">Velkorysý prostor a maximální pohodlí s vlastní terasou.</p>
                            <span class="inline-flex items-center gap-2 text-brand-caramel text-[0.7rem] font-bold uppercase tracking-widest group-hover:text-white transition-colors">Prozkoumat <i data-lucide="arrow-right" class="w-4 h-4"></i></span>
                        </div>
                    </div>
                    
                    <div onclick="openBooking('8301,8302,8303,8306,8307,8309')" class="mood-card reveal delay-100 group" role="button" tabindex="0" aria-label="Zobrazit vybavená studia">
                        <img src="https://images.unsplash.com/photo-1522708323590-d24dbb6b0267?auto=format&fit=crop&w=800&q=80" alt="Světlý pokoj s kuchyňkou" loading="lazy">
                        <div class="card-gradient"></div>
                        <div class="absolute bottom-0 left-0 p-8 w-full z-10 text-white card-content">
                            <h3 class="font-serif text-3xl mb-2">Vybavená studia</h3>
                            <p class="text-sm text-[#d8d3ca] font-light mb-6">Naprosté soukromí a pohodlí s plnohodnotnou kuchyňkou.</p>
                            <span class="inline-flex items-center gap-2 text-brand-caramel text-[0.7rem] font-bold uppercase tracking-widest group-hover:text-white transition-colors">Prozkoumat <i data-lucide="arrow-right" class="w-4 h-4"></i></span>
                        </div>
                    </div>
                    
                    <div onclick="openBooking('8300,8304,8305')" class="mood-card reveal delay-200 group" role="button" tabindex="0" aria-label="Zobrazit praktické pokoje">
                        <img src="https://images.unsplash.com/photo-1631049307264-da0ec9d70304?auto=format&fit=crop&w=800&q=80" alt="Útulný praktický pokoj" loading="lazy">
                        <div class="card-gradient"></div>
                        <div class="absolute bottom-0 left-0 p-8 w-full z-10 text-white card-content">
                            <h3 class="font-serif text-3xl mb-2">Praktické pokoje</h3>
                            <p class="text-sm text-[#d8d3ca] font-light mb-6 italic">Chytrá a útulná volba pro nenáročné cestovatele.</p>
                            <span class="inline-flex items-center gap-2 text-brand-caramel text-[0.7rem] font-bold uppercase tracking-widest group-hover:text-white transition-colors">Prozkoumat <i data-lucide="arrow-right" class="w-4 h-4"></i></span>
                        </div>
                    </div>
                </div>

                <!-- Tematická grafika pod apartmány -->
                <div class="mt-16 md:mt-24 relative rounded-3xl overflow-hidden aspect-[21/9] md:aspect-[21/6] reveal shadow-premium group">
                    <img src="https://images.unsplash.com/photo-1499955085172-a104c9463ece?auto=format&fit=crop&w=1600&q=80" alt="Pohodlný detail ložnice" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-1000" loading="lazy">
                    <div class="absolute inset-0 bg-brand-dark/40 transition-colors duration-500 group-hover:bg-brand-dark/50"></div>
                    <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-6">
                        <span class="font-serif text-3xl md:text-5xl text-white drop-shadow-lg tracking-wide mb-3">Váš druhý domov</span>
                        <span class="text-brand-caramel italic text-lg md:text-2xl font-light drop-shadow-md">Klid a péče, kterou si zasloužíte</span>
                    </div>
                </div>

            </div>
        </section>

        <!-- B2B FIREMNÍ ZÓNA -->
        <section id="pro-firmy" class="w-full min-h-screen flex flex-col justify-center bg-brand-dark text-white relative py-24 lg:py-32 overflow-hidden">
            <div class="absolute inset-0 z-0 opacity-15 mix-blend-luminosity bg-fixed bg-center bg-cover" style="background-image: url('https://images.unsplash.com/photo-1497366216548-37526070297c?auto=format&fit=crop&w=2560&q=80');"></div>
            <div class="absolute inset-0 bg-gradient-to-t from-brand-dark via-brand-dark/90 to-brand-dark/50 z-0"></div>
            
            <!-- ÚPRAVA COPY: Přidána zmínka o průmyslové zóně Triangle -->
            <div class="max-w-6xl mx-auto px-6 w-full relative z-10 text-center reveal">
                <span class="text-brand-caramel uppercase tracking-[0.5em] font-bold text-[0.7rem] mb-6 block">Corporate & B2B</span>
                <h2 class="font-serif text-5xl md:text-7xl mb-8 leading-tight text-white drop-shadow-lg">Hladká spolupráce.<br><span class="italic font-light text-brand-caramel">Spokojený tým.</span></h2>
                <p class="text-white/70 text-lg md:text-xl font-light leading-relaxed max-w-2xl mx-auto mb-16">
                    Poskytujeme více než jen postel. Nabízíme stabilní a plně vybavené zázemí pro Vaše zaměstnance na cestách. Díky strategické poloze blízko <strong>průmyslové zóny Triangle</strong> jsme ideálním výchozím bodem. Od první poptávky až po odjezd se postaráme o to, aby vše běželo hladce.
                </p>
                
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 md:gap-8 mb-16 text-left">
                    <div class="bg-white/5 backdrop-blur-md p-8 rounded-2xl border border-white/10 hover:border-brand-caramel/50 transition-colors hover:-translate-y-1 transform duration-300">
                        <i data-lucide="zap" class="w-8 h-8 text-brand-caramel mb-5"></i>
                        <h4 class="font-serif text-xl mb-3 text-white">Rychlost reakce</h4>
                        <p class="text-sm text-white/60 font-light leading-relaxed">Vypracování nabídky na míru garantujeme do 24 hodin. Zakládáme si na přímém a rychlém jednání bez zbytečných prostředníků.</p>
                    </div>
                    <div class="bg-white/5 backdrop-blur-md p-8 rounded-2xl border border-white/10 hover:border-brand-caramel/50 transition-colors hover:-translate-y-1 transform duration-300">
                        <i data-lucide="file-text" class="w-8 h-8 text-brand-caramel mb-5"></i>
                        <h4 class="font-serif text-xl mb-3 text-white">Bez administrativy</h4>
                        <p class="text-sm text-white/60 font-light leading-relaxed">Jsme plátci DPH. Zajistíme spolehlivou fakturaci s požadovanými náležitostmi přesně podle zvyklostí Vašeho účetního oddělení.</p>
                    </div>
                    <div class="bg-white/5 backdrop-blur-md p-8 rounded-2xl border border-white/10 hover:border-brand-caramel/50 transition-colors hover:-translate-y-1 transform duration-300">
                        <i data-lucide="washing-machine" class="w-8 h-8 text-brand-caramel mb-5"></i>
                        <h4 class="font-serif text-xl mb-3 text-white">Plný servis</h4>
                        <p class="text-sm text-white/60 font-light leading-relaxed">Vybrané byty disponují vlastní pračkou a oddělenými lůžky (Twin). Bezproblémové parkování dodávek je u nás samozřejmostí.</p>
                    </div>
                </div>

                <button onclick="openOverlay('b2bOverlay')" class="bg-brand-caramel text-white hover:bg-white hover:text-brand-dark transition-all duration-300 px-12 py-5 rounded-full font-bold uppercase tracking-[0.2em] text-[0.8rem] shadow-glow flex items-center justify-center gap-3 mx-auto">
                    Vstoupit do B2B Zóny <i data-lucide="arrow-right" class="w-4 h-4"></i>
                </button>
                
                <div class="border-t border-white/10 pt-12 mt-20 max-w-4xl mx-auto">
                    <p class="text-[0.6rem] uppercase tracking-[0.4em] text-white/30 font-bold mb-8">Dlouhodobě nám důvěřují stabilní partneři</p>
                    <div class="flex flex-wrap justify-center gap-x-12 gap-y-8 opacity-50 text-white text-sm font-serif tracking-widest grayscale hover:grayscale-0 transition-all duration-500">
                        <span class="flex items-center gap-2"><i data-lucide="briefcase" class="w-5 h-5"></i> PPA ENERGO</span>
                        <span class="flex items-center gap-2"><i data-lucide="settings" class="w-5 h-5"></i> M-Tech & Auto</span>
                        <span class="flex items-center gap-2"><i data-lucide="hard-hat" class="w-5 h-5"></i> Freyssinet</span>
                        <span class="flex items-center gap-2"><i data-lucide="factory" class="w-5 h-5"></i> HAKU</span>
                        <span class="flex items-center gap-2"><i data-lucide="truck" class="w-5 h-5"></i> POZIS BAU</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- ZAHRADA A PERGOLA -->
        <section id="zahrada" class="py-24 bg-brand-light relative border-b border-[#e5e0d8]">
            <div class="max-w-7xl mx-auto px-6 grid grid-cols-1 lg:grid-cols-2 gap-12 lg:gap-24 items-center">
                <div class="reveal lg:order-2">
                    <span class="text-brand-caramel uppercase tracking-[0.4em] font-bold text-[0.65rem] mb-4 block italic flex items-center gap-2"><i data-lucide="shield" class="w-4 h-4"></i> Vaše bezpečí a klid</span>
                    <h2 class="font-serif text-4xl md:text-5xl tracking-tight text-brand-dark mb-6">Zahrada & Pergola</h2>
                    <p class="text-brand-muted text-lg leading-relaxed font-light mb-8 text-justify">
                        Skutečný úkryt před okolním světem. Vytvořili jsme pro Vás soukromou oázu s pečlivě udržovanou zelení, venkovním posezením a prosklenou pergolou s krbem pro dokonalou relaxaci po náročném dni. 
                    </p>
                    <p class="text-brand-dark text-sm font-medium mb-10 pl-4 border-l-2 border-brand-caramel">Tento prostor je vyhrazen striktně a exkluzivně pouze pro naše ubytované hosty.</p>
                    <button onclick="openOverlay('pergolaOverlay')" class="btn-outline px-10 py-4 rounded-full font-bold uppercase tracking-widest text-[0.7rem] hover:shadow-glow">Objevit více</button>
                </div>
                
                <div class="reveal relative rounded-2xl overflow-hidden shadow-premium aspect-square md:aspect-video lg:aspect-[4/3] bg-brand-dark lg:order-1 group">
                    <img src="https://images.unsplash.com/photo-1558438832-57ee02164d1f?auto=format&fit=crop&w=1200&q=80" alt="Klidná prosklená pergola s výhledem do zahrady" class="absolute inset-0 w-full h-full object-cover group-hover:scale-105 transition-transform duration-1000" loading="lazy">
                    <div class="absolute inset-0 bg-brand-dark/20 group-hover:bg-transparent transition-colors duration-500"></div>
                </div>
            </div>
        </section>

        <!-- GALERIE -->
        <section id="galerie" class="py-24 bg-white border-t border-[#e5e0d8] overflow-hidden">
            <div class="max-w-7xl mx-auto px-6 mb-12 flex flex-col md:flex-row justify-between items-end reveal">
                <div>
                    <span class="text-brand-caramel uppercase tracking-[0.3em] font-bold text-[0.65rem] mb-3 block">Prohlídka areálu</span>
                    <h3 class="font-serif text-4xl text-brand-dark">Galerie Fotografií</h3>
                </div>
                <div class="flex gap-4 mt-6 md:mt-0">
                    <button onclick="scrollSlider(-400)" class="p-4 border border-[#e5e0d8] rounded-full text-brand-dark hover:bg-brand-caramel hover:text-white hover:border-brand-caramel transition-all shadow-sm" aria-label="Posunout galerii vlevo"><i data-lucide="arrow-left" class="w-5 h-5"></i></button>
                    <button onclick="scrollSlider(400)" class="p-4 border border-[#e5e0d8] rounded-full text-brand-dark hover:bg-brand-caramel hover:text-white hover:border-brand-caramel transition-all shadow-sm" aria-label="Posunout galerii vpravo"><i data-lucide="arrow-right" class="w-5 h-5"></i></button>
                </div>
            </div>
            
            <div class="w-full reveal">
                <!-- Posuvný pruh -->
                <div id="garden-slider" class="slider-container px-6 xl:px-[calc((100vw-1280px)/2+24px)] pb-12 pt-4">
                    <div class="slider-item group" onclick="openLightbox(0)">
                        <img src="https://images.unsplash.com/photo-1596243169804-245c117e33f3?auto=format&fit=crop&w=800&q=80" alt="Prostorná zahrada ubytování" loading="lazy">
                        <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center"><i data-lucide="maximize-2" class="w-8 h-8 text-white"></i></div>
                    </div>
                    <div class="slider-item group" onclick="openLightbox(1)">
                        <img src="https://images.unsplash.com/photo-1510798831971-661eb04b3739?auto=format&fit=crop&w=800&q=80" alt="Relaxační zóna s křesílky" loading="lazy">
                        <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center"><i data-lucide="maximize-2" class="w-8 h-8 text-white"></i></div>
                    </div>
                    <div class="slider-item group" onclick="openLightbox(2)">
                        <img src="https://images.unsplash.com/photo-1523306401731-238f0317f240?auto=format&fit=crop&w=800&q=80" alt="Slunná privátní terasa" loading="lazy">
                        <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center"><i data-lucide="maximize-2" class="w-8 h-8 text-white"></i></div>
                    </div>
                    <div class="slider-item group" onclick="openLightbox(3)">
                        <img src="https://images.unsplash.com/photo-1558438832-57ee02164d1f?auto=format&fit=crop&w=800&q=80" alt="Detail prosklené pergoly" loading="lazy">
                        <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center"><i data-lucide="maximize-2" class="w-8 h-8 text-white"></i></div>
                    </div>
                    <div class="slider-item group" onclick="openLightbox(4)">
                        <img src="https://images.unsplash.com/photo-1512917774080-9991f1c4c750?auto=format&fit=crop&w=800&q=80" alt="Moderní interiér apartmánu" loading="lazy">
                        <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center"><i data-lucide="maximize-2" class="w-8 h-8 text-white"></i></div>
                    </div>
                    <div class="slider-item group" onclick="openLightbox(5)">
                        <img src="https://images.unsplash.com/photo-1502672260266-1c1ef2d93688?auto=format&fit=crop&w=800&q=80" alt="Komfortní ložnice" loading="lazy">
                        <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center"><i data-lucide="maximize-2" class="w-8 h-8 text-white"></i></div>
                    </div>
                    <div class="slider-item group" onclick="openLightbox(6)">
                        <img src="https://images.unsplash.com/photo-1473448912268-2022ce9509d8?auto=format&fit=crop&w=800&q=80" alt="Jídelní kout" loading="lazy">
                        <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center"><i data-lucide="maximize-2" class="w-8 h-8 text-white"></i></div>
                    </div>
                    <div class="slider-item group" onclick="openLightbox(7)">
                        <img src="https://images.unsplash.com/photo-1600210491892-03d54c0aaf87?auto=format&fit=crop&w=800&q=80" alt="Čistá a moderní koupelna" loading="lazy">
                        <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center"><i data-lucide="maximize-2" class="w-8 h-8 text-white"></i></div>
                    </div>
                </div>
            </div>
        </section>

        <!-- HODNOCENÍ HOSTŮ (Social Proof) -->
        <section id="hodnoceni" class="py-24 bg-brand-light text-center border-t border-[#e5e0d8]">
             <div class="max-w-7xl mx-auto px-6 reveal">
                 <span class="text-brand-caramel uppercase tracking-[0.3em] font-bold text-[0.65rem] mb-4 block">Co o nás říkají klienti</span>
                 <h2 class="font-serif text-4xl md:text-5xl tracking-tight text-brand-dark mb-16">Hodnocení hostů</h2>
                 
                 <div class="grid grid-cols-1 md:grid-cols-3 gap-8 text-left">
                     <!-- Recenze 1 -->
                     <div class="bg-white p-8 rounded-3xl shadow-premium border border-[#e5e0d8] flex flex-col justify-between hover:-translate-y-2 transition-transform duration-300">
                         <div>
                             <div class="flex text-brand-caramel mb-5">
                                 <i data-lucide="star" class="w-4 h-4 fill-current"></i><i data-lucide="star" class="w-4 h-4 fill-current"></i><i data-lucide="star" class="w-4 h-4 fill-current"></i><i data-lucide="star" class="w-4 h-4 fill-current"></i><i data-lucide="star" class="w-4 h-4 fill-current"></i>
                             </div>
                             <p class="text-brand-text font-light italic mb-6 leading-relaxed">„Naprosto kouzelné místo! Čistota na jedničku, krásně vybavená kuchyňka a ten klid v zahradě... Určitě se s rodinou brzy vrátíme.“</p>
                         </div>
                         <div class="flex items-center gap-4 border-t border-brand-sand pt-4">
                             <div class="w-10 h-10 rounded-full bg-brand-sand flex items-center justify-center text-brand-caramel font-serif font-bold">M</div>
                             <div>
                                 <strong class="block text-brand-dark text-sm">Martina N.</strong>
                                 <span class="text-xs text-brand-muted">Ověřený host (Google)</span>
                             </div>
                         </div>
                     </div>
                     <!-- Recenze 2 -->
                     <div class="bg-white p-8 rounded-3xl shadow-premium border border-[#e5e0d8] flex flex-col justify-between hover:-translate-y-2 transition-transform duration-300">
                         <div>
                             <div class="flex text-brand-caramel mb-5">
                                 <i data-lucide="star" class="w-4 h-4 fill-current"></i><i data-lucide="star" class="w-4 h-4 fill-current"></i><i data-lucide="star" class="w-4 h-4 fill-current"></i><i data-lucide="star" class="w-4 h-4 fill-current"></i><i data-lucide="star" class="w-4 h-4 fill-current"></i>
                             </div>
                             <p class="text-brand-text font-light italic mb-6 leading-relaxed">„Zajišťovali jsme zde ubytování pro naše zaměstnance na delší dobu. Vše proběhlo bez problému, fakturace i komunikace perfektní.“</p>
                         </div>
                         <div class="flex items-center gap-4 border-t border-brand-sand pt-4">
                             <div class="w-10 h-10 rounded-full bg-brand-sand flex items-center justify-center text-brand-caramel font-serif font-bold">P</div>
                             <div>
                                 <strong class="block text-brand-dark text-sm">Petr S.</strong>
                                 <span class="text-xs text-brand-muted">Firemní klient</span>
                             </div>
                         </div>
                     </div>
                     <!-- Recenze 3 -->
                     <div class="bg-white p-8 rounded-3xl shadow-premium border border-[#e5e0d8] flex flex-col justify-between hover:-translate-y-2 transition-transform duration-300">
                         <div>
                             <div class="flex text-brand-caramel mb-5">
                                 <i data-lucide="star" class="w-4 h-4 fill-current"></i><i data-lucide="star" class="w-4 h-4 fill-current"></i><i data-lucide="star" class="w-4 h-4 fill-current"></i><i data-lucide="star" class="w-4 h-4 fill-current"></i><i data-lucide="star" class="w-4 h-4 fill-current"></i>
                             </div>
                             <p class="text-brand-text font-light italic mb-6 leading-relaxed">„Krásný a nadstandardní mezonet! Obrovskou výhodou je chytrý check-in a vyhrazené parkování. Kousek do centra Žatce.“</p>
                         </div>
                         <div class="flex items-center gap-4 border-t border-brand-sand pt-4">
                             <div class="w-10 h-10 rounded-full bg-brand-sand flex items-center justify-center text-brand-caramel font-serif font-bold">J</div>
                             <div>
                                 <strong class="block text-brand-dark text-sm">Jana K.</strong>
                                 <span class="text-xs text-brand-muted">Ověřený host (Booking)</span>
                             </div>
                         </div>
                     </div>
                 </div>
             </div>
        </section>

        <!-- AI PLANNER -->
        <section id="ai-planner" class="py-24 bg-brand-sand text-center border-t border-[#e5e0d8]">
            <div class="max-w-4xl mx-auto px-6 relative z-10 reveal">
                <div class="w-20 h-20 bg-white rounded-full flex items-center justify-center mx-auto mb-8 shadow-sm border border-[#e5e0d8]"><i data-lucide="sparkles" class="w-8 h-8 text-brand-caramel"></i></div>
                <h2 class="font-serif text-4xl md:text-5xl mb-4 text-brand-dark tracking-tighter">Zažijte Žatec jako místní</h2>
                <p class="text-brand-text mb-12 text-lg font-light max-w-2xl mx-auto">Vyberte si charakter Vaší cesty a naše AI recepční Vám obratem sestaví osobní doporučení, jak si pobyt u nás užít naplno.</p>
                
                <div class="bg-white p-8 md:p-12 rounded-[2rem] shadow-xl border border-[#e5e0d8] text-left max-w-3xl mx-auto relative overflow-hidden">
                    <div class="absolute top-0 right-0 w-32 h-32 bg-brand-sand rounded-full blur-3xl opacity-50"></div>
                    <div class="relative z-10">
                        <div class="flex flex-col sm:flex-row gap-6 items-end">
                            <div class="flex-grow w-full relative">
                                <label for="ai-who-footer" class="block text-[0.65rem] font-bold uppercase tracking-[0.2em] mb-3 text-brand-caramel">Kdo s Vámi cestuje?</label>
                                <select id="ai-who-footer" class="w-full bg-brand-sand/30 border border-[#e5e0d8] rounded-xl p-4 outline-none text-brand-dark text-base font-medium focus:border-brand-caramel focus:ring-1 focus:ring-brand-caramel transition-all cursor-pointer appearance-none">
                                    <option value="pár">Romantický únik ve dvou</option>
                                    <option value="rodina">Aktivní výlet s rodinou a dětmi</option>
                                    <option value="cyklista">Sportovní víkend na kolech</option>
                                    <option value="pracovník">Čistě pracovní záležitosti</option>
                                </select>
                                <i data-lucide="chevron-down" class="absolute right-4 bottom-4 w-5 h-5 text-brand-muted pointer-events-none"></i>
                            </div>
                            <button onclick="generateItinerary()" class="btn-premium w-full sm:w-auto px-10 py-4 rounded-xl shadow-md uppercase tracking-widest text-[0.7rem] font-bold">Inspirujte mě</button>
                        </div>

                        <div id="ai-result-container" class="hidden mt-10 pt-8 border-t border-[#e5e0d8]" aria-live="polite">
                            <div id="ai-loading" class="hidden flex-col items-center justify-center py-10">
                                <i data-lucide="loader-2" class="w-10 h-10 text-brand-caramel animate-spin mb-4"></i>
                                <span class="text-xs text-brand-muted uppercase tracking-[0.3em] font-bold">Připravuji Váš plán...</span>
                            </div>
                            <div id="ai-result" class="prose prose-brand font-light text-brand-dark leading-relaxed text-lg italic border-l-4 border-brand-caramel pl-6"></div>
                        </div>
                    </div>
                </div>

                <!-- Tematická grafika pod AI Plannerem -->
                <div class="mt-16 max-w-5xl mx-auto relative rounded-3xl overflow-hidden aspect-[16/9] md:aspect-[21/7] reveal shadow-premium group">
                    <img src="https://images.unsplash.com/photo-1555396273-367ea4eb4db5?auto=format&fit=crop&w=1600&q=80" alt="Atmosféra města a kaváren" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-1000" loading="lazy">
                    <div class="absolute inset-0 bg-gradient-to-t from-brand-dark/90 via-brand-dark/40 to-transparent"></div>
                    <div class="absolute bottom-0 left-0 w-full p-8 md:p-12 text-left">
                        <p class="font-serif text-2xl md:text-4xl text-white mb-3">Město chmele a památek</p>
                        <p class="text-white/80 font-light text-sm md:text-base max-w-xl">Zařazení na seznam UNESCO dělá z Žatce světový unikát. Objevte nespočet malebných uliček, útulných kaváren a nezapomenutelných výhledů jen pár minut od našich apartmánů.</p>
                    </div>
                </div>

            </div>
        </section>

        <!-- ČASTÉ DOTAZY (FAQ) -->
        <section id="faq" class="py-24 bg-brand-light border-t border-[#e5e0d8]">
            <div class="max-w-4xl mx-auto px-6 reveal">
                <div class="text-center mb-16">
                    <span class="text-brand-caramel uppercase tracking-[0.3em] font-bold text-[0.65rem] mb-4 flex justify-center items-center gap-2"><i data-lucide="info" class="w-4 h-4"></i> Praktické informace</span>
                    <h2 class="font-serif text-4xl md:text-5xl tracking-tight text-brand-dark">Časté dotazy</h2>
                </div>
                
                <div class="space-y-6">
                    <!-- FAQ 1 -->
                    <div class="bg-white rounded-3xl p-6 md:p-8 shadow-sm border border-[#e5e0d8] hover:border-brand-caramel/30 transition-colors">
                        <h4 class="font-serif text-lg text-brand-dark mb-3 flex items-center gap-3"><i data-lucide="clock" class="w-6 h-6 text-brand-caramel"></i> Kdy probíhá Check-in a Check-out?</h4>
                        <p class="text-brand-text font-light text-sm md:text-base leading-relaxed pl-9">Standardní čas příjezdu <strong>(Check-in) je od 15:00</strong>. Pokoj prosíme uvolnit <strong>(Check-out) do 10:00</strong>. Díky našemu chytrému bezkontaktnímu systému můžete přijet naprosto flexibilně kdykoliv v odpoledních či nočních hodinách. Nemusíte se tak bát zdržení na cestě.</p>
                    </div>
                    
                    <!-- FAQ 2 -->
                    <div class="bg-white rounded-3xl p-6 md:p-8 shadow-sm border border-[#e5e0d8] hover:border-brand-caramel/30 transition-colors">
                        <h4 class="font-serif text-lg text-brand-dark mb-3 flex items-center gap-3"><i data-lucide="car" class="w-6 h-6 text-brand-caramel"></i> Kde přesně mohu zaparkovat?</h4>
                        <p class="text-brand-text font-light text-sm md:text-base leading-relaxed pl-9">Parkování je pro naše hosty <strong>zajištěno bezplatně</strong>. Své vozidlo můžete zanechat přímo na vyhrazených místech u objektu, nebo na přilehlém veřejném a bezpečném prostranství. Pohodlně u nás zaparkujete i s nadrozměrnou firemní dodávkou.</p>
                    </div>

                    <!-- FAQ ÚPRAVA COPY: Přidány storno a platební podmínky -->
                    <div class="bg-white rounded-3xl p-6 md:p-8 shadow-sm border border-[#e5e0d8] hover:border-brand-caramel/30 transition-colors">
                        <h4 class="font-serif text-lg text-brand-dark mb-3 flex items-center gap-3"><i data-lucide="credit-card" class="w-6 h-6 text-brand-caramel"></i> Jaké jsou možnosti platby a storno podmínky?</h4>
                        <p class="text-brand-text font-light text-sm md:text-base leading-relaxed pl-9">Rezervaci můžete uhradit pohodlně <strong>online platební kartou</strong> nebo bankovním převodem. Pro firemní klientelu nabízíme platbu na fakturu. Bezplatné zrušení rezervace je možné nejpozději <strong>3 dny před plánovaným příjezdem</strong>.</p>
                    </div>
                    
                    <!-- FAQ 4 -->
                    <div class="bg-white rounded-3xl p-6 md:p-8 shadow-sm border border-[#e5e0d8] hover:border-brand-caramel/30 transition-colors">
                        <h4 class="font-serif text-lg text-brand-dark mb-3 flex items-center gap-3"><i data-lucide="heart" class="w-6 h-6 text-brand-caramel"></i> Mohu si s sebou vzít domácího mazlíčka?</h4>
                        <p class="text-brand-text font-light text-sm md:text-base leading-relaxed pl-9">Abychom dlouhodobě udrželi maximální standard čistoty a ohleduplnosti vůči všem hostům (včetně alergiků), pobyt s domácími zvířaty je možný <strong>výhradně po předchozí domluvě s recepcí</strong>. Před rezervací nás prosím kontaktujte, rádi to s Vámi probereme.</p>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- PATIČKA -->
    <footer class="bg-brand-dark pt-24 pb-8 text-white/60 relative overflow-hidden">
        <div class="absolute top-[-50%] left-[-10%] w-[500px] h-[500px] bg-brand-caramel/5 blur-[100px] rounded-full pointer-events-none"></div>
        <div class="max-w-7xl mx-auto px-6 relative z-10">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12 lg:gap-16 border-b border-white/10 pb-16 mb-8">
                <div class="lg:col-span-1">
                    <span class="font-serif text-3xl text-brand-caramel block mb-6 tracking-widest">ARANKA</span>
                    <p class="text-sm font-light leading-relaxed mb-8">Vaše luxusní zázemí v tiché čtvrti královského města Žatce. Jen 5 minut příjemnou chůzí od samého historického centra.</p>
                    <div class="flex gap-4">
                        <a href="#" aria-label="Facebook" class="w-10 h-10 rounded-full border border-white/20 flex items-center justify-center hover:bg-brand-caramel hover:border-brand-caramel hover:text-white transition-all transform hover:-translate-y-1"><i data-lucide="facebook" class="w-4 h-4"></i></a>
                        <a href="#" aria-label="Instagram" class="w-10 h-10 rounded-full border border-white/20 flex items-center justify-center hover:bg-brand-caramel hover:border-brand-caramel hover:text-white transition-all transform hover:-translate-y-1"><i data-lucide="instagram" class="w-4 h-4"></i></a>
                    </div>
                </div>
                <div class="lg:col-span-1">
                    <h4 class="text-white font-bold uppercase text-[0.65rem] tracking-[0.2em] mb-6 text-brand-caramel">Prozkoumejte</h4>
                    <ul class="space-y-4 text-sm font-light">
                        <li><a href="#o-nas" class="hover:text-brand-caramel transition-colors inline-block transform hover:translate-x-1">Příběh Aranky</a></li>
                        <li><a href="#ubytovani" class="hover:text-brand-caramel transition-colors inline-block transform hover:translate-x-1">Apartmány a studia</a></li>
                        <li><a href="#pro-firmy" class="hover:text-brand-caramel transition-colors inline-block transform hover:translate-x-1">Nabídka pro firmy</a></li>
                        <li><a href="#galerie" class="hover:text-brand-caramel transition-colors inline-block transform hover:translate-x-1">Fotogalerie areálu</a></li>
                    </ul>
                </div>
                <div class="lg:col-span-1">
                    <h4 class="text-white font-bold uppercase text-[0.65rem] tracking-[0.2em] mb-6 text-brand-caramel">Pro hosty</h4>
                    <ul class="space-y-4 text-sm font-light">
                        <li><a href="#faq" class="hover:text-brand-caramel transition-colors inline-block transform hover:translate-x-1">Časté dotazy</a></li>
                        <li><a href="#" class="hover:text-brand-caramel transition-colors inline-block transform hover:translate-x-1">Rezervační podmínky</a></li>
                        <li><a href="#" class="hover:text-brand-caramel transition-colors inline-block transform hover:translate-x-1">Ubytovací řád</a></li>
                    </ul>
                </div>
                <div class="lg:col-span-1 text-sm font-light leading-relaxed">
                    <h4 class="text-white font-bold uppercase text-[0.65rem] tracking-[0.2em] mb-6 text-brand-caramel">Spojte se s námi</h4>
                    <address class="not-italic">
                        <p class="mb-4 flex items-start gap-3"><i data-lucide="map-pin" class="w-5 h-5 text-brand-caramel shrink-0"></i> <span>Francouzská 1398<br>438 01 Žatec</span></p>
                        <p class="mb-4 flex items-center gap-3"><i data-lucide="phone" class="w-5 h-5 text-brand-caramel shrink-0"></i> <a href="tel:+420776604006" class="hover:text-white transition-colors">+420 776 604 006</a></p>
                        <p class="mb-6 flex items-center gap-3"><i data-lucide="mail" class="w-5 h-5 text-brand-caramel shrink-0"></i> <a href="mailto:info@arankacompany.eu" class="hover:text-white transition-colors">info@arankacompany.eu</a></p>
                    </address>
                    <div class="pt-4 border-t border-white/10 text-xs text-white/30">
                        Aranka company s.r.o.<br>IČO: 22366695<br>
                    </div>
                </div>
            </div>
            <div class="flex flex-col md:flex-row justify-between items-center text-[0.6rem] uppercase tracking-[0.2em] font-bold text-white/30">
                <p>© <span id="current-year"></span> Aranka Company s.r.o. Všechna práva vyhrazena.</p>
                <p class="mt-4 md:mt-0">Všechny uvedené ceny obsahují platnou sazbu DPH.</p>
            </div>
        </div>
    </footer>

    <!-- JS LOGIKA -->
    <script>
        document.addEventListener("DOMContentLoaded", () => {
            lucide.createIcons();
            document.getElementById('current-year').textContent = new Date().getFullYear();
            
            // Kontrola Cookie Banneru
            if (!localStorage.getItem('cookies_accepted')) {
                setTimeout(() => {
                    document.getElementById('cookie-banner').classList.add('show');
                }, 1500); // Ukázat po 1.5s pro lepší UX
            }

            // TODO [AGENTURA]: Zabezpečení VIP brány!
            // Toto řešení přes sessionStorage na front-endu slouží pouze pro prototyp.
            // V ostré verzi musí probíhat ověření hesla vůči backendu.
            if (sessionStorage.getItem('aranka_auth') === 'true') {
                const overlay = document.getElementById('password-protection');
                overlay.style.display = 'none';
                overlay.classList.remove('active');
                document.body.classList.remove('overflow-hidden');
            }

            const stickyNav = document.getElementById('site-nav');
            const scrollProgress = document.getElementById('scroll-progress');
            
            window.addEventListener('scroll', () => {
                if (window.scrollY > 50) {
                    stickyNav.classList.add('nav-visible', 'nav-scrolled');
                } else {
                    stickyNav.classList.remove('nav-visible', 'nav-scrolled');
                }
                const winScroll = document.body.scrollTop || document.documentElement.scrollTop;
                const height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
                const scrolled = (winScroll / height) * 100;
                scrollProgress.style.width = scrolled + "%";
            });
            window.dispatchEvent(new Event('scroll'));

            const revealOptions = { threshold: 0.15, rootMargin: "0px 0px -50px 0px" };
            const revealObserver = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('active');
                        observer.unobserve(entry.target); 
                    }
                });
            }, revealOptions);
            
            document.querySelectorAll('.reveal').forEach(el => revealObserver.observe(el));

            const checkinInput = document.getElementById('filter-checkin');
            const checkoutInput = document.getElementById('filter-checkout');
            if(checkinInput && checkoutInput) {
                const today = new Date();
                const checkoutDate = new Date();
                checkoutDate.setDate(today.getDate() + 2);
                checkinInput.value = today.toISOString().split('T')[0];
                checkoutInput.value = checkoutDate.toISOString().split('T')[0];
            }

            document.addEventListener('keydown', (e) => {
                if(!document.getElementById('lightboxOverlay').classList.contains('active')) return;
                if(e.key === 'Escape') closeAllOverlays();
                if(e.key === 'ArrowRight') nextImage();
                if(e.key === 'ArrowLeft') prevImage();
            });
        });

        // Logika Cookie Banneru
        function acceptCookies(type) {
            localStorage.setItem('cookies_accepted', type);
            const banner = document.getElementById('cookie-banner');
            banner.classList.remove('show');
            // Zde by normálně následovalo spuštění Google Analytics atd., pokud type === 'all'
        }

        function checkPassword() {
            const pwdInput = document.getElementById('site-password');
            const errorMsg = document.getElementById('password-error');
            // TODO [AGENTURA]: Zde napojit bezpečné ověření (API POST request)
            if (pwdInput.value.toLowerCase() === 'lukas2026') {
                sessionStorage.setItem('aranka_auth', 'true');
                const overlay = document.getElementById('password-protection');
                overlay.style.opacity = '0';
                setTimeout(() => {
                    overlay.style.display = 'none';
                    overlay.classList.remove('active');
                    document.body.classList.remove('overflow-y-hidden');
                }, 800);
            } else {
                errorMsg.style.opacity = '1';
                setTimeout(() => { errorMsg.style.opacity = '0'; }, 3000);
            }
        }

        function toggleMobileMenu() { document.getElementById('mobile-menu').classList.toggle('active'); }
        function openOverlay(id) { 
            document.querySelectorAll('.overlay').forEach(o => o.classList.remove('active')); 
            document.getElementById(id).classList.add('active'); 
            document.body.style.overflow='hidden'; 
        }
        function closeAllOverlays() { 
            document.querySelectorAll('.overlay').forEach(o => o.classList.remove('active')); 
            document.body.style.overflow='auto'; 
        }
        
        function openBooking(id) {
            let url = 'https://book.trevlix.com/book/app/?cid=3998666';
            if(id !== 'all') url += '&room_type_id=' + id;
            document.getElementById('trevlixIframe').src = url;
            openOverlay('bookingOverlay');
        }

        function submitB2BForm(e) {
            e.preventDefault();
            const btn = e.target.querySelector('button[type="submit"]');
            const originalText = btn.innerHTML;
            
            btn.innerHTML = '<i data-lucide="loader-2" class="w-5 h-5 animate-spin mx-auto"></i> Odesílám...';
            btn.classList.add('opacity-80', 'cursor-not-allowed');
            lucide.createIcons();

            setTimeout(() => {
                btn.innerHTML = '<i data-lucide="check-circle" class="w-5 h-5"></i> Úspěšně odesláno!';
                btn.classList.remove('bg-[#2C241B]', 'border-[#2C241B]');
                btn.classList.add('bg-green-700', 'border-green-700', 'text-white');
                lucide.createIcons();
                
                setTimeout(() => {
                    closeAllOverlays();
                    setTimeout(() => {
                        btn.innerHTML = originalText;
                        btn.classList.remove('bg-green-700', 'border-green-700', 'opacity-80', 'cursor-not-allowed');
                        btn.classList.add('bg-[#2C241B]', 'border-[#2C241B]');
                        e.target.reset();
                    }, 500);
                }, 2000);
            }, 1500);
        }

        // TODO [AGENTURA]: Odstranit statické pole!
        // Tato data musí být načítána dynamicky přes API z rezervačního systému (Trevlix/CMS),
        // aby reflektovala aktuální ceny a obsazenost.
        const roomsData = [
            { id: 8300, capacity: 1, price: 790, bedrooms: 1, name: "Pokoj Standard s vyvýšeným lůžkem", photo: "https://images.unsplash.com/photo-1554995207-c18c203602cb?auto=format&fit=crop&w=400&q=80" },
            { id: 8301, capacity: 4, price: 1400, bedrooms: 1, name: "Velké Studio s vlastní kuchyní", photo: "https://images.unsplash.com/photo-1522708323590-d24dbb6b0267?auto=format&fit=crop&w=400&q=80" },
            { id: 8302, capacity: 2, price: 1400, bedrooms: 1, name: "Studio s vlastní kuchyní a vanou", photo: "https://images.unsplash.com/photo-1502672260266-1c1ef2d93688?auto=format&fit=crop&w=400&q=80" },
            { id: 8303, capacity: 2, price: 1000, bedrooms: 1, name: "Dvoulůžkový pokoj s vlastní koupelnou", photo: "https://images.unsplash.com/photo-1556910103-1c02745aae4d?auto=format&fit=crop&w=400&q=80" },
            { id: 8304, capacity: 1, price: 550, bedrooms: 1, name: "Pokoj Economy pro jednoho", photo: "https://images.unsplash.com/photo-1631049307264-da0ec9d70304?auto=format&fit=crop&w=400&q=80" },
            { id: 8305, capacity: 3, price: 1000, bedrooms: 1, name: "Třílůžkový pokoj Economy", photo: "https://images.unsplash.com/photo-1555854877-bab0e564b8d5?auto=format&fit=crop&w=400&q=80" },
            { id: 8306, capacity: 3, price: 1750, bedrooms: 1, name: "Apartmán se společenskou místností", photo: "https://images.unsplash.com/photo-1497366216548-37526070297c?auto=format&fit=crop&w=400&q=80" },
            { id: 8307, capacity: 2, price: 1400, bedrooms: 1, name: "Studio s vlastní kuchyní", photo: "https://images.unsplash.com/photo-1512917774080-9991f1c4c750?auto=format&fit=crop&w=400&q=80" },
            { id: 8308, capacity: 6, price: 3600, bedrooms: 2, name: "Velkorysý Mezonet GRAND s terasou (3+3 os.)", photo: "https://images.unsplash.com/photo-1600596542815-ffad4c1539a9?auto=format&fit=crop&w=400&q=80" },
            { id: 8309, capacity: 2, price: 1600, bedrooms: 1, name: "Dvoulůžkový pokoj Comfort", photo: "https://images.unsplash.com/photo-1600607687920-4e2a09cf159d?auto=format&fit=crop&w=400&q=80" },
            { id: 8310, capacity: 6, price: 3450, bedrooms: 2, name: "Prostorný Mezonet GRAND (2+4 os.)", photo: "https://images.unsplash.com/photo-1510798831971-661eb04b3739?auto=format&fit=crop&w=400&q=80" },
            { id: 8311, capacity: 2, price: 1700, bedrooms: 1, name: "Mezonetové Studio s vlastním venkovním posezením", photo: "https://images.unsplash.com/photo-1523306401731-238f0317f240?auto=format&fit=crop&w=400&q=80" },
            { id: 8312, capacity: 3, price: 2100, bedrooms: 1, name: "Mezonet COMFORT s terasou (2+1 os.)", photo: "https://images.unsplash.com/photo-1582719478250-c89fae4658c0?auto=format&fit=crop&w=400&q=80" },
            { id: 8313, capacity: 3, price: 2350, bedrooms: 1, name: "Nadstandardní mezonet s podkrovní ložnicí a terasou", photo: "https://images.unsplash.com/photo-1600210491892-03d54c0aaf87?auto=format&fit=crop&w=400&q=80" },
            { id: 8314, capacity: 4, price: 2450, bedrooms: 2, name: "Apartmán s balkonem a vanou (2+2 os.)", photo: "https://images.unsplash.com/photo-1596243169804-245c117e33f3?auto=format&fit=crop&w=400&q=80" },
            { id: 8315, capacity: 6, price: 2880, bedrooms: 2, name: "Prostorný byt se dvěma třílůžkovými pokoji", photo: "https://images.unsplash.com/photo-1558438832-57ee02164d1f?auto=format&fit=crop&w=400&q=80" },
            { id: 8316, capacity: 6, price: 2900, bedrooms: 2, name: "Apartmán COMFORT s balkonem", photo: "https://images.unsplash.com/photo-1473448912268-2022ce9509d8?auto=format&fit=crop&w=400&q=80" },
            { id: 8317, capacity: 6, price: 2800, bedrooms: 2, name: "Apartmán COMFORT v přízemí", photo: "https://images.unsplash.com/photo-1600210492486-724fe5c67fb0?auto=format&fit=crop&w=400&q=80" }
        ];

        let peopleCount = 2;
        let roomsCount = 1;
        
        function updatePeople(c) { 
            peopleCount = Math.max(1, Math.min(15, peopleCount + c)); 
            document.getElementById('people-val').innerHTML = `${peopleCount}`; 
        }
        
        function updateRooms(c) { 
            roomsCount = Math.max(1, Math.min(10, roomsCount + c)); 
            document.getElementById('rooms-val').innerHTML = `${roomsCount}`; 
        }

        function runSmartFilter() {
            const checkinVal = document.getElementById('filter-checkin').value;
            const checkoutVal = document.getElementById('filter-checkout').value;

            if (!checkinVal || !checkoutVal) {
                alert("Prosím, vyberte platné datum příjezdu a odjezdu.");
                return;
            }

            const rc = document.getElementById('filter-results');
            
            rc.classList.remove('hidden');
            rc.innerHTML = '<div class="flex justify-center py-10"><i data-lucide="loader-2" class="w-8 h-8 text-brand-caramel animate-spin"></i></div>';
            lucide.createIcons();

            setTimeout(() => {
                const checkin = new Date(checkinVal);
                const checkout = new Date(checkoutVal);
                let daysCount = Math.ceil((checkout - checkin) / (1000 * 60 * 60 * 24));
                if (daysCount < 1 || isNaN(daysCount)) daysCount = 1;
                
                let capableRooms = [];
                
                roomsData.forEach(r => {
                    let unitsNeededForRooms = Math.ceil(roomsCount / r.bedrooms);
                    if ((r.capacity * unitsNeededForRooms) >= peopleCount) {
                        capableRooms.push({ ...r, unitsNeeded: unitsNeededForRooms });
                    }
                });

                let finalRooms = [];
                let html = '';
                
                if (capableRooms.length > 0) {
                    finalRooms = capableRooms.sort((a,b) => (a.price * a.unitsNeeded) - (b.price * b.unitsNeeded)).slice(0, 4);
                    html += '<h4 class="font-serif text-white text-xl mb-6 flex items-center gap-2"><i data-lucide="check-circle" class="w-5 h-5 text-brand-caramel"></i> Volné kapacity pro Váš pobyt:</h4>';
                } else {
                    rc.innerHTML = `
                    <div class="bg-white/5 p-10 rounded-2xl border border-white/10 text-center">
                        <i data-lucide="users" class="w-10 h-10 text-brand-caramel mx-auto mb-4 opacity-80"></i>
                        <h4 class="font-serif text-xl text-white mb-2">Pro takto velkou skupinu připravujeme nabídky na míru.</h4>
                        <p class="text-white/60 font-light text-sm mb-6">Rádi Vám chytře propojíme více apartmánů dohromady.</p>
                        <button onclick="openOverlay('b2bOverlay')" class="btn-outline px-8 py-3 text-xs rounded-full uppercase tracking-widest font-bold">Odeslat poptávku</button>
                    </div>`;
                    lucide.createIcons();
                    return;
                }

                html += '<div class="grid grid-cols-1 lg:grid-cols-2 gap-4">';
                finalRooms.forEach(r => {
                    const total = r.price * daysCount * r.unitsNeeded;
                    let bookingDescription = r.unitsNeeded > 1 ? 
                        `<span class="text-brand-caramel font-bold">${r.unitsNeeded}x pronájem jednotky</span>` : 
                        `<span class="text-brand-caramel font-bold">1x celý apartmán</span> <span class="font-light opacity-70">(${r.bedrooms > 1 ? r.bedrooms + ' ložnice' : '1 ložnice'})</span>`;

                    html += `
                    <div class="bg-[#fdfbf9] p-4 rounded-2xl flex flex-col sm:flex-row items-center gap-5 shadow-lg transition-transform hover:-translate-y-1 border border-[#e5e0d8] group">
                        <div class="w-full sm:w-28 h-32 sm:h-28 shrink-0 overflow-hidden rounded-xl relative">
                           <img src="${r.photo}" alt="${r.name}" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                        </div>
                        <div class="flex-grow w-full text-left">
                            <h4 class="font-serif text-lg text-brand-dark mb-1 leading-tight">${r.name}</h4>
                            <p class="text-brand-dark text-xs mb-2">${bookingDescription}</p>
                            <p class="text-brand-muted font-light text-xs mb-3 flex items-center gap-3">
                                <span><i data-lucide="users" class="w-3 h-3 inline"></i> Max. ${r.capacity * r.unitsNeeded} os.</span>
                                <span><i data-lucide="wallet" class="w-3 h-3 inline"></i> ${r.price} Kč / noc</span>
                            </p>
                            <div class="flex items-center justify-between w-full">
                                <span class="text-brand-dark font-bold text-sm">Celkem: ${total.toLocaleString('cs-CZ')} Kč</span>
                                <button onclick="openBooking(${r.id})" class="text-brand-caramel hover:text-brand-dark transition-colors uppercase tracking-widest text-[0.65rem] font-bold flex items-center gap-1">Zvolit <i data-lucide="arrow-right" class="w-3 h-3"></i></button>
                            </div>
                        </div>
                    </div>`;
                });
                html += '</div>';
                rc.innerHTML = html;
                lucide.createIcons(); 
            }, 600);
        }

        function scrollSlider(px) { 
            const slider = document.getElementById('garden-slider'); 
            const maxScrollLeft = slider.scrollWidth - slider.clientWidth;
            if (px > 0 && slider.scrollLeft >= maxScrollLeft - 10) slider.scrollTo({ left: 0, behavior: 'smooth' }); 
            else if (px < 0 && slider.scrollLeft <= 10) slider.scrollTo({ left: maxScrollLeft, behavior: 'smooth' }); 
            else slider.scrollBy({ left: px, behavior: 'smooth' }); 
        }

        let currentImgIndex = 0;
        const galleryImagesData = [
            { src: "https://images.unsplash.com/photo-1596243169804-245c117e33f3?auto=format&fit=crop&w=1600&q=80", title: "Zahrada - Váš prostor pro klid" },
            { src: "https://images.unsplash.com/photo-1510798831971-661eb04b3739?auto=format&fit=crop&w=1600&q=80", title: "Zákoutí stvořené pro ranní kávu" },
            { src: "https://images.unsplash.com/photo-1523306401731-238f0317f240?auto=format&fit=crop&w=1600&q=80", title: "Sluncem zalitá privátní terasa" },
            { src: "https://images.unsplash.com/photo-1558438832-57ee02164d1f?auto=format&fit=crop&w=1600&q=80", title: "Prosklená pergola s výhledem" },
            { src: "https://images.unsplash.com/photo-1512917774080-9991f1c4c750?auto=format&fit=crop&w=1600&q=80", title: "Obývací prostor v apartmánu" },
            { src: "https://images.unsplash.com/photo-1502672260266-1c1ef2d93688?auto=format&fit=crop&w=1600&q=80", title: "Minimalistická prémiová ložnice" },
            { src: "https://images.unsplash.com/photo-1473448912268-2022ce9509d8?auto=format&fit=crop&w=1600&q=80", title: "Kuchyňský a jídelní kout" },
            { src: "https://images.unsplash.com/photo-1600210491892-03d54c0aaf87?auto=format&fit=crop&w=1600&q=80", title: "Prostorná a čistá koupelna" }
        ];

        function openLightbox(i) { 
            currentImgIndex = i; 
            updateLightbox(); 
            document.getElementById('lightboxOverlay').classList.add('active'); 
            document.body.style.overflow='hidden'; 
        }
        function updateLightbox() { 
            const img = document.getElementById('lightboxImg'); 
            const caption = document.getElementById('lightboxCaption');
            img.style.opacity='0.3'; 
            img.style.transform='scale(0.98)';
            setTimeout(()=>{ 
                img.src = galleryImagesData[currentImgIndex].src; 
                caption.innerText = galleryImagesData[currentImgIndex].title;
                document.getElementById('lightboxCounter').innerText = `${currentImgIndex+1} / ${galleryImagesData.length}`; 
                img.style.opacity='1'; 
                img.style.transform='scale(1)';
            }, 200); 
        }
        function nextImage() { currentImgIndex = (currentImgIndex + 1) % galleryImagesData.length; updateLightbox(); }
        function prevImage() { currentImgIndex = (currentImgIndex - 1 + galleryImagesData.length) % galleryImagesData.length; updateLightbox(); }

        async function generateItinerary() {
            const container = document.getElementById('ai-result-container');
            const resultArea = document.getElementById('ai-result');
            const loader = document.getElementById('ai-loading');
            const mood = document.getElementById('ai-who-footer').value;
            
            container.classList.remove('hidden'); 
            resultArea.innerHTML = ''; 
            loader.classList.remove('hidden'); 
            loader.classList.add('flex');
            
            setTimeout(() => {
                loader.classList.add('hidden'); loader.classList.remove('flex');
                
                let aiText = "";
                switch(mood) {
                    case "pár":
                        aiText = "Zpomalte a užijte si jeden druhého. Začněte den výběrovou kávou v útulné kavárně na náměstí. Pokračujte ruku v ruce křivolakými uličkami historického centra, vystoupejte na Chmelový maják, odkud budete mít Žatec jako na dlani. Večer Vám doporučujeme zarezervovat stůl v nedaleké restauraci U Orloje a noc zakončit se sklenkou vína u krbu v naší soukromé zahradě.";
                        break;
                    case "rodina":
                        aiText = "Žatec baví i ty nejmenší! Vaše první kroky by měly směřovat do Chrámu chmele a piva, kde na rodiny čeká interaktivní bludiště z chmelových žoků a unikátní 3D výtah. Na oběd se stavte v prostorné restauraci místního pivovaru. Odpoledne doporučujeme nenáročnou procházku k řece Ohři a večer se těšíme, až u nás na zahradě strávíte bezpečný čas s rodinou.";
                        break;
                    case "cyklista":
                        aiText = "Ideální výchozí bod. Hned po snídani se napojte na novou cyklostezku vedoucí přímo podél řeky Ohře, která Vás dovede až ke břehům rozlehlé Nechranické přehrady. Je to nádherná, z velké části rovinatá trasa. Vaše kola u nás bezpečně uschováme a věříme, že po takovém výkonu si vychutnáte správně načepovanou Žateckou sedmičku v centru!";
                        break;
                    case "pracovník":
                        aiText = "Chápeme, že po dlouhém dni potřebujete hlavně efektivitu a klid. Čeká na Vás rychlý check-in a vysoce stabilní Wi-Fi, pokud potřebujete večer ještě pracovat. Skvělou a svižnou večeři pořídíte jen 5 minut chůze od Aranky. Pro utřídění myšlenek pak doporučujeme posedět v naší prosklené pergole, kde Vás nebude vůbec nic rušit.";
                        break;
                    default:
                        aiText = "Historické centrum, zapsané na seznamu UNESCO, máte od nás doslova za rohem. Rádi Vám s plány pomůžeme po Vašem příjezdu osobně, protože každému hostu se věnujeme s individuální péčí.";
                }
                
                resultArea.innerHTML = `<p>"${aiText}"</p>`;
            }, 1200);
        }
    </script>
    
    <!-- Tawk.to -->
    <script type="text/javascript">
        window.addEventListener('unhandledrejection', function(event) {
            if (event.reason && event.reason.toString().includes('$_Tawk.i18next')) event.preventDefault();
        });
        var Tawk_API=Tawk_API||{}, Tawk_LoadStart=new Date();
        (function(){
        var s1=document.createElement("script"),s0=document.getElementsByTagName("script")[0];
        s1.async=true; s1.src='https://embed.tawk.to/699c7aae593adb1c36dddd0f/1ji5juenf'; s1.charset='UTF-8'; s1.setAttribute('crossorigin','*'); s0.parentNode.insertBefore(s1,s0);
        })();
    </script>
</body>
</html>

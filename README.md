<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PUFFKERS | Cereal On-The-Go</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;800;900&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #fcfcfc;
            color: #111;
        }
        h1, h2, h3, .font-heading {
            font-family: 'Montserrat', sans-serif;
        }
        
        /* Hero Text Effect */
        .hero-text {
            font-size: clamp(4rem, 15vw, 15rem);
            line-height: 0.8;
            letter-spacing: -0.05em;
            color: rgba(255, 255, 255, 0.9);
            text-transform: uppercase;
        }
        .hero-text-outline {
            color: transparent;
            -webkit-text-stroke: 2px rgba(255, 255, 255, 0.5);
        }

        .bg-hero {
            background-color: #050505;
            background-image: radial-gradient(circle at 50% 50%, #2a0845 0%, #050505 70%);
        }

        /* Hide sections by default for SPA routing */
        .page-section {
            display: none;
            animation: fadeIn 0.3s ease-in-out;
        }
        .page-section.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Product Circle Background */
        .product-circle {
            background: #eaeaea;
            border-radius: 50%;
            aspect-ratio: 1/1;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        /* Value Prop Card Hover */
        .value-card {
            transition: all 0.3s ease;
        }
        .value-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px -5px rgba(168, 85, 247, 0.15);
            border-color: #d8b4fe;
        }
    </style>
</head>
<body class="antialiased flex flex-col min-h-screen">

    <!-- Navigation -->
    <nav class="sticky top-0 z-50 bg-white border-b border-gray-100 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <!-- Logo -->
                <div class="flex-shrink-0 flex items-center cursor-pointer" onclick="navigate('home')">
                    <span class="font-heading font-black text-2xl tracking-tighter">PUFFKERS</span>
                </div>
                
                <!-- Desktop Menu -->
                <div class="hidden md:flex items-center space-x-8">
                    <button onclick="navigate('tienda')" class="text-sm font-semibold hover:text-purple-600 transition-colors">Tienda</button>
                    <button onclick="navigate('acerca')" class="text-sm font-semibold hover:text-purple-600 transition-colors">Acerca de</button>
                    <button onclick="navigate('contacto')" class="text-sm font-semibold hover:text-purple-600 transition-colors">Contacto</button>
                    
                    <div class="flex items-center space-x-4 border-l pl-6 border-gray-200">
                        <a href="#" class="text-gray-600 hover:text-black"><i data-lucide="twitter" class="w-5 h-5"></i></a>
                        <a href="#" class="text-gray-600 hover:text-black"><i data-lucide="instagram" class="w-5 h-5"></i></a>
                        <button onclick="navigate('carrito')" class="text-gray-600 hover:text-black relative">
                            <span class="font-semibold text-sm">Carrito</span>
                            <span id="cart-badge" class="absolute -top-2 -right-3 bg-black text-white text-xs rounded-full h-4 w-4 flex items-center justify-center hidden">0</span>
                        </button>
                    </div>
                </div>

                <!-- Mobile menu button -->
                <div class="md:hidden flex items-center">
                    <button onclick="toggleMobileMenu()" class="text-gray-600 hover:text-black">
                        <i data-lucide="menu" class="w-6 h-6"></i>
                    </button>
                </div>
            </div>
        </div>
        
        <!-- Mobile Menu Panel -->
        <div id="mobile-menu" class="hidden md:hidden bg-white border-b border-gray-100">
            <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
                <button onclick="navigate('tienda')" class="block w-full text-left px-3 py-2 text-base font-semibold hover:bg-gray-50">Tienda</button>
                <button onclick="navigate('acerca')" class="block w-full text-left px-3 py-2 text-base font-semibold hover:bg-gray-50">Acerca de</button>
                <button onclick="navigate('contacto')" class="block w-full text-left px-3 py-2 text-base font-semibold hover:bg-gray-50">Contacto</button>
                <button onclick="navigate('carrito')" class="block w-full text-left px-3 py-2 text-base font-semibold hover:bg-gray-50">Carrito</button>
            </div>
        </div>
    </nav>

    <!-- Main Content Area -->
    <main class="flex-grow">

        <!-- ================= HOME PAGE ================= -->
        <div id="home" class="page-section active">
            
            <!-- Hero Section -->
            <section class="bg-black flex items-center justify-center">
                <img src="ChatGPT Image 10 may 2026, 10_00_46.png" alt="PUFFKERS Hero" class="w-full max-w-7xl object-cover">
            </section>

            <!-- Tagline Section -->
            <section class="py-20 px-4 text-center max-w-4xl mx-auto">
                <h2 class="font-heading font-bold text-3xl md:text-5xl mb-6">No es solo un snack...<br>ES UNA MARCA URBANA</h2>
                <p class="text-gray-600 text-lg max-w-2xl mx-auto">Diseñado para el ritmo acelerado del estudiante de hoy. Práctico, nutritivo y con una estética moderna que conecta con la Generación Z.</p>
            </section>

            <!-- Feature Preview -->
            <section class="py-10 max-w-6xl mx-auto px-4 flex flex-col md:flex-row items-center justify-center gap-12">
                <div class="text-center md:text-right flex-1">
                    <div class="inline-flex items-center justify-center w-12 h-12 rounded-full bg-blue-100 text-blue-600 mb-4">
                        <i data-lucide="zap"></i>
                    </div>
                    <h3 class="font-heading font-bold text-xl mb-2">Energía Inmediata</h3>
                    <p class="text-gray-500 text-sm">Formato listo para llevar. Te da el impulso necesario justo cuando más lo necesitas, sin complicaciones.</p>
                </div>
                
                <div class="flex-shrink-0 w-64 h-64 rounded-full bg-gradient-to-tr from-purple-500 to-pink-500 p-1">
                    <div class="w-full h-full bg-white rounded-full flex flex-col items-center justify-center p-4 text-center">
                        <h4 class="font-heading font-black text-2xl">PUFF✦KERS</h4>
                        <p class="text-xs text-gray-500 mt-2">CEREAL PRÁCTICO</p>
                    </div>
                </div>

                <div class="text-center md:text-left flex-1">
                    <div class="inline-flex items-center justify-center w-12 h-12 rounded-full bg-purple-100 text-purple-600 mb-4">
                        <i data-lucide="gem"></i>
                    </div>
                    <h3 class="font-heading font-bold text-xl mb-2">Diseño Coleccionable</h3>
                    <p class="text-gray-500 text-sm">Figuras metálicas del Oso Puffkers. Una estética rebelde y llamativa que querrás mostrar.</p>
                </div>
            </section>

            <!-- Products Preview -->
            <section class="py-20 bg-gray-50">
                <div class="max-w-7xl mx-auto px-4">
                    <h2 class="font-heading font-bold text-3xl text-center mb-16">NUESTRO PRODUCTO</h2>
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-12">
                        <!-- Product 1 -->
                        <div class="flex flex-col items-center">
                            <div class="product-circle w-full max-w-[300px] mb-6">
                                <img src="https://placehold.co/400x400/e2e8f0/64748b?text=[Imagen+de+Vaso+Puffkers+Q.25]" alt="Cereal Puffkers 25" class="w-full h-full object-cover">
                            </div>
                            <div class="flex items-center justify-center w-full max-w-[300px] gap-4">
                                <div class="flex items-center border border-gray-300 rounded px-3 py-2 bg-white">
                                    <button class="text-gray-500 hover:text-black px-2">-</button>
                                    <span class="px-4 font-semibold">1</span>
                                    <button class="text-gray-500 hover:text-black px-2">+</button>
                                </div>
                                <button onclick="addToCart()" class="flex-1 bg-transparent border border-black text-black font-semibold py-2 px-4 rounded hover:bg-black hover:text-white transition-colors">Añadir al carrito</button>
                            </div>
                        </div>
                        <!-- Product 2 -->
                        <div class="flex flex-col items-center">
                            <div class="product-circle w-full max-w-[300px] mb-6">
                                <img src="https://placehold.co/400x400/e2e8f0/64748b?text=[Imagen+de+Vaso+Puffkers+Q.20]" alt="Cereal Puffkers 20" class="w-full h-full object-cover">
                            </div>
                            <div class="flex items-center justify-center w-full max-w-[300px] gap-4">
                                <div class="flex items-center border border-gray-300 rounded px-3 py-2 bg-white">
                                    <button class="text-gray-500 hover:text-black px-2">-</button>
                                    <span class="px-4 font-semibold">1</span>
                                    <button class="text-gray-500 hover:text-black px-2">+</button>
                                </div>
                                <button onclick="addToCart()" class="flex-1 bg-transparent border border-black text-black font-semibold py-2 px-4 rounded hover:bg-black hover:text-white transition-colors">Añadir al carrito</button>
                            </div>
                        </div>
                        <!-- Product 3 -->
                        <div class="flex flex-col items-center">
                            <div class="product-circle w-full max-w-[300px] mb-6">
                                <img src="https://placehold.co/400x400/e2e8f0/64748b?text=[Imagen+de+Vaso+Puffkers+Q.15]" alt="Cereal Puffkers 15" class="w-full h-full object-cover">
                            </div>
                            <div class="flex items-center justify-center w-full max-w-[300px] gap-4">
                                <div class="flex items-center border border-gray-300 rounded px-3 py-2 bg-white">
                                    <button class="text-gray-500 hover:text-black px-2">-</button>
                                    <span class="px-4 font-semibold">1</span>
                                    <button class="text-gray-500 hover:text-black px-2">+</button>
                                </div>
                                <button onclick="addToCart()" class="flex-1 bg-transparent border border-black text-black font-semibold py-2 px-4 rounded hover:bg-black hover:text-white transition-colors">Añadir al carrito</button>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Propuesta de Valor -->
            <section class="py-20 max-w-7xl mx-auto px-4">
                <h2 class="font-heading font-bold text-3xl mb-12">PROPUESTA DE VALOR</h2>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                    <div class="value-card border border-gray-200 rounded-2xl p-8 text-center bg-white shadow-sm">
                        <div class="mx-auto w-16 h-16 flex items-center justify-center text-blue-400 mb-6 border-2 border-blue-100 rounded-2xl">
                            <i data-lucide="package" class="w-8 h-8"></i>
                        </div>
                        <h3 class="font-heading font-bold text-xl mb-4">PRACTICIDAD</h3>
                        <p class="text-gray-500 text-sm">Porciones individuales diseñadas para ser consumidas en el bus o entre clases. Sin necesidad de platos ni cucharas extra.</p>
                    </div>
                    <div class="value-card border border-gray-200 rounded-2xl p-8 text-center bg-white shadow-sm">
                        <div class="mx-auto w-16 h-16 flex items-center justify-center text-purple-400 mb-6 border-2 border-purple-100 rounded-2xl">
                            <i data-lucide="leaf" class="w-8 h-8"></i>
                        </div>
                        <h3 class="font-heading font-bold text-xl mb-4">NUTRICIÓN</h3>
                        <p class="text-gray-500 text-sm">Ingredientes balanceados que brindan saciedad y energía real para afrontar las jornadas universitarias más exigentes.</p>
                    </div>
                    <div class="value-card border border-gray-200 rounded-2xl p-8 text-center bg-white shadow-sm">
                        <div class="mx-auto w-16 h-16 flex items-center justify-center text-pink-400 mb-6 border-2 border-pink-100 rounded-2xl">
                            <i data-lucide="palette" class="w-8 h-8"></i>
                        </div>
                        <h3 class="font-heading font-bold text-xl mb-4">DISEÑO</h3>
                        <p class="text-gray-500 text-sm">Estética urbana. Empaques metálicos vibrantes y figuras coleccionables del Oso Puffkers que construyen identidad.</p>
                    </div>
                </div>
            </section>

            <!-- Equipo de Trabajo -->
            <section class="py-20 bg-gray-50">
                <div class="max-w-6xl mx-auto px-4">
                    <h2 class="font-heading font-bold text-3xl mb-16 text-center">EQUIPO DE TRABAJO</h2>
                    
                    <div class="flex justify-center w-full">
                        <img src="Copia de PROYECTO EMPRENDIMIENTO - PITCH (3).png" alt="Equipo de Trabajo Puffkers" class="w-full max-w-5xl h-auto object-contain">
                    </div>
                </div>
            </section>

            <!-- Osos Coleccionables -->
            <section class="py-20 max-w-6xl mx-auto px-4 text-center">
                <h2 class="font-heading font-bold text-3xl mb-12 uppercase">Oso Puffkers</h2>
                <div class="w-full flex justify-center">
                    <img src="046c9fc7-b0f8-44ee-87e6-aa7e031b5c11 (1).png" alt="Osos Puffkers Coleccionables" class="w-full max-w-5xl h-auto object-contain">
                </div>
            </section>
        </div>

        <!-- ================= TIENDA PAGE ================= -->
        <div id="tienda" class="page-section">
            <div class="max-w-7xl mx-auto px-4 py-20">
                <h1 class="font-heading font-bold text-4xl mb-16 text-center">TIENDA</h1>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-16 items-center">
                    
                    <!-- Producto 1 (Grande) -->
                    <div class="flex justify-center">
                        <div class="product-circle w-full max-w-[450px]">
                            <img src="https://placehold.co/600x600/e2e8f0/64748b?text=[Imagen+Vaso+Puffkers+Mora+Berry]" alt="Puffkers Mora Berry" class="w-full h-full object-cover">
                        </div>
                    </div>
                    <div class="flex flex-col justify-center">
                        <h2 class="font-heading font-bold text-3xl mb-2">PUFFKERS Sabor Mora Berry</h2>
                        <p class="text-gray-500 mb-6">Cereal On-The-Go. Porción 70g.</p>
                        <p class="text-2xl mb-8">Q.25.00 <span class="text-sm text-gray-400 line-through ml-2">USD 20.00</span></p>
                        
                        <div class="flex items-center gap-4 max-w-md">
                            <div class="flex items-center border border-gray-300 rounded px-4 py-3 bg-white">
                                <button class="text-gray-500 hover:text-black px-2">-</button>
                                <span class="px-6 font-semibold">1</span>
                                <button class="text-gray-500 hover:text-black px-2">+</button>
                            </div>
                            <button onclick="addToCart()" class="flex-1 bg-black border border-black text-white font-semibold py-3 px-6 rounded hover:bg-gray-800 transition-colors">Añadir al carrito</button>
                        </div>
                    </div>

                </div>
            </div>
        </div>

        <!-- ================= ACERCA DE PAGE ================= -->
        <div id="acerca" class="page-section">
            <div class="max-w-6xl mx-auto px-4 py-20 grid grid-cols-1 md:grid-cols-2 gap-16 items-center">
                <div>
                    <h1 class="font-heading font-bold text-5xl mb-8 uppercase tracking-tight">Puffkers</h1>
                    <p class="text-gray-600 mb-6 leading-relaxed">
                        ¿Sabías que los universitarios en la Ciudad de Guatemala pierden hasta 4 horas diarias en el tráfico? La mayoría termina saltándose el desayuno y rindiendo menos en clases. 
                    </p>
                    <p class="text-gray-600 mb-6 leading-relaxed">
                        Por eso creamos <strong>PUFFKERS</strong>. Somos una marca de cereal urbano en porciones individuales, listo para consumir en movimiento. Ofrecemos energía inmediata, nutrición real y una estética metálica coleccionable que conecta con la Generación Z. 
                    </p>
                    <p class="text-gray-600 leading-relaxed">
                        Con Puffkers, estamos redefiniendo el desayuno para los que no tienen tiempo que perder.
                    </p>
                </div>
                <div class="flex justify-center">
                    <img src="Copia de PROYECTO EMPRENDIMIENTO - PITCH (4).png" alt="Oso Cromo Puffkers" class="w-full max-w-md object-contain">
                </div>
            </div>
        </div>

        <!-- ================= CONTACTO PAGE ================= -->
        <div id="contacto" class="page-section">
            <div class="max-w-6xl mx-auto px-4 py-20 grid grid-cols-1 md:grid-cols-2 gap-16">
                <div>
                    <h1 class="font-heading font-bold text-4xl mb-4">Enviar tu consulta</h1>
                    <p class="text-gray-500 mb-10">¿Tienes un proyecto en mente? Llena el formulario y diseñemos juntos algo increíble.</p>
                    
                    <form class="space-y-6" onsubmit="event.preventDefault(); alert('Mensaje enviado. ¡Gracias!');">
                        <div class="grid grid-cols-2 gap-6">
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-1">Nombre <span class="text-gray-400">(obligatorio)</span></label>
                                <input type="text" required class="w-full border-b border-gray-300 py-2 focus:outline-none focus:border-black bg-transparent">
                            </div>
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-1">Apellido <span class="text-gray-400">(obligatorio)</span></label>
                                <input type="text" required class="w-full border-b border-gray-300 py-2 focus:outline-none focus:border-black bg-transparent">
                            </div>
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-1">Correo electrónico <span class="text-gray-400">(obligatorio)</span></label>
                            <input type="email" required class="w-full border-b border-gray-300 py-2 focus:outline-none focus:border-black bg-transparent">
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-1">Mensaje <span class="text-gray-400">(obligatorio)</span></label>
                            <textarea required rows="4" class="w-full border-b border-gray-300 py-2 focus:outline-none focus:border-black bg-transparent resize-none"></textarea>
                        </div>
                        <button type="submit" class="bg-black text-white px-8 py-3 rounded text-sm font-semibold hover:bg-gray-800 transition-colors">ENVIAR</button>
                    </form>
                </div>
                <div class="hidden md:block">
                    <img src="https://placehold.co/600x800/eaeaea/a3a3a3?text=[Imagen+de+Esfera+Decorativa]" alt="Decoración" class="w-full h-full object-cover rounded-sm">
                </div>
            </div>
        </div>

        <!-- ================= CARRITO PAGE ================= -->
        <div id="carrito" class="page-section">
            <div class="max-w-4xl mx-auto px-4 py-32 text-center">
                <h1 class="font-heading font-bold text-3xl mb-6 text-left">Carrito de compra</h1>
                
                <div id="cart-empty" class="py-12">
                    <p class="text-gray-500 mb-8 text-left">No tienes nada en tu carrito de compras.</p>
                    <div class="text-left">
                        <button onclick="navigate('tienda')" class="border border-black text-black px-6 py-2 rounded text-sm font-semibold hover:bg-black hover:text-white transition-colors">Seguir comprando</button>
                    </div>
                </div>

                <div id="cart-filled" class="hidden text-left py-8">
                    <p class="text-green-600 mb-4 font-semibold">¡Tienes artículos en tu carrito!</p>
                    <button onclick="clearCart()" class="bg-red-500 text-white px-6 py-2 rounded text-sm font-semibold hover:bg-red-600 transition-colors">Vaciar Carrito</button>
                </div>
            </div>
        </div>

    </main>

    <!-- Footer -->
    <footer class="bg-[#222] text-white pt-16 pb-8 border-t-4 border-gray-800">
        <div class="max-w-7xl mx-auto px-4 flex flex-col items-center">
            
            <h2 class="font-heading font-black text-5xl md:text-7xl tracking-tighter mb-2 flex items-center">
                PUFF<i data-lucide="sparkles" class="w-8 h-8 md:w-12 md:h-12 mx-1 text-gray-300"></i>KERS
            </h2>
            <p class="text-gray-400 text-lg mb-10">Practicidad en movimiento.</p>
            
            <div class="flex space-x-6 mb-16">
                <a href="#" class="w-12 h-12 rounded-full border border-gray-600 flex items-center justify-center hover:bg-white hover:text-black transition-colors">
                    <i data-lucide="instagram" class="w-5 h-5"></i>
                </a>
                <a href="#" class="w-12 h-12 rounded-full border border-gray-600 flex items-center justify-center hover:bg-white hover:text-black transition-colors">
                    <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                        <path d="M19.59 6.69a4.83 4.83 0 0 1-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 0 1-5.2 1.74 2.89 2.89 0 0 1 2.31-4.64 2.93 2.93 0 0 1 .88.13V9.4a6.84 6.84 0 0 0-1-.05A6.33 6.33 0 0 0 5 20.1a6.34 6.34 0 0 0 10.86-4.43v-7a8.16 8.16 0 0 0 4.77 1.52v-3.4a5.63 5.63 0 0 1-1.04-.1z"></path>
                    </svg>
                </a>
                <a href="#" class="w-12 h-12 rounded-full border border-gray-600 flex items-center justify-center hover:bg-white hover:text-black transition-colors">
                    <i data-lucide="map-pin" class="w-5 h-5"></i>
                </a>
            </div>

            <div class="w-full border-t border-gray-800 pt-8 flex flex-col md:flex-row justify-between items-center text-sm text-gray-500">
                <p>&copy; 2026 Puffkers. Todos los derechos reservados.</p>
                <p class="mt-4 md:mt-0 uppercase tracking-widest">PUFFKERS.COM</p>
            </div>
        </div>
    </footer>

    <!-- JavaScript for Interactions -->
    <script>
        // Initialize Lucide Icons
        lucide.createIcons();

        // SPA Navigation Logic
        function navigate(sectionId) {
            const sections = document.querySelectorAll('.page-section');
            sections.forEach(sec => sec.classList.remove('active'));
            
            const target = document.getElementById(sectionId);
            if (target) {
                target.classList.add('active');
                window.scrollTo(0, 0);
            }

            const mobileMenu = document.getElementById('mobile-menu');
            if (!mobileMenu.classList.contains('hidden')) {
                mobileMenu.classList.add('hidden');
            }
        }

        // Mobile Menu Toggle
        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }

        // Basic Cart Logic
        let cartItems = 0;
        function addToCart() {
            cartItems++;
            updateCartUI();
            
            const btn = event.currentTarget;
            const originalText = btn.innerText;
            btn.innerText = "¡Añadido!";
            btn.classList.add('bg-green-500', 'text-white', 'border-green-500');
            setTimeout(() => {
                btn.innerText = originalText;
                btn.classList.remove('bg-green-500', 'text-white', 'border-green-500');
            }, 1500);
        }

        function clearCart() {
            cartItems = 0;
            updateCartUI();
        }

        function updateCartUI() {
            const badge = document.getElementById('cart-badge');
            const emptyState = document.getElementById('cart-empty');
            const filledState = document.getElementById('cart-filled');

            if (cartItems > 0) {
                badge.innerText = cartItems;
                badge.classList.remove('hidden');
            } else {
                badge.classList.add('hidden');
            }

            if (cartItems > 0) {
                emptyState.classList.add('hidden');
                filledState.classList.remove('hidden');
            } else {
                emptyState.classList.remove('hidden');
                filledState.classList.add('hidden');
            }
        }
    </script>
</body>
</html>

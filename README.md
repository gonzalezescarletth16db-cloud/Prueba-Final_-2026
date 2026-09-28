<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animals Friends - Café, Librería y Refugio</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700&family=Playfair+Display:ital,wght@0,600;0,700;1,400&display=swap" rel="stylesheet">
    <!-- FontAwesome para iconos -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body {
            font-family: 'Outfit', sans-serif;
            background-color: #FDFBF7;
            color: #4A3E3D;
        }
        h1, h2, h3, .font-serif {
            font-family: 'Playfair Display', serif;
        }
        .gallery-item {
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }
        .gallery-item:hover {
            transform: translateY(-6px);
        }
    </style>
</head>
<body class="bg-[#FDFBF7] text-[#4A3E3D] antialiased">

    <!-- BARRA DE NAVEGACIÓN -->
    <header class="sticky top-0 z-50 bg-[#FDFBF7]/90 backdrop-blur-md border-b border-[#EFECE6]">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <!-- Logo -->
            <a href="#" class="flex items-center space-x-3 group">
                <div class="w-11 h-11 bg-[#8D5B4C] rounded-full flex items-center justify-center text-white shadow-md group-hover:scale-105 transition-transform">
                    <i class="fa-solid fa-paw text-xl"></i>
                </div>
                <div>
                    <span class="text-2xl font-bold font-serif tracking-wide text-[#332625]">Animals Friends</span>
                    <span class="block text-xs uppercase tracking-widest text-[#8D5B4C] font-semibold">Café y Librería</span>
                </div>
            </a>

            <!-- Menú de Navegación -->
            <nav class="hidden md:flex items-center space-x-8 font-medium text-sm">
                <a href="#inicio" class="text-[#8D5B4C] font-semibold transition-colors">Inicio</a>
                <a href="#galeria" class="hover:text-[#8D5B4C] transition-colors">Galería</a>
                <a href="#mascotas" class="hover:text-[#8D5B4C] transition-colors">Amigos Peludos</a>
                <a href="#contacto" class="hover:text-[#8D5B4C] transition-colors">Contacto</a>
            </nav>

            <!-- Botón de acción -->
            <div class="hidden md:block">
                <a href="#contacto" class="px-5 py-2.5 rounded-full bg-[#8D5B4C] text-white font-medium text-sm hover:bg-[#72463B] transition-colors shadow-sm">
                    Visítanos
                </a>
            </div>
        </div>
    </header>

    <!-- SECCIÓN HERO -->
    <section id="inicio" class="relative py-20 lg:py-28 overflow-hidden bg-gradient-to-b from-[#F5EFEB] to-[#FDFBF7]">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="text-center max-w-3xl mx-auto">
                <span class="inline-block py-1 px-3 rounded-full bg-[#E8DDD9] text-[#72463B] text-xs font-semibold uppercase tracking-wider mb-4">
                    Café de especialidad, lectura y rescate animal 🐾
                </span>
                <h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold font-serif text-[#332625] leading-tight mb-6">
                    Donde cada libro cuenta una historia y cada mascota encuentra un hogar
                </h1>
                <p class="text-lg text-[#6B5B5A] mb-8 font-light">
                    Disfruta de un excelente café y una lectura inspiradora rodeado de un ambiente cálido y entrañable. Conoce nuestro espacio y a nuestros residentes de cuatro patas.
                </p>
                <div class="flex flex-wrap justify-center gap-4">
                    <a href="#galeria" class="px-8 py-3 rounded-full bg-[#8D5B4C] text-white font-medium hover:bg-[#72463B] transition shadow-md">
                        Explorar Galería
                    </a>
                    <a href="#mascotas" class="px-8 py-3 rounded-full bg-white border border-[#DCD3CC] text-[#4A3E3D] font-medium hover:bg-[#F4ECE6] transition">
                        Conoce a los Peludos
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- SECCIÓN DE GALERÍA FILTRABLE -->
    <section id="galeria" class="py-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-12">
            <h2 class="text-3xl sm:text-4xl font-bold font-serif text-[#332625] mb-3">Nuestra Galería de Momentos</h2>
            <p class="text-[#6B5B5A] max-w-xl mx-auto text-sm sm:text-base">Un vistazo a nuestro rincón de paz, café recién hecho, estanterías llenas de magia y patitas felices.</p>
        </div>

        <!-- Botones de Filtro -->
        <div class="flex flex-wrap justify-center gap-2 sm:gap-3 mb-12" id="filter-buttons">
            <button onclick="filterSelection('all')" class="filter-btn active px-5 py-2 rounded-full text-sm font-medium transition bg-[#8D5B4C] text-white shadow-sm cursor-pointer">Todos</button>
            <button onclick="filterSelection('cafe')" class="filter-btn px-5 py-2 rounded-full text-sm font-medium transition bg-white border border-[#DCD3CC] text-[#4A3E3D] hover:bg-[#F4ECE6] cursor-pointer">Cafetería</button>
            <button onclick="filterSelection('libreria')" class="filter-btn px-5 py-2 rounded-full text-sm font-medium transition bg-white border border-[#DCD3CC] text-[#4A3E3D] hover:bg-[#F4ECE6] cursor-pointer">Librería</button>
            <button onclick="filterSelection('animales')" class="filter-btn px-5 py-2 rounded-full text-sm font-medium transition bg-white border border-[#DCD3CC] text-[#4A3E3D] hover:bg-[#F4ECE6] cursor-pointer">Amigos Peludos</button>
            <button onclick="filterSelection('ambiente')" class="filter-btn px-5 py-2 rounded-full text-sm font-medium transition bg-white border border-[#DCD3CC] text-[#4A3E3D] hover:bg-[#F4ECE6] cursor-pointer">Ambiente</button>
        </div>

        <!-- Grid de Fotos -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 sm:gap-8" id="gallery-grid">
            
            <!-- Item 1: Café -->
            <div class="gallery-item column cafe overflow-hidden rounded-2xl bg-white shadow-sm border border-[#EFECE6]" data-category="cafe">
                <div class="relative h-64 overflow-hidden group">
                    <img src="https://images.unsplash.com/photo-1514432324607-a09d9b4aefdd?auto=format&fit=crop&q=80&w=800" alt="Café de especialidad con arte latte" class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end p-6">
                        <span class="text-white font-medium text-sm">Latte Art y Café de Grano</span>
                    </div>
                </div>
                <div class="p-5">
                    <span class="text-xs font-semibold uppercase tracking-wider text-[#8D5B4C]">Cafetería</span>
                    <h3 class="text-lg font-bold font-serif text-[#332625] mt-1">Nuestros Cafés de Especialidad</h3>
                    <p class="text-sm text-[#6B5B5A] mt-2">Preparados con granos locales de altura y mucho amor en cada taza.</p>
                </div>
            </div>

            <!-- Item 2: Librería -->
            <div class="gallery-item column libreria overflow-hidden rounded-2xl bg-white shadow-sm border border-[#EFECE6]" data-category="libreria">
                <div class="relative h-64 overflow-hidden group">
                    <img src="https://images.unsplash.com/photo-1524995997946-a1c2e315a42f?auto=format&fit=crop&q=80&w=800" alt="Librería acogedora" class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end p-6">
                        <span class="text-white font-medium text-sm">Rincón de Lectura</span>
                    </div>
                </div>
                <div class="p-5">
                    <span class="text-xs font-semibold uppercase tracking-wider text-[#8D5B4C]">Librería</span>
                    <h3 class="text-lg font-bold font-serif text-[#332625] mt-1">Estanterías Literarias</h3>
                    <p class="text-sm text-[#6B5B5A] mt-2">Un catálogo lleno de literatura contemporánea, clásicos y literatura sobre animales.</p>
                </div>
            </div>

            <!-- Item 3: Animales -->
            <div class="gallery-item column animales overflow-hidden rounded-2xl bg-white shadow-sm border border-[#EFECE6]" data-category="animales">
                <div class="relative h-64 overflow-hidden group">
                    <img src="https://images.unsplash.com/photo-1548199973-03cce0bbc87b?auto=format&fit=crop&q=80&w=800" alt="Perritos felices jugando" class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end p-6">
                        <span class="text-white font-medium text-sm">Área de Residentes Peludos</span>
                    </div>
                </div>
                <div class="p-5">
                    <span class="text-xs font-semibold uppercase tracking-wider text-[#8D5B4C]">Amigos Peludos</span>
                    <h3 class="text-lg font-bold font-serif text-[#332625] mt-1">Tardes de Compañía</h3>
                    <p class="text-sm text-[#6B5B5A] mt-2">Espacios seguros y adaptados para que nuestros rescatados convivan sanamente.</p>
                </div>
            </div>

            <!-- Item 4: Ambiente -->
            <div class="gallery-item column ambiente overflow-hidden rounded-2xl bg-white shadow-sm border border-[#EFECE6]" data-category="ambiente">
                <div class="relative h-64 overflow-hidden group">
                    <img src="https://images.unsplash.com/photo-1554118811-1e0d58224f24?auto=format&fit=crop&q=80&w=800" alt="Interior de la cafetería" class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end p-6">
                        <span class="text-white font-medium text-sm">Diseño y Calidez</span>
                    </div>
                </div>
                <div class="p-5">
                    <span class="text-xs font-semibold uppercase tracking-wider text-[#8D5B4C]">Ambiente</span>
                    <h3 class="text-lg font-bold font-serif text-[#332625] mt-1">Un Refugio Urbano</h3>
                    <p class="text-sm text-[#6B5B5A] mt-2">Mesas iluminadas y rincones cómodos ideales para concentrarse o conversar.</p>
                </div>
            </div>

            <!-- Item 5: Café -->
            <div class="gallery-item column cafe overflow-hidden rounded-2xl bg-white shadow-sm border border-[#EFECE6]" data-category="cafe">
                <div class="relative h-64 overflow-hidden group">
                    <img src="https://images.unsplash.com/photo-1509042239860-f550ce710b93?auto=format&fit=crop&q=80&w=800" alt="Repostería casera" class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end p-6">
                        <span class="text-white font-medium text-sm">Panadería Artesanal</span>
                    </div>
                </div>
                <div class="p-5">
                    <span class="text-xs font-semibold uppercase tracking-wider text-[#8D5B4C]">Cafetería</span>
                    <h3 class="text-lg font-bold font-serif text-[#332625] mt-1">Repostería del Día</h3>
                    <p class="text-sm text-[#6B5B5A] mt-2">Galletas, panecillos y pasteles horneados diariamente para acompañar tu bebida.</p>
                </div>
            </div>

            <!-- Item 6: Animales -->
            <div class="gallery-item column animales overflow-hidden rounded-2xl bg-white shadow-sm border border-[#EFECE6]" data-category="animales">
                <div class="relative h-64 overflow-hidden group">
                    <img src="https://images.unsplash.com/photo-1533738363-b7f9aef128ce?auto=format&fit=crop&q=80&w=800" alt="Gatito descansando en la librería" class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end p-6">
                        <span class="text-white font-medium text-sm">Michi Inspector de Libros</span>
                    </div>
                </div>
                <div class="p-5">
                    <span class="text-xs font-semibold uppercase tracking-wider text-[#8D5B4C]">Amigos Peludos</span>
                    <h3 class="text-lg font-bold font-serif text-[#332625] mt-1">Nuestros Protectores Felinos</h3>
                    <p class="text-sm text-[#6B5B5A] mt-2">A algunos les encanta dormir plácidamente sobre las pilas de novelas.</p>
                </div>
            </div>

        </div>
    </section>

    <!-- SECCIÓN DE MASCOTAS RESIDENTES -->
    <section id="mascotas" class="py-20 bg-[#F5EFEB] border-t border-b border-[#EFECE6]">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <span class="text-xs font-semibold uppercase tracking-wider text-[#8D5B4C]">Adopción y Cuidado</span>
                <h2 class="text-3xl sm:text-4xl font-bold font-serif text-[#332625] mt-2 mb-3">Conoce a algunos de nuestros Amigos</h2>
                <p class="text-[#6B5B5A] max-w-lg mx-auto text-sm sm:text-base">Ellos forman parte de nuestra familia temporal y están buscando un hogar lleno de cariño definitivo.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Mascota 1 -->
                <div class="bg-white rounded-2xl overflow-hidden shadow-sm border border-[#EFECE6] p-6 text-center">
                    <div class="w-32 h-32 mx-auto rounded-full overflow-hidden mb-4 shadow-md">
                        <img src="https://images.unsplash.com/photo-1543466835-00a7907e9de1?auto=format&fit=crop&q=80&w=400" alt="Bruno" class="w-full h-full object-cover">
                    </div>
                    <h3 class="text-xl font-bold font-serif text-[#332625]">Bruno</h3>
                    <span class="inline-block text-xs font-semibold text-[#8D5B4C] bg-[#F5EFEB] px-2.5 py-1 rounded-full mt-1">2 años • Mestizo</span>
                    <p class="text-sm text-[#6B5B5A] mt-4">Amigable, le encanta saludar a los visitantes en la entrada y es experto en dar la patita a cambio de galletas caninas.</p>
                </div>

                <!-- Mascota 2 -->
                <div class="bg-white rounded-2xl overflow-hidden shadow-sm border border-[#EFECE6] p-6 text-center">
                    <div class="w-32 h-32 mx-auto rounded-full overflow-hidden mb-4 shadow-md">
                        <img src="https://images.unsplash.com/photo-1514888286974-6c03e2ca1dba?auto=format&fit=crop&q=80&w=400" alt="Luna" class="w-full h-full object-cover">
                    </div>
                    <h3 class="text-xl font-bold font-serif text-[#332625]">Luna</h3>
                    <span class="inline-block text-xs font-semibold text-[#8D5B4C] bg-[#F5EFEB] px-2.5 py-1 rounded-full mt-1">1 año • Gata Atigrada</span>
                    <p class="text-sm text-[#6B5B5A] mt-4">Tranquila y curiosa. Su lugar favorito es la sección de poesía, donde se acurruca pacientemente a escuchar lecturas.</p>
                </div>

                <!-- Mascota 3 -->
                <div class="bg-white rounded-2xl overflow-hidden shadow-sm border border-[#EFECE6] p-6 text-center">
                    <div class="w-32 h-32 mx-auto rounded-full overflow-hidden mb-4 shadow-md">
                        <img src="https://images.unsplash.com/photo-1583511655857-d19b40a7a54e?auto=format&fit=crop&q=80&w=400" alt="Simón" class="w-full h-full object-cover">
                    </div>
                    <h3 class="text-xl font-bold font-serif text-[#332625]">Simón</h3>
                    <span class="inline-block text-xs font-semibold text-[#8D5B4C] bg-[#F5EFEB] px-2.5 py-1 rounded-full mt-1">3 años • Pequinés Mix</span>
                    <p class="text-sm text-[#6B5B5A] mt-4">Tranquilo, cariñoso y de paso calmado. Ideal para acompañarte durante tus tardes de café y estudio.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- FOOTER / CONTACTO -->
    <footer id="contacto" class="bg-[#332625] text-[#EFECE6] py-16">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 grid grid-cols-1 md:grid-cols-3 gap-10">
            <div>
                <div class="flex items-center space-x-3 mb-4">
                    <div class="w-10 h-10 bg-[#8D5B4C] rounded-full flex items-center justify-center text-white">
                        <i class="fa-solid fa-paw text-lg"></i>
                    </div>
                    <span class="text-2xl font-bold font-serif text-white">Animals Friends</span>
                </div>
                <p class="text-sm text-[#B3A6A4] leading-relaxed">
                    Un espacio comunitario donde el amor por los animales, la buena literatura y el café se unen en perfecta armonía.
                </p>
            </div>

            <div>
                <h4 class="text-white font-serif font-bold text-lg mb-4">Horarios</h4>
                <ul class="space-y-2 text-sm text-[#B3A6A4]">
                    <li>Martes a Viernes: 8:00 AM – 8:00 PM</li>
                    <li>Sábados y Domingos: 9:00 AM – 9:00 PM</li>
                    <li>Lunes: Cerrado por descanso de los peludos</li>
                </ul>
            </div>

            <div>
                <h4 class="text-white font-serif font-bold text-lg mb-4">Encuéntranos</h4>
                <p class="text-sm text-[#B3A6A4] mb-2"><i class="fa-solid fa-location-dot mr-2 text-[#8D5B4C]"></i> Av. de las Mascotas #456, Ciudad</p>
                <p class="text-sm text-[#B3A6A4] mb-4"><i class="fa-solid fa-phone mr-2 text-[#8D5B4C]"></i> +123 456 7890</p>
                <div class="flex space-x-4 text-lg">
                    <a href="#" class="hover:text-[#8D5B4C] transition"><i class="fa-brands fa-instagram"></i></a>
                    <a href="#" class="hover:text-[#8D5B4C] transition"><i class="fa-brands fa-facebook"></i></a>
                    <a href="#" class="hover:text-[#8D5B4C] transition"><i class="fa-brands fa-tiktok"></i></a>
                </div>
            </div>
        </div>
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mt-12 pt-8 border-t border-[#4A3E3D] text-center text-xs text-[#998A88]">
            &copy; 2026 Animals Friends Café y Librería. Todos los derechos reservados.
        </div>
    </footer>

    <!-- SCRIPT PARA EL FILTRO DE LA GALERÍA -->
    <script>
        function filterSelection(category) {
            let items = document.getElementsByClassName("gallery-item");
            if (category == "all") category = "";
            
            for (let i = 0; i < items.length; i++) {
                let item = items[i];
                if (category === "" || item.getAttribute("data-category") === category) {
                    item.style.display = "block";
                } else {
                    item.style.display = "none";
                }
            }

            // Cambiar estilos de los botones activos
            let buttons = document.getElementsByClassName("filter-btn");
            for (let i = 0; i < buttons.length; i++) {
                buttons[i].classList.remove("bg-[#8D5B4C]", "text-white", "shadow-sm");
                buttons[i].classList.add("bg-white", "border", "border-[#DCD3CC]", "text-[#4A3E3D]", "hover:bg-[#F4ECE6]");
            }
            event.target.classList.remove("bg-white", "border", "border-[#DCD3CC]", "text-[#4A3E3D]", "hover:bg-[#F4ECE6]");
            event.target.classList.add("bg-[#8D5B4C]", "text-white", "shadow-sm");
        }
    </script>
</body>
</html>

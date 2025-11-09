<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>María & Juan - Nuestra Boda</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        .font-serif {
            font-family: 'Playfair Display', serif;
        }
        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body class="bg-gradient-to-b from-amber-50 via-green-50 to-amber-50">
    <!-- Decorative top border -->
    <div class="h-2 bg-gradient-to-r from-amber-700 via-emerald-700 to-amber-700"></div>
    
    <!-- Navigation -->
    <nav class="sticky top-0 w-full bg-white/95 backdrop-blur-sm shadow-md z-50 border-b-2 border-emerald-200">
        <div class="max-w-5xl mx-auto px-6 py-4 flex justify-center gap-8 text-emerald-900 uppercase text-xs font-semibold">
            <a href="#home" class="hover:text-emerald-800 transition-colors text-sm tracking-wide">Inicio</a>
            <a href="#locations" class="hover:text-emerald-800 transition-colors text-sm tracking-wide">Ubicaciones</a>
            <a href="#dresscode" class="hover:text-emerald-800 transition-colors text-sm tracking-wide">Vestimenta</a>
            <a href="#registry" class="hover:text-emerald-800 transition-colors text-sm tracking-wide">Regalos</a>
            <a href="#recommendations" class="hover:text-emerald-800 transition-colors text-sm tracking-wide">Hospedaje</a>
            <a href="#gallery" class="hover:text-emerald-800 transition-colors text-sm tracking-wide">Galería</a>
            <a href="#itinerary" class="hover:text-emerald-800 transition-colors text-sm tracking-wide">Programa</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="min-h-screen flex items-center justify-center pt-12 px-6 relative overflow-hidden">
        <!-- Decorative elements -->
        <div class="absolute top-20 left-10 opacity-20">
            <svg class="w-32 h-32 text-emerald-600" fill="none" stroke="currentColor" stroke-width="1" viewBox="0 0 24 24">
                <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>
            </svg>
        </div>
        <div class="absolute bottom-20 right-10 opacity-20">
            <svg class="w-40 h-40 text-amber-600" fill="none" stroke="currentColor" stroke-width="1" viewBox="0 0 24 24">
                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"/>
            </svg>
        </div>
        
        <div class="text-center max-w-3xl relative z-10">
            <div class="mb-8">
                <svg class="w-16 h-16 mx-auto text-emerald-700 mb-6" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24">
                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2z"/>
                </svg>
                <div class="flex items-center justify-center gap-4 mb-6">
                    <div class="w-24 h-px bg-gradient-to-r from-transparent via-amber-600 to-transparent"></div>
                    <svg class="w-6 h-6 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                    </svg>
                    <div class="w-24 h-px bg-gradient-to-r from-transparent via-amber-600 to-transparent"></div>
                </div>
            </div>
            
            <p class="text-sm uppercase tracking-widest text-emerald-800 mb-8 font-semibold">
                Unidos en Amor
            </p>
            
            <h1 class="text-7xl md:text-8xl font-serif text-amber-900 mb-4 drop-shadow-sm">
                María
            </h1>
            <div class="my-6">
                <svg class="w-10 h-10 mx-auto text-rose-600 fill-rose-600" viewBox="0 0 24 24">
                    <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
                </svg>
            </div>
            <h1 class="text-7xl md:text-8xl font-serif text-amber-900 mb-12 drop-shadow-sm">
                Juan
            </h1>
            
            <div class="flex items-center justify-center gap-4 my-8">
                <div class="w-20 h-px bg-gradient-to-r from-transparent via-emerald-600 to-transparent"></div>
                <svg class="w-5 h-5 text-amber-700" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <circle cx="12" cy="12" r="10"/>
                </svg>
                <div class="w-20 h-px bg-gradient-to-r from-transparent via-emerald-600 to-transparent"></div>
            </div>
            
            <div class="bg-white/80 backdrop-blur-sm border-2 border-emerald-300 rounded-lg shadow-xl p-8 mb-10">
                <p class="text-lg tracking-wide text-emerald-900 mb-2 font-semibold">
                    Sábado
                </p>
                <p class="text-3xl font-serif text-amber-800 mb-1">
                    15 de Junio
                </p>
                <p class="text-2xl font-serif text-amber-700">
                    2025
                </p>
            </div>
            
            <!-- Countdown -->
            <p class="text-sm uppercase tracking-wider text-emerald-800 mb-4 font-semibold">Faltan</p>
            <div class="flex justify-center gap-4 mb-8">
                <div class="text-center">
                    <div class="bg-gradient-to-br from-amber-100 to-green-100 border-2 border-emerald-400 rounded-lg shadow-lg px-4 py-4 min-w-[85px]">
                        <div class="text-4xl font-serif text-amber-900" id="days">0</div>
                        <div class="text-xs uppercase tracking-wide text-emerald-800 mt-2 font-semibold">Días</div>
                    </div>
                </div>
                <div class="text-center">
                    <div class="bg-gradient-to-br from-amber-100 to-green-100 border-2 border-emerald-400 rounded-lg shadow-lg px-4 py-4 min-w-[85px]">
                        <div class="text-4xl font-serif text-amber-900" id="hours">0</div>
                        <div class="text-xs uppercase tracking-wide text-emerald-800 mt-2 font-semibold">Horas</div>
                    </div>
                </div>
                <div class="text-center">
                    <div class="bg-gradient-to-br from-amber-100 to-green-100 border-2 border-emerald-400 rounded-lg shadow-lg px-4 py-4 min-w-[85px]">
                        <div class="text-4xl font-serif text-amber-900" id="minutes">0</div>
                        <div class="text-xs uppercase tracking-wide text-emerald-800 mt-2 font-semibold">Min</div>
                    </div>
                </div>
                <div class="text-center">
                    <div class="bg-gradient-to-br from-amber-100 to-green-100 border-2 border-emerald-400 rounded-lg shadow-lg px-4 py-4 min-w-[85px]">
                        <div class="text-4xl font-serif text-amber-900" id="seconds">0</div>
                        <div class="text-xs uppercase tracking-wide text-emerald-800 mt-2 font-semibold">Seg</div>
                    </div>
                </div>
            </div>
            
            <div class="flex items-center justify-center gap-3 mt-12">
                <svg class="w-5 h-5 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                </svg>
                <div class="w-16 h-px bg-emerald-400"></div>
                <svg class="w-6 h-6 text-amber-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <circle cx="12" cy="12" r="10"/>
                </svg>
                <div class="w-16 h-px bg-emerald-400"></div>
                <svg class="w-5 h-5 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                </svg>
            </div>
        </div>
    </section>

    <!-- Locations Section -->
    <section id="locations" class="py-20 px-6 bg-gradient-to-b from-white to-green-50">
        <div class="max-w-5xl mx-auto">
            <div class="text-center mb-16">
                <svg class="w-12 h-12 mx-auto mb-4 text-emerald-700" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24">
                    <circle cx="12" cy="12" r="10"/>
                </svg>
                <p class="text-xs uppercase tracking-widest text-emerald-800 mb-4 font-semibold">Dónde Celebraremos</p>
                <h2 class="text-5xl font-serif text-amber-900 mb-4">
                    Nuestras Ubicaciones
                </h2>
                <div class="flex items-center justify-center gap-3 mt-6">
                    <div class="w-20 h-px bg-gradient-to-r from-transparent via-emerald-500 to-transparent"></div>
                    <svg class="w-4 h-4 text-amber-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                    </svg>
                    <div class="w-20 h-px bg-gradient-to-r from-transparent via-emerald-500 to-transparent"></div>
                </div>
            </div>
            
            <div class="grid md:grid-cols-2 gap-8">
                <!-- Church -->
                <div class="bg-white border-4 border-emerald-200 rounded-xl shadow-xl p-10 relative overflow-hidden">
                    <div class="absolute top-4 right-4 opacity-10">
                        <svg class="w-32 h-32 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <circle cx="12" cy="12" r="10"/>
                        </svg>
                    </div>
                    <div class="relative z-10">
                        <svg class="w-8 h-8 mx-auto mb-4 text-emerald-700" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                            <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/>
                            <circle cx="12" cy="10" r="3"/>
                        </svg>
                        <div class="h-1 w-16 bg-gradient-to-r from-amber-600 to-emerald-600 mx-auto mb-6 rounded"></div>
                        <h3 class="text-3xl font-serif mb-6 text-amber-900 text-center">Ceremonia Religiosa</h3>
                        <p class="text-xl text-emerald-900 mb-3 text-center font-semibold">Parroquia de San Miguel Arcángel</p>
                        <p class="text-amber-800 mb-2 text-center">Avenida Principal Número 123</p>
                        <p class="text-amber-700 mb-6 text-center">Centro Histórico</p>
                        <div class="bg-gradient-to-r from-emerald-100 to-amber-100 border-2 border-emerald-300 rounded-lg p-4 mb-6">
                            <p class="text-2xl font-serif text-emerald-900 text-center">4:00 PM</p>
                        </div>
                        <div class="text-center">
                            <a 
                                href="https://maps.google.com" 
                                target="_blank" 
                                rel="noopener noreferrer"
                                class="inline-block bg-gradient-to-r from-emerald-700 to-emerald-600 text-white px-8 py-3 rounded-full text-sm uppercase tracking-wide hover:from-emerald-800 hover:to-emerald-700 transition-all shadow-lg font-semibold"
                            >
                                Ver en el Mapa
                            </a>
                        </div>
                    </div>
                </div>

                <!-- Reception -->
                <div class="bg-white border-4 border-amber-200 rounded-xl shadow-xl p-10 relative overflow-hidden">
                    <div class="absolute top-4 right-4 opacity-10">
                        <svg class="w-32 h-32 text-amber-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                        </svg>
                    </div>
                    <div class="relative z-10">
                        <svg class="w-8 h-8 mx-auto mb-4 text-amber-700" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                            <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/>
                            <circle cx="12" cy="10" r="3"/>
                        </svg>
                        <div class="h-1 w-16 bg-gradient-to-r from-emerald-600 to-amber-600 mx-auto mb-6 rounded"></div>
                        <h3 class="text-3xl font-serif mb-6 text-amber-900 text-center">Recepción</h3>
                        <p class="text-xl text-emerald-900 mb-3 text-center font-semibold">Hacienda Los Olivos</p>
                        <p class="text-amber-800 mb-2 text-center">Camino Real Kilómetro 5</p>
                        <p class="text-amber-700 mb-6 text-center">Valle Verde</p>
                        <div class="bg-gradient-to-r from-amber-100 to-emerald-100 border-2 border-amber-300 rounded-lg p-4 mb-6">
                            <p class="text-2xl font-serif text-amber-900 text-center">6:00 PM</p>
                        </div>
                        <div class="text-center">
                            <a 
                                href="https://maps.google.com" 
                                target="_blank" 
                                rel="noopener noreferrer"
                                class="inline-block bg-gradient-to-r from-amber-700 to-amber-600 text-white px-8 py-3 rounded-full text-sm uppercase tracking-wide hover:from-amber-800 hover:to-amber-700 transition-all shadow-lg font-semibold"
                            >
                                Ver en el Mapa
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Dress Code Section -->
    <section id="dresscode" class="py-20 px-6 bg-gradient-to-b from-green-50 to-amber-50">
        <div class="max-w-4xl mx-auto text-center">
            <svg class="w-12 h-12 mx-auto mb-4 text-amber-700" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24">
                <path d="M12 2L2 7l10 5 10-5-10-5z"/>
            </svg>
            <p class="text-xs uppercase tracking-widest text-emerald-800 mb-4 font-semibold">Código de Vestimenta</p>
            <h2 class="text-5xl font-serif mb-6 text-amber-900">
                Etiqueta de Gala
            </h2>
            <div class="flex items-center justify-center gap-3 mb-12">
                <div class="w-20 h-px bg-gradient-to-r from-transparent via-amber-500 to-transparent"></div>
                <svg class="w-4 h-4 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <circle cx="12" cy="12" r="10"/>
                </svg>
                <div class="w-20 h-px bg-gradient-to-r from-transparent via-amber-500 to-transparent"></div>
            </div>
            
            <div class="bg-white border-4 border-double border-emerald-300 rounded-xl shadow-2xl p-12 relative overflow-hidden">
                <div class="relative z-10">
                    <p class="text-5xl font-serif mb-6 text-emerald-900">
                        Formal
                    </p>
                    <p class="text-amber-800 mb-10 text-lg italic">Etiqueta rigurosa</p>
                    
                    <div class="grid md:grid-cols-2 gap-10 mb-10">
                        <div class="bg-gradient-to-br from-emerald-50 to-amber-50 border-2 border-emerald-300 rounded-lg p-8">
                            <div class="w-36 h-36 bg-gradient-to-br from-gray-800 to-gray-900 rounded-lg mx-auto mb-6 shadow-lg border-4 border-amber-200"></div>
                            <p class="text-emerald-900 font-semibold text-xl mb-2">Caballeros</p>
                            <p class="text-amber-800">Traje oscuro o smoking</p>
                            <p class="text-sm text-emerald-700 mt-2">Corbata de preferencia</p>
                        </div>
                        <div class="bg-gradient-to-br from-amber-50 to-emerald-50 border-2 border-amber-300 rounded-lg p-8">
                            <div class="w-36 h-36 bg-gradient-to-br from-rose-300 via-purple-200 to-pink-200 rounded-lg mx-auto mb-6 shadow-lg border-4 border-emerald-200"></div>
                            <p class="text-emerald-900 font-semibold text-xl mb-2">Damas</p>
                            <p class="text-amber-800">Vestido largo de gala</p>
                            <p class="text-sm text-emerald-700 mt-2">Colores vibrantes bienvenidos</p>
                        </div>
                    </div>
                    
                    <div class="flex items-center justify-center gap-3 my-8">
                        <div class="w-16 h-px bg-amber-400"></div>
                        <svg class="w-5 h-5 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <circle cx="12" cy="12" r="10"/>
                        </svg>
                        <div class="w-16 h-px bg-amber-400"></div>
                    </div>
                    
                    <div class="bg-amber-100 border-2 border-amber-300 rounded-lg p-6">
                        <p class="text-sm text-amber-900 italic font-semibold">
                            Reservado para la novia: blanco, marfil y beige
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Registry Section -->
    <section id="registry" class="py-20 px-6 bg-gradient-to-b from-amber-50 to-white">
        <div class="max-w-4xl mx-auto">
            <div class="text-center mb-16">
                <svg class="w-12 h-12 mx-auto mb-4 text-emerald-700" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24">
                    <path d="M20 7h-4V5a2 2 0 00-2-2h-4a2 2 0 00-2 2v2H4a2 2 0 00-2 2v10a2 2 0 002 2h16a2 2 0 002-2V9a2 2 0 00-2-2zm-6 0h-4V5h4v2z"/>
                </svg>
                <p class="text-xs uppercase tracking-widest text-emerald-800 mb-4 font-semibold">Mesa de Regalos</p>
                <h2 class="text-5xl font-serif text-amber-900">
                    Vuestros Obsequios
                </h2>
                <div class="flex items-center justify-center gap-3 mt-6">
                    <div class="w-20 h-px bg-gradient-to-r from-transparent via-emerald-500 to-transparent"></div>
                    <svg class="w-4 h-4 text-rose-600 fill-rose-600" viewBox="0 0 24 24">
                        <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
                    </svg>
                    <div class="w-20 h-px bg-gradient-to-r from-transparent via-emerald-500 to-transparent"></div>
                </div>
            </div>
            
            <div class="bg-white border-4 border-double border-amber-300 rounded-xl shadow-2xl p-12 relative overflow-hidden">
                <div class="relative z-10">
                    <p class="text-center text-amber-900 mb-10 leading-relaxed text-lg italic">
                        Vuestra presencia es el mayor regalo que podríamos recibir.
                        <br />
                        Si deseáis honrarnos con un presente, hemos preparado las siguientes opciones:
                    </p>
                    
                    <div class="space-y-6">
                        <div class="bg-gradient-to-r from-emerald-50 to-amber-50 border-2 border-emerald-300 rounded-lg p-8 text-center">
                            <div class="inline-block bg-white rounded-full p-3 mb-4">
                                <svg class="w-6 h-6 text-emerald-700" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path d="M20 7h-4V5a2 2 0 00-2-2h-4a2 2 0 00-2 2v2H4a2 2 0 00-2 2v10a2 2 0 002 2h16a2 2 0 002-2V9a2 2 0 00-2-2z"/>
                                </svg>
                            </div>
                            <h3 class="text-2xl font-serif mb-3 text-emerald-900">Liverpool</h3>
                            <p class="text-amber-800 mb-2 font-semibold">Número de evento</p>
                            <p class="text-emerald-900 text-2xl font-bold">12345678</p>
                        </div>
                        
                        <div class="bg-gradient-to-r from-amber-50 to-emerald-50 border-2 border-amber-300 rounded-lg p-8 text-center">
                            <div class="inline-block bg-white rounded-full p-3 mb-4">
                                <svg class="w-6 h-6 text-amber-700" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path d="M20 7h-4V5a2 2 0 00-2-2h-4a2 2 0 00-2 2v2H4a2 2 0 00-2 2v10a2 2 0 002 2h16a2 2 0 002-2V9a2 2 0 00-2-2z"/>
                                </svg>
                            </div>
                            <h3 class="text-2xl font-serif mb-3 text-amber-900">Amazon</h3>
                            <a href="#" class="text-emerald-700 hover:text-emerald-900 underline decoration-2 decoration-emerald-400 font-semibold text-lg">
                                Ver nuestra lista de deseos
                            </a>
                        </div>
                        
                        <div class="bg-gradient-to-r from-emerald-50 to-amber-50 border-2 border-emerald-300 rounded-lg p-8 text-center">
                            <div class="inline-block bg-white rounded-full p-3 mb-4">
                                <svg class="w-6 h-6 text-rose-600 fill-rose-600" viewBox="0 0 24 24">
                                    <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
                                </svg>
                            </div>
                            <h3 class="text-2xl font-serif mb-3 text-emerald-900">Lluvia de Sobres</h3>
                            <p class="text-amber-800 font-semibold">Habrá un buzón especial en la recepción</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Recommendations Section -->
    <section id="recommendations" class="py-20 px-6 bg-gradient-to-b from-white to-green-50">
        <div class="max-w-5xl mx-auto">
            <div class="text-center mb-16">
                <svg class="w-12 h-12 mx-auto mb-4 text-amber-700" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24">
                    <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                </svg>
                <p class="text-xs uppercase tracking-widest text-emerald-800 mb-4 font-semibold">Para Invitados de Fuera</p>
                <h2 class="text-5xl font-serif text-amber-900">
                    Hospedaje y Visitas
                </h2>
                <div class="flex items-center justify-center gap-3 mt-6">
                    <div class="w-20 h-px bg-gradient-to-r from-transparent via-amber-500 to-transparent"></div>
                    <svg class="w-4 h-4 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <circle cx="12" cy="12" r="10"/>
                    </svg>
                    <div class="w-20 h-px bg-gradient-to-r from-transparent via-amber-500 to-transparent"></div>
                </div>
            </div>
            
            <div class="grid md:grid-cols-2 gap-8">
                <div class="bg-white border-4 border-emerald-200 rounded-xl shadow-xl p-10">
                    <div class="text-center mb-8">
                        <div class="inline-block bg-gradient-to-br from-emerald-100 to-amber-100 rounded-full p-4 mb-4">
                            <svg class="w-8 h-8 text-emerald-700" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/>
                            </svg>
                        </div>
                        <h3 class="text-3xl font-serif text-emerald-900">Alojamiento</h3>
                        <div class="w-16 h-1 bg-gradient-to-r from-emerald-500 to-amber-500 mx-auto mt-4 rounded"></div>
                    </div>
                    
                    <div class="space-y-6">
                        <div class="bg-gradient-to-r from-emerald-50 to-amber-50 border-l-4 border-emerald-600 rounded-lg p-6">
                            <h4 class="text-xl font-serif text-emerald-900 mb-2">Hotel Boutique Centro</h4>
                            <p class="text-amber-800 mb-1 font-semibold">A 10 minutos de los eventos</p>
                            <p class="text-emerald-700 text-sm">Teléfono: (555) 123-4567</p>
                        </div>
                        <div class="bg-gradient-to-r from-amber-50 to-emerald-50 border-l-4 border-amber-600 rounded-lg p-6">
                            <h4 class="text-xl font-serif text-emerald-900 mb-2">Grand Hotel Plaza</h4>
                            <p class="text-amber-800 mb-1 font-semibold">A 15 minutos de los eventos</p>
                            <p class="text-emerald-700 text-sm">Teléfono: (555) 987-6543</p>
                        </div>
                    </div>
                </div>

                <div class="bg-white border-4 border-amber-200 rounded-xl shadow-xl p-10">
                    <div class="text-center mb-8">
                        <div class="inline-block bg-gradient-to-br from-amber-100 to-emerald-100 rounded-full p-4 mb-4">
                            <svg class="w-8 h-8 text-amber-700" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <circle cx="12" cy="12" r="10"/>
                            </svg>
                        </div>
                        <h3 class="text-3xl font-serif text-amber-900">Sitios de Interés</h3>
                        <div class="w-16 h-1 bg-gradient-to-r from-amber-500 to-emerald-500 mx-auto mt-4 rounded"></div>
                    </div>
                    
                    <div class="space-y-4">
                        <div class="bg-gradient-to-r from-amber-50 to-emerald-50 border-l-4 border-amber-500 rounded-lg p-4">
                            <p class="text-emerald-900 font-semibold">Centro Histórico</p>
                        </div>
                        <div class="bg-gradient-to-r from-emerald-50 to-amber-50 border-l-4 border-emerald-500 rounded-lg p-4">
                            <p class="text-emerald-900 font-semibold">Museo de Arte Contemporáneo</p>
                        </div>
                        <div class="bg-gradient-to-r from-amber-50 to-emerald-50 border-l-4 border-amber-500 rounded-lg p-4">
                            <p class="text-emerald-900 font-semibold">Mercado de Artesanías</p>
                        </div>
                        <div class="bg-gradient-to-r from-emerald-50 to-amber-50 border-l-4 border-emerald-500 rounded-lg p-4">
                            <p class="text-emerald-900 font-semibold">Parque Natural La Sierra</p>
                        </div>
                        <div class="bg-gradient-to-r from-amber-50 to-emerald-50 border-l-4 border-amber-500 rounded-lg p-4">
                            <p class="text-emerald-900 font-semibold">Zona Gastronómica del Barrio Viejo</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section id="gallery" class="py-20 px-6 bg-gradient-to-b from-green-50 to-amber-50">
        <div class="max-w-6xl mx-auto">
            <div class="text-center mb-16">
                <svg class="w-12 h-12 mx-auto mb-4 text-rose-600 fill-rose-600" viewBox="0 0 24 24">
                    <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
                </svg>
                <p class="text-xs uppercase tracking-widest text-emerald-800 mb-4 font-semibold">Momentos Especiales</p>
                <h2 class="text-5xl font-serif text-amber-900">
                    Nuestra Historia de Amor
                </h2>
                <div class="flex items-center justify-center gap-3 mt-6">
                    <div class="w-20 h-px bg-gradient-to-r from-transparent via-emerald-500 to-transparent"></div>
                    <svg class="w-4 h-4 text-amber-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                    </svg>
                    <div class="w-20 h-px bg-gradient-to-r from-transparent via-emerald-500 to-transparent"></div>
                </div>
            </div>
            
            <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
                <div class="aspect-square border-4 border-emerald-300 bg-gradient-to-br from-amber-100 to-green-100 rounded-lg shadow-lg flex items-center justify-center hover:scale-105 transition-transform relative overflow-hidden">
                    <div class="absolute inset-0 bg-white/30"></div>
                    <svg class="w-16 h-16 text-emerald-600 opacity-30 relative z-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <circle cx="12" cy="12" r="10"/>
                    </svg>
                </div>
                <div class="aspect-square border-4 border-emerald-300 bg-gradient-to-br from-amber-100 to-green-100 rounded-lg shadow-lg flex items-center justify-center hover:scale-105 transition-transform relative overflow-hidden">
                    <div class="absolute inset-0 bg-white/30"></div>
                    <svg class="w-16 h-16 text-emerald-600 opacity-30 relative z-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <circle cx="12" cy="12" r="10"/>
                    </svg>
                </div>
                <div class="aspect-square border-4 border-emerald-300 bg-gradient-to-br from-amber-100 to-green-100 rounded-lg shadow-lg flex items-center justify-center hover:scale-105 transition-transform relative overflow-hidden">
                    <div class="absolute inset-0 bg-white/30"></div>
                    <svg class="w-16 h-16 text-emerald-600 opacity-30 relative z-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <circle cx="12" cy="12" r="10"/>
                    </svg>
                </div>
                <div class="aspect-square border-4 border-emerald-300 bg-gradient-to-br from-amber-100 to-green-100 rounded-lg shadow-lg flex items-center justify-center hover:scale-105 transition-transform relative overflow-hidden">
                    <div class="absolute inset-0 bg-white/30"></div>
                    <svg class="w-16 h-16 text-emerald-600 opacity-30 relative z-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <circle cx="12" cy="12" r="10"/>
                    </svg>
                </div>
                <div class="aspect-square border-4 border-emerald-300 bg-gradient-to-br from-amber-100 to-green-100 rounded-lg shadow-lg flex items-center justify-center hover:scale-105 transition-transform relative overflow-hidden">
                    <div class="absolute inset-0 bg-white/30"></div>
                    <svg class="w-16 h-16 text-emerald-600 opacity-30 relative z-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <circle cx="12" cy="12" r="10"/>
                    </svg>
                </div>
                <div class="aspect-square border-4 border-emerald-300 bg-gradient-to-br from-amber-100 to-green-100 rounded-lg shadow-lg flex items-center justify-center hover:scale-105 transition-transform relative overflow-hidden">
                    <div class="absolute inset-0 bg-white/30"></div>
                    <svg class="w-16 h-16 text-emerald-600 opacity-30 relative z-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <circle cx="12" cy="12" r="10"/>
                    </svg>
                </div>
                <div class="aspect-square border-4 border-emerald-300 bg-gradient-to-br from-amber-100 to-green-100 rounded-lg shadow-lg flex items-center justify-center hover:scale-105 transition-transform relative overflow-hidden">
                    <div class="absolute inset-0 bg-white/30"></div>
                    <svg class="w-16 h-16 text-emerald-600 opacity-30 relative z-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <circle cx="12" cy="12" r="10"/>
                    </svg>
                </div>
                <div class="aspect-square border-4 border-emerald-300 bg-gradient-to-br from-amber-100 to-green-100 rounded-lg shadow-lg flex items-center justify-center hover:scale-105 transition-transform relative overflow-hidden">
                    <div class="absolute inset-0 bg-white/30"></div>
                    <svg class="w-16 h-16 text-emerald-600 opacity-30 relative z-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <circle cx="12" cy="12" r="10"/>
                    </svg>
                </div>
            </div>
            <p class="text-center text-amber-800 mt-10 italic text-lg font-semibold">
                Colocar vuestras fotografías favoritas
            </p>
        </div>
    </section>

    <!-- Itinerary Section -->
    <section id="itinerary" class="py-20 px-6 bg-gradient-to-b from-amber-50 to-white">
        <div class="max-w-4xl mx-auto">
            <div class="text-center mb-16">
                <svg class="w-12 h-12 mx-auto mb-4 text-emerald-700" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24">
                    <circle cx="12" cy="12" r="10"/>
                    <path d="M12 6v6l4 2"/>
                </svg>
                <p class="text-xs uppercase tracking-widest text-emerald-800 mb-4 font-semibold">Cronograma</p>
                <h2 class="text-5xl font-serif text-amber-900">
                    Programa del Día
                </h2>
                <div class="flex items-center justify-center gap-3 mt-6">
                    <div class="w-20 h-px bg-gradient-to-r from-transparent via-amber-500 to-transparent"></div>
                    <svg class="w-4 h-4 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <circle cx="12" cy="12" r="10"/>
                    </svg>
                    <div class="w-20 h-px bg-gradient-to-r from-transparent via-amber-500 to-transparent"></div>
                </div>
            </div>
            
            <div class="bg-white border-4 border-double border-emerald-300 rounded-xl shadow-2xl p-10 relative overflow-hidden">
                <div class="space-y-8 relative z-10">
                    <div class="flex items-start bg-gradient-to-r from-emerald-50 to-amber-50 border-l-4 border-emerald-600 rounded-lg p-6 shadow-md">
                        <div class="min-w-[100px] mr-6 text-right">
                            <p class="text-3xl font-serif text-emerald-900">4:00</p>
                            <p class="text-xs uppercase tracking-wider text-amber-700 mt-1 font-semibold">PM</p>
                        </div>
                        <div class="flex-1 pt-2">
                            <h3 class="text-2xl font-serif text-amber-900 mb-2">Ceremonia Religiosa</h3>
                            <p class="text-emerald-800 font-semibold">Parroquia de San Miguel Arcángel</p>
                        </div>
                        <svg class="w-8 h-8 text-emerald-600 ml-4" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24">
                            <circle cx="12" cy="12" r="10"/>
                        </svg>
                    </div>
                    
                    <div class="flex items-start bg-gradient-to-r from-amber-50 to-emerald-50 border-l-4 border-amber-600 rounded-lg p-6 shadow-md">
                        <div class="min-w-[100px] mr-6 text-right">
                            <p class="text-3xl font-serif text-amber-900">6:00</p>
                            <p class="text-xs uppercase tracking-wider text-emerald-700 mt-1 font-semibold">PM</p>
                        </div>
                        <div class="flex-1 pt-2">
                            <h3 class="text-2xl font-serif text-amber-900 mb-2">Cóctel de Recepción</h3>
                            <p class="text-emerald-800 font-semibold">Jardines de Hacienda Los Olivos</p>
                        </div>
                        <svg class="w-8 h-8 text-amber-600 ml-4" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24">
                            <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                        </svg>
                    </div>
                    
                    <div class="flex items-start bg-gradient-to-r from-emerald-50 to-amber-50 border-l-4 border-emerald-600 rounded-lg p-6 shadow-md">
                        <div class="min-w-[100px] mr-6 text-right">
                            <p class="text-3xl font-serif text-emerald-900">7:30</p>
                            <p class="text-xs uppercase tracking-wider text-amber-700 mt-1 font-semibold">PM</p>
                        </div>
                        <div class="flex-1 pt-2">
                            <h3 class="text-2xl font-serif text-amber-900 mb-2">Cena de Gala</h3>
                            <p class="text-emerald-800 font-semibold">Salón Principal</p>
                        </div>
                        <svg class="w-8 h-8 text-emerald-600 ml-4" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24">
                            <circle cx="12" cy="12" r="10"/>
                        </svg>
                    </div>
                    
                    <div class="flex items-start bg-gradient-to-r from-amber-50 to-emerald-50 border-l-4 border-amber-600 rounded-lg p-6 shadow-md">
                        <div class="min-w-[100px] mr-6 text-right">
                            <p class="text-3xl font-serif text-amber-900">9:00</p>
                            <p class="text-xs uppercase tracking-wider text-emerald-700 mt-1 font-semibold">PM</p>
                        </div>
                        <div class="flex-1 pt-2">
                            <h3 class="text-2xl font-serif text-amber-900 mb-2">Vals de los Novios</h3>
                            <p class="text-emerald-800 font-semibold">Apertura de Pista de Baile</p>
                        </div>
                        <svg class="w-8 h-8 text-rose-600 fill-rose-600 ml-4" stroke-width="1.5" viewBox="0 0 24 24">
                            <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
                        </svg>
                    </div>
                    
                    <div class="flex items-start bg-gradient-to-r from-emerald-50 to-amber-50 border-l-4 border-emerald-600 rounded-lg p-6 shadow-md">
                        <div class="min-w-[100px] mr-6 text-right">
                            <p class="text-3xl font-serif text-emerald-900">9:30</p>
                            <p class="text-xs uppercase tracking-wider text-amber-700 mt-1 font-semibold">PM</p>
                        </div>
                        <div class="flex-1 pt-2">
                            <h3 class="text-2xl font-serif text-amber-900 mb-2">Baile y Celebración</h3>
                            <p class="text-emerald-800 font-semibold">¡A bailar hasta el amanecer!</p>
                        </div>
                        <svg class="w-8 h-8 text-amber-600 ml-4" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24">
                            <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                        </svg>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gradient-to-b from-emerald-900 to-emerald-950 text-white py-16 px-6 text-center relative overflow-hidden">
        <div class="absolute top-10 left-10 opacity-10">
            <svg class="w-32 h-32 text-amber-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <circle cx="12" cy="12" r="10"/>
            </svg>
        </div>
        <div class="absolute bottom-10 right-10 opacity-10">
            <svg class="w-32 h-32 text-amber-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path d="M12 2L2 7l10 5 10-5-10-5z"/>
            </svg>
        </div>
        
        <div class="relative z-10">
            <div class="flex items-center justify-center gap-3 mb-6">
                <div class="w-16 h-px bg-amber-400"></div>
                <svg class="w-8 h-8 text-rose-400 fill-rose-400" viewBox="0 0 24 24">
                    <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
                </svg>
                <div class="w-16 h-px bg-amber-400"></div>
            </div>
            
            <p class="text-4xl font-serif mb-4 text-amber-100">
                María & Juan
            </p>
            <p class="text-amber-300 mb-2 tracking-wide text-lg">15 de Junio de 2025</p>
            
            <div class="flex items-center justify-center gap-3 my-8">
                <svg class="w-5 h-5 text-amber-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                </svg>
                <div class="w-12 h-px bg-amber-400"></div>
                <svg class="w-6 h-6 text-amber-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <circle cx="12" cy="12" r="10"/>
                </svg>
                <div class="w-12 h-px bg-amber-400"></div>
                <svg class="w-5 h-5 text-amber-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                </svg>
            </div>
            
            <p class="text-emerald-200 text-lg italic">
                Será un honor celebrar este día tan especial con vosotros
            </p>
        </div>
    </footer>
    
    <div class="h-2 bg-gradient-to-r from-amber-700 via-emerald-700 to-amber-700"></div>

    <script>
        // Countdown Timer
        function updateCountdown() {
            const weddingDate = new Date('2025-06-15T16:00:00').getTime();
            const now = new Date().getTime();
            const difference = weddingDate - now;
            
            const days = Math.floor(difference / (1000 * 60 * 60 * 24));
            const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((difference % (1000 * 60)) / 1000);
            
            document.getElementById('days').textContent = days;
            document.getElementById('hours').textContent = hours;
            document.getElementById('minutes').textContent = minutes;
            document.getElementById('seconds').textContent = seconds;
        }
        
        updateCountdown();
        setInterval(updateCountdown, 1000);
    </script>
</body>
</html>

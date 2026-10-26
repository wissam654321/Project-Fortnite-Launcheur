<!DOCTYPE html>
<html lang="fr" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Launcheur Fortnite V1 - Showcase</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600;700&family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        fn: {
                            purple: '#8a2be2',
                            neon: '#00d2ff',
                            dark: '#0a0914',
                            card: '#131127',
                            accent: '#ff007f'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        mono: ['Fira Code', 'monospace']
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #0a0914;
            color: #f3f4f6;
            background-image: 
                radial-gradient(circle at 15% 20%, rgba(138, 43, 226, 0.15) 0%, transparent 40%),
                radial-gradient(circle at 85% 80%, rgba(0, 210, 255, 0.12) 0%, transparent 40%);
        }

        .neon-glow {
            box-shadow: 0 0 25px rgba(138, 43, 226, 0.4), 0 0 10px rgba(0, 210, 255, 0.3);
        }

        .neon-text {
            text-shadow: 0 0 10px rgba(0, 210, 255, 0.6), 0 0 20px rgba(138, 43, 226, 0.6);
        }

        .custom-scrollbar::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
            background: #0d0c1d;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: #262242;
            border-radius: 4px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb:hover {
            background: #8a2be2;
        }

        /* Scanline Terminal Effect */
        .terminal-bg {
            background: linear-gradient(rgba(18, 16, 38, 0.95), rgba(10, 9, 20, 0.98)),
                        repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0, 0, 0, 0.2) 3px);
        }
    </style>
</head>
<body class="min-h-screen font-sans flex flex-col justify-between selection:bg-purple-600 selection:text-white">

    <!-- Header Navigation -->
    <header class="border-b border-purple-900/40 bg-fn-dark/80 backdrop-blur-md sticky top-0 z-50">
        <div class="max-w-6xl mx-auto px-4 py-4 flex justify-between items-center">
            <div class="flex items-center gap-3">
                <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-purple-600 to-cyan-400 flex items-center justify-center text-white font-extrabold text-xl shadow-lg shadow-purple-500/30">
                    F
                </div>
                <div>
                    <h1 class="text-lg font-bold tracking-wide text-white flex items-center gap-2">
                        Launcheur Fortnite <span class="bg-purple-600/30 text-cyan-400 text-xs px-2 py-0.5 rounded-full border border-cyan-400/30 font-mono">v1.0</span>
                    </h1>
                    <p class="text-xs text-gray-400">Script Batch Open Source pour GitHub</p>
                </div>
            </div>

            <div class="flex items-center gap-3">
                <button onclick="copyCode()" class="px-4 py-2 bg-purple-900/40 hover:bg-purple-800/60 border border-purple-500/40 text-purple-200 text-sm font-medium rounded-lg transition-all flex items-center gap-2 active:scale-95">
                    <i class="fa-regular fa-copy"></i>
                    <span id="copyBtnText">Copier le Code</span>
                </button>
                <button onclick="downloadBat()" class="px-4 py-2 bg-gradient-to-r from-purple-600 to-cyan-500 hover:from-purple-500 hover:to-cyan-400 text-white text-sm font-semibold rounded-lg shadow-md hover:shadow-cyan-500/20 transition-all flex items-center gap-2 active:scale-95">
                    <i class="fa-solid fa-download"></i>
                    <span>Télécharger .bat</span>
                </button>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="max-w-6xl mx-auto px-4 py-8 flex-1 w-full space-y-10">

        <!-- Hero Section -->
        <section class="text-center space-y-4 max-w-3xl mx-auto pt-4">
            <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-purple-900/30 border border-purple-500/30 text-cyan-300 text-xs font-mono mb-2">
                <i class="fa-solid fa-bolt text-yellow-400"></i> Lancement Direct Sans Anti-Cheat Bug
            </div>
            <h2 class="text-4xl md:text-5xl font-extrabold tracking-tight text-white">
                Un Launcher Fortnite <span class="text-transparent bg-clip-text bg-gradient-to-r from-purple-400 via-cyan-400 to-pink-500">Rapide & Infaillible</span>
            </h2>
            <p class="text-gray-300 text-base md:text-lg">
                Un script Batch `.bat` universel conçu pour exécuter Fortnite instantanément depuis ton bureau. 100% anonyme, zéro bug et prêt à être partagé sur GitHub !
            </p>
        </section>

        <!-- Interactive Terminal Simulator -->
        <section class="space-y-3">
            <div class="flex justify-between items-center px-1">
                <h3 class="text-sm font-semibold text-gray-400 uppercase tracking-wider flex items-center gap-2">
                    <i class="fa-solid fa-terminal text-cyan-400"></i> Aperçu de la Console Windows (cmd.exe)
                </h3>
                <button onclick="restartTerminalAnimation()" class="text-xs text-purple-400 hover:text-cyan-300 transition-colors flex items-center gap-1">
                    <i class="fa-solid fa-rotate-right"></i> Relancer la simulation
                </button>
            </div>

            <div class="rounded-xl border border-purple-900/50 overflow-hidden shadow-2xl terminal-bg">
                <!-- Terminal Header Bar -->
                <div class="bg-gray-900/90 px-4 py-3 border-b border-purple-900/40 flex items-center justify-between select-none">
                    <div class="flex items-center gap-2">
                        <span class="w-3 h-3 rounded-full bg-red-500/80 inline-block"></span>
                        <span class="w-3 h-3 rounded-full bg-yellow-500/80 inline-block"></span>
                        <span class="w-3 h-3 rounded-full bg-green-500/80 inline-block"></span>
                        <span class="ml-2 text-xs font-mono text-gray-400">C:\Windows\System32\cmd.exe - Launcheur Fortnite V1</span>
                    </div>
                    <div class="text-xs text-gray-500 font-mono">CMD Prompt</div>
                </div>

                <!-- Terminal Console Body -->
                <div class="p-6 font-mono text-sm leading-relaxed overflow-x-auto custom-scrollbar min-h-[380px] text-gray-200">
                    <div class="text-gray-500 mb-2">C:\Users\User\Desktop&gt; Launcheur_Fortnite_V1.bat</div>
                    
                    <!-- Simulated Command Output -->
                    <div id="terminal-content" class="space-y-1">
                        <!-- Content inserted via JS for smooth typing effect -->
                    </div>
                </div>
            </div>
        </section>

        <!-- Features Grid -->
        <section class="grid grid-cols-1 md:grid-cols-3 gap-6 pt-4">
            <div class="p-6 rounded-xl bg-fn-card border border-purple-900/40 space-y-3 hover:border-purple-500/50 transition-all">
                <div class="w-12 h-12 rounded-lg bg-purple-900/40 border border-purple-500/30 flex items-center justify-center text-purple-400 text-xl">
                    <i class="fa-solid fa-user-shield"></i>
                </div>
                <h4 class="text-lg font-bold text-white">100% Anonyme</h4>
                <p class="text-sm text-gray-400">Utilise la variable système <code>%USERPROFILE%</code>. Aucun nom d'utilisateur n'est écrit en dur dans le code.</p>
            </div>

            <div class="p-6 rounded-xl bg-fn-card border border-purple-900/40 space-y-3 hover:border-cyan-500/50 transition-all">
                <div class="w-12 h-12 rounded-lg bg-cyan-900/40 border border-cyan-500/30 flex items-center justify-center text-cyan-400 text-xl">
                    <i class="fa-solid fa-wand-magic-sparkles"></i>
                </div>
                <h4 class="text-lg font-bold text-white">Dessin ASCII Art "FORT"</h4>
                <p class="text-sm text-gray-400">Intègre un logo rétro en texte ASCII soigneusement formaté sans planter la console Windows.</p>
            </div>

            <div class="p-6 rounded-xl bg-fn-card border border-purple-900/40 space-y-3 hover:border-pink-500/50 transition-all">
                <div class="w-12 h-12 rounded-lg bg-pink-900/40 border border-pink-500/30 flex items-center justify-center text-pink-400 text-xl">
                    <i class="fa-brands fa-github"></i>
                </div>
                <h4 class="text-lg font-bold text-white">Prêt pour GitHub</h4>
                <p class="text-sm text-gray-400">Un code propre et universel que n'importe quel joueur peut télécharger et utiliser directement.</p>
            </div>
        </section>

        <!-- Source Code Section -->
        <section class="space-y-4">
            <div class="flex justify-between items-center">
                <h3 class="text-lg font-bold text-white flex items-center gap-2">
                    <i class="fa-solid fa-code text-purple-400"></i> Code Source du Script (.bat)
                </h3>
                <span class="text-xs text-gray-400 font-mono">Fichier : Launcheur_Fortnite_V1.bat</span>
            </div>

            <div class="relative rounded-xl border border-purple-900/50 bg-fn-card overflow-hidden">
                <pre class="p-5 font-mono text-xs md:text-sm text-cyan-300 overflow-x-auto custom-scrollbar leading-relaxed"><code id="raw-code">@echo off
title Launcheur Fortnite V1


echo.
echo        ______     ________      ________     _____________
echo       /  ___/    /  ___   /     /  ____  \   /____    ____/
echo      /  /__     /  /  /  /     /  /____|  |       /   /    
echo     /   __/    /  /  /  /     /   ___    /       /   /     
echo    /  /       /  /__/  /     /  /    \  \       /   /      
echo   /__/       /________/     /___/      \__\     /___/      
echo.
echo   ================================================
echo           En attente Du lancement Du Jeu 
echo   ================================================
if exist "%USERPROFILE%\Desktop\Fortnite.url" (
    start "" "%USERPROFILE%\Desktop\Fortnite.url"
    
)
echo.
echo   Fortnite Et lancer ! Bonne partie !
echo.
echo   ================================================
echo     Meci d'avoir utilise Le Launcheur Fortnite V1
echo   ================================================
echo.
echo.
pause</code></pre>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="border-t border-purple-900/40 py-6 mt-12 bg-fn-dark/90 text-center text-gray-500 text-xs space-y-2">
        <p>Présentation créée pour le projet <strong>Launcheur Fortnite V1</strong></p>
        <p class="text-gray-600">Optimisé pour la publication sur GitHub • 100% Fonctionnel</p>
    </footer>

    <!-- Notification Toast -->
    <div id="toast" class="fixed bottom-5 right-5 bg-gradient-to-r from-purple-600 to-cyan-500 text-white px-5 py-3 rounded-xl shadow-xl flex items-center gap-3 transform translate-y-20 opacity-0 transition-all duration-300 pointer-events-none z-50 font-medium text-sm">
        <i class="fa-solid fa-circle-check text-lg"></i>
        <span id="toast-msg">Action effectuée !</span>
    </div>

    <!-- JavaScript Logic -->
    <script>
        const batScriptCode = `@echo off
title Launcheur Fortnite V1


echo.
echo        ______     ________      ________     -------------
echo       /  ___/    /  ___   /     /  ____  \\   /____    ____/
echo      /  /__     /  /  /  /     /  /____|  |       /   /    
echo     /   __/    /  /  /  /     /   ___    /       /   /     
echo    /  /       /  /__/  /     /  /    \\  \\       /   /      
echo   /__/       /________/     /___/      \\__\\     /___/      
echo.
echo   ================================================
echo           En attente Du lancement Du Jeu 
echo   ================================================
if exist "%USERPROFILE%\\Desktop\\Fortnite.url" (
    start "" "%USERPROFILE%\\Desktop\\Fortnite.url"
    
)
echo.
echo   Fortnite Et lancer ! Bonne partie !
echo.
echo   ================================================
echo     Meci d'avoir utilise Le Launcheur Fortnite V1
echo   ================================================
echo.
echo.
pause`;

        // Terminal Output Lines Simulation
        const terminalLines = [
            { text: "", delay: 100 },
            { text: "       ______     ________      ________     _____________", color: "text-purple-400 font-bold" },
            { text: "      /  ___/    /  ___   /     /  ____  \\   /____    ____/", color: "text-purple-400 font-bold" },
            { text: "     /  /__     /  /  /  /     /  /____|  |       /   /    ", color: "text-purple-400 font-bold" },
            { text: "    /   __/    /  /  /  /     /   ___    /       /   /     ", color: "text-purple-400 font-bold" },
            { text: "   /  /       /  /__/  /     /  /    \\  \\       /   /      ", color: "text-purple-400 font-bold" },
            { text: "  /__/       /________/     /___/      \\__\\     /___/      ", color: "text-purple-400 font-bold" },
            { text: "", delay: 100 },
            { text: "  ================================================", color: "text-cyan-400" },
            { text: "          En attente Du lancement Du Jeu ", color: "text-yellow-300 font-bold" },
            { text: "  ================================================", color: "text-cyan-400" },
            { text: "", delay: 200 },
            { text: "  Fortnite Et lancer ! Bonne partie !", color: "text-green-400 font-bold" },
            { text: "", delay: 100 },
            { text: "  ================================================", color: "text-cyan-400" },
            { text: "    Meci d'avoir utilise Le Launcheur Fortnite V1", color: "text-pink-400 font-semibold" },
            { text: "  ================================================", color: "text-cyan-400" },
            { text: "", delay: 100 },
            { text: "Appuyez sur une touche pour continuer... _", color: "text-gray-400 animate-pulse" }
        ];

        let animationTimeout = null;

        function runTerminalAnimation() {
            const container = document.getElementById('terminal-content');
            container.innerHTML = '';
            
            let index = 0;

            function printNextLine() {
                if (index < terminalLines.length) {
                    const lineData = terminalLines[index];
                    const div = document.createElement('div');
                    div.className = lineData.color || 'text-gray-200';
                    div.textContent = lineData.text;
                    container.appendChild(div);
                    index++;
                    animationTimeout = setTimeout(printNextLine, lineData.delay || 80);
                }
            }

            printNextLine();
        }

        function restartTerminalAnimation() {
            if (animationTimeout) clearTimeout(animationTimeout);
            runTerminalAnimation();
        }

        // Copy Functionality
        function copyCode() {
            const rawText = document.getElementById('raw-code').innerText;
            
            // Clipboard fallback mechanism
            const tempArea = document.createElement('textarea');
            tempArea.value = rawText;
            document.body.appendChild(tempArea);
            tempArea.select();
            document.execCommand('copy');
            document.body.removeChild(tempArea);

            showToast("Code copié dans le presse-papier !");
            
            const btnText = document.getElementById('copyBtnText');
            btnText.textContent = "Copié !";
            setTimeout(() => {
                btnText.textContent = "Copier le Code";
            }, 2000);
        }

        // Download .bat File Functionality
        function downloadBat() {
            const rawText = document.getElementById('raw-code').innerText;
            const blob = new Blob([rawText], { type: 'text/plain;charset=utf-8' });
            const link = document.createElement('a');
            link.href = URL.createObjectURL(blob);
            link.download = 'Launcheur_Fortnite_V1.bat';
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);

            showToast("Téléchargement de Launcheur_Fortnite_V1.bat démarré !");
        }

        // Show Toast Notification
        function showToast(message) {
            const toast = document.getElementById('toast');
            const toastMsg = document.getElementById('toast-msg');
            toastMsg.textContent = message;

            toast.classList.remove('translate-y-20', 'opacity-0');
            toast.classList.add('translate-y-0', 'opacity-100');

            setTimeout(() => {
                toast.classList.remove('translate-y-0', 'opacity-100');
                toast.classList.add('translate-y-20', 'opacity-0');
            }, 3000);
        }

        // Initialize Animation on load
        window.onload = function() {
            runTerminalAnimation();
        };
    </script>
</body>
</html>

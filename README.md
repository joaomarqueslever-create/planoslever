
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simulador de Planos - Lever</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            box-sizing: border-box;
        }
        
        .bg-custom-gradient {
            background: linear-gradient(135deg, #1a1a1a 0%, #2d2d2d 25%, #FF6B35 75%, #FF8C42 100%);
        }
        
        .card-hover {
            transition: all 0.3s ease;
        }
        
        .card-hover:hover {
            transform: translateY(-4px);
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
        }
        
        .plan-card {
            background: linear-gradient(145deg, #ffffff 0%, #f9fafb 100%);
            border: 2px solid transparent;
            transition: all 0.3s ease;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }
        
        .plan-card.selected {
            border-color: #FF6B35;
            background: linear-gradient(145deg, #fff7ed 0%, #ffedd5 100%);
            box-shadow: 0 20px 25px -5px rgba(255, 107, 53, 0.1), 0 10px 10px -5px rgba(255, 107, 53, 0.04);
        }
        
        .feature-check {
            color: #10b981;
        }
        
        .animate-pulse-slow {
            animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
        }
    </style>
</head>
<body class="min-h-full bg-gray-50">
    <div class="min-h-screen bg-custom-gradient">
        <!-- Header -->
        <header class="bg-white shadow-sm">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4">
                <div class="flex items-center justify-between">
                    <div class="flex items-center space-x-3">
                        <div class="w-10 h-10 bg-black rounded-lg flex items-center justify-center">
                            <span class="text-white font-bold text-xl">L</span>
                        </div>
                        <h1 class="text-2xl font-bold text-gray-900">Lever</h1>
                    </div>
                    <nav class="hidden md:flex space-x-8">
                        <a href="#" class="text-gray-600 hover:text-orange-600 transition-colors">Planos</a>
                        <a href="#" class="text-gray-600 hover:text-orange-600 transition-colors">Recursos</a>
                        <a href="#" class="text-gray-600 hover:text-orange-600 transition-colors">Contato</a>
                    </nav>
                </div>
            </div>
        </header>

        <!-- Main Content -->
        <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
            <!-- Title Section -->
            <section class="mb-8">
                <h2 id="setup-price" class="text-2xl font-semibold text-white mb-6 text-center" contenteditable="true">
                    Setup R$1.997,00
                </h2>
                <p class="text-white/80 text-center max-w-2xl mx-auto">
                    Escolha o plano ideal para sua empresa e comece a transformar seus processos hoje mesmo.
                </p>
            </section>

            <!-- Plan Selector -->
            <section class="mb-8">
                <div class="bg-white rounded-xl shadow-lg p-6">
                    <h3 class="text-xl font-semibold text-gray-900 mb-4">Selecione seu Plano</h3>
                    <div class="grid md:grid-cols-3 gap-6">
                        <!-- Start Plan -->
                        <div class="plan-card rounded-lg p-6 cursor-pointer" onclick="selectPlan('start', 347)">
                            <div class="text-center mb-4">
                                <h4 class="text-lg font-semibold text-gray-900">Start</h4>
                                <div class="mt-2">
                                    <span class="text-3xl font-bold" style="color: #FF6B35;">R$347,00</span>
                                    <span class="text-gray-600">/mês</span>
                                </div>
                            </div>
                            <ul class="space-y-2 text-sm">
                                <li class="flex items-center">
                                    <span class="feature-check mr-2">✓</span>
                                    1 usuário
                                </li>
                                <li class="flex items-center">
                                    <span class="feature-check mr-2">✓</span>
                                    1 canal
                                </li>
                                <li class="flex items-center">
                                    <span class="feature-check mr-2">✓</span>
                                    Suporte básico
                                </li>
                            </ul>
                        </div>

                        <!-- Business Plan -->
                        <div class="plan-card rounded-lg p-6 cursor-pointer selected" onclick="selectPlan('business', 497)">
                            <div class="text-center mb-4">
                                <div class="text-white text-xs px-3 py-1 rounded-full inline-block mb-2" style="background: linear-gradient(135deg, #FF6B35 0%, #FF8C42 100%);">
                                    Mais Popular
                                </div>
                                <h4 class="text-lg font-semibold text-gray-900">Business</h4>
                                <div class="mt-2">
                                    <span class="text-3xl font-bold" style="color: #FF6B35;">R$497,00</span>
                                    <span class="text-gray-600">/mês</span>
                                </div>
                            </div>
                            <ul class="space-y-2 text-sm">
                                <li class="flex items-center">
                                    <span class="feature-check mr-2">✓</span>
                                    3 usuários
                                </li>
                                <li class="flex items-center">
                                    <span class="feature-check mr-2">✓</span>
                                    1 canal
                                </li>
                                <li class="flex items-center">
                                    <span class="feature-check mr-2">✓</span>
                                    Suporte prioritário
                                </li>
                                <li class="flex items-center">
                                    <span class="feature-check mr-2">✓</span>
                                    Dashboard avançado
                                </li>
                            </ul>
                        </div>

                        <!-- High Business Plan -->
                        <div class="plan-card rounded-lg p-6 cursor-pointer" onclick="selectPlan('high-business', 997)">
                            <div class="text-center mb-4">
                                <h4 class="text-lg font-semibold text-gray-900">High Business</h4>
                                <div class="mt-2">
                                    <span class="text-3xl font-bold" style="color: #FF6B35;">R$997,00</span>
                                    <span class="text-gray-600">/mês</span>
                                </div>
                            </div>
                            <ul class="space-y-2 text-sm">
                                <li class="flex items-center">
                                    <span class="feature-check mr-2">✓</span>
                                    10 usuários
                                </li>
                                <li class="flex items-center">
                                    <span class="feature-check mr-2">✓</span>
                                    3 canais
                                </li>
                                <li class="flex items-center">
                                    <span class="feature-check mr-2">✓</span>
                                    Suporte 24/7
                                </li>
                                <li class="flex items-center">
                                    <span class="feature-check mr-2">✓</span>
                                    Dashboard personalizado
                                </li>
                                <li class="flex items-center">
                                    <span class="feature-check mr-2">✓</span>
                                    Integrações avançadas
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Calculator Section -->
            <section class="mb-8">
                <div class="bg-white rounded-xl shadow-lg p-6">
                    <h3 class="text-xl font-semibold text-gray-900 mb-6">Calculadora de Investimento</h3>
                    
                    <div class="grid md:grid-cols-2 gap-8">
                        <!-- Input Controls -->
                        <div class="space-y-6">
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">
                                    Recursos Adicionais
                                </label>
                                <div class="space-y-6">
                                    <div>
                                        <label class="block text-sm font-medium text-gray-700 mb-3">
                                            Usuários Adicionais (R$99,00 cada)
                                        </label>
                                        <div class="flex items-center justify-center space-x-4">
                                            <button onclick="changeUsers(-1)" class="w-12 h-12 rounded-full border-2 border-gray-200 flex items-center justify-center text-gray-600 hover:border-orange-400 hover:text-white hover:bg-gradient-to-r hover:from-orange-400 hover:to-orange-500 transition-all duration-300 shadow-sm">
                                                <span class="text-xl font-bold">-</span>
                                            </button>
                                            <div class="bg-gradient-to-r from-gray-50 to-gray-100 px-8 py-4 rounded-xl min-w-[100px] text-center shadow-inner">
                                                <span id="extra-users-value" class="text-2xl font-bold text-gray-800">0</span>
                                            </div>
                                            <button onclick="changeUsers(1)" class="w-12 h-12 rounded-full border-2 border-gray-200 flex items-center justify-center text-gray-600 hover:border-orange-400 hover:text-white hover:bg-gradient-to-r hover:from-orange-400 hover:to-orange-500 transition-all duration-300 shadow-sm">
                                                <span class="text-xl font-bold">+</span>
                                            </button>
                                        </div>
                                    </div>
                                    
                                    <div>
                                        <label class="block text-sm font-medium text-gray-700 mb-3">
                                            Canais Adicionais (R$120,00 cada)
                                        </label>
                                        <div class="flex items-center justify-center space-x-4">
                                            <button onclick="changeChannels(-1)" class="w-12 h-12 rounded-full border-2 border-gray-200 flex items-center justify-center text-gray-600 hover:border-orange-400 hover:text-white hover:bg-gradient-to-r hover:from-orange-400 hover:to-orange-500 transition-all duration-300 shadow-sm">
                                                <span class="text-xl font-bold">-</span>
                                            </button>
                                            <div class="bg-gradient-to-r from-gray-50 to-gray-100 px-8 py-4 rounded-xl min-w-[100px] text-center shadow-inner">
                                                <span id="extra-channels-value" class="text-2xl font-bold text-gray-800">0</span>
                                            </div>
                                            <button onclick="changeChannels(1)" class="w-12 h-12 rounded-full border-2 border-gray-200 flex items-center justify-center text-gray-600 hover:border-orange-400 hover:text-white hover:bg-gradient-to-r hover:from-orange-400 hover:to-orange-500 transition-all duration-300 shadow-sm">
                                                <span class="text-xl font-bold">+</span>
                                            </button>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Results -->
                        <div class="bg-gray-50 rounded-lg p-6">
                            <h4 class="text-lg font-semibold text-gray-900 mb-4">Resumo do Investimento</h4>
                            
                            <div class="space-y-4">
                                <div class="flex justify-between">
                                    <span class="text-gray-600">Plano Selecionado:</span>
                                    <span id="selected-plan" class="font-semibold">Professional</span>
                                </div>
                                
                                <div class="flex justify-between">
                                    <span class="text-gray-600">Valor Mensal:</span>
                                    <span id="monthly-cost" class="font-semibold">R$597,00</span>
                                </div>
                                

                                
                                <div class="flex justify-between">
                                    <span class="text-gray-600">Recursos Adicionais:</span>
                                    <span id="addons-cost" class="font-semibold">R$0,00</span>
                                </div>
                                
                                <hr class="border-gray-300">
                                
                                <div class="flex justify-between text-lg">
                                    <span class="font-semibold text-gray-900">Total Mensal:</span>
                                    <span id="total-cost" class="font-bold text-2xl" style="color: #FF6B35;">R$497,00</span>
                                </div>
                                
                                <div class="mt-6">
                                    <button class="w-full text-white py-4 px-6 rounded-xl font-semibold transition-all duration-300 shadow-lg hover:shadow-xl transform hover:-translate-y-1" style="background: linear-gradient(135deg, #FF6B35 0%, #FF8C42 100%);" onmouseover="this.style.background='linear-gradient(135deg, #FF5722 0%, #FF7043 100%)'" onmouseout="this.style.background='linear-gradient(135deg, #FF6B35 0%, #FF8C42 100%)'">
                                        🚀 Solicitar Proposta
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Features Comparison -->
            <section class="mb-8">
                <div class="bg-white rounded-xl shadow-lg p-6">
                    <h3 class="text-xl font-semibold text-gray-900 mb-6 text-center">Comparação de Recursos</h3>
                    
                    <div class="overflow-x-auto">
                        <table class="w-full">
                            <thead>
                                <tr class="border-b-2 border-gray-200">
                                    <th class="text-left py-4 px-6 font-semibold text-gray-900">Recursos</th>
                                    <th class="text-center py-4 px-6 font-semibold text-gray-700">Start</th>
                                    <th class="text-center py-4 px-6 font-semibold text-white rounded-t-lg" style="background: linear-gradient(135deg, #FF6B35 0%, #FF8C42 100%);">Business</th>
                                    <th class="text-center py-4 px-6 font-semibold text-gray-700">High Business</th>
                                </tr>
                            </thead>
                            <tbody class="text-sm">
                                <tr class="border-b border-gray-100 hover:bg-gray-50 transition-colors">
                                    <td class="py-4 px-6 font-medium text-gray-900">Usuários</td>
                                    <td class="text-center py-4 px-6 text-gray-600">1</td>
                                    <td class="text-center py-4 px-6 font-semibold" style="background: linear-gradient(135deg, rgba(255, 107, 53, 0.1) 0%, rgba(255, 140, 66, 0.1) 100%); color: #FF6B35;">3</td>
                                    <td class="text-center py-4 px-6 text-gray-600">10</td>
                                </tr>
                                <tr class="border-b border-gray-100 hover:bg-gray-50 transition-colors">
                                    <td class="py-4 px-6 font-medium text-gray-900">Canais</td>
                                    <td class="text-center py-4 px-6 text-gray-600">1</td>
                                    <td class="text-center py-4 px-6 font-semibold" style="background: linear-gradient(135deg, rgba(255, 107, 53, 0.1) 0%, rgba(255, 140, 66, 0.1) 100%); color: #FF6B35;">1</td>
                                    <td class="text-center py-4 px-6 text-gray-600">3</td>
                                </tr>
                                <tr class="border-b border-gray-100 hover:bg-gray-50 transition-colors">
                                    <td class="py-4 px-6 font-medium text-gray-900">Dashboard</td>
                                    <td class="text-center py-4 px-6 text-gray-600">Básico</td>
                                    <td class="text-center py-4 px-6 font-semibold" style="background: linear-gradient(135deg, rgba(255, 107, 53, 0.1) 0%, rgba(255, 140, 66, 0.1) 100%); color: #FF6B35;">Avançado</td>
                                    <td class="text-center py-4 px-6 text-gray-600">Personalizado</td>
                                </tr>
                                <tr class="border-b border-gray-100 hover:bg-gray-50 transition-colors">
                                    <td class="py-4 px-6 font-medium text-gray-900">Suporte</td>
                                    <td class="text-center py-4 px-6 text-gray-600">Básico</td>
                                    <td class="text-center py-4 px-6 font-semibold" style="background: linear-gradient(135deg, rgba(255, 107, 53, 0.1) 0%, rgba(255, 140, 66, 0.1) 100%); color: #FF6B35;">Prioritário</td>
                                    <td class="text-center py-4 px-6 text-gray-600">24/7</td>
                                </tr>
                                <tr class="hover:bg-gray-50 transition-colors">
                                    <td class="py-4 px-6 font-medium text-gray-900">Integrações</td>
                                    <td class="text-center py-4 px-6 text-gray-600">❌</td>
                                    <td class="text-center py-4 px-6 font-semibold rounded-b-lg" style="background: linear-gradient(135deg, rgba(255, 107, 53, 0.1) 0%, rgba(255, 140, 66, 0.1) 100%); color: #FF6B35;">❌</td>
                                    <td class="text-center py-4 px-6 text-gray-600">✅</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </section>
        </main>
    </div>

    <script>
        let currentPlan = {
            name: 'Business',
            price: 497
        };
        
        let extraUsers = 0;
        let extraChannels = 0;

        function selectPlan(planName, price) {
            // Remove selection from all cards
            document.querySelectorAll('.plan-card').forEach(card => {
                card.classList.remove('selected');
            });
            
            // Add selection to clicked card
            event.currentTarget.classList.add('selected');
            
            // Update current plan
            currentPlan = {
                name: planName.charAt(0).toUpperCase() + planName.slice(1),
                price: price
            };
            
            updateCalculation();
        }
        
        function changeUsers(delta) {
            extraUsers = Math.max(0, Math.min(50, extraUsers + delta));
            updateCalculation();
        }
        
        function changeChannels(delta) {
            extraChannels = Math.max(0, Math.min(20, extraChannels + delta));
            updateCalculation();
        }

        function updateCalculation() {
            // Update display values
            document.getElementById('extra-users-value').textContent = extraUsers;
            document.getElementById('extra-channels-value').textContent = extraChannels;
            
            // Calculate additional costs
            let addonsMonthly = 0;
            addonsMonthly += extraUsers * 99; // R$99 per additional user
            addonsMonthly += extraChannels * 120; // R$120 per additional channel
            
            const monthlyTotal = currentPlan.price + addonsMonthly;
            
            // Update display
            document.getElementById('selected-plan').textContent = currentPlan.name;
            document.getElementById('monthly-cost').textContent = `R$${currentPlan.price.toLocaleString('pt-BR')},00`;
            document.getElementById('addons-cost').textContent = `R$${addonsMonthly.toLocaleString('pt-BR')},00`;
            document.getElementById('total-cost').textContent = `R$${monthlyTotal.toLocaleString('pt-BR')},00`;
        }

        // Initialize calculation
        updateCalculation();

        // Make setup price editable
        document.getElementById('setup-price').addEventListener('input', function() {
            const newText = this.textContent;
            // Extract price from text if it contains currency format
            const priceMatch = newText.match(/R\$\s*([\d.,]+)/);
            if (priceMatch) {
                const newPrice = parseFloat(priceMatch[1].replace(/\./g, '').replace(',', '.'));
                if (!isNaN(newPrice)) {
                    updateCalculation();
                }
            }
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'99219d69e782f610',t:'MTc2MTA1ODcyNS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>

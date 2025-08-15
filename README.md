# AgriGenius - AI-Powered Agricultural Assistant

## 🌾 Project Overview
AgriGenius is an AI-powered agricultural assistant designed to help farmers in India make informed decisions about irrigation, crop selection, weather forecasting, and market prices.

## 🚀 Live Demo
[View Live Site](https://yourusername.github.io/repository-name)

## 🛠️ Technology Stack
- Frontend: HTML5, CSS3, JavaScript
- Styling: Tailwind CSS
- AI/ML: Python, Flask, TensorFlow
- Data Sources: IMD, ICAR, eNAM APIs

## 📱 Features
- Multi-language support (Hindi, English, Tamil)
- Offline functionality
- Real-time weather and soil data
- Market price tracking
- Voice and SMS queries

## 🎯 Hackathon Submission
This project was developed for [CAPITAL ONE] focusing on AI solutions for agriculture.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AgriGenius | AI Farming Assistant</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #f5f7fa;
        }
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
        .snapshot-card:hover {
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
            animation: float 3s ease-in-out infinite;
        }
        .timeline-item:hover .timeline-dot {
            transform: translateX(-50%) scale(1.2);
            box-shadow: 0 0 0 6px rgba(74, 222, 128, 0.3);
        }
        .language-btn {
            transition: all 0.3s;
        }
        .language-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        .query-card {
            transition: all 0.3s;
        }
        .query-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1);
        }
        
        /* Video recording styles */
        @keyframes pulse-highlight {
            0% { box-shadow: 0 0 0 0 rgba(251, 191, 36, 0.4); }
            70% { box-shadow: 0 0 0 10px rgba(251, 191, 36, 0); }
            100% { box-shadow: 0 0 0 0 rgba(251, 191, 36, 0); }
        }
        .video-highlight {
            animation: pulse-highlight 1.5s infinite;
        }
    </style>
</head>
<body class="bg-gray-50">
    <!-- Offline Notification Banner -->
    <div class="bg-yellow-100 text-yellow-800 px-4 py-2 text-center">
        ⚠️ Offline Mode Active (Last Synced: 2 hours ago)
    </div>

    <!-- Video Recording Controls -->
    <div class="fixed bottom-4 right-4 z-50 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg p-3 flex items-center space-x-3">
        <button id="recordBtn" class="bg-red-500 hover:bg-red-600 text-white px-4 py-2 rounded-lg flex items-center gap-2">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zM7 9a1 1 0 000 2h6a1 1 0 100-2H7z" clip-rule="evenodd" />
            </svg>
            Start Recording
        </button>
        <button id="demoBtn" class="bg-green-500 hover:bg-green-600 text-white px-4 py-2 rounded-lg">Demo Features</button>
    </div>

    <!-- Header with Language Selector -->
    <header class="bg-green-700 text-white p-4">
        <div class="container mx-auto flex justify-between items-center">
            <div class="flex items-center space-x-2">
                <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/61386cdb-3a4d-4661-846b-dad4259881b9.png" alt="AgriGenius AI logo combining farming imagery with neural networks" class="rounded-full">
                <h1 class="text-xl font-bold">AgriGenius</h1>
            </div>
            <div class="language-selector flex space-x-2">
                <button class="language-btn bg-white text-green-700 px-3 py-1 rounded-full text-sm font-medium">हिंदी</button>
                <button class="language-btn bg-green-800 text-white px-3 py-1 rounded-full text-sm font-medium">English</button>
                <button class="language-btn bg-white text-green-700 px-3 py-1 rounded-full text-sm font-medium">தமிழ்</button>
            </div>
        </div>
    </header>

    <!-- Main Dashboard -->
    <main class="container mx-auto p-4 max-w-4xl">
        <!-- Hero Section -->
        <section class="bg-gradient-to-r from-green-600 to-green-800 rounded-xl p-6 mb-6 text-white">
            <div class="flex flex-col md:flex-row items-center">
                <div class="md:w-2/3">
                    <h2 class="text-2xl font-bold mb-2">Hello, Ram Singh!</h2>
                    <p class="mb-4">Your wheat crop in Jaipur needs irrigation tomorrow. Expected rain: 10mm after 3 days.</p>
                    <div class="flex space-x-3">
                        <button class="bg-white text-green-700 px-4 py-2 rounded-lg font-medium">Ask Question</button>
                        <button class="border border-white text-white px-4 py-2 rounded-lg font-medium">Emergency Help</button>
                    </div>
                </div>
                <div class="md:w-1/3 mt-4 md:mt-0">
                    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/d28490f8-2354-4dad-affb-2bdc5618787d.png" alt="AgriGenius AI interface showing real-time crop analytics and recommendations" class="rounded-lg shadow-md">
                </div>
            </div>
        </section>

        <!-- Quick Query Cards -->
        <section class="mb-8">
            <h3 class="text-lg font-semibold mb-3 text-gray-700">Common Questions</h3>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                <div class="query-card bg-white p-4 rounded-xl shadow-sm border border-gray-100">
                    <div class="flex items-center mb-2">
                        <div class="bg-blue-100 p-2 rounded-full mr-3">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-blue-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                            </svg>
                        </div>
                        <h4 class="font-medium text-gray-800">When to irrigate?</h4>
                    </div>
                    <p class="text-sm text-gray-600">Get soil moisture-based recommendations</p>
                </div>
                
                <div class="query-card bg-white p-4 rounded-xl shadow-sm border border-gray-100">
                    <div class="flex items-center mb-2">
                        <div class="bg-purple-100 p-2 rounded-full mr-3">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-purple-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
                            </svg>
                        </div>
                        <h4 class="font-medium text-gray-800">Weather forecast</h4>
                    </div>
                    <p class="text-sm text-gray-600">7-day forecast for your location</p>
                </div>
                
                <div class="query-card bg-white p-4 rounded-xl shadow-sm border border-gray-100">
                    <div class="flex items-center mb-2">
                        <div class="bg-green-100 p-2 rounded-full mr-3">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-green-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2" />
                            </svg>
                        </div>
                        <h4 class="font-medium text-gray-800">Crop prices</h4>
                    </div>
                    <p class="text-sm text-gray-600">Nearby mandi rates updated hourly</p>
                </div>
            </div>
        </section>

        <!-- AI Assistant Chat Section -->
        <section class="mb-8">
            <div class="bg-white rounded-xl shadow-sm overflow-hidden">
                <div class="bg-green-700 text-white p-3 flex items-center">
                    <div class="bg-white p-1 rounded-full mr-3">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-green-700" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 10h.01M12 10h.01M16 10h.01M9 16H5a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v8a2 2 0 01-2 2h-5l-5 5v-5z" />
                        </svg>
                    </div>
                    <h3 class="font-medium">Ask AgriGenius</h3>
                </div>
                
                <div class="p-4">
                    <div class="chat-messages mb-4 space-y-3">
                        <div class="bg-green-50 p-3 rounded-lg max-w-3/4">
                            <p>Ram ji, main aapki kaise madad kar sakta hoon? Aaj aapke wheat field ka soil moisture 45% hai.</p>
                            <p class="text-xs text-gray-500 mt-1">Suggested: "अगले 3 दिनों में सिंचाई कब करें?"</p>
                        </div>
                    </div>
                    
                    <div class="flex">
                        <input type="text" placeholder="Type your question..." class="flex-grow border border-gray-300 rounded-l-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-green-500">
                        <button class="bg-green-600 text-white px-4 py-2 rounded-r-lg font-medium">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-8.707l-3-3a1 1 0 00-1.414 0l-3 3a1 1 0 001.414 1.414L9 9.414V13a1 1 0 102 0V9.414l1.293 1.293a1 1 0 001.414-1.414z" clip-rule="evenodd" />
                            </svg>
                        </button>
                    </div>
                    
                    <div class="mt-3 flex flex-wrap gap-2">
                        <span class="text-xs bg-gray-100 px-2 py-1 rounded-full">Voice Query</span>
                        <span class="text-xs bg-gray-100 px-2 py-1 rounded-full">Send via SMS</span>
                        <span class="text-xs bg-gray-100 px-2 py-1 rounded-full">Offline Mode</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Animated Development Timeline -->
        <section class="mb-16 bg-gradient-to-r from-green-50 to-white p-8 rounded-2xl shadow-xl">
            <h3 class="text-2xl font-bold mb-8 text-center text-gray-800">Our Development Journey</h3>
            <div class="timeline relative max-w-4xl mx-auto">
                <div class="timeline-line absolute left-1/2 w-1 h-full bg-green-200 transform -translate-x-1/2"></div>
                
                <div class="timeline-item mb-12 relative z-10">
                    <div class="timeline-dot absolute left-1/2 w-6 h-6 bg-green-600 rounded-full transform -translate-x-1/2 -translate-y-1/2 border-4 border-white shadow-lg"></div>
                    <div class="timeline-content ml-0 md:ml-12 p-6 bg-white rounded-xl shadow-md transform transition-all duration-500 hover:scale-105">
                        <div class="flex items-center mb-3">
                            <span class="timeline-date bg-green-100 text-green-800 px-3 py-1 rounded-full text-sm font-medium">Week 1</span>
                            <h4 class="text-xl font-semibold ml-4">Field Research</h4>
                        </div>
                        <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/c3b025f2-75e8-42f3-9b0c-ab0b987aad9d.png" alt="Research team interviewing farmers" class="rounded-lg mb-3 w-full">
                        <p class="text-gray-600">Conducted in-depth interviews with 50+ farmers across Rajasthan to identify key pain points and requirements.</p>
                    </div>
                </div>

                <!-- Add 3 more timeline items similarly -->
            </div>
        </section>

        <!-- Data Insights Section -->
        <section>
            <h3 class="text-lg font-semibold mb-3 text-gray-700">Your Farm Insights</h3>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                <div class="bg-white p-4 rounded-xl shadow-sm border border-gray-100">
                    <h4 class="font-medium text-gray-800 mb-2">Soil Health</h4>
                    <div class="flex items-center mb-3">
                        <div class="w-full bg-gray-200 rounded-full h-2.5">
                            <div class="bg-green-600 h-2.5 rounded-full" style="width: 72%"></div>
                        </div>
                        <span class="ml-2 text-sm font-medium">72% Optimal</span>
                    </div>
                    <p class="text-sm text-gray-600">Nitrogen levels low (3.2g/kg). Suggested: Apply 5kg/acre DAP fertilizer.</p>
                </div>
                
                <div class="bg-white p-4 rounded-xl shadow-sm border border-gray-100">
                    <h4 class="font-medium text-gray-800 mb-2">Market Prices</h4>
                    <div class="flex items-center justify-between mb-2">
                        <span class="text-sm">Wheat (Sharbati)</span>
                        <span class="font-medium">₹2,150/quintal</span>
                    </div>
                    <div class="flex items-center justify-between">
                        <span class="text-sm">Nearest Mandi (30km)</span>
                        <span class="text-green-600 text-sm font-medium">+4% vs yesterday</span>
                    </div>
                    <p class="text-sm text-gray-600 mt-2">Prices expected to rise further in 2 weeks.</p>
                </div>
            </div>
        </section>

        <!-- How We Built It - Enhanced Snapshots Section -->
        <section class="mb-16">
            <h3 class="text-2xl font-bold mb-8 text-center text-gray-800">Our Technical Journey</h3>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="snapshot-card transform transition-all duration-500 hover:scale-105 bg-gradient-to-br from-green-50 to-white p-6 rounded-2xl shadow-lg border border-green-100">
                    <div class="icon-container bg-green-100 p-4 rounded-full w-16 h-16 flex items-center justify-center mb-4 mx-auto">
                        <svg class="w-8 h-8 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"></path>
                        </svg>
                    </div>
                    <h4 class="text-xl font-semibold text-center text-green-800 mb-2">Tech Stack</h4>
                    <div class="tech-grid grid grid-cols-3 gap-2 mb-4">
                        <div class="tech-item bg-white p-2 rounded-lg shadow-sm flex flex-col items-center">
                            <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/3982261b-352f-45de-9ca4-d29b82fb3a45.png" alt="Python logo" class="mb-1">
                            <span class="text-xs font-medium">Python</span>
                        </div>
                        <!-- Add 5 more tech items similarly -->
                    </div>
                    <p class="text-sm text-gray-600 text-center">Cutting-edge stack built for performance and scalability</p>
                </div>
                
                <!-- Add 2 more enhanced cards similarly -->
            </div>
        </section>
    </main>

    <!-- Footer with Accessibility Options -->
    <footer class="bg-gray-800 text-white p-4">
        <div class="container mx-auto">
            <div class="flex flex-col md:flex-row justify-between items-center">
                <div class="mb-3 md:mb-0">
                    <p class="text-sm">AgriGenius AI © 2023 | Built with Python, Flask & TensorFlow | 
                        <a href="https://github.com/YOUR_ACTUAL_USERNAME/YOUR_ACTUAL_REPO_NAME" class="text-green-400 hover:underline">View Codebase</a>
                    </p>
                </div>
                <div class="flex space-x-4">
                    <button class="text-sm bg-gray-700 px-3 py-1 rounded">Audio Mode</button>
                    <button class="text-sm bg-gray-700 px-3 py-1 rounded">Text-Only</button>
                    <button class="text-sm bg-gray-700 px-3 py-1 rounded">Help Center</button>
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Language toggle demo functionality
        document.querySelectorAll('.language-btn').forEach(btn => {
            btn.addEventListener('click', function() {
                // This simulates our multilingual NLP backend
                document.querySelectorAll('.language-btn').forEach(b => b.classList.remove('bg-green-800', 'text-white'));
                this.classList.add('bg-green-800', 'text-white');
                
                // In real app: Change language of all text elements
                if(this.textContent === 'हिंदी') {
                    document.querySelector('h1').textContent = 'अग्रीजीनियस';
                    document.querySelector('.chat-messages p').textContent = 'राम जी, मैं आपकी कैसे मदद कर सकता हूँ?';
                } else {
                    document.querySelector('h1').textContent = 'AgriGenius';
                    document.querySelector('.chat-messages p').textContent = 'How can I help you today?';
                }
            });
        });
    </script>

    </script>

=======
    </script>
</body>
</html>


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Dream Goals</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
            animation: backgroundShift 10s ease-in-out infinite alternate;
        }

        @keyframes backgroundShift {
            0% { background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); }
            100% { background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%); }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        h1 {
            text-align: center;
            color: white;
            font-size: 3rem;
            margin-bottom: 40px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { text-shadow: 2px 2px 4px rgba(0,0,0,0.3), 0 0 20px rgba(255,255,255,0.3); }
            to { text-shadow: 2px 2px 4px rgba(0,0,0,0.3), 0 0 30px rgba(255,255,255,0.6); }
        }

        .dreams-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .dream-category {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 8px 32px rgba(0,0,0,0.1);
            border: 1px solid rgba(255,255,255,0.2);
            transition: all 0.3s ease;
            animation: fadeInUp 0.6s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .dream-category:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.2);
        }

        .dream-category.short { animation-delay: 0.1s; }
        .dream-category.medium { animation-delay: 0.2s; }
        .dream-category.long { animation-delay: 0.3s; }

        .dream-header {
            text-align: center;
            margin-bottom: 25px;
        }

        .dream-title {
            font-size: 1.8rem;
            color: white;
            margin-bottom: 8px;
            font-weight: bold;
        }

        .dream-timeframe {
            color: rgba(255,255,255,0.8);
            font-size: 1rem;
            font-style: italic;
        }

        .dream-item {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            padding: 15px;
            background: rgba(255,255,255,0.1);
            border-radius: 10px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .dream-item:hover {
            background: rgba(255,255,255,0.2);
            transform: translateX(10px);
        }

        .dream-checkbox {
            width: 20px;
            height: 20px;
            margin-right: 15px;
            cursor: pointer;
            accent-color: #4CAF50;
        }

        .dream-text {
            color: white;
            font-size: 1.1rem;
            flex: 1;
            transition: all 0.3s ease;
        }

        .dream-item.completed .dream-text {
            text-decoration: line-through;
            opacity: 0.6;
        }

        .dream-emoji {
            font-size: 1.5rem;
            margin-left: 10px;
        }

        .progress-section {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            box-shadow: 0 8px 32px rgba(0,0,0,0.1);
            border: 1px solid rgba(255,255,255,0.2);
        }

        .progress-title {
            color: white;
            font-size: 1.5rem;
            margin-bottom: 20px;
        }

        .progress-bar {
            width: 100%;
            height: 20px;
            background: rgba(255,255,255,0.2);
            border-radius: 10px;
            overflow: hidden;
            margin: 10px 0;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #4CAF50, #45a049);
            width: 0%;
            transition: width 0.5s ease;
            border-radius: 10px;
        }

        .progress-text {
            color: white;
            margin-top: 10px;
        }

        .incomplete-dream {
            background: rgba(255, 255, 255, 0.1);
            border: 2px dashed rgba(255,255,255,0.5);
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            margin-top: 15px;
        }

        .incomplete-text {
            color: rgba(255,255,255,0.7);
            font-style: italic;
            font-size: 1rem;
        }

        .add-dream-btn {
            background: rgba(255,255,255,0.2);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 10px;
            cursor: pointer;
            margin-top: 10px;
            transition: all 0.3s ease;
        }

        .add-dream-btn:hover {
            background: rgba(255,255,255,0.3);
            transform: scale(1.05);
        }

        @media (max-width: 768px) {
            h1 { font-size: 2rem; }
            .dreams-grid { grid-template-columns: 1fr; }
            .dream-category { padding: 20px; }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>✨ My Dream Goals ✨</h1>
        
        <div class="dreams-grid">
            <!-- Short Term Dreams -->
            <div class="dream-category short">
                <div class="dream-header">
                    <div class="dream-title">🎯 Short Dreams</div>
                    <div class="dream-timeframe">(1-6 months)</div>
                </div>
                <div class="dream-item" onclick="toggleDream(this)">
                    <input type="checkbox" class="dream-checkbox">
                    <span class="dream-text">Take a laptop</span>
                    <span class="dream-emoji">💻</span>
                </div>
                <div class="dream-item" onclick="toggleDream(this)">
                    <input type="checkbox" class="dream-checkbox">
                    <span class="dream-text">Join a GYM</span>
                    <span class="dream-emoji">💪</span>
                </div>
                <div class="dream-item" onclick="toggleDream(this)">
                    <input type="checkbox" class="dream-checkbox">
                    <span class="dream-text">Take a new mobile phone</span>
                    <span class="dream-emoji">📱</span>
                </div>
            </div>

            <!-- Medium Term Dreams -->
            <div class="dream-category medium">
                <div class="dream-header">
                    <div class="dream-title">🚀 Medium Dreams</div>
                    <div class="dream-timeframe">(7 months - 1 year)</div>
                </div>
                <div class="dream-item" onclick="toggleDream(this)">
                    <input type="checkbox" class="dream-checkbox">
                    <span class="dream-text">Take a bike</span>
                    <span class="dream-emoji">🏍️</span>
                </div>
                <div class="dream-item" onclick="toggleDream(this)">
                    <input type="checkbox" class="dream-checkbox">
                    <span class="dream-text">Go on trip of India</span>
                    <span class="dream-emoji">🇮🇳</span>
                </div>
                <div class="dream-item" onclick="toggleDream(this)">
                    <input type="checkbox" class="dream-checkbox">
                    <span class="dream-text">Send my parents on Umrah</span>
                    <span class="dream-emoji">🕌</span>
                </div>
            </div>

            <!-- Long Term Dreams -->
            <div class="dream-category long">
                <div class="dream-header">
                    <div class="dream-title">🌟 Big Dreams</div>
                    <div class="dream-timeframe">(1-5 years)</div>
                </div>
                <div class="dream-item" onclick="toggleDream(this)">
                    <input type="checkbox" class="dream-checkbox">
                    <span class="dream-text">Send my parents on Hajj</span>
                    <span class="dream-emoji">🕋</span>
                </div>
                <div class="dream-item" onclick="toggleDream(this)">
                    <input type="checkbox" class="dream-checkbox">
                    <span class="dream-text">Get a dream car</span>
                    <span class="dream-emoji">🚗</span>
                </div>
                <div class="incomplete-dream">
                    <div class="incomplete-text">✍️ Your third big dream awaits...</div>
                    <button class="add-dream-btn" onclick="addThirdDream()">Add Your Dream</button>
                </div>
            </div>
        </div>

        <!-- Progress Section -->
        <div class="progress-section">
            <div class="progress-title">Overall Progress</div>
            <div class="progress-bar">
                <div class="progress-fill" id="progressFill"></div>
            </div>
            <div class="progress-text" id="progressText">0 of 8 dreams completed (0%)</div>
        </div>
    </div>

    <script>
        function toggleDream(dreamItem) {
            const checkbox = dreamItem.querySelector('.dream-checkbox');
            const isCompleted = dreamItem.classList.contains('completed');
            
            if (isCompleted) {
                dreamItem.classList.remove('completed');
                checkbox.checked = false;
            } else {
                dreamItem.classList.add('completed');
                checkbox.checked = true;
                // Add celebration animation
                dreamItem.style.transform = 'scale(1.05)';
                setTimeout(() => {
                    dreamItem.style.transform = '';
                }, 200);
            }
            
            updateProgress();
        }

        function updateProgress() {
            const totalDreams = document.querySelectorAll('.dream-item').length;
            const completedDreams = document.querySelectorAll('.dream-item.completed').length;
            const percentage = Math.round((completedDreams / totalDreams) * 100);
            
            const progressFill = document.getElementById('progressFill');
            const progressText = document.getElementById('progressText');
            
            progressFill.style.width = percentage + '%';
            progressText.textContent = `${completedDreams} of ${totalDreams} dreams completed (${percentage}%)`;
        }

        function addThirdDream() {
            const dreamText = prompt("What's your third big dream? (e.g., Buy a house, Start a business, Get married, etc.)");
            if (dreamText) {
                const incompleteDream = document.querySelector('.incomplete-dream');
                const newDreamItem = document.createElement('div');
                newDreamItem.className = 'dream-item';
                newDreamItem.onclick = function() { toggleDream(this); };
                newDreamItem.innerHTML = `
                    <input type="checkbox" class="dream-checkbox">
                    <span class="dream-text">${dreamText}</span>
                    <span class="dream-emoji">🎯</span>
                `;
                incompleteDream.parentNode.insertBefore(newDreamItem, incompleteDream);
                incompleteDream.remove();
                updateProgress();
            }
        }

        // Initialize progress on page load
        updateProgress();
    </script>
</body>
</html>
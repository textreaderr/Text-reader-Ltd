# Text-reader-Ltd
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Premium Free Text-to-Speech</title>
    <style>
        :root {
            --primary: #4f46e5;
            --primary-dark: #4338ca;
            --secondary: #ef4444;
            --secondary-dark: #dc2626;
            --text: #1f2937;
            --bg: #f9fafb;
            --card: #ffffff;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg);
            color: var(--text);
            margin: 0;
            padding: 2rem;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .container {
            width: 100%;
            max-width: 800px;
        }
        
        h1 {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            text-align: center;
            background: linear-gradient(90deg, #4f46e5, #7c3aed);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .card {
            background-color: var(--card);
            border-radius: 12px;
            padding: 2rem;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            margin-bottom: 2rem;
        }
        
        textarea {
            width: 100%;
            min-height: 150px;
            padding: 1rem;
            border: 2px solid #e5e7eb;
            border-radius: 8px;
            font-size: 1rem;
            resize: vertical;
            margin-bottom: 1.5rem;
        }
        
        .controls {
            display: grid;
            gap: 1.5rem;
        }
        
        .control-group {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }
        
        label {
            font-weight: 600;
            font-size: 0.875rem;
        }
        
        select {
            padding: 0.75rem;
            border-radius: 8px;
            border: 1px solid #e5e7eb;
            font-size: 1rem;
        }
        
        .button-group {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }
        
        button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            padding: 0.75rem 1.5rem;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            border: none;
            transition: all 0.2s;
        }
        
        #speak-button {
            background-color: var(--primary);
            color: white;
            flex: 1;
        }
        
        #speak-button:hover {
            background-color: var(--primary-dark);
        }
        
        #pause-button {
            background-color: #f59e0b;
            color: white;
            display: none;
        }
        
        #pause-button:hover {
            background-color: #d97706;
        }
        
        #stop-button {
            background-color: var(--secondary);
            color: white;
        }
        
        #stop-button:hover {
            background-color: var(--secondary-dark);
        }
        
        .status {
            margin-top: 1rem;
            font-size: 0.875rem;
            color: #6b7280;
            text-align: center;
        }
        
        @media (max-width: 768px) {
            body {
                padding: 1rem;
            }
            
            .button-group {
                flex-direction: column;
            }
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
</head>
<body>
    <div class="container">
        <h1>Premium Free Text-to-Speech</h1>
        
        <div class="card">
            <textarea id="text-input" placeholder="Enter text to convert to high-quality speech..."></textarea>
            
            <div class="controls">
                <div class="control-group">
                    <label for="voice-select">Select Voice:</label>
                    <select id="voice-select">
                        <option value="UK English Male">British Male</option>
                        <option value="US English Female">American Female</option>
                        <option value="Australian Female">Australian Female</option>
                        <option value="French Female">French Female</option>
                        <option value="Spanish Female">Spanish Female</option>
                    </select>
                </div>
            </div>
            
            <div class="button-group">
                <button id="speak-button">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
                        <path d="M11.536 14.01A8.473 8.473 0 0 0 14.026 8a8.473 8.473 0 0 0-2.49-6.01l-.708.707A7.476 7.476 0 0 1 13.025 8c0 2.071-.84 3.946-2.197 5.303l.708.707z"/>
                        <path d="M10.121 12.596A6.48 6.48 0 0 0 12.025 8a6.48 6.48 0 0 0-1.904-4.596l-.707.707A5.483 5.483 0 0 1 11.025 8a5.483 5.483 0 0 1-1.61 3.89l.706.706z"/>
                        <path d="M8.707 11.182A4.486 4.486 0 0 0 10.025 8c0-1.243-.53-2.369-1.377-3.182l-.707.707A3.489 3.489 0 0 1 9.025 8c0 .966-.392 1.841-1.024 2.475l.706.707zM6.717 3.55A.5.5 0 0 1 7 4v8a.5.5 0 0 1-1 0V4a.5.5 0 0 1 .717-.454l3 1.5a.5.5 0 0 1 0 .908l-3 1.5z"/>
                    </svg>
                    Speak
                </button>
                <button id="pause-button">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
                        <path d="M5.5 3.5A1.5 1.5 0 0 1 7 5v6a1.5 1.5 0 0 1-3 0V5a1.5 1.5 0 0 1 1.5-1.5zm5 0A1.5 1.5 0 0 1 12 5v6a1.5 1.5 0 0 1-3 0V5a1.5 1.5 0 0 1 1.5-1.5z"/>
                    </svg>
                    Pause
                </button>
                <button id="stop-button">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
                        <path d="M5 3.5h6A1.5 1.5 0 0 1 12.5 5v6a1.5 1.5 0 0 1-1.5 1.5H5A1.5 1.5 0 0 1 3.5 11V5A1.5 1.5 0 0 1 5 3.5z"/>
                    </svg>
                    Stop
                </button>
            </div>
            
            <div class="status" id="status">Ready to speak</div>
        </div>
    </div>

    <!-- ResponsiveVoice JS library -->
    <script src="https://code.responsivevoice.org/responsivevoice.js"></script>
    
    <script>
        // DOM Elements
        const textInput = document.getElementById('text-input');
        const voiceSelect = document.getElementById('voice-select');
        const speakButton = document.getElementById('speak-button');
        const pauseButton = document.getElementById('pause-button');
        const stopButton = document.getElementById('stop-button');
        const status = document.getElementById('status');
        
        // Check if ResponsiveVoice is loaded
        if (typeof responsiveVoice === 'undefined') {
            status.textContent = 'Error loading speech engine. Please try again.';
            speakButton.disabled = true;
        }
        
        // Speak text
        function speakText() {
            const text = textInput.value.trim();
            if (!text) {
                status.textContent = 'Please enter text to speak';
                return;
            }
            
            const voice = voiceSelect.value;
            
            responsiveVoice.speak(text, voice, {
                onstart: () => {
                    status.textContent = 'Speaking...';
                    speakButton.disabled = true;
                    pauseButton.style.display = 'inline-flex';
                    stopButton.style.display = 'inline-flex';
                },
                onend: () => {
                    status.textContent = 'Finished speaking';
                    speakButton.disabled = false;
                    pauseButton.style.display = 'none';
                    stopButton.style.display = 'none';
                },
                onerror: () => {
                    status.textContent = 'Error occurred during speech';
                    speakButton.disabled = false;
                }
            });
        }
        
        // Pause speech
        function pauseSpeech() {
            responsiveVoice.pause();
            status.textContent = 'Paused';
            pauseButton.innerHTML = `
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
                    <path d="M11.536 14.01A8.473 8.473 0 0 0 14.026 8a8.473 8.473 0 0 0-2.49-6.01l-.708.707A7.476 7.476 0 0 1 13.025 8c0 2.071-.84 3.946-2.197 5.303l.708.707z"/>
                    <path d="M10.121 12.596A6.48 6.48 0 0 0 12.025 8a6.48 6.48 0 0 0-1.904-4.596l-.707.707A5.483 5.483 0 0 1 11.025 8a5.483 5.483 0 0 1-1.61 3.89l.706.706z"/>
                    <path d="M8.707 11.182A4.486 4.486 0 0 0 10.025 8c0-1.243-.53-2.369-1.377-3.182l-.707.707A3.489 3.489 0 0 1 9.025 8c0 .966-.392 1.841-1.024 2.475l.706.707zM6.717 3.55A.5.5 0 0 1 7 4v8a.5.5 0 0 1-1 0V4a.5.5 0 0 1 .717-.454l3 1.5a.5.5 0 0 1 0 .908l-3 1.5z"/>
                </svg>
                Resume
            `;
            pauseButton.onclick = resumeSpeech;
        }
        
        // Resume speech
        function resumeSpeech() {
            responsiveVoice.resume();
            status.textContent = 'Speaking...';
            pauseButton.innerHTML = `
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
                    <path d="M5.5 3.5A1.5 1.5 0 0 1 7 5v6a1.5 1.5 0 0 1-3 0V5a1.5 1.5 0 0 1 1.5-1.5zm5 0A1.5 1.5 0 0 1 12 5v6a1.5 1.5 0 0 1-3 0V5a1.5 1.5 0 0 1 1.5-1.5z"/>
                </svg>
                Pause
            `;
            pauseButton.onclick = pauseSpeech;
        }
        
        // Stop speech
        function stopSpeech() {
            responsiveVoice.cancel();
            status.textContent = 'Stopped';
            speakButton.disabled = false;
            pauseButton.style.display = 'none';
            stopButton.style.display = 'none';
            
            // Reset pause button to pause state
            pauseButton.innerHTML = `
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
                    <path d="M5.5 3.5A1.5 1.5 0 0 1 7 5v6a1.5 1.5 0 0 1-3 0V5a1.5 1.5 0 0 1 1.5-1.5zm5 0A1.5 1.5 0 0 1 12 5v6a1.5 1.5 0 0 1-3 0V5a1.5 1.5 0 0 1 1.5-1.5z"/>
                </svg>
                Pause
            `;
            pauseButton.onclick = pauseSpeech;
        }
        
        // Event listeners
        speakButton.addEventListener('click', speakText);
        pauseButton.addEventListener('click', pauseSpeech);
        stopButton.addEventListener('click', stopSpeech);
        
        // Initialize with default voice
        responsiveVoice.init();
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Brigitte Castañeda Rodríguez - AI Agent</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        /* Base styles for chat elements */
        .bcr-body {
            font-family: 'Inter', sans-serif;
        }
        .bcr-chat-container::-webkit-scrollbar {
            width: 6px;
        }
        .bcr-chat-container::-webkit-scrollbar-track {
            background: #f1f5f9;
        }
        .bcr-chat-container::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 3px;
        }
        .bcr-chat-container::-webkit-scrollbar-thumb:hover {
            background: #94a3b8;
        }
        .bcr-ai-bubble {
            background-color: #eef2ff; /* Tailwind indigo-50 */
            color: #3730a3; /* Tailwind indigo-800 */
        }
        .bcr-user-bubble {
            background-color: #4f46e5; /* Tailwind indigo-600 */
            color: #ffffff;
        }
        .bcr-pulsing-dot {
            width: 8px;
            height: 8px;
            background-color: #a5b4fc; /* Tailwind indigo-300 */
            border-radius: 50%;
            display: inline-block;
            animation: bcr-pulse 1.5s infinite ease-in-out;
        }
        @keyframes bcr-pulse {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 1; }
        }

        /* Styles for the floating widget */
        #bcr-chat-toggle {
            transition: all 0.3s ease;
        }
        #bcr-chat-widget-container {
            height: 80vh;
            max-height: 600px;
            width: 90vw;
            max-width: 400px;
            transition: all 0.3s ease-in-out;
        }
    </style>
</head>
<body class="bcr-body">

    <!-- 1. CHAT WIDGET CONTAINER: This holds the entire chat window. It's hidden by default. -->
    <div id="bcr-chat-widget-container" class="hidden fixed bottom-24 right-5 bg-white rounded-2xl shadow-2xl flex flex-col z-50">
        <!-- Header -->
        <div class="p-4 border-b border-slate-200 flex justify-between items-center flex-shrink-0">
            <div class="flex items-center space-x-3">
                <div class="w-10 h-10 bg-indigo-600 rounded-full flex items-center justify-center text-white text-lg font-bold">
                    BC
                </div>
                <div>
                    <h1 class="text-md font-bold text-slate-900">Brigitte's AI Assistant</h1>
                    <p class="text-xs text-slate-500">Online</p>
                </div>
            </div>
            <button id="bcr-chat-close-btn" class="text-slate-400 hover:text-slate-600">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"></line><line x1="6" y1="6" x2="18" y2="18"></line></svg>
            </button>
        </div>

        <!-- Chat Messages -->
        <div id="bcr-chat-container" class="flex-1 p-4 overflow-y-auto bcr-chat-container">
            <div class="flex items-start gap-3 mb-4">
                <div class="w-8 h-8 bg-indigo-600 rounded-full flex-shrink-0 flex items-center justify-center text-white text-sm font-bold">AI</div>
                <div class="bcr-ai-bubble p-3 rounded-xl rounded-tl-none max-w-xs text-sm">
                    <p>Hello! I can answer your questions about Brigitte's research, experience, and job market profile. How can I help?</p>
                </div>
            </div>
            <div id="bcr-typing-indicator" class="hidden flex items-start gap-3 mb-4">
                <div class="w-8 h-8 bg-indigo-600 rounded-full flex-shrink-0 flex items-center justify-center text-white text-sm font-bold">AI</div>
                <div class="bcr-ai-bubble p-3 rounded-xl rounded-tl-none">
                    <div class="flex items-center space-x-1">
                        <span class="bcr-pulsing-dot"></span>
                        <span class="bcr-pulsing-dot" style="animation-delay: 0.2s;"></span>
                        <span class="bcr-pulsing-dot" style="animation-delay: 0.4s;"></span>
                    </div>
                </div>
            </div>
        </div>

        <!-- Input Area -->
        <div class="p-4 border-t border-slate-200 bg-white rounded-b-2xl flex-shrink-0">
             <form id="bcr-chat-form" class="flex items-center space-x-2">
                <input type="text" id="bcr-user-input" placeholder="Ask a question..." class="w-full px-4 py-2 border border-slate-300 rounded-full focus:outline-none focus:ring-2 focus:ring-indigo-500 transition duration-200 text-sm">
                <button type="submit" class="bg-indigo-600 text-white p-2.5 rounded-full hover:bg-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 transition duration-200 flex-shrink-0">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="22" y1="2" x2="11" y2="13"></line><polygon points="22 2 15 22 11 13 2 9 22 2"></polygon></svg>
                </button>
            </form>
        </div>
    </div>

    <!-- 2. CHAT TOGGLE BUTTON: This button is always visible and opens the chat widget. -->
    <button id="bcr-chat-toggle" class="fixed bottom-5 right-5 w-16 h-16 bg-indigo-600 rounded-full text-white shadow-lg flex items-center justify-center hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 z-40">
        <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path></svg>
    </button>
    
    <script>
        // All variable and ID names are prefixed with 'bcr-' to avoid conflicts with your site's existing styles/scripts.
        const chatToggle = document.getElementById('bcr-chat-toggle');
        const chatWidgetContainer = document.getElementById('bcr-chat-widget-container');
        const chatCloseBtn = document.getElementById('bcr-chat-close-btn');
        const chatContainer = document.getElementById('bcr-chat-container');
        const chatForm = document.getElementById('bcr-chat-form');
        const userInput = document.getElementById('bcr-user-input');
        const typingIndicator = document.getElementById('bcr-typing-indicator');

        chatToggle.addEventListener('click', () => {
            chatWidgetContainer.classList.toggle('hidden');
            chatToggle.classList.toggle('hidden');
        });

        chatCloseBtn.addEventListener('click', () => {
            chatWidgetContainer.classList.add('hidden');
            chatToggle.classList.remove('hidden');
        });

        const systemInstruction = `# Act as Brigitte Castañeda Rodríguez
You are Brigitte Castañeda Rodríguez, currently on the 2024/2025 Economics Job Market... (rest of your system prompt is unchanged)`; // NOTE: Keep your full system prompt here.
        // ... (The rest of your existing JavaScript logic remains the same) ...

        chatForm.addEventListener('submit', async (e) => {
            e.preventDefault();
            const userMessage = userInput.value.trim();
            if (!userMessage) return;
            appendMessage(userMessage, 'user');
            userInput.value = '';
            showTypingIndicator();
            try {
                const aiResponse = await getAIResponse(userMessage);
                hideTypingIndicator();
                appendMessage(aiResponse, 'ai');
            } catch (error) {
                console.error('Error fetching AI response:', error);
                hideTypingIndicator();
                appendMessage("I'm sorry, I'm having trouble connecting at the moment. Please try again later.", 'ai');
            }
        });

        function showTypingIndicator() {
            typingIndicator.classList.remove('hidden');
            chatContainer.scrollTop = chatContainer.scrollHeight;
        }

        function hideTypingIndicator() {
            typingIndicator.classList.add('hidden');
        }
        
        function appendMessage(message, sender) {
            const messageWrapper = document.createElement('div');
            if (sender === 'user') {
                messageWrapper.innerHTML = `
                    <div class="flex items-end justify-end gap-2 mb-4">
                        <div class="bcr-user-bubble p-3 rounded-xl rounded-br-none max-w-xs text-sm">
                            <p>${message}</p>
                        </div>
                    </div>`;
            } else {
                 messageWrapper.innerHTML = `
                    <div class="flex items-start gap-3 mb-4">
                        <div class="w-8 h-8 bg-indigo-600 rounded-full flex-shrink-0 flex items-center justify-center text-white text-sm font-bold">AI</div>
                        <div class="bcr-ai-bubble p-3 rounded-xl rounded-tl-none max-w-xs text-sm">
                            <p>${message.replace(/\n/g, '<br>')}</p>
                        </div>
                    </div>`;
            }
            // Insert the new message before the typing indicator
            chatContainer.insertBefore(messageWrapper, typingIndicator);
            chatContainer.scrollTop = chatContainer.scrollHeight;
        }

        async function getAIResponse(userQuery) {
            const apiKey = "";
            const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-05-20:generateContent?key=${apiKey}`;
            const payload = {
                contents: [{ parts: [{ text: userQuery }] }],
                systemInstruction: { parts: [{ text: systemInstruction }] },
            };
            let response;
            let result;
            let retries = 3;
            let delay = 1000;
            for (let i = 0; i < retries; i++) {
                try {
                    response = await fetch(apiUrl, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });
                    if (response.ok) {
                        result = await response.json();
                        break;
                    } else if (response.status === 429 || response.status >= 500) {
                        await new Promise(res => setTimeout(res, delay));
                        delay *= 2;
                    } else {
                         throw new Error(`API request failed with status ${response.status}`);
                    }
                } catch (error) {
                     if (i === retries - 1) {
                        console.error("Fetch error after multiple retries:", error);
                        throw error;
                    }
                    await new Promise(res => setTimeout(res, delay));
                    delay *= 2;
                }
            }
            const candidate = result.candidates?.[0];
            if (candidate && candidate.content?.parts?.[0]?.text) {
                return candidate.content.parts[0].text;
            } else {
                console.error("Unexpected API response structure:", result);
                return "I apologize, but I received an unexpected response. Could you please rephrase your question?";
            }
        }
    </script>
</body>
</html>


<!-- ---
layout: about
permalink: /
title: <strong>Brigitte</strong> Castañeda Rodríguez
order: 1
description: Evaluating climate and energy policies <br/> #

profile:
  align: left
  image: circle_pic_prof.png

news: true
social: true
---
<link rel="stylesheet" href="https://www.gstatic.com/dialogflow-console/fast/df-messenger/prod/v1/themes/df-messenger-default.css">
<script src="https://www.gstatic.com/dialogflow-console/fast/df-messenger/prod/v1/df-messenger.js"></script>
<df-messenger
  location="us-central1"
  project-id="gneerative-learning"
  agent-id="a9a55d46-0f2b-4592-a9d8-902505f57a96"
  language-code="en"
  max-query-length="-1">
  <df-messenger-chat
    chat-title="Hi, I’m Brigitte’s AI assistant. Ask me anything about her research, experience, and job market profile.">
  </df-messenger-chat>
</df-messenger>
<style>
  df-messenger {
    z-index: 999;
    position: fixed;
    --df-messenger-font-color: #000;
    --df-messenger-font-family: Google Sans;
    --df-messenger-chat-background: #f3f6fc;
    --df-messenger-message-user-background: #d3e3fd;
    --df-messenger-message-bot-background: #fff;
    bottom: 0;
    right: 0;
    top: 0;
    width: 350px;
  }
</style>

👉 **On the right, you’ll find Brigitte’s AI assistant — ask anything about her research, experience, and job market profile.**

PhD Candidate in Economics, [Universidad de los Andes](https://economia.uniandes.edu.co/)

Research Interest: _Macroeconomics, Environmental Economics._

Topics: _Climate Policies, Energy Transition.

Supervisor: [Hernando Zuleta](https://scholar.google.com/citations?user=CgFQtFIAAAAJ&hl=en)

Thesis Overview:

- *Can Growth Take Place While Reducing Emissions? The role of Energy Mix*  [Link](https://github.com/brigitte-castaneda/brigitte-castaneda.github.io/blob/506517921f3871f335ded852451211b83a969a4b/assets/docs/Can_growth_take_place_while_reducing_emissions.pdf)

- *Climate Policy and Structural Change: Evidence from Energy Transition in Latin America* (with Hernando Zuleta)  [Link](https://github.com/brigitte-castaneda/brigitte-castaneda.github.io/blob/02c28593dc3809e0be0a6ee34501ee10b994035b/assets/docs/Structural_change_and_climate_policies.pdf)

- *Spreading Jam Across the National Toast: Royalties and Local Fiscal Capacities (JMP)* (with Andrés Álvarez and Marc Hofstetter)  [Link](https://github.com/brigitte-castaneda/brigitte-castaneda.github.io/blob/506517921f3871f335ded852451211b83a969a4b/assets/docs/JMP_Brigitte_Castaneda.pdf)


Languages: Spanish (Native), English (Fluent), Russian (Fluent), French (Basic).

Previous Experience:
Consultant for [GGGI](https://gggi.org/), [EDF](https://www.edf.org/), [CFS](https://cfs.uniandes.edu.co/es/), [CREE](https://creenergia.org/), and World Bank.

Affiliations: Member of the [EfD Network](https://www.efdinitiative.org/) via [REES Colombia](https://reesefdcolombia.uniandes.edu.co/).

**I will be on the Job Market in 2025/2026.**

<small>*Last updated: September 2025*</small>
-->
 ---
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


<!-- Load chatbot font and Tailwind -->
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>

<!-- Tailwind-style floating chatbot (no <html>, <head>, <body>) -->
<style>
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
    background-color: #eef2ff;
    color: #3730a3;
  }
  .bcr-user-bubble {
    background-color: #4f46e5;
    color: #ffffff;
  }
  .bcr-pulsing-dot {
    width: 8px;
    height: 8px;
    background-color: #a5b4fc;
    border-radius: 50%;
    display: inline-block;
    animation: bcr-pulse 1.5s infinite ease-in-out;
  }
  @keyframes bcr-pulse {
    0%, 100% { opacity: 0.3; }
    50% { opacity: 1; }
  }
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

<!-- Chatbot widget HTML -->
<div id="bcr-chat-widget-container" class="hidden fixed bottom-24 right-5 bg-white rounded-2xl shadow-2xl flex flex-col z-50">
  <div class="p-4 border-b border-slate-200 flex justify-between items-center flex-shrink-0">
    <div class="flex items-center space-x-3">
      <div class="w-10 h-10 bg-indigo-600 rounded-full flex items-center justify-center text-white text-lg font-bold">BC</div>
      <div>
        <h1 class="text-md font-bold text-slate-900">Brigitte's AI Assistant</h1>
        <p class="text-xs text-slate-500">Online</p>
      </div>
    </div>
    <button id="bcr-chat-close-btn" class="text-slate-400 hover:text-slate-600">
      ✕
    </button>
  </div>
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
  <div class="p-4 border-t border-slate-200 bg-white rounded-b-2xl flex-shrink-0">
    <form id="bcr-chat-form" class="flex items-center space-x-2">
      <input type="text" id="bcr-user-input" placeholder="Ask a question..." class="w-full px-4 py-2 border border-slate-300 rounded-full focus:outline-none focus:ring-2 focus:ring-indigo-500 transition duration-200 text-sm">
      <button type="submit" class="bg-indigo-600 text-white p-2.5 rounded-full hover:bg-indigo-500">
        ➤
      </button>
    </form>
  </div>
</div>

<button id="bcr-chat-toggle" class="fixed bottom-5 right-5 w-16 h-16 bg-indigo-600 rounded-full text-white shadow-lg flex items-center justify-center hover:bg-indigo-700 z-40">
  💬
</button>

<script>
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
Brigitte is currently on the Job Market 2025/2026 in economics. She has a background in engineering and economics and her research focuses on carbon pricing, energy transitions, and the macroeconomic impacts of climate policies, especially in Latin America...`;

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
      appendMessage("Sorry, I'm having trouble right now. Please try again later.", 'ai');
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
    chatContainer.insertBefore(messageWrapper, typingIndicator);
    chatContainer.scrollTop = chatContainer.scrollHeight;
  }

  async function getAIResponse(userQuery) {
    const apiKey = ""; // ← debes ingresar aquí tu API KEY de Gemini
    const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-05-20:generateContent?key=${apiKey}`;
    const payload = {
      contents: [{ parts: [{ text: userQuery }] }],
      systemInstruction: { parts: [{ text: systemInstruction }] },
    };
    const response = await fetch(apiUrl, {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify(payload)
    });
    const result = await response.json();
    return result.candidates?.[0]?.content?.parts?.[0]?.text || "No response";
  }
</script>
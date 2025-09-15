---
layout: about
permalink: /
title: <strong>Brigitte</strong> Castañeda Rodríguez
order: 1
description: Evaluating climate/energy policies <br/> #

profile:
  align: right
  image: prof_pic.jpg

news: true
social: true
---
<!-- El contenedor desplegable que ya te funciona -->
<details>
  <summary><b>Try Brigitte's Chatbot</b></summary>

  <div id="chat" class="w-full px-1 h-screen">
    <!-- Aquí he insertado la configuración de tu NUEVO bot -->
    <df-messenger
      location="us-central1"
      project-id="gneerative-learning"
      agent-id="a9a55d46-0f2b-4592-a9d8-902505f57a96"
      language-code="en"
      max-query-length="-1">
      <df-messenger-chat
        chat-title="Brigitte">
        <!-- Opcional: Si quieres añadirle un icono a Brigitte, puedes agregar la línea chat-icon como en tu bot anterior -->
        <!-- chat-icon="https://example.com/path/to/brigitte_icon.png" -->
      </df-messenger-chat>
    </df-messenger>
  </div>
</details>

<!-- El script necesario para que Dialogflow Messenger funcione (ya lo tenías) -->
<script src="https://www.gstatic.com/dialogflow-console/fast/df-messenger/prod/v1/df-messenger.js"></script>

<!-- Todos tus estilos personalizados para mantener la apariencia (los he copiado exactos) -->
<style>
  df-messenger {
    --df-messenger-bot-message: #004aad; /* Bot message background color - dark blue */
    --df-messenger-button-titlebar-color: #b76e2a; /* Title bar button color */
    --df-messenger-chat-background-color: #ffffff; /* Chat background color - pure white */
    --df-messenger-font-color: #000000; /* Font color for messages - black for high contrast */
    --df-messenger-send-icon: #fca103; /* Send icon color */
    --df-messenger-user-message: #005c2e; /* User message background color - dark green */
    --df-messenger-chat-border-radius: 10px; /* Rounded corners for chat window */
    --df-messenger-chat-box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Subtle shadow for chat window */
  }

  df-messenger .chat-wrapper[opened] df-messenger-chat .message-list .message.user {
    background-color: var(--df-messenger-user-message);
    border-radius: 10px; /* Rounded corners for user messages */
    animation: fadeIn 0.5s ease-in-out; /* Fade-in animation for user messages */
  }

  df-messenger .chat-wrapper[opened] df-messenger-chat .message-list .message.bot {
    background-color: var(--df-messenger-bot-message);
    border-radius: 10px; /* Rounded corners for bot messages */
    animation: fadeIn 0.5s ease-in-out; /* Fade-in animation for bot messages */
  }

  df-messenger .chat-wrapper[opened] df-messenger-chat {
    background-color: var(--df-messenger-chat-background-color);
    border-radius: var(--df-messenger-chat-border-radius);
    box-shadow: var(--df-messenger-chat-box-shadow);
  }

  df-messenger .chat-wrapper[opened] df-messenger-titlebar {
    background-color: var(--df-messenger-button-titlebar-color);
    border-radius: var(--df-messenger-chat-border-radius) var(--df-messenger-chat-border-radius) 0 0;
  }

  df-messenger .chat-wrapper[opened] df-messenger-input {
    color: var(--df-messenger-font-color);
  }

  df-messenger .chat-wrapper[opened] df-messenger-send-icon {
    fill: var(--df-messenger-send-icon);
  }

  .df-messenger-message {
    font-family: Arial, sans-serif; /* Specify a fallback font */
    font-size: 18px; /* Increase font size for better readability */
    line-height: 1.5; /* Set line spacing */
    padding: 14px; /* Add padding for better spacing */
    margin: 10px 0; /* Add margins for better spacing between messages */
    color: var(--df-messenger-font-color); /* Apply the font color variable */
  }

  .w-full {
    width: 95%;
  }

  .px-1 {
    padding-left: 1rem;
    padding-right: 1rem;
  }

  .h-screen {
    height: 60vh;
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
</style>

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
# Journey: Context-Aware Fitness & Nutrition Agent

**Journey** is a holistic fitness application designed to bridge the gap between workout tracking and automated, macro-aware nutrition. 

## 📱 What Journey Does Today

Currently, Journey serves as a highly contextual daily fitness companion. Unlike static trackers, Journey understands your body's readiness by analyzing your holistic health data.

- **Comprehensive Tracking:** We currently track your daily **workouts, water intake, step counts, and sleep metrics**.
- **Context Awareness:** The app knows if today is a "Training Day" or a "Rest Day" and adjusts your recovery profile accordingly.
- **Archetype Profiling:** We tailor the experience based on user archetypes (e.g., Strength Purist vs. Wellness Starter).

<img width="350" alt="Simulator Screenshot - iPhone 17 Pro - 2026-04-28 at 20 44 11" src="https://github.com/user-attachments/assets/cfe8fec8-bd44-48b1-a8f0-640c7dbf8b77" />


While our physical tracking is robust, the nutrition aspect—arguably the most crucial part of fitness—is still a manual, fragmented process for users. That's where Swiggy comes in.

---

## 🌟 The Vision with Swiggy MCP

Current fitness apps tell you *what* you should eat. Journey will actually get it for you. 
By integrating Swiggy Food, Instamart, and Dineout MCPs directly into our upcoming AI chat interface, we will turn nutritional advice into instant, actionable delivery.

---

## 🚀 Planned Integrations & Use Cases

### 1. 🥗 Macro-Aware Meal Ordering (Swiggy Food MCP)
**The Problem:** Hitting your exact protein/carb/fat targets when ordering delivery is tedious and involves a lot of mental math.
**The Journey Solution:** Our AI Agent will read your daily macro targets and current intake. When you ask for a meal, it will filter local restaurant menus via Swiggy MCP to find dishes that perfectly fit your remaining macros.

> *"I need a high-protein dinner under 600 calories."*

**MCP Tools We Will Use:** `search_menu`, `get_restaurant_menu`, `update_food_cart`, `place_food_order`

---

### 2. 🛒 Fitness Pantry Auto-Restock (Swiggy Instamart MCP)
**The Problem:** Running out of essential fitness staples (protein powder, eggs, oats, Greek yogurt) disrupts diet consistency.
**The Journey Solution:** The agent will monitor your supplement and pantry usage. It will automatically build an Instamart cart to restock your essentials before you run out, or bulk-order ingredients for your AI-generated weekly meal plan.

> *"Plan my meals for next week and buy the ingredients."*

**MCP Tools We Will Use:** `search_products`, `update_cart`, `checkout`

---

### 3. 🍽️ Healthy Dine-Out Concierge (Swiggy Dineout MCP)
**The Problem:** Finding a restaurant that accommodates specific dietary goals (keto, high-protein, vegan) for social outings is difficult.
**The Journey Solution:** The agent will use the Dineout MCP to find restaurants with healthy/clean eating options, check table availability, and book reservations based on your dietary profile.

> *"Book a healthy dinner for two tonight at 8 PM."*

**MCP Tools We Will Use:** `search_restaurants_dineout`, `get_available_slots`, `book_table`

---

## 🛠️ Architecture Overview

Our mobile client will use a dual-model strategy to maintain privacy and speed:
1. **Local Apple Foundation Models:** Handles quick Q&A, macro math, and general coaching securely on-device.
2. **Gemini 3.1 Flash Lite (Proxy Backend):** Routes complex Swiggy API calls, multi-step orders, and Vision-to-Macros requests. 

The iOS app will implement a lightweight Swiggy MCP client that the AI Agent invokes as registered **Tools**, seamlessly blending conversation with real-world Swiggy commerce.

---

*This repository is a demonstration created for the Swiggy Builders Club application.*

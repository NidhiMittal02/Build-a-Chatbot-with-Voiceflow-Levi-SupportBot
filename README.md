# 🧵 Levi SupportBot – Voiceflow Chatbot

## 📌 Project Overview

**Levi SupportBot** is an AI-powered customer support chatbot built using **Voiceflow**.  
It assists Levi’s customers with:

- Product-related queries  
- New jeans information  
- Women’s clothing overview  
- Order tracking  
- Delivery updates  
- Return assistance  

The chatbot is deployed as a **web widget** with both **chat and voice capabilities** enabled.

---

## 🚀 Live Demo

You can test the chatbot here:

👉 **Voiceflow Share Link:**  
https://creator.voiceflow.com/share/698dcc4c3bb28873a3623413/development

---

# 🏗️ System Architecture (Block Flow Explanation)

Below is a structured explanation of the complete conversational flow based on the Voiceflow blocks.

---

## 🔹 1️⃣ Welcome Block

**Block: Welcome Message**

Message:
> "Welcome to Levis, please let me know how I can help you today"

User Options:
- I have a question about product  
- I need help with my order  

This block acts as the **entry point** of the chatbot.

---

## 🔹 2️⃣ Product Inquiry Flow

If user selects:

➡ **“I have a question about product”**

### Block 2:
Message:
> "Sure! What would you like to know"

- Saves user reply as: `{last_utterance}`
- Passes response to AI Agent block

### Block 4:
AI Agent processes the user query dynamically.

### Block 5:
> "Is there anything else I can help you with today?"

Options:
- Yes → Loop back to conversation
- No → Go to closing message

### Block 6 (Closing Message):
> "Thank you for visiting our store, we are here to help at any time"

---

## 🔹 3️⃣ Order Help Flow

If user selects:

➡ **“I need help with my order”**

### Block 3:
Message:
> "No problem at all, how can I help with your order"

Options:
- Returns  
- Update on delivery  
- I have a problem with a product received  

---

## 🔹 4️⃣ Delivery Update Flow

If user selects:
➡ **Update on delivery**

- Sets variable: `{order_issue} = on delivery`
- Moves to Agent block (Block 8)

---

## 🔹 5️⃣ Product Issue Flow

If user selects:
➡ **Problem with received product**

- Sets variable: `{order_issue} = order received`
- Moves to Block 7

---

## 🔹 6️⃣ Order Number Collection

### Block 7:
Message:
> "Please provide your product number"

- Saves input as: `{order_number}`

This ensures structured data collection before API call.

---

## 🔹 7️⃣ API Integration

### Block 11:
HTTP Request Block (POST)

Used to:
- Send order number
- Fetch order details
- Process tracking information

This enables backend connectivity.

---

## 🔹 8️⃣ Track Order Shortcut

### Block 9:
Contains:

- Text input  
- Quick reply: **Track my order**  
- Direct link:  
  https://levi.in/pages/track-order  

Provides fast redirection for order tracking.

---

## 🔹 9️⃣ Resolution Confirmation

### Block 10:
Message:
> "Does that resolve your issue?"

Options:
- Yes → End conversation  
- No → Loop back for further assistance  

---

# 🎤 Voice & Interface Configuration

### Modality:
- Chat enabled  
- Voice input enabled  
- Voice output enabled  
- Voice mode enabled  
- Stream text enabled  

### Interface:
- Widget  
- Positioned on Right  
- Side spacing: 40px  
- Bottom spacing: 20px  

---

# 🧠 Variables Used

| Variable | Purpose |
|----------|----------|
| `{last_utterance}` | Stores user product query |
| `{order_issue}` | Stores type of order problem |
| `{order_number}` | Stores user order ID |

---

# 🔄 Complete Conversation Flow Summary

```
User Entry
   ↓
Welcome Block
   ↓
Product Flow  → AI Agent → Follow-up → Close
         OR
Order Help Flow
   ↓
Select Issue
   ↓
Collect Order Number
   ↓
API Call (POST)
   ↓
Provide Tracking / Resolution
   ↓
Confirmation
   ↓
End or Loop
```

---

# 🚀 Features

✅ Product inquiry handling  
✅ Order tracking support  
✅ Delivery update assistance  
✅ Return issue guidance  
✅ API integration  
✅ Voice-enabled interaction  
✅ Quick reply buttons  
✅ Structured variable handling  

---

# 📊 Benefits

- 24/7 automated support  
- Reduced manual workload  
- Improved customer experience  
- Faster resolution process  
- Clear conversational structure  

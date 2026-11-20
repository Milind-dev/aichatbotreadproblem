# 💊 Pharma Chatbot — Product Summary Navigation

A React-based mock chatbot that answers pharmaceutical product queries and lets users
navigate to a focused supplier table or a complete product summary page.

Built for the "AI Chatbot with Product Summary Navigation" assignment.

---

## ✨ Features

### 1. Chatbot Interface
- Message input with send button (Enter key also sends)
- User and bot message bubbles (distinct styles)
- Animated loading indicator (`● ● ●`) while awaiting mock API response
- Auto-scroll to the latest message
- Input disabled while loading to prevent duplicate sends

### 2. Chatbot Functionality
- Mock AI responses (no real backend / no API key required)
- Recognizes the query `Show me suppliers of Paracetamol`
- Replies with inline action buttons:
  - **View Supplier Data** → `/product/paracetamol/suppliers`
  - **View Complete Summary** → `/product/paracetamol/summary`
- Handles unrecognized queries gracefully with a fallback message
- Chat history persists across route navigation (React Context)

### 3. Supplier Data Page
- Table columns: **Company**, **Country**, **Type**
- Live search across all columns
- Country dropdown filter (India / China / Germany)
- Pagination (2 rows per page so the feature is visible)
- Empty state when search/filter yields no results

### 4. Complete Product Summary Page
- 4 tabs:
  - **API Data**
  - **FDF Data**
  - **FDF Combination**
  - **Commercial Information**
- Each tab renders a table using the same reusable `<DataTable>` component
- Loading state while fetching mock summary data

### 5. Engineering Requirements
- ✅ React functional components + hooks (`useState`, `useEffect`, `useRef`, `useReducer`, `useContext`)
- ✅ React Router (`/`, `/product/:id/suppliers`, `/product/:id/summary`)
- ✅ Reusable components (`DataTable`, `MessageBubble`, `ChatInput`, `LoadingDots`, `Tabs`, `EmptyState`)
- ✅ Chat history survives navigation via `<ChatProvider>` mounted **above** `<Routes>`
- ✅ API logic isolated in `src/api/mockApi.js` — UI never calls `setTimeout` or `fetch` directly
- ✅ Loading + empty states handled everywhere
- ✅ Tailwind CSS for styling

---

## 🛠 Tech Stack

| Layer         | Technology              |
|---------------|-------------------------|
| Framework     | React 18 (Vite)         |
| Routing       | react-router-dom v6     |
| Styling       | Tailwind CSS            |
| State         | React Context + useReducer |
| Data          | Mock API (Promises + setTimeout) |
| Language      | JavaScript (JSX)        |

---

## 🚀 Getting Started

### Prerequisites
- Node.js ≥ 18
- npm ≥ 9

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/pharma-chatbot.git
cd pharma-chatbot

# 2. Install dependencies
npm install

# 3. Start the dev server
npm run dev

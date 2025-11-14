# Search App

A modern Next.js application with search functionality and chat feature.

## Features

- 🔍 **Advanced Search**: Search for products with real-time results
- 💬 **Chat Assistant**: Interactive chat feature for user assistance
- 📱 **Responsive Design**: Works perfectly on desktop and mobile
- 🎨 **Modern UI**: Clean and intuitive interface with Tailwind CSS
- ⚡ **Fast Performance**: Built with Next.js 14 and optimized for speed

## Getting Started

### Prerequisites

- Node.js 18+ 
- npm or yarn

### Installation

1. Install dependencies:
```bash
npm install
```

2. Run the development server:
```bash
npm run dev
```

3. Open [http://localhost:3000](http://localhost:3000) in your browser.

## Project Structure

```
├── app/
│   ├── globals.css          # Global styles
│   ├── layout.tsx           # Root layout
│   └── page.tsx             # Main page component
├── lib/
│   └── utils.ts             # Utility functions
├── components/              # Reusable components (to be added)
└── public/                  # Static assets
```

## Features Overview

### Search Functionality
- Real-time search with loading states
- Filtered results based on query
- Product cards with images, descriptions, and pricing
- Category-based filtering

### Chat Feature
- Interactive chat interface
- Message history
- Typing indicators
- Responsive sidebar design

### UI Components
- Modern card-based layout
- Responsive grid system
- Interactive buttons and inputs
- Loading states and animations

## Customization

### Adding Real API Integration

Replace the mock search function in `app/page.tsx` with your actual API calls:

```typescript
const performSearch = async (query: string) => {
  setIsSearching(true)
  try {
    const response = await fetch(`/api/search?q=${encodeURIComponent(query)}`)
    const results = await response.json()
    setSearchResults(results)
  } catch (error) {
    console.error('Search failed:', error)
  } finally {
    setIsSearching(false)
  }
}
```

### Styling

The app uses Tailwind CSS with custom components. You can modify the styles in:
- `app/globals.css` for global styles
- `tailwind.config.js` for theme customization

## Deployment

Build the application for production:

```bash
npm run build
npm start
```

## Technologies Used

- **Next.js 14** - React framework
- **TypeScript** - Type safety
- **Tailwind CSS** - Styling
- **Lucide React** - Icons
- **clsx & tailwind-merge** - Utility functions

## 🔗 Connecting to Shopify-AI Backend

This frontend connects to the Shopify-AI backend API for product search and chat functionality.

### Prerequisites

1. **Backend Running**: Your Shopify-AI backend must be running
   ```bash
   cd path/to/Shopify-AI
   python3 search_api.py
   ```

2. **Environment Configuration**: Copy `.env.example` to `.env.local`
   ```bash
   cp .env.example .env.local
   ```

3. **Update API URL** (if needed):
   - For local development: `NEXT_PUBLIC_API_BASE_URL=http://localhost:8000`
   - For production: `NEXT_PUBLIC_API_BASE_URL=https://your-backend-url.com`

### Setup Instructions

1. **Install Dependencies**:
   ```bash
   npm install
   ```

2. **Run Development Server**:
   ```bash
   npm run dev
   ```

3. **Open in Browser**:
   ```
   http://localhost:3000
   ```

### API Endpoints Used

The frontend connects to these backend endpoints:

- `GET /get-collections` - Fetch available product collections
- `POST /search-fast` - Fast product search
- `POST /chat` - AI-powered chat assistance

### Features

- 🔍 **Product Search**: Real-time search with filters
- 💬 **AI Chat**: Conversational product recommendations
- 📊 **Collections**: Browse different product catalogs
- ⚡ **Fast**: Optimized with Next.js 14 and server-side rendering

### Repository Links

- **Frontend**: https://github.com/amulyatayal/ai-search-frontend
- **Backend**: https://github.com/amulyatayal/Shopify-AI


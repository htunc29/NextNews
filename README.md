# Next.js News App - Routing & Rendering Demo

Modern news application demonstrating advanced routing features with Next.js 14 App Router.

## 🚀 Features

- **Route Groups** - Organizes marketing and content pages
- **Dynamic Routes** - Uses `[slug]` parameter for news detail pages
- **Parallel Routes** - Renders modal and content simultaneously
- **Intercepting Routes** - Modal overlay for image viewing
- **Error Boundaries** - Error handling and custom 404 pages
- **Catch-all Routes** - Archive filtering with `[[...filter]]`

## 📁 Project Structure

```
app/
├── (marketing)/           # Route group: Marketing pages
│   ├── layout.js         # Marketing layout
│   └── page.js           # Home page
├── (content)/            # Route group: Content pages
│   ├── layout.js         # Content layout
│   ├── news/
│   │   ├── page.js       # News list
│   │   └── [slug]/       # Dynamic route
│   │       ├── page.js   # News detail
│   │       ├── layout.js # Parallel route layout
│   │       ├── image/
│   │       │   └── page.js      # Image page
│   │       └── @modal/          # Parallel route slot
│   │           ├── default.js   # Default modal state
│   │           └── (.)image/    # Intercepting route
│   │               └── page.js  # Modal overlay
│   └── archive/
│       ├── layout.js     # Parallel route layout
│       ├── @latest/      # Latest news slot
│       └── @archive/     # Archive slot
│           └── [[...filter]]/   # Catch-all route
│               ├── page.js
│               └── error.js
├── api/
│   └── route.js          # API endpoint
└── globals.css           # Global styles
```

## 🛠️ Technologies Used

- **Next.js 14** - App Router
- **React 18** - UI library
- **CSS Modules** - Styling
- **JavaScript** - Programming language

## 📋 Installation

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Production build
npm run build

# Start production server
npm start

# Linting
npm run lint
```

## 🔧 Development Server

```bash
npm run dev
```

The application will run at [http://localhost:3000](http://localhost:3000).

## 📖 Route Examples

- `/` - Home page (marketing layout)
- `/news` - News list
- `/news/will-ai-replace-humans` - News detail
- `/news/will-ai-replace-humans/image` - Image page (intercepted as modal)
- `/archive` - News archive
- `/archive/2021` - 2021 news
- `/archive/2021/tech` - 2021 technology news

## 🎯 Key Features

### Modal Intercepting
When clicking on an image in news detail page, it opens as a modal without page navigation. When accessing the URL directly, it shows as a normal page.

### Parallel Routes
Archive page renders latest news and filtered news simultaneously in different slots.

### Error Handling
Custom error boundaries and 404 pages at each route level.

### Route Groups
Marketing and content pages are organized in different layouts.

## 📁 File Structure

- `dummy-news.js` - Sample news data
- `components/` - Reusable components
- `lib/` - Utility functions
- `public/` - Static files
- `middleware.js` - Route middleware

## 🎨 Styling

The project uses global CSS. Custom styles are available for modal, news-list, and other components.

## 🚧 Important Notes

- Route intercepting only works with client-side navigation
- Parallel routes must define slot props in layout file
- Dynamic routes use `params` prop
- Optional catch-all routes use `[[...param]]` syntax
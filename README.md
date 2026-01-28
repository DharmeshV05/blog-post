# 📚 CA Monk Blog Application - React + TypeScript Edition

A modern, full-stack blog application built with React, TypeScript, Tailwind CSS, shadcn/ui, TanStack Query, and JSON Server.

## Features

- ✅ **Get All Blogs** - Display all blogs in a responsive sidebar with loading states
- ✅ **Get Blog by ID** - View detailed blog posts with cover images and formatted content
- ✅ **Create New Blog** - Add new blogs with title, description, categories, cover image, and content
- ✅ **Real-time Updates** - Uses TanStack Query for intelligent caching and automatic updates
- ✅ **Loading States** - Beautiful skeleton loaders for better UX
- ✅ **Error Handling** - Comprehensive error boundaries and user-friendly messages
- ✅ **Responsive Design** - Mobile-first design that works on all devices
- ✅ **Modern UI** - Built with shadcn/ui components and Tailwind CSS
- ✅ **TypeScript** - Fully typed for maximum developer experience

## Tech Stack

- **Frontend Framework**: React 19
- **Language**: TypeScript
- **Build Tool**: Vite
- **Styling**: Tailwind CSS
- **UI Components**: shadcn/ui
- **State Management**: TanStack Query v5
- **HTTP Client**: Axios
- **Backend API**: JSON Server
- **Component Library**: Radix UI

## 🛠️ Installation & Setup

### Prerequisites
- Node.js (v18+)
- npm or yarn

### 1. Clone and Install Dependencies

```bash
cd Blog-App-React
npm install
```

### 2. Start JSON Server

In a terminal, run the backend API:

```bash
npm run server
```

This will start JSON Server on `http://localhost:3001` with the sample data from `db.json`.

### 3. Start Development Server

In another terminal, run the React app:

```bash
npm run dev
```

Or run both simultaneously:

```bash
npm run dev:full
```

The app will be available at `http://localhost:5173`

## Project Structure

```
src/
├── components/           # React components
│   ├── ui/              # shadcn/ui components
│   │   ├── button.tsx
│   │   ├── card.tsx
│   │   ├── dialog.tsx
│   │   ├── input.tsx
│   │   └── textarea.tsx
│   ├── BlogList.tsx     # Blog list component
│   ├── BlogDetail.tsx   # Blog detail view
│   ├── BlogSkeleton.tsx # Loading skeletons
│   └── CreateBlogForm.tsx # Create blog modal
├── hooks/               # Custom hooks
│   └── useBlog.ts       # TanStack Query hooks
├── lib/                 # Utilities
│   ├── api.ts           # API client and types
│   └── utils.ts         # Helper utilities
├── pages/               # Page components (for future routing)
├── App.tsx              # Main app component
├── main.tsx             # React entry point
└── index.css            # Global styles with Tailwind

db.json                  # JSON Server database
tailwind.config.js       # Tailwind configuration
vite.config.ts           # Vite configuration
```

## API Endpoints

The application communicates with JSON Server running on `http://localhost:3001`:

### GET /blogs
Returns all blogs

**Response:**
```json
[
  {
    "id": 1,
    "title": "Blog Title",
    "category": ["TECH", "FINANCE"],
    "description": "Brief description",
    "date": "2026-01-11T09:12:45.120Z",
    "coverImage": "https://...",
    "content": "Full blog content..."
  }
]
```

### GET /blogs/:id
Returns a specific blog by ID

**Response:**
```json
{
  "id": 1,
  "title": "Blog Title",
  "category": ["TECH"],
  "description": "Brief description",
  "date": "2026-01-11T09:12:45.120Z",
  "coverImage": "https://...",
  "content": "Full blog content..."
}
```

### POST /blogs
Creates a new blog

**Request Body:**
```json
{
  "title": "New Blog",
  "description": "Brief description",
  "category": ["TECH"],
  "coverImage": "https://...",
  "content": "Full blog content..."
}
```

**Response:** Created blog object with auto-generated `id` and `date`

## Component Architecture

### BlogList Component
- Fetches all blogs using `useBlogList()` hook
- Displays blogs in a scrollable sidebar
- Shows loading skeletons while fetching
- Handles error states gracefully
- Highlights selected blog

### BlogDetail Component
- Fetches individual blog using `useBlog(id)` hook
- Displays cover image with fallback
- Shows blog metadata (date, categories)
- Renders content with proper formatting
- Includes back button navigation

### CreateBlogForm Component
- Modal dialog for creating new blogs
- Form fields for all blog properties
- Dynamic category input/removal
- Real-time form validation
- Shows loading state during submission
- Auto-invalidates blog list after successful creation

## TanStack Query Implementation

### useBlogList Hook
- Fetches all blogs with 5-minute stale time
- Automatic background refetching
- Query caching for performance
- Retry logic on failures

### useBlog Hook
- Fetches individual blog by ID
- Conditional fetching (only when ID is provided)
- Same caching strategy as list

### useCreateBlog Hook
- Handles blog creation mutations
- Automatically invalidates blog list after success
- Updates query cache with new blog
- Error handling with user feedback

## Available Scripts

```bash
# Start development server
npm run dev

# Start JSON Server backend
npm run server

# Start both dev server and JSON Server
npm run dev:full

# Build for production
npm build

# Preview production build
npm run preview

# Run linting
npm run lint
```

## Styling with Tailwind CSS

The application uses Tailwind CSS for styling with:
- Custom color variables for light/dark mode support
- Responsive design with mobile-first approach
- Animation utilities for smooth transitions
- Grid layouts for responsive components

## Error Handling

- **API Errors**: User-friendly error messages with AlertCircle icons
- **Network Issues**: Automatic retry with backoff strategy
- **Validation**: Form validation with required field checks
- **Error Boundaries**: Graceful error states in all components

## 📱 Responsive Design

The application is fully responsive:
- **Mobile**: Single column layout with stacked components
- **Tablet**: Two column layout beginning to form
- **Desktop**: Three column layout with sidebar, main content

## Deployment Tips

1. Build the production bundle:
   ```bash
   npm run build
   ```

2. Deploy the `dist/` folder to your hosting platform

3. For the backend, deploy JSON Server or use a real backend API

4. Update the `API_BASE_URL` in `src/lib/api.ts` if needed

##  Sample Data

The application comes with 3 sample blogs in `db.json`:
1. "Future of Fintech" - About AI and blockchain
2. "React Best Practices" - React hooks and patterns
3. "TypeScript in Production" - TypeScript best practices

You can add more blogs through the UI!

##  Troubleshooting

### JSON Server not connecting
- Ensure JSON Server is running: `npm run server`
- Check that it's on port 3001
- Look for firewall issues

### Styling not working
- Clear cache: `npm run dev` with `--force` flag
- Rebuild Tailwind: Restart dev server

### TypeScript errors
- Run `npm run lint` to check for issues
- Ensure all dependencies are installed: `npm install`

##  Learning Resources

- [React Documentation](https://react.dev)
- [Tailwind CSS](https://tailwindcss.com)
- [TanStack Query](https://tanstack.com/query/latest)
- [shadcn/ui](https://ui.shadcn.com)
- [JSON Server](https://github.com/typicode/json-server)

##  License

MIT License

##  Contributing

Feel free to fork this project and submit pull requests for any improvements!

---

**Happy blogging! **

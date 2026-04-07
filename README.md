# 🚀 Next.js A–Z Guide (With Practical Examples)

## 📌 What is Next.js?

Next.js is a **React framework** for building:

* Server-side rendered (SSR) apps
* Static websites (SSG)
* Full-stack applications (API routes)

👉 Built on top of React + Node.js

---

## ⚡ Why Use Next.js?

* ✅ SEO friendly (SSR & SSG)
* ✅ Full-stack support (API routes)
* ✅ Fast performance (automatic optimization)
* ✅ File-based routing
* ✅ Built-in image optimization
* ✅ Easy deployment (Vercel, Docker, etc.)

---

## 🏗️ Project Setup

### 1. Create Project

```bash
npx create-next-app@latest my-app
cd my-app
npm run dev
```

👉 Open: http://localhost:3000

---

## 📁 Folder Structure

```
my-app/
│── app/                # App Router (modern)
│── pages/              # Old router (optional)
│── components/         # Reusable UI
│── public/             # Static files
│── styles/             # CSS files
│── package.json
```

---

## 🧭 Routing (File-based)

### Example:

```
app/
 ├── page.js        → "/"
 ├── about/page.js → "/about"
```

### Code:

```javascript
export default function About() {
  return <h1>About Page</h1>;
}
```

---

## 🔁 Dynamic Routing

```
app/blog/[id]/page.js
```

```javascript
export default function Blog({ params }) {
  return <h1>Blog ID: {params.id}</h1>;
}
```

---

## 🌐 Data Fetching

### 1. Server-side (Default in App Router)

```javascript
async function getData() {
  const res = await fetch('https://api.example.com/data');
  return res.json();
}

export default async function Page() {
  const data = await getData();
  return <div>{data.name}</div>;
}
```

---

### 2. Static Generation

```javascript
export const revalidate = 60; // ISR (rebuild every 60s)
```

---

## ⚙️ API Routes (Backend inside Next.js)

```
app/api/user/route.js
```

```javascript
export async function GET() {
  return Response.json({ name: "Mahim" });
}
```

👉 Access: `/api/user`

---

## 🎨 Styling

### Tailwind CSS (Recommended)

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

```javascript
export default function Home() {
  return <h1 className="text-3xl font-bold">Hello Next.js</h1>;
}
```

---

## 🧩 Components

```javascript
function Button({ text }) {
  return <button>{text}</button>;
}
```

Use:

```javascript
<Button text="Click Me" />
```

---

## 🔐 Authentication (Basic Idea)

* Use JWT / NextAuth
* Store token in cookies

---

## 🖼️ Image Optimization

```javascript
import Image from "next/image";

<Image src="/img.png" width={300} height={200} alt="img" />
```

---

## ⚡ Performance Features

* Automatic code splitting
* Lazy loading
* Image optimization
* Server components

---

## 🌍 Environment Variables

```
.env.local
```

```
NEXT_PUBLIC_API_URL=http://localhost:5000
```

---

## 🐳 Docker (Production Ready)

### Dockerfile

```dockerfile
FROM node:18

WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

CMD ["npm", "start"]
```

---

## 🚀 Deployment

### 1. Vercel (Best)

```bash
npm install -g vercel
vercel
```

### 2. Docker / VPS

```bash
docker build -t next-app .
docker run -p 3000:3000 next-app
```

---

## 🔥 Best Practices

* Use **App Router (not pages)**
* Keep components reusable
* Use server components by default
* Optimize images
* Avoid unnecessary client-side JS

---

## ❌ Common Mistakes

* Using `useEffect` unnecessarily
* Fetching data on client instead of server
* Not using caching/revalidation
* Ignoring SEO

---

## 🎯 Interview Questions

1. SSR vs SSG difference?
2. What is ISR?
3. What are Server Components?
4. How routing works in Next.js?
5. How to optimize performance?

---

## 🧠 Summary

Next.js = React + Backend + Optimization

👉 You can build:

* SaaS apps
* Full-stack MERN apps
* SEO websites
* Dashboards

---

## 🚀 Next Step

* Build: Blog app (SSR + API)
* Build: SaaS dashboard
* Add: Authentication + Database

---

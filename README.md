<div align="center">
  <h1>☕ Gossip Cafe | Modern Web Experience</h1>
  <p><strong>A highly optimized, performant landing page and digital menu experience for Gossip Cafe.</strong></p>

  <p>
    <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white" alt="Next.js" />
    <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React" />
    <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind CSS" />
    <img src="https://img.shields.io/badge/Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white" alt="Netlify" />
  </p>
</div>

---

## 📖 Project Overview

This repository hosts the **production deployment build** for the Gossip Cafe web application. Engineered to deliver a lightning-fast user experience, the application transitions a traditional restaurant menu into a modern, highly interactive digital storefront. 

Originally prototyped as a monolithic HTML/CSS application, this iteration has been completely re-architected using **Next.js** to leverage static site generation (SSG) and edge caching, resulting in near-instantaneous page loads even on constrained mobile networks.

---

## ✨ Core Features & Technical Highlights

- 🚀 **Next.js Static Generation**: The entire site is pre-rendered into static HTML/JS/CSS (`_next` chunks) to guarantee zero layout shift and maximum SEO performance.
- 📱 **Mobile-First Responsive UI**: Styled with Tailwind CSS, ensuring the cafe's rich imagery (from signature Zinger Burgers to Peri Wraps) scales perfectly across all devices.
- ⚡ **Advanced Edge Caching**: Configured via `netlify.toml` with strict `Cache-Control: public, max-age=31536000, immutable` headers for Next.js static assets to leverage browser and CDN caching.
- 🖼️ **Optimized Asset Delivery**: High-quality UI assets (SVG icons, WOFF2 fonts, and optimized WebP/PNG images) are served directly from the edge.

---

## 🛠️ Detailed Technology Stack

### Front-End Engineering
* **Next.js**: Core framework for routing, compilation, and static asset generation.
* **React 18**: Underlying UI library powering component hydration.
* **Tailwind CSS**: Utility-first CSS framework used for pixel-perfect design constraints and responsive breakpoints.

### Infrastructure & Deployment
* **Netlify**: Serverless deployment platform handling global CDN distribution.
* **netlify.toml**: Infrastructure-as-code configuration defining custom headers, redirects, and image optimization pipelines.

---

## 🏗️ Production System Architecture

<details>
<summary><b>View Deployment Architecture Diagram</b> (Click to expand)</summary>

```mermaid
flowchart TD
    classDef client fill:#1e3a8a,stroke:#3b82f6,stroke-width:2px,color:#fff
    classDef edge fill:#064e3b,stroke:#10b981,stroke-width:2px,color:#fff
    classDef repo fill:#701a75,stroke:#d946ef,stroke-width:2px,color:#fff

    User(("Mobile / Desktop Client")) --> |HTTPS Request| CDN["Netlify Global Edge CDN"]:::edge
    
    subgraph Edge Network Delivery
        CDN --> |"Cache-Control: Immutable"| StaticJS["Pre-compiled _next/static JS Chunks"]:::edge
        CDN --> |Image Optimization| Media["Optimized Cafe Imagery (Zinger, Pasta, etc.)"]:::edge
    end

    subgraph GitHub Repository
        Repo["CAFE-WEBSITE Repo (Production Build)"]:::repo --> |Continuous Deployment| CDN
    end
    
    StaticJS --> User
    Media --> User
```
</details>

---

## 📂 Repository Note
> [!NOTE]  
> **This repository contains the finalized production build artifacts** (the `.next` / `out` equivalents) required by Netlify for hosting, rather than the raw `.tsx` source code. This ensures the live environment perfectly mirrors the tested production bundle.

---

## 👨‍💻 Developed By

**Muhammad Mateen**  
*Full-Stack & Front-End Specialist*

- 🌐 **Portfolio**: [mmateenn.netlify.app](https://mmateenn.netlify.app/)
- 💼 **LinkedIn**: [muhammadmateen112](https://www.linkedin.com/in/muhammadmateen112/)
- 📧 **Email**: [meetmuhammadmateen@gmail.com](mailto:meetmuhammadmateen@gmail.com)

# Outdoor Bachata Málaga

<div align="center">
    <img src="https://img.shields.io/badge/Astro-5.17.1-FF5D01?style=for-the-badge&logo=astro" alt="Framework" />
    <img src="https://img.shields.io/badge/Tailwind_CSS-4.2.1-38B2AC?style=for-the-badge&logo=tailwind-css" alt="Styling" />
    <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5" />
    <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3" />
    <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript" />
    <img src="https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Deployment" />
</div>

<p align="center">
    <i>A highly-optimized, single-page promotional landing site designed to capture Mediterranean cruise tourists seeking outdoor bachata and salsa classes in Málaga.</i>
</p>

## Interactive Engagement Sections

The landing page relies on distinct immersive visual sections to funnel users toward our main service domain.

| Section                  | Visual Strategy                                                  | Conversion Goal                                                  |
| ------------------------ | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| **Hero (Port Arrival)**  | Parallax background of a docked Mediterranean cruise             | Immediate value proposition and primary Call-To-Action (CTA)     |
| **Destination SEO Info** | Split-pane layout with high-readability typography               | Build desire for the destination and inject primary SEO keywords |
| **Alcazaba Experience**  | Dynamic random background selector showing historic Málaga views | Secondary CTA targeting users convinced by the location's beauty |

## Dynamic Background Engine

To keep the page lightweight while offering visual variety, the page bypasses external rate-limited image APIs in favor of a client-side randomized asset selection. Check `src/pages/index.astro` for specific path injections.

| Component                     | Responsibility                                                                                               |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------ |
| **bgImages[]**                | Array of predefined, high-resolution `.jpg` and `.avif` local assets located in `/public/images/fondos/`     |
| **DOMContentLoaded Listener** | Injects a randomized background image using inline styles to bypass default Astro/Tailwind specificity locks |

## SEO and Accessibility Architecture

The landing page structure prioritizing discoverability by search engines targeting specific tourism queries.

| Optimization Layer | Implementation Details                                                                                    |
| ------------------ | --------------------------------------------------------------------------------------------------------- |
| **Semantic HTML**  | Strict use of `<main>`, `<section>`, and `<header>` tags with linear `h1` to `h3` hierarchy               |
| **Metadata**       | Custom title, descriptions, and manifest links passed via Astro props in `src/layouts/Layout.astro`       |
| **Link Strategy**  | Dofollow links (`rel="dofollow"`) explicitly implemented on all CTAs pointing to `bachataalairelibre.com` |

## System Architecture

| Component                | Role                                                                                                                        |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| **Astro Build Engine**   | Statically generates the entire HTML payload resulting in near-instant load times with zero client-side React/Vue overhead. |
| **TailwindCSS Compiler** | Injects utility classes and removes unused CSS during the Vite build step.                                                  |
| **Client-side JS**       | Handles the lightweight dynamic assignment of the parallax background images on the end-user's device natively.             |

## Technology Stack

- **Frontend**: Astro 5.17, Vanilla JavaScript
- **Styling**: TailwindCSS 4.2
- **Deployment**: Vercel

## Key Features

1. **Performant Parallax Scrolling** — Creates a deeply immersive, premium feel without heavy Javascript libraries by relying on native CSS `background-attachment: fixed`.
2. **Glassmorphism Overlays** — Ensures perfect text readability regardless of the varied dynamic background images loaded behind the text.
3. **Zero-API Dynamic Asset Rotation** — Provides fresh visual experiences on every page load natively over local assets, avoiding 3rd-party API rate limits.
4. **Tailor-made SEO Targeting** — Structurally optimized exclusively for "Mediterranean cruises", "Málaga port", and "outdoor bachata/salsa" keywords.
5. **Dofollow Link Injection** — Built primarily as a high-quality satellite asset to pass domain authority to the parent business site.

## Testing Strategy

The project relies on Astro's internal compiler validation. Verification that components generate valid HTML without hydration errors is done via `npm run build`. Visual regression, responsive layout breaking points, and cross-browser parallax behavior are verified manually by running the development server.

## Project Setup

1. Install dependencies:

   ```bash
   npm install
   ```

2. Start the development server:

   ```bash
   npm run dev
   ```

3. Visit `http://localhost:4321`

---

Built for [Bachata al Aire Libre](https://bachataalairelibre.com/).

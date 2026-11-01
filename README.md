# Vykuntapuram Brand Sarees: Online Store

A modern, mobile-first e-commerce website for **Vykuntapuram Brand Sarees**, a successful local saree business that is now taking its wholesale-price brand sarees online. Customers can browse, choose and pay for sarees from their phone, and resellers can register for wholesale.

> **Status:** In development

---

## About the Business

Vykuntapuram Brand Sarees sells brand sarees at wholesale prices from its offline store, and also through Instagram and WhatsApp. This website brings that business online so that:

- Retail customers can shop and pay securely, any time.
- Resellers and dealers have a dedicated way to enquire and register.
- The owner can manage products, stock and orders without writing code.

**Store policy:** Returns are accepted only for damaged items.

---

## Features

### For customers
- Browse by category, fabric, colour, price and occasion
- Search with suggestions
- Product pages with image gallery, zoom and stock status
- Wishlist, quick view and cart drawer
- Guest checkout or account login (mobile OTP)
- Secure online payment through **Razorpay** (UPI, cards, net banking, wallets)
- Order tracking and email / WhatsApp updates
- One-tap "Ask on WhatsApp" on every product

### For resellers
- Wholesale page with benefits and how it works
- Reseller registration form
- "Get wholesale catalogue on WhatsApp" button
- Approved-reseller price tiers (planned)

### For the owner (admin panel)
- Add, edit and hide products with multi-image upload
- Stock management with low-stock alerts
- Order management with status updates and tracking links
- Refunds for approved damage claims through Razorpay
- Homepage banners and offers

---

## Design

- Layout and shopping flow follow the structure of a modern saree storefront (header with mega-menu, slide-in cart, hero banners, shop by occasion and price, product grids, brand story, footer).
- Bright, festive colour palette on a warm ivory background.
- Mobile first, designed from 360 px wide screens upwards.

| Role | Colour |
| --- | --- |
| Primary | Royal magenta `#C2185B` |
| Secondary | Peacock teal `#00897B` |
| Accent | Marigold gold `#FFB300` |
| Highlight | Vermilion `#FF5722` |
| Background | Warm ivory `#FFF8F0` |
| Text | Deep plum-charcoal `#2D1B2E` |

Fonts: Playfair Display (headings) and Poppins (body).

---

## Tech Stack

| Layer | Technology |
| --- | --- |
| Frontend | Next.js, React, Tailwind CSS |
| Backend and database | Node.js with PostgreSQL (or Supabase) |
| Payments | Razorpay (Orders API, Checkout, Webhooks, Refunds) |
| Images | Cloud storage with CDN (for example Cloudinary) |
| Email and messaging | Transactional email and WhatsApp Business API |
| Hosting | Vercel or a managed cloud in an Indian region |

---

## Getting Started

### Prerequisites
- Node.js 20 or later
- npm, yarn or pnpm
- A Razorpay account (Test Mode keys are enough for development)

### Installation

```bash
# 1. Clone the repository
git clone <your-repository-url>
cd <project-folder>

# 2. Install dependencies
npm install

# 3. Create your environment file
cp .env.example .env.local

# 4. Start the development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### Environment variables

Create a `.env.local` file with the following. **Never commit this file or share your secrets.**

```env
# App
NEXT_PUBLIC_SITE_URL=http://localhost:3000

# Database
DATABASE_URL=

# Razorpay (use Test Mode keys while developing)
NEXT_PUBLIC_RAZORPAY_KEY_ID=
RAZORPAY_KEY_SECRET=
RAZORPAY_WEBHOOK_SECRET=

# Email
EMAIL_API_KEY=
EMAIL_FROM=

# WhatsApp
NEXT_PUBLIC_WHATSAPP_NUMBER=919100648380
```

---

## Razorpay Payments

All online payments go through Razorpay. The server is the source of truth for every amount and payment status.

1. The server recalculates the cart total and creates a Razorpay order.
2. The browser opens Razorpay Checkout.
3. After payment, the server verifies the payment signature.
4. A verified webhook also confirms the payment, so orders stay correct even if the customer closes the browser.
5. Stock is reduced only after payment is confirmed.

**Testing:** Build and test fully in Razorpay **Test Mode**. Switch to **Live Mode** only after the go-live checklist is complete.

**Security:** Razorpay secrets live only in server environment variables and are never exposed in browser code or the repository.

---

## Project Structure

```text
/
├── app/               # Pages and routes
├── components/        # Reusable UI components
├── lib/               # Helpers (payments, database, utilities)
├── public/            # Static assets
├── styles/            # Global styles and design tokens
├── .env.example       # Template for environment variables
└── README.md
```

*(Update this section as the project grows.)*

---

## Roadmap

**Release 1 (launch)**
- [ ] Catalogue, search and filters
- [ ] Cart, wishlist and checkout
- [ ] Razorpay payments and webhooks
- [ ] Order emails and WhatsApp updates
- [ ] Admin panel for products, stock and orders
- [ ] Reseller registration and WhatsApp catalogue
- [ ] SEO, analytics and policy pages

**Release 2 (later)**
- [ ] Approved-reseller login with bulk price tiers
- [ ] Coupons and abandoned-cart reminders
- [ ] Reviews and loyalty points
- [ ] Sales dashboard
- [ ] Telugu and Hindi language support
- [ ] Automated courier integration

---

## Required Policy Pages

Razorpay needs these live before approving a live account: Privacy Policy, Terms and Conditions, Shipping Policy, and Refund and Cancellation Policy. The Returns page must state that returns are accepted only for damaged items.

---

## Contact

**Vykuntapuram Brand Sarees**
- Instagram: [@vykuntapuram_brand_sareesdealr](https://www.instagram.com/vykuntapuram_brand_sareesdealr)
- WhatsApp: +91 91006 48380

---

## License

All rights reserved. This project is proprietary to Vykuntapuram Brand Sarees. Replace this section if you choose a different license.

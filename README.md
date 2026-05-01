# 💧 BestOne Water Delivery — Booking App

A clean, mobile-friendly web app to book borehole water tank delivery.  
Customers select tank capacity, share location, and get a confirmation call within 5 minutes.

---

## 🚀 Deploy to Netlify (3 steps)

1. Push this repo to GitHub
2. Go to [netlify.com](https://netlify.com) → **Add new site** → **Import from Git**
3. Select your repo → click **Deploy** ✅

---

## 📧 Set Up Email Notifications (EmailJS)

Booking details are emailed to `bestoneagency4@gmail.com` via [EmailJS](https://emailjs.com) (free plan: 200 emails/month).

### Steps:

1. **Create account** at [emailjs.com](https://emailjs.com)

2. **Add Email Service**
   - Dashboard → Email Services → Add Service → **Gmail**
   - Connect your Gmail account (`bestoneagency4@gmail.com`)
   - Note the **Service ID** (e.g., `service_abc123`)

3. **Create Email Template**
   - Dashboard → Email Templates → Create New Template
   - Set **To Email**: `bestoneagency4@gmail.com`
   - Set **Subject**: `New Water Tank Booking 🚰`
   - Set **Body**:
     ```
     New Booking Received!

     Phone: {{phone}}
     Tank: {{tank}}
     Price: {{price}}
     Location: {{location}}
     Booked At: {{booked_at}}

     Full Details:
     {{message}}
     ```
   - Note the **Template ID** (e.g., `template_xyz789`)

4. **Get Public Key**
   - Dashboard → Account → General → **Public Key**

5. **Update `index.html`** — find these 3 lines near the top of the `<script>` tag:

```javascript
const EMAILJS_PUBLIC_KEY  = 'YOUR_PUBLIC_KEY';   // ← paste here
const EMAILJS_SERVICE_ID  = 'YOUR_SERVICE_ID';   // ← paste here
const EMAILJS_TEMPLATE_ID = 'YOUR_TEMPLATE_ID';  // ← paste here
```

6. Push to GitHub → Netlify auto-redeploys ✅

---

## 💰 Tank Pricing

| Capacity  | Price     |
|-----------|-----------|
| 5,000 Ltr | Rs. 1,050 |
| 6,000 Ltr | Rs. 1,050 |
| 7,000 Ltr | Rs. 1,350 |
| 8,000 Ltr | Rs. 1,350 |

---

## 📍 Location Feature

- **Paste Link**: Customer pastes any Google Maps URL
- **GPS Button**: Uses browser geolocation → shows OpenStreetMap preview → sends as `https://www.google.com/maps?q=LAT,LON`

---

## 📁 Files

```
├── index.html      # The entire app (single file)
├── netlify.toml    # Netlify config
└── README.md       # This file
```

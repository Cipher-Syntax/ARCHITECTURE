### 📁 FOLDER ARCHITECTURE

---

## 🔧 BACKEND

```bash
backend/
│
├── manage.py
├── .env
├── requirements.txt
│
├── config/                        # project configuration
│   ├── __init__.py
│   ├── settings/
│   │   ├── __init__.py
│   │   ├── base.py               # shared settings
│   │   ├── dev.py                # development
│   │   └── prod.py               # production
│   │
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
├── apps/                          # domain apps
│   ├── __init__.py
│   │
│   ├── users/
│   │   ├── __init__.py
│   │   ├── models.py
│   │   ├── serializers.py
│   │   ├── views.py
│   │   ├── urls.py
│   │   ├── services.py           # business logic
│   │   ├── selectors.py          # query logic
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── tests/
│   │   └── migrations/
│   │
│   ├── bookings/
│   │   ├── models.py
│   │   ├── serializers.py
│   │   ├── views.py
│   │   ├── urls.py
│   │   ├── services.py
│   │   ├── selectors.py
│   │   ├── tests/
│   │   └── migrations/
│   │
│   └── core/                     # shared/common logic
│       ├── models.py
│       ├── permissions.py
│       ├── pagination.py
│       ├── utils.py
│
├── common/                        # cross-project reusable code
│   ├── __init__.py
│   ├── exceptions.py
│   ├── middleware.py
│   └── constants.py
│
├── static/
├── media/
└── docs/
    └── ARCHITECTURE.md
```

---

## 🌐 WEB (React + Tailwind)

```bash
src/
│
├── app/                      # App-level setup (top-most layer)
│   ├── App.jsx
│   ├── routes.jsx           # Centralized routing
│   └── providers.jsx        # Context providers (auth, theme, etc.)
│
├── layouts/                 # Page layouts (Top-Down)
│   ├── MainLayout.jsx
│   ├── AuthLayout.jsx
│
├── pages/                   # Screens / routes (Top-Down)
│   ├── dashboard/
│   │   ├── DashboardPage.jsx
│   │   └── components/
│   │       ├── StatsCard.jsx
│   │       └── ActivityFeed.jsx
│   │
│   ├── booking/
│   │   ├── BookingPage.jsx
│   │   └── components/
│   │       ├── BookingCard.jsx
│   │       └── BookingForm.jsx
│   │
│   └── auth/
│       ├── LoginPage.jsx
│       └── RegisterPage.jsx
│
├── components/              # GLOBAL reusable UI (Bottom-Up)
│   ├── ui/
│   │   ├── Button.jsx
│   │   ├── Input.jsx
│   │   ├── Modal.jsx
│   │
│   ├── common/
│   │   ├── Navbar.jsx
│   │   ├── Sidebar.jsx
│   │   └── Loader.jsx
│
├── hooks/                   # Custom hooks
│   ├── useAuth.js
│   ├── useFetch.js
│   └── useDebounce.js
│
├── services/                # API layer (Django integration)
│   ├── api.js
│   ├── authService.js
│   ├── bookingService.js
│
├── context/                 # Global state
│   ├── AuthContext.jsx
│
├── utils/
│   ├── formatDate.js
│   ├── currency.js
│
├── styles/
│   └── index.css
│
└── assets/
    └── images/
```

---

## 📱 MOBILE APP (React Native + Expo)

```bash
app/                          # routing layer (Expo Router)
│   ├── _layout.tsx
│   ├── index.tsx
│   ├── auth/
│   │   ├── login.tsx
│   │   └── register.tsx
│   ├── bookings/
│   │   ├── index.tsx
│   │   └── details.tsx
│
├── src/                      # actual app logic
│   ├── components/
│   │   ├── ui/
│   │   └── common/
│   │
│   ├── features/
│   │   ├── auth/
│   │   │   ├── hooks/
│   │   │   ├── services/
│   │   │   └── components/
│   │   │
│   │   ├── bookings/
│   │   │   ├── hooks/
│   │   │   ├── services/
│   │   │   └── components/
│   │
│   ├── hooks/
│   ├── services/
│   ├── utils/
│   ├── store/               # Zustand / Redux (optional)
│
├── assets/
```

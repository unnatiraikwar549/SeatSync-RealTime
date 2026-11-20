# 🏢 SeatSync — Smart Library Seat Finder (3D Edition)

[![React 18](https://img.shields.io/badge/React-18.3-blue.svg?logo=react)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.6-3178C6.svg?logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-3.4-38B2AC.svg?logo=tailwind-css)](https://tailwindcss.com/)
[![Vite](https://img.shields.io/badge/Vite-5.4-646CFF.svg?logo=vite)](https://vitejs.dev/)
[![Supabase](https://img.shields.io/badge/Supabase-Realtime-3ECF8E.svg?logo=supabase)](https://supabase.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **SeatSync** eliminates the frustration of climbing crowded library stairs by combining **real-time seat occupancy**, **interactive 3D spatial floor mapping**, **anti-bag-hogging 20-minute protected breaks**, **QR pass verification**, and **acoustic noise-free study zone tracking** into one seamless web application.

---

## 🌟 Key Features

### 1. 🏢 3D Spatial Floor Maps & Multi-Angle Camera
- **3-Tier Interactive Campus Building**: Switch between Ground Floor (Commons), First Floor (Silent Vista), and Second Floor (Deep Focus).
- **Volumetric Workstations**: True 3D desks rendering individual monitors, ergonomic task chairs, power sockets, and real-time status beacons.
- **Camera Presets & Free Orbit**: Instant toggles between `📐 Isometric (54°)`, `🦅 Top-Down (18°)`, `🚶 Eye-Level (68°)`, and interactive pitch/yaw controls.

### 2. 🤫 Acoustic Noise-Free Area Availability Finder
- **<30 dB Guaranteed Quiet Study**: Real-time acoustic telemetry tracking vacant seats in silence-enforced zones.
- **Smart Telemetry Bar**: Live noise-free vacancy metrics across floors (e.g., *14 of 20 Desks Free • 70% Vacancy Rate*).
- **One-Click Quiet Filter**: Instantly isolate window carrels and pin-drop silent workstations.

### 3. ⏳ Session Extender & Flexible Seating Time
- **Dynamic Session Extension**: Students can extend their active study session with quick chips (`+30m`, `+1 Hour`, `+2 Hours`, `+3 Hours`).
- **Fair Access Daily Quota**: Built-in 4-hour daily extension limit prevents desk monopolies.
- **Live Boarding Pass Synchronization**: Checkout time and RFID tokens update in real-time.

### 4. 🛡️ Anti-Bag-Hogging Protocol (20-Minute Protected Break)
- **Protected Away Mode**: Step away for coffee or rest with a 20-minute countdown lock.
- **Auto-Release Policy**: If a student fails to check back in before 00:00, the desk automatically releases to peers.
- **Demo Fast-Forward**: Test the countdown auto-release in 15 seconds with a single click.

### 5. 🎫 3D Holographic Pass & QR Check-In
- **Dynamic Boarding Pass**: 3D interactive tilting card with encrypted QR verification token.
- **Camera QR Scanner**: Built-in camera feed simulator for zero-friction desk check-ins.

### 6. 🛠️ Defect Reporting & General Query Helpdesk
- **Desk Anomaly Inspector**: Report broken sockets, flickering lamps, or chair defects with automated priority routing.
- **General Inquiries Mode**: Ask staff library questions and receive replies within 15 minutes.
- **Admin Management Operations**: Full administrative dashboard with live occupancy analytics, rush hour graphs, force-release controls, and ticket triage.

---

## 🎨 Design System & Typography

- **Deep Navy Base**: `#070c1d` (primary background) & `#0a1128` (elevated panels)
- **Ice White Text**: `#ffffff` & `#f8fafc` for maximum readability
- **Electric Blue Accent**: `#38bdf8` & `#0ea5e9` for glowing telemetry highlights
- **Emerald Silence Accent**: `#10b981` & `#34d399` for noise-free study zones
- **Typography Pair**:
  - **Headings & Editorial**: `Lora` (Google Fonts serif)
  - **Interface, Badges & Code**: `Manrope` (Google Fonts clean sans-serif)

---

## 🚀 Quick Start Guide

### Prerequisites
- Node.js 18+ & npm (or yarn / pnpm)

### Local Development Setup

```bash
# 1. Clone repository
git clone https://github.com/your-username/seatsync.git
cd seatsync

# 2. Install dependencies
npm install

# 3. (Optional) Configure Supabase environment variables
cp .env.example .env

# 4. Start Vite development server
npm run dev
```

Visit `http://localhost:3000/` in your browser.

> **💡 Zero-Config Demo Mode**: SeatSync operates seamlessly offline or without database credentials using its built-in local state engine and sound synthesizer.

---

## 🏗️ Production Build

```bash
# Verify TypeScript types and generate optimized static build
npm run build

# Preview production build locally
npm run preview
```

The production output is generated in the `dist/` directory, optimized with minified chunks and CSS purge.

---

## 🗄️ Supabase Database Setup (Optional)

To connect SeatSync to your live Supabase cloud database:

1. Create a project at [supabase.com](https://supabase.com/).
2. Open the **SQL Editor** in the Supabase Dashboard.
3. Paste and run the complete database schema located in [supabase/schema.sql](./supabase/schema.sql).
4. Copy your project URL and public anon key into `.env`:
   ```env
   VITE_SUPABASE_URL=https://your-project.supabase.co
   VITE_SUPABASE_ANON_KEY=your-anon-key-here
   ```
5. Real-time desk availability updates will automatically sync across all open browsers via Supabase WebSockets.

---

## 🌐 Deploying to Vercel

### Method 1: Deploy from GitHub (Recommended)
1. Push this repository to GitHub.
2. Sign in to [vercel.com](https://vercel.com/) and click **"Add New Project"**.
3. Import your `seatsync` repository.
4. Vercel automatically detects Vite:
   - **Framework Preset**: `Vite`
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
5. (Optional) Add your `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` under Environment Variables.
6. Click **Deploy**. Your app will be live with automatic HTTPS in ~45 seconds!

### Method 2: Deploy using Vercel CLI
```bash
npm install -g vercel
vercel
```

---

## 📁 Repository Structure

```
seatsync/
├── public/                 # Static assets (optimized logo & icons)
│   ├── seatsync_icon.png   # 256x256 Retina favicon
│   └── seatsync_logo.png   # 512x512 High-DPI system emblem
├── src/                    # TypeScript React modular codebase
│   ├── components/         # 10 modular UI views & modals
│   │   ├── AdminDashboard.tsx
│   │   ├── BookingModal.tsx
│   │   ├── BugDetectorModal.tsx
│   │   ├── DemoControlsModal.tsx
│   │   ├── FloorMap.tsx
│   │   ├── LandingPage.tsx
│   │   ├── Navbar.tsx
│   │   ├── QRCheckInModal.tsx
│   │   ├── SendQuerySection.tsx
│   │   └── StudentDashboard.tsx
│   ├── data/
│   │   └── initialSeats.ts # 60 volumetric desk topologies
│   ├── services/
│   │   ├── soundService.ts # Synthesized Web Audio alerts
│   │   ├── storageService.ts # Anti-hogging & session state engine
│   │   └── supabaseClient.ts # Supabase Realtime client
│   ├── types/
│   │   └── index.ts        # TypeScript schemas & interfaces
│   ├── App.tsx             # Master application coordinator
│   ├── index.css           # Tailwind directives & 3D animations
│   └── main.tsx            # Vite root mount
├── supabase/
│   └── schema.sql          # Postgres schema, RLS policies & seeds
├── .env.example            # Environment template without credentials
├── .gitignore              # Clean exclude rules (node_modules, .env, dist)
├── demo.html               # Standalone zero-dependency offline runner
├── index.html              # Vite SPA entry point
├── package.json            # Node.js dependencies & scripts
├── postcss.config.js       # PostCSS Tailwind processor
├── tailwind.config.js      # Custom theme colors & typography
├── tsconfig.json           # Strict TypeScript configuration
├── vite.config.ts          # Vite bundler configuration
└── README.md               # Project documentation
```

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
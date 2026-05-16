# SmartAttend - College Attendance Management System

A modern, production-ready college attendance management web application with premium admin dashboard UI. Built with React, Vite, TailwindCSS, and Firebase.

## 🎯 Key Features

### Core Features
- **Faculty-Controlled Attendance System**: Teachers manually mark attendance with smart defaults
- **Role-Based Access Control**: Separate Admin and Teacher dashboards
- **Smart Attendance Sessions**: Auto-generated session IDs with 10-minute expiration
- **Security-First Design**: 2-hour edit locks, device metadata tracking, and audit logs
- **Real-Time Synchronization**: Live updates across all connected clients
- **Advanced Analytics**: Charts, trends, and detailed reports
- **Mobile Responsive**: Works seamlessly on desktop, tablet, and mobile

### Admin Features
- ✅ Create/manage teachers and students
- ✅ Create departments and sections/classes
- ✅ Assign teachers to subjects/classes
- ✅ View all attendance data
- ✅ Unlock/edit locked records (after 2-hour window)
- ✅ Export reports (PDF/CSV)
- ✅ Dashboard analytics with trends
- ✅ Manage system settings

### Teacher Features
- ✅ Secure login/logout
- ✅ View assigned classes
- ✅ Start quick attendance sessions
- ✅ Mark attendance (default all present, mark absents)
- ✅ View previous attendance records
- ✅ Edit attendance within 2-hour window
- ✅ Generate class reports
- ✅ View personal analytics

## 🏗️ Tech Stack

- **Frontend**: React 19 + Vite 7
- **Styling**: TailwindCSS + ShadCN UI components
- **Backend**: Firebase (Authentication, Firestore)
- **Charts**: Recharts
- **Data Tables**: TanStack Table
- **Icons**: Lucide React
- **Date Handling**: Date-fns
- **Deployment**: Vercel-ready

## 📋 Project Structure

```
src/
├── components/
│   ├── dashboard/      # Dashboard components
│   ├── layout/         # Layout components (Sidebar, Topbar)
│   ├── routes/         # Route protection
│   └── ui/             # UI components
├── contexts/           # React context (Auth, Theme, Toast)
├── pages/              # Page components
├── services/           # Firebase & storage services
├── hooks/              # Custom hooks
├── lib/                # Firebase & utilities
├── data/               # Mock data
└── styles/             # Global styles
```

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ and npm/yarn
- Firebase account (free tier OK)
- Vercel account (for deployment - optional)

### Installation

1. **Install dependencies**
   ```bash
   npm install
   ```

2. **Set up environment variables**
   ```bash
   cp .env.example .env.local
   ```
   
   Then fill in your Firebase credentials in `.env.local`

3. **Start development server**
   ```bash
   npm run dev
   ```

The app will be available at `http://localhost:5173`

## 🔐 Demo Credentials

The app works with or without Firebase configured:

**Admin Account:**
- Email: `admin@smartattend.edu`
- Password: `admin123`

**Teacher Account:**
- Email: `teacher@smartattend.edu`
- Password: `teacher123`

## 🔧 Development

### Available Scripts

```bash
npm run dev       # Start dev server
npm run build     # Build for production
npm run preview   # Preview production build
npm run lint      # Run ESLint
```

## 📊 Database Schema

Firestore collections:
- **users**: User accounts with roles
- **students**: Student records
- **teachers**: Faculty information
- **departments**: Department/Faculty
- **classes**: Class/Section definitions
- **attendance_sessions**: Session metadata
- **attendance_records**: Individual records
- **reports**: Activity logs & audit trails

See [firebase-schema.md](./firebase-schema.md) for detailed schema.

## 🔒 Security Features

1. **Role-Based Access Control (RBAC)**
   - Admin: Full system access
   - Teacher: Limited to assigned classes
   
2. **Attendance Security**
   - 2-hour edit lock on submissions
   - Device/browser metadata tracking
   - Duplicate session prevention
   - Complete audit trail

3. **Data Protection**
   - Firebase Authentication
   - Firestore Security Rules
   - Environment variable protection
   - Secure password handling

## 🎨 UI/UX

- Modern SaaS-style dashboard
- Dark/Light mode toggle
- Responsive design (mobile, tablet, desktop)
- Smooth animations
- Loading states with skeletons
- Toast notifications
- Confirmation dialogs
- Empty states

## 📱 Mobile Responsive

The application is fully responsive:
- ✅ Mobile: Touch-optimized, simplified layouts
- ✅ Tablet: Adaptive component sizing
- ✅ Desktop: Full feature set with optimal spacing

## 🌓 Dark Mode

Toggle between light and dark modes using the theme button in the topbar.

## 🚢 Deployment

### Deploy to Vercel (Recommended)
```bash
npm run build
vercel --prod
```

### Deploy to Firebase Hosting
```bash
firebase init hosting
npm run build
firebase deploy --only hosting
```

See [DEPLOYMENT.md](./DEPLOYMENT.md) for detailed instructions.

## 📖 Documentation

- [Firebase Setup](./firebase-schema.md)
- [Security Rules](./firestore-rules.txt)
- [Deployment Guide](./DEPLOYMENT.md)

## 🐛 Troubleshooting

**Firebase credentials not working:**
- Verify all environment variables are set
- Check Firebase project is active
- Ensure authentication is enabled

**Attendance not saving:**
- Check Firestore rules are deployed
- Verify write permissions
- Check browser console for errors

**UI not rendering:**
- Clear browser cache
- Restart dev server
- Check for console errors

## 📝 Sample Data

Includes comprehensive mock data:
- 10+ students across departments
- 3+ teachers with assigned classes
- 3 departments with multiple classes
- Mock attendance sessions
- Activity logs

Data stored in localStorage, can be reset by clearing browser storage.

## 🎓 Learning Resources

This project demonstrates:
- Modern React patterns (hooks, context, custom hooks)
- Firebase integration (Auth, Firestore)
- State management without Redux
- Responsive design with TailwindCSS
- Component-driven architecture
- Security best practices
- Performance optimization

## 📄 License

MIT License - Feel free to use for commercial or educational purposes.

## 🤝 Contributing

1. Create a feature branch
2. Follow existing code style
3. Test thoroughly
4. Submit pull request

## 📞 Support

For issues:
1. Check troubleshooting section
2. Review Firebase documentation
3. Check browser console for errors
4. Clear cache and try again

---

**SmartAttend** - Making college attendance management smart, secure, and simple. ✨

npm install
npm run dev
```

Copy `.env.example` to `.env` and fill in Firebase values:

```bash
VITE_FIREBASE_API_KEY=
VITE_FIREBASE_AUTH_DOMAIN=
VITE_FIREBASE_PROJECT_ID=
VITE_FIREBASE_STORAGE_BUCKET=
VITE_FIREBASE_MESSAGING_SENDER_ID=
VITE_FIREBASE_APP_ID=
VITE_APP_NAME=SmartAttend
```

## Firebase Deployment Notes

1. Create a Firebase project.
2. Enable Email/Password authentication.
3. Create `users/{uid}` documents with `role: "admin"` or `role: "teacher"`.
4. Deploy `firestore.rules`.
5. Add Firestore indexes from `firestore.schema.md`.
6. Import seed data from `src/data/mockData.js` or create records in the dashboard.

## Vercel Deployment

1. Push the repository to GitHub.
2. Import it in Vercel.
3. Add all `VITE_FIREBASE_*` variables.
4. Build command: `npm run build`.
5. Output directory: `dist`.

`vercel.json` is included for SPA route rewrites.

## GitHub Pages Deployment

This repo includes `.github/workflows/deploy.yml`. After pushing to GitHub:

1. Open repository settings.
2. Go to `Pages`.
3. Set source to `GitHub Actions`.
4. Add Firebase secrets if you want live Firebase mode.
5. Push to `main` or `master`, or run the workflow manually.

Your app will be available at:

```text
https://YOUR_USERNAME.github.io/YOUR_REPOSITORY_NAME/
```

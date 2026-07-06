# 📚 SISTEM MANAJEMEN AKADEMIK - UI/UX DESIGN GUIDE

## 1. DESIGN STRATEGY & BRANDING

### Konsep Utama
Sistem akademik yang **profesional, terpercaya, dan efisien**. Interface dirancang untuk mengurangi cognitive load saat mengelola data akademik yang kompleks.

### Color Palette (Akademik + Modern)
```
Primary:      #2563EB (Royal Blue)    - Trust, profesional
Secondary:    #7C3AED (Purple)       - Inovasi, keunggulan
Success:      #10B981 (Emerald)      - Nilai baik, approval
Warning:      #F59E0B (Amber)        - Perhatian, grade tengah
Danger:       #EF4444 (Red)          - Nilai rendah, alert
Neutral:      #6B7280 (Gray-600)     - Text, supporting
Light BG:     #F9FAFB (Gray-50)      - Background utama
Card BG:      #FFFFFF (White)        - Cards, content areas
```

### Typography
- **Display (Heading)**: Inter Bold / Semibold (System Font)
  - H1: 32px / 40px, Bold, Letter-spacing: -0.5px
  - H2: 24px / 32px, Semibold
  - H3: 18px / 28px, Semibold
  
- **Body**: Inter Regular / Medium
  - Body L: 16px / 24px, Regular
  - Body M: 14px / 20px, Regular (default)
  - Label: 12px / 16px, Medium

- **Code/Data**: IBM Plex Mono (monospace untuk NPM, NIDN, nilai)

### Spacing System
```
xs: 4px    | sm: 8px   | md: 16px
lg: 24px   | xl: 32px  | 2xl: 48px
```

### Komponen Signature
- **Grade Indicator**: Circular badge dengan gradient sesuai range nilai
- **Status Pill**: Rounded badge dengan icon
- **Data Table**: Striped rows dengan hover state untuk readability
- **Stat Card**: Numeric focus dengan supporting text

---

## 2. NAVIGATION STRUCTURE

### Global Navigation
```
Header (sticky):
├── Logo + "SISTEM AKADEMIK"
├── User Profile (Dropdown)
│   ├── Profil
│   ├── Ubah Password
│   └── Logout
└── Notifications (Bell icon)

Sidebar (Collapsible):
├── Dashboard
├── [Role-specific menu items]
└── Settings
```

---

## 3. ROLE-BASED NAVIGATION

### 🎓 STUDENT (MAHASISWA)
```
├── Dashboard
│   └── Overview nilai semester ini
├── My Courses
│   └── Daftar mata kuliah
├── My Grades
│   └── Detail nilai per course (Tugas, UTS, Kuis, Kehadiran, Nilai Akhir)
├── Profile
│   ├── Data personal (NPM, Nama, Jurusan, Fakultas, Angkatan)
│   ├── Edit Profile
│   └── Ubah Password
└── Notifications
```

### 👨‍🏫 LECTURER (DOSEN)
```
├── Dashboard
│   └── Summary: courses taught, students, pending grades
├── My Courses
│   └── Daftar course yang diampu
├── Grade Management
│   ├── Select Course
│   ├── Student List
│   ├── Input Grade (Tugas, UTS, Kuis, Kehadiran)
│   ├── Auto-calculate Nilai Akhir
│   └── Publish Grades
├── Profile
│   ├── Data personal (NIDN, Nama, Status)
│   ├── Edit Profile
│   └── Ubah Password
└── Notifications
```

### 👨‍💼 ADMIN (ADMINISTRATOR)
```
├── Dashboard
│   └── System overview, stats
├── Student Management
│   ├── List all students
│   ├── Add New Student
│   ├── Edit Student
│   └── Delete Student
├── Lecturer Management
│   ├── List all lecturers
│   ├── Add/Edit/Delete Lecturers
├── Course Management
│   ├── List all courses
│   ├── Add/Edit/Delete Courses
│   └── Assign lecturers to courses
├── Grade Management
│   ├── View all grades
│   ├── Verify/Publish grades
├── Reports
│   ├── Student Performance
│   ├── Course Statistics
│   └── Export Data
├── System Settings
│   ├── Academic Calendar
│   ├── Grade Scale
│   └── System Configuration
└── User Accounts
    ├── Manage all users
    ├── Reset passwords
```

---

## 4. KEY PAGES WIREFRAME

### A. LOGIN PAGE
```
┌─────────────────────────────────────┐
│                                     │
│                                     │
│       SISTEM AKADEMIK UNIV XYZ     │
│                                     │
│       [Role Selector]               │
│       ┌─────┬─────┬─────┐          │
│       │ Admin│Student│Dosen│       │
│       └─────┴─────┴─────┘          │
│                                     │
│       Email/Username: [_______]     │
│       Password:       [_______]     │
│                                     │
│       [ Login ]  [ Forgot Password]│
│                                     │
└─────────────────────────────────────┘
```

### B. STUDENT DASHBOARD
```
┌──────────────────────────────────────────┐
│  DASHBOARD                        [≡]   │
├──────────────────────────────────────────┤
│                                          │
│  Welcome, Ahmad Pratama!                 │
│  NPM: 2024001 | Semester: 4              │
│                                          │
│  ┌──────────┐  ┌──────────┐  ┌────────┐ │
│  │ GPA      │  │Courses   │  │Completed│ │
│  │ 3.45     │  │ 6        │  │ 12     │ │
│  └──────────┘  └──────────┘  └────────┘ │
│                                          │
│  📊 NILAI SEMESTER INI                   │
│  ┌────────────────────────────────────┐  │
│  │ Mata Kuliah    │ Nilai │ Grade    │  │
│  ├────────────────┼───────┼──────────┤  │
│  │ Algoritma      │ 85    │ A-       │  │
│  │ Database       │ 78    │ B+       │  │
│  │ Web Dev        │ 92    │ A        │  │
│  │ Sistem Op.     │ 72    │ B        │  │
│  └────────────────────────────────────┘  │
│                                          │
└──────────────────────────────────────────┘
```

### C. GRADE DETAIL PAGE (STUDENT VIEW)
```
┌──────────────────────────────────────────┐
│  Algoritma dan Pemrograman                │
│  Kode: IF2101 | SKS: 3 | Dosen: Dr. Budi│
├──────────────────────────────────────────┤
│                                          │
│  BREAKDOWN NILAI                         │
│  ┌──────────────────────────────────┐   │
│  │ Komponen    │ Nilai │ Bobot │%   │   │
│  ├─────────────┼───────┼────────┼───┤   │
│  │ Tugas       │ 88    │ 20%   │   │   │
│  │ Kehadiran   │ 95    │ 10%   │   │   │
│  │ Kuis        │ 82    │ 20%   │   │   │
│  │ UTS         │ 85    │ 25%   │   │   │
│  │ UAS         │ 87    │ 25%   │   │   │
│  └──────────────────────────────────┘   │
│                                          │
│  NILAI AKHIR: 85 (Grade: A-)             │
│                                          │
│  📅 Diupload: 15-01-2024 | Opublikasi: 20-01-2024│
│                                          │
└──────────────────────────────────────────┘
```

### D. LECTURER GRADE INPUT PAGE
```
┌────────────────────────────────────────────┐
│  INPUT NILAI - Algoritma (IF2101)           │
├────────────────────────────────────────────┤
│                                            │
│  [Filter: Semester 4 ▼] [Search Mahasiswa]│
│                                            │
│  ┌──────────────────────────────────────┐  │
│  │ NPM    │ Nama         │ T │K│U│N│Final│ │
│  ├────────┼──────────────┼──┼─┼─┼─┼────┤  │
│  │2024001 │Ahmad Pratama │88│82│85│95│ - │ │
│  │        │              │  │  │  │  │✏️ │  │
│  ├────────┼──────────────┼──┼─┼─┼─┼────┤  │
│  │2024002 │Budi Santoso  │92│78│90│93│ - │ │
│  │        │              │  │  │  │  │✏️ │  │
│  └──────────────────────────────────────┘  │
│                                            │
│  [Save as Draft] [Publish Grades]          │
│                                            │
└────────────────────────────────────────────┘
```

### E. ADMIN - STUDENT MANAGEMENT
```
┌──────────────────────────────────────────┐
│  MANAJEMEN MAHASISWA                      │
├──────────────────────────────────────────┤
│  [+ Add Student] [Import CSV] [Export]    │
│  [Search...] [Filter: Angkatan ▼]         │
│                                          │
│  ┌──────────────────────────────────┐   │
│  │ NPM   │ Nama        │ Jur │ Akt  │   │
│  ├───────┼─────────────┼────┼──────┤   │
│  │202400 │Ahmad Pratam │IF  │✓     │   │
│  │1      │             │    │[Edit]│   │
│  ├───────┼─────────────┼────┼──────┤   │
│  │202400 │Budi Santoso │SI  │✓     │   │
│  │2      │             │    │[Edit]│   │
│  └──────────────────────────────────┘   │
│                                          │
└──────────────────────────────────────────┘
```

---

## 5. KOMPONEN UI STANDAR

### Status Badge
```
✓ Active (Green)
⊘ Inactive (Gray)
! Pending (Yellow)
✕ Rejected (Red)
```

### Grade Color Coding
```
A   (85-100) → Emerald (#10B981)
B   (70-84)  → Blue (#2563EB)
C   (55-69)  → Amber (#F59E0B)
D   (40-54)  → Orange (#EF4444)
E   (<40)    → Red (#DC2626)
```

### Form Components
- Input: Border bottom only, focus: blue underline
- Dropdown: Select dengan chevron, custom styling
- Checkbox: Custom checkbox dengan animation
- Date Picker: Calendar modal
- Button: Rounded (8px), Primary (blue), Secondary (gray), Danger (red)

### Data Table Standards
- Striped rows (alternate gray background)
- Hover state: Light blue background
- Sticky header
- Sortable columns (with arrow indicators)
- Pagination: 10/25/50 items per page
- Bulk actions: Checkbox select semua dengan actions bar

### Modals
- Centered on desktop, fullscreen on mobile
- Close button (X) di top-right
- Clear title dan action buttons
- Backdrop: Semi-transparent dark

---

## 6. RESPONSIVE DESIGN

### Breakpoints
```
Mobile:  320px - 640px  (Sidebar hidden, hamburger menu)
Tablet:  641px - 1024px (Sidebar collapsed icons only)
Desktop: 1025px+        (Full sidebar)
```

---

## 7. INTERACTION PATTERNS

### Loading States
- Skeleton loaders untuk cards dan tables
- Progress indicator untuk upload/processing
- Spinner untuk modal actions

### Success/Error Messages
- Toast notifications (top-right, auto-dismiss 4s)
- Success: Green with checkmark
- Error: Red with warning icon
- Validation errors: Inline di form fields

### Transitions
- Page change: Fade in (150ms)
- Sidebar toggle: Slide (200ms)
- Hover effects: Color change (100ms)
- No excessive animations (respect prefers-reduced-motion)

---

## 8. ACCESSIBILITY

- ✓ WCAG 2.1 AA compliant
- ✓ Keyboard navigation support
- ✓ Focus indicators visible
- ✓ Color not the only indicator
- ✓ Alt text untuk images
- ✓ Semantic HTML (nav, main, section)
- ✓ ARIA labels di interactive elements
- ✓ Sufficient color contrast (4.5:1 untuk text)

---

## 9. TECHNICAL STACK RECOMMENDATION

```
Frontend:
- React / Vue.js
- TailwindCSS untuk styling
- React Query untuk data fetching
- React Router untuk navigation

Backend:
- Node.js (Express) / Laravel / Django
- PostgreSQL / MySQL untuk database

UI Library:
- Headless UI atau Radix UI untuk accessible components
- React Hook Form untuk form management
- Chart.js / Recharts untuk visualisasi data
```

---

## 10. NEXT STEPS

1. ✓ Design System defined
2. ⏳ Create interactive mockup/prototype (Figma/Adobe XD)
3. ⏳ Develop HTML/CSS for key pages
4. ⏳ API integration
5. ⏳ Testing & refinement
6. ⏳ Deployment

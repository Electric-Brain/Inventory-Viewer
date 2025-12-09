# 🔧 Electronics Inventory Manager

A modern, cloud-based inventory management system designed specifically for electronics enthusiasts, makers, and engineers to track components, modules, and devices.

## 📸 Preview

A beautiful, responsive web application with a modern gradient UI that works seamlessly across all devices - from desktop to mobile.

## ✨ Features

### 🎨 Modern UI/UX
- **Beautiful Gradient Design** - Purple to indigo gradient theme
- **Glass Morphism Effects** - Frosted glass cards and modals
- **Smooth Animations** - Fade-in effects and hover transitions
- **Fully Responsive** - Perfect on desktop, tablet, and mobile devices

### 📦 Component Management
- **Add Components** - Track name, category, value, quantity, location, and notes
- **Edit & Delete** - Easily update or remove components
- **Search & Filter** - Find components quickly by name, value, or category
- **14 Categories** - Microcontroller, Display, LED, Resistor, Capacitor, IC, Module, and more

### 🚨 Smart Features
- **Low Stock Alerts** - Automatic warnings when components are running low (≤5 units)
- **Color-Coded Quantities** - Red for low stock, green for adequate stock
- **Real-time Sync** - All changes instantly saved to cloud database
- **Responsive Tables** - Adapts to screen size with optimized mobile view

### ☁️ Cloud-Based Storage
- **Supabase Integration** - Free PostgreSQL database in the cloud
- **Access Anywhere** - View and manage inventory from any device
- **No Data Loss** - All data safely stored and backed up
- **Real-time Updates** - Sync across multiple devices

### 🔒 Security
- **Password Protected** - Secure login to access your inventory
- **Private Data** - Only you can access your components
- **Session Management** - Automatic logout for security

## 🚀 Live Demo

**[View Live Demo](https://electric-brain.github.io/Inventory-Viewer/)** 

## 📋 Prerequisites

Before you begin, you'll need:

1. A GitHub account
2. A free [Supabase](https://supabase.com) account
3. Basic knowledge of Git (optional)

## 🛠️ Installation & Setup

### Step 1: Clone or Fork This Repository

```bash
git clone https://github.com/yourusername/electronics-inventory.git
cd electronics-inventory
```

Or simply fork this repository to your GitHub account.

### Step 2: Set Up Supabase Database

1. Go to [supabase.com](https://supabase.com) and create a free account
2. Create a new project
3. Go to **SQL Editor** and run this SQL:

```sql
CREATE TABLE components (
  id BIGSERIAL PRIMARY KEY,
  name TEXT NOT NULL,
  category TEXT NOT NULL,
  value TEXT,
  quantity INTEGER NOT NULL,
  location TEXT,
  notes TEXT,
  date_purchased DATE,
  date_added TIMESTAMPTZ DEFAULT NOW()
);
```

4. Go to **Settings → API**
5. Copy your:
   - **Project URL** (e.g., `https://xxxxx.supabase.co`)
   - **anon public key** (starts with `eyJ...`)

### Step 3: Configure the Application

#### Option A: Enter Credentials via Website (Recommended)
1. Deploy to GitHub Pages (see Step 4)
2. Login with password
3. Click "DB Config" button
4. Enter your Supabase URL and API key
5. Click "Save Configuration"

#### Option B: Hardcode Credentials (For Single User)
Edit `index.html` and update these lines (around line 21):

```javascript
var SUPABASE_URL = 'https://your-project.supabase.co';  // Your Supabase URL
var SUPABASE_KEY = 'your-anon-key-here';                 // Your anon public key
```

### Step 4: Deploy to GitHub Pages

1. Go to your repository **Settings**
2. Click **Pages** in the sidebar
3. Under "Source", select **main** branch
4. Click **Save**
5. Your site will be live at: `https://yourusername.github.io/repository-name`

### Step 5: Change Default Password (Important!)

Edit `index.html` and change the password (line 19):

```javascript
var APP_PASSWORD = 'YourSecurePassword123!';  // Change this!
```

⚠️ **Important**: If your repository is public, use Option A (enter credentials via website) to keep your Supabase credentials private.

## 📱 Usage

### Login
1. Visit your deployed website
2. Enter your password
3. Configure database (first time only)

### Add Components
1. Click **"Add Component"** button
2. Fill in component details:
   - Name (required)
   - Category (required)
   - Value/Specification (optional)
   - Quantity (required)
   - Storage Location (optional)
   - Purchase Date (optional)
   - Notes (optional)
3. Click **"Add Component"**

### Search & Filter
- Use the **search bar** to find components by name or value
- Use the **category dropdown** to filter by component type
- Results update in real-time

### Edit Components
1. Click the **Edit** icon (pencil) on any component
2. Modify the details
3. Click **"Update Component"**

### Delete Components
1. Click the **Delete** icon (trash) on any component
2. Confirm deletion

## 🎨 Categories

The system includes 14 pre-configured categories:
- Microcontroller
- Display
- Sensor
- LED
- Resistor
- Capacitor
- IC (Integrated Circuit)
- Module
- Buzzer
- Motor
- Power Supply
- Transistor
- Diode
- Other

## 📊 Features Breakdown

| Feature | Description |
|---------|-------------|
| 🔍 Search | Search components by name or value |
| 🏷️ Categories | Filter by 14 component categories |
| 📈 Quantity Tracking | Visual indicators for stock levels |
| 📍 Location Tracking | Remember where you stored components |
| 📝 Notes | Add custom notes for each component |
| 📅 Purchase Date | Track when you bought components |
| ⚡ Real-time Sync | Instant updates across all devices |
| 📱 Mobile Friendly | Optimized for phones and tablets |
| 🔒 Secure | Password protected access |

## 🔧 Customization

### Change Password
Edit line 19 in `index.html`:
```javascript
var APP_PASSWORD = 'YourNewPassword';
```

### Add More Categories
Edit line 23 in `index.html`:
```javascript
var categories = ['Microcontroller', 'Display', 'YourNewCategory', ...];
```

### Change Theme Colors
The app uses Tailwind CSS. You can customize colors by modifying the gradient classes:
- `gradient-bg` - Main gradient (purple to indigo)
- Search for `from-purple-` and `to-indigo-` to change theme

## 🐛 Troubleshooting

### Can't Connect to Database
- ✅ Check that you created the `components` table in Supabase
- ✅ Verify you're using the **anon public** key (not service_role)
- ✅ Ensure the Project URL is correct (includes `https://`)

### Row Level Security Error
If you see "new row violates row-level security policy":

1. Go to Supabase → **Authentication → Policies**
2. Either disable RLS on the `components` table, OR
3. Run this SQL:

```sql
CREATE POLICY "Allow public access" ON components
FOR ALL USING (true)
WITH CHECK (true);
```

### Website Shows 404 Error
- ✅ Make sure GitHub Pages is enabled in repository settings
- ✅ Confirm the repository is **public** (private repos need GitHub Pro)
- ✅ Check that `index.html` is in the root directory

### Mobile View Issues
- ✅ Clear your browser cache
- ✅ Ensure you have good internet connection
- ✅ Try different browsers (Chrome, Safari, Firefox)

## 🤝 Contributing

Contributions are welcome! Feel free to:
- 🐛 Report bugs
- 💡 Suggest new features
- 🔧 Submit pull requests

## 📄 License

This project is licensed under the MIT License

## 👨‍💻 Author

**Your Name**
- GitHub: [@Electric-Brain](https://github.com/Electric-Brain)

## 🙏 Acknowledgments

- [Tailwind CSS](https://tailwindcss.com/) - For the beautiful UI framework
- [Supabase](https://supabase.com/) - For the awesome backend-as-a-service
- [Lucide Icons](https://lucide.dev/) - For the clean SVG icons

## 📞 Support

If you have any questions or need help:
- Contact me via GitHub or Instagram - (https://www.instagram.com/electricbrain_?igsh=MW50emVhbWlyd2I0dw==)

---

⭐ **If you find this project helpful, please give it a star!** ⭐

Made with ❤️ for electronics enthusiasts everywhere

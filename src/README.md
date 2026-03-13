# Animated Image Carousel

An elegant, fully-featured image carousel built with React, Motion (Framer Motion), and Tailwind CSS. Features seamless infinite scrolling, custom image uploads, and smooth animations with a glassmorphism design aesthetic.

![Carousel Demo](https://img.shields.io/badge/React-18+-61DAFB?style=flat&logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5+-3178C6?style=flat&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.0-38B2AC?style=flat&logo=tailwind-css&logoColor=white)

## ✨ Features

### Core Functionality
- **Seamless Infinite Scrolling**: True infinite loop with no visual jumps or resets
- **Auto-Play with Controls**: Automatic progression with play/pause functionality
- **Custom Image Upload**: Upload 1-5 custom images to replace defaults
- **Synchronized Animations**: Background and thumbnail containers move in perfect harmony
- **Responsive Design**: Fully responsive with proportional scaling that maintains design integrity

### Animation Details
- **Timing**: 1.5s ease-in-out-cubic transitions with 2.5s pauses between changes
- **Active State**: Thumbnails expand from 1:1 to 1.3:1 aspect ratio when active
- **Smooth Transitions**: Uses Motion (Framer Motion) for buttery-smooth animations
- **Background Blur**: Glassmorphism effect with 27.15px backdrop blur

### Technical Highlights
- **Dual Index System**: Separate indices for thumbnails and background positioning enable seamless infinite scroll
- **Proportional Sizing**: All dimensions use `min()` functions with responsive calculations
- **Memory Management**: Proper cleanup of object URLs for uploaded images
- **80vw Constraint**: Thumbnail container auto-hugs content but never exceeds 80% viewport width

## 🎨 Design System

### Proportional Sizing
The carousel uses a sophisticated proportional sizing system:

- **Thumbnail Corner Radius**: 10% of thumbnail height
- **Container Padding/Gaps**: 15% of thumbnail height  
- **Container Corner Radius**: 18% of thumbnail height
- **Max Width Constraint**: 80vw with all elements scaling proportionally

### Responsive Calculations
```css
/* Example from the implementation */
height: min(12vh, calc(80vw / 6.5))
gap: min(1.8vh, calc(80vw / 43.3))
borderRadius: min(1.2vh, calc(80vw / 65))
```

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- npm or yarn

### Installation

```bash
# Clone the repository
git clone <your-repo-url>
cd animated-image-carousel

# Install dependencies
npm install

# Start development server
npm run dev
```

## 📁 Project Structure

```
/
├── App.tsx                 # Main carousel component
├── components/
│   └── ui/
│       └── button.tsx     # UI button component
├── styles/
│   └── globals.css        # Global styles and Tailwind configuration
└── README.md
```

## 🎯 Usage

### Basic Implementation

The carousel is implemented as the main `App` component:

```tsx
import App from './App';

// Simply render the App component
<App />
```

### Upload Custom Images

1. Click the upload icon in the top-right corner
2. Select 1-5 images from your device
3. Images will immediately replace the defaults
4. Use "Reset to Default" to restore original images

### Play/Pause Control

Click the play/pause button in the top-right to control auto-progression.

## 🔧 Configuration

### Timing Configuration

Adjust the animation timing in `App.tsx`:

```tsx
const transitionConfig = {
  duration: 1.5,  // Animation duration in seconds
  ease: [0.25, 0.1, 0.25, 1]  // Cubic bezier curve
};

// Auto-play interval
setInterval(() => {
  // Change slide
}, 4000);  // 1.5s transition + 2.5s pause = 4s total
```

### Aspect Ratios

Modify thumbnail aspect ratios:

```tsx
animate={{
  width: activeIndex === index 
    ? 'min(15.6vh, calc(80vw / 5))'   // Active: 1.3:1
    : 'min(12vh, calc(80vw / 6.5))',  // Inactive: 1:1
  aspectRatio: activeIndex === index ? '1.3' : '1'
}}
```

## 🛠️ Technical Implementation

### Seamless Infinite Scroll

The carousel achieves seamless infinite scrolling using a dual-index system:

```tsx
const [activeIndex, setActiveIndex] = useState(0);  // For thumbnails (0-4)
const [scrollIndex, setScrollIndex] = useState(0);  // For background (0-∞)
const infiniteImages = [...images, ...images];      // Duplicate array

// Background scrolls continuously
animate={{ x: -scrollIndex * 100 + 'vw' }}

// Reset scroll position after completing one cycle
useEffect(() => {
  if (scrollIndex === images.length) {
    setTimeout(() => setScrollIndex(0), 1500);
  }
}, [scrollIndex]);
```

### Memory Management

Proper cleanup of object URLs prevents memory leaks:

```tsx
const handleFileUpload = (event) => {
  // Revoke old blob URLs before creating new ones
  images.forEach(img => {
    if (img.startsWith('blob:')) {
      URL.revokeObjectURL(img);
    }
  });
  
  const newImages = files.map(file => URL.createObjectURL(file));
  setImages(newImages);
};
```

## 🎨 Styling

### Glassmorphism Effect

The carousel uses a glassmorphism design with:
- `backdrop-blur-[27.15px]` for frosted glass effect
- `bg-[rgba(0,0,0,0.2)]` for semi-transparent backgrounds
- Border radius calculated proportionally to maintain design harmony

### Responsive Breakpoints

All sizing uses viewport-relative units with `min()` functions to ensure:
- Elements scale proportionally on all screen sizes
- Container never exceeds 80% viewport width
- Maintains aspect ratios across devices

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Credits

Built with:
- [React](https://react.dev/) - UI framework
- [Motion](https://motion.dev/) - Animation library (formerly Framer Motion)
- [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
- [Lucide React](https://lucide.dev/) - Icon library

---

**Note**: This carousel is optimized for modern browsers that support CSS `backdrop-filter` and native `aspect-ratio` properties.

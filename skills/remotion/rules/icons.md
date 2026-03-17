---
name: icons
description: Product-grade icon patterns for Remotion - SVG icons with gradient backgrounds instead of emoji
metadata:
  tags: icons, svg, design, visual, emoji, production
---

## Icon Rules

Emojis are FORBIDDEN in production Remotion videos. They render inconsistently across platforms, look unprofessional, and cannot be styled or animated.

Always use inline SVG icons wrapped in styled containers with gradient backgrounds.

## Icon Component Pattern

Create a reusable `IconWrapper` that provides consistent styling:

```tsx
import React from "react";

const IconWrapper: React.FC<{
  gradient: string;
  size?: number;
  children: React.ReactNode;
}> = ({ gradient, size = 48, children }) => (
  <div
    style={{
      width: size,
      height: size,
      borderRadius: size * 0.28,
      background: gradient,
      display: "flex",
      alignItems: "center",
      justifyContent: "center",
      flexShrink: 0,
      boxShadow: "0 4px 16px rgba(0,0,0,0.25)",
    }}
  >
    <svg
      width={size * 0.5}
      height={size * 0.5}
      viewBox="0 0 24 24"
      fill="none"
      stroke="white"
      strokeWidth="2"
      strokeLinecap="round"
      strokeLinejoin="round"
    >
      {children}
    </svg>
  </div>
);
```

## Example Icons

```tsx
// Video / Film
const IconVideo: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #6366f1, #8b5cf6)" size={size}>
    <rect x="2" y="4" width="20" height="16" rx="2" />
    <polygon points="10,9 15,12 10,15" fill="white" stroke="none" />
  </IconWrapper>
);

// Lightning / Power
const IconBolt: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #f59e0b, #d97706)" size={size}>
    <polygon points="13,2 3,14 12,14 11,22 21,10 12,10" fill="white" stroke="none" />
  </IconWrapper>
);

// Checkmark / Success
const IconCheck: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #22c55e, #16a34a)" size={size}>
    <polyline points="6,12 10,16 18,8" strokeWidth="3" />
  </IconWrapper>
);

// Document / Book
const IconDocs: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #3b82f6, #2563eb)" size={size}>
    <path d="M4 4h6a2 2 0 0 1 2 2v14l-3-2-3 2V6a2 2 0 0 0-2-2z" />
    <path d="M20 4h-6a2 2 0 0 0-2 2v14l3-2 3 2V6a2 2 0 0 1 2-2z" />
  </IconWrapper>
);

// Music / Audio
const IconAudio: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #14b8a6, #0d9488)" size={size}>
    <path d="M9 18V5l12-2v13" />
    <circle cx="6" cy="18" r="3" fill="white" />
    <circle cx="18" cy="16" r="3" fill="white" />
  </IconWrapper>
);

// Chart / Analytics
const IconChart: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #f97316, #ea580c)" size={size}>
    <rect x="4" y="12" width="4" height="8" rx="1" fill="white" stroke="none" />
    <rect x="10" y="6" width="4" height="14" rx="1" fill="white" stroke="none" />
    <rect x="16" y="9" width="4" height="11" rx="1" fill="white" stroke="none" />
  </IconWrapper>
);

// Globe / Map
const IconGlobe: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #06b6d4, #0891b2)" size={size}>
    <circle cx="12" cy="12" r="10" />
    <path d="M2 12h20" />
    <path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z" />
  </IconWrapper>
);

// 3D Cube
const IconCube: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #a855f7, #9333ea)" size={size}>
    <path d="M12 2L2 7l10 5 10-5-10-5z" fill="rgba(255,255,255,0.3)" />
    <path d="M2 7v10l10 5V12L2 7z" fill="rgba(255,255,255,0.5)" />
    <path d="M22 7v10l-10 5V12l10-5z" fill="rgba(255,255,255,0.8)" />
    <path d="M2 7l10 5 10-5M12 12v10" />
  </IconWrapper>
);

// Chat / Message
const IconChat: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #3b82f6, #2563eb)" size={size}>
    <path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z" />
  </IconWrapper>
);

// Target / Precision
const IconTarget: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #10b981, #059669)" size={size}>
    <circle cx="12" cy="12" r="10" />
    <circle cx="12" cy="12" r="6" />
    <circle cx="12" cy="12" r="2" fill="white" />
  </IconWrapper>
);

// Palette / Design
const IconPalette: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #ec4899, #db2777)" size={size}>
    <circle cx="12" cy="12" r="10" />
    <circle cx="9" cy="9" r="1.5" fill="rgba(236,72,153,0.8)" stroke="none" />
    <circle cx="15" cy="9" r="1.5" fill="rgba(236,72,153,0.8)" stroke="none" />
    <circle cx="8" cy="13" r="1.5" fill="rgba(236,72,153,0.8)" stroke="none" />
    <circle cx="16" cy="14" r="2" fill="white" stroke="none" />
  </IconWrapper>
);

// Typography / Text
const IconType: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #8b5cf6, #7c3aed)" size={size}>
    <polyline points="4,7 12,7 20,7" />
    <line x1="12" y1="7" x2="12" y2="20" />
    <line x1="8" y1="20" x2="16" y2="20" />
  </IconWrapper>
);

// Rocket / Launch
const IconRocket: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #10b981, #059669)" size={size}>
    <path d="M12 2C12 2 7 7 7 13L9 15L12 13L15 15L17 13C17 7 12 2 12 2Z" fill="white" stroke="none" />
    <path d="M7 13L5 17L9 15" fill="white" stroke="none" />
    <path d="M17 13L19 17L15 15" fill="white" stroke="none" />
    <circle cx="12" cy="9" r="1.5" fill="rgba(16,185,129,1)" />
  </IconWrapper>
);

// Star / Sparkle
const IconStar: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #f59e0b, #ef4444)" size={size}>
    <path d="M12 2 L14 9 L21 9 L15 14 L17 21 L12 17 L7 21 L9 14 L3 9 L10 9 Z" fill="white" stroke="none" />
  </IconWrapper>
);

// Shield / Security
const IconShield: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #6366f1, #4f46e5)" size={size}>
    <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z" />
  </IconWrapper>
);

// Settings / Gear
const IconGear: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #64748b, #475569)" size={size}>
    <circle cx="12" cy="12" r="3" />
    <path d="M12 1v2M12 21v2M4.22 4.22l1.42 1.42M18.36 18.36l1.42 1.42M1 12h2M21 12h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42" />
  </IconWrapper>
);

// User / Profile
const IconUser: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #f472b6, #ec4899)" size={size}>
    <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2" />
    <circle cx="12" cy="7" r="4" />
  </IconWrapper>
);

// Code / Terminal
const IconCode: React.FC<{ size?: number }> = ({ size }) => (
  <IconWrapper gradient="linear-gradient(135deg, #22d3ee, #06b6d4)" size={size}>
    <polyline points="16,18 22,12 16,6" />
    <polyline points="8,6 2,12 8,18" />
  </IconWrapper>
);
```

## Gradient Color Palette

Use semantically meaningful gradient colors:

| Category | Gradient | Use for |
|----------|----------|---------|
| Primary | `#6366f1 → #8b5cf6` | Video, media, core features |
| Success | `#22c55e → #16a34a` | Complete, check, rocket |
| Warning | `#f59e0b → #d97706` | Lightning, star, highlight |
| Info | `#3b82f6 → #2563eb` | Docs, chat, info |
| Creative | `#ec4899 → #db2777` | Design, palette, art |
| Code | `#8b5cf6 → #7c3aed` | Code, typography, dev |
| Data | `#f97316 → #ea580c` | Charts, analytics |
| Nature | `#14b8a6 → #0d9488` | Audio, music, media |
| World | `#06b6d4 → #0891b2` | Maps, globe, network |
| Premium | `#a855f7 → #9333ea` | 3D, advanced, pro |
| Neutral | `#64748b → #475569` | Settings, gear, utility |
| People | `#f472b6 → #ec4899` | User, profile, social |

## Size Guidelines

- Feature cards / hero sections: `size={52}` or `size={64}`
- Bullet points / list items: `size={36}` or `size={44}`
- Inline / compact: `size={24}` or `size={28}`

## Usage Example

```tsx
// ❌ BAD - emoji, inconsistent rendering, not animatable
<div style={{ fontSize: 40 }}>🎬</div>
<BulletPoint icon="✨" text="Some feature" />

// ✅ GOOD - SVG icon with gradient, consistent, animatable
<IconVideo size={52} />
<BulletPoint icon={<IconVideo size={44} />} text="Some feature" />
```

## Animating Icons

Icons can be animated using Remotion's `spring()` and `interpolate()`:

```tsx
const frame = useCurrentFrame();
const { fps } = useVideoConfig();

const scale = spring({ frame, fps, config: { damping: 12 } });

<div style={{ transform: `scale(${scale})` }}>
  <IconVideo size={64} />
</div>
```

# LinkedIn Banner (Profile Background) Template

## Asset Specifications

- **Dimensions**: 1584 x 396 pixels
- **Aspect Ratio**: 4:1 (horizontal)
- **File Format**: PNG or JPEG
- **Max File Size**: 8MB
- **Display Size**: Varies by device (desktop vs mobile)
- **Profile Photo Overlap**:
  - Desktop: Bottom-left corner (~200px circle)
  - Mobile: Profile photo overlaps more of left side
  - Safe Zone: Avoid critical content in bottom-left 250x250px area

## Platform Best Practices

### Text Guidelines
- **Headline/Tagline**: 3-8 words maximum
- **Supporting Text**: Brief descriptor or value proposition (under 15 words)
- **Minimum Font Size**: 36px for main text (legibility across devices)
- **Text Placement**: Right side or top-right (avoid bottom-left due to profile photo)
- **Readability**: High contrast essential - banner is often viewed at small size in feed

### Visual Guidelines
- **Orientation**: Horizontal landscape
- **Background**: Can be gradient, solid color, subtle pattern, or branded imagery
- **Logo Placement**: Top-right or right-center (never bottom-left)
- **Profile Photo Consideration**: Design around the profile photo, not fighting it
- **Mobile vs Desktop**: Check how it looks on both - mobile crops more aggressively

### Design Considerations
- **Professional Context**: More formal than other social platforms
- **First Impression**: Often the first thing visitors see on your profile
- **Brand Consistency**: Should align with company brand or personal brand
- **Longevity**: Typically changed infrequently - avoid time-sensitive content
- **Networking Focus**: Can communicate role, expertise, or value proposition
- **Accessibility**: Clear, professional, and easy to read at a glance

## Common Use Cases

### 1. Personal Brand / Professional Identity
- Name or headline (Job Title at Company)
- Key skills or expertise areas
- Professional but approachable design
- Consistent with resume/portfolio

### 2. Company Representation
- Company logo and tagline
- Brand colors and visual identity
- Professional polish
- Reinforces employer brand

### 3. Thought Leadership
- Signature topic or expertise
- Speaking/content themes
- Establishes authority
- Memorable positioning

### 4. Entrepreneur / Freelancer
- Services offered
- Value proposition
- Contact or CTA
- Portfolio or work examples (subtle)

### 5. Job Seeker
- Target role or industry
- Key qualifications
- "Open to opportunities" message
- Professional presentation

### 6. Event / Speaking
- Conference logos or speaking topics
- Credentials or achievements
- Temporary promotional banner
- Drives to specific content

## Layout Patterns That Work Well

### Right-Aligned Text
```
┌────────────────────────────────────────────┐
│                                            │
│                      YOUR HEADLINE         │
│  [Profile           Supporting text or     │
│   Photo]            tagline here           │
│                                   [Logo]   │
└────────────────────────────────────────────┘
```

### Centered with Safe Zone
```
┌────────────────────────────────────────────┐
│                                            │
│              CENTERED HEADLINE             │
│           Your professional tagline        │
│  [Profile                                  │
│   Photo]                          [Logo]   │
└────────────────────────────────────────────┘
```

### Split Background
```
┌────────────────────────────────────────────┐
│ COLOR/    │                                │
│ PATTERN   │    TEXT CONTENT                │
│  BLOCK    │    ON CONTRASTING              │
│ [Profile] │    BACKGROUND                  │
│           │                                │
└────────────────────────────────────────────┘
```

### Minimal Professional
```
┌────────────────────────────────────────────┐
│                                            │
│                                            │
│  [Profile]              SIMPLE CLEAN       │
│                         TYPOGRAPHY         │
│                                            │
└────────────────────────────────────────────┘
```

### Branded Gradient
```
┌────────────────────────────────────────────┐
│ ░░░░░░░░░░░░░░░░░░░░░░░░░░░▒▒▒▒▒▒▒▒▒▒▒▒▒ │
│ ░░░░░░░░   YOUR TEXT   ░░░▒▒▒▒▒▒▒▒▒▒▒▒▒▒ │
│ ░░[Profile]           ░░░▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒ │
│ ░░░░░░░░░░░░░░░░░░░░░▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒ │
│ (Gradient from brand color to brand color) │
└────────────────────────────────────────────┘
```

## What to Avoid

❌ **Content in bottom-left**: Will be covered by profile photo
❌ **Busy backgrounds**: Reduces text readability
❌ **Small text**: Won't be legible in feed views
❌ **Low contrast**: Text must stand out from background
❌ **Too much text**: This isn't a resume - be concise
❌ **Personal/casual photos**: Keep it professional
❌ **Time-sensitive content**: "Hiring for 2023" dates quickly
❌ **Multiple messages**: One clear communication
❌ **Stretched images**: Maintain proper aspect ratio

## Design Tips

✅ **Think about negative space** - The banner is wide and short; embrace it
✅ **Test on mobile** - Check how it crops on smaller screens
✅ **Design around profile photo** - Work with it, not against it
✅ **Use brand colors** - Reinforce visual identity
✅ **Keep it simple** - Clean, professional designs age better
✅ **Consider your industry** - Finance vs creative fields have different expectations
✅ **Update periodically** - Refresh every 6-12 months or for major changes
✅ **Align with content** - Banner should reflect what you post about
✅ **Professional quality** - This is your header; make it polished

## Accessibility Notes

- **Color Contrast**: Minimum 4.5:1 ratio for all text
- **Text Size**: Large enough to read when banner is small (36px+ for main text)
- **Alternative Text**: Add alt text when uploading ("LinkedIn banner showing [description]")
- **No Text in Images**: If possible, overlay text with HTML/CSS for better accessibility
- **Simple Message**: Clear and direct communication
- **Avoid Color-Only Meaning**: Don't rely solely on color to convey information

## Content Planning Questions

When creating a LinkedIn Banner, ask:
1. **What's your professional goal?** (job search, thought leadership, sales, networking)
2. **What do you want visitors to know immediately?** (one key message)
3. **Who's your target audience?** (recruiters, clients, peers, employers)
4. **What's your industry standard?** (conservative or creative acceptable)
5. **Does it align with your profile?** (headline, about section consistency)
6. **Is it timeless?** (will it still be relevant in 6 months?)
7. **How does it look next to your profile photo?** (complementary colors and style)

## Technical Implementation

### HTML Structure
```html
<div style="width: 1584px; height: 396px; position: relative; overflow: hidden;
            background: linear-gradient(135deg, [brand-color-1], [brand-color-2]);">

  <!-- Optional background pattern or image -->
  <div style="position: absolute; inset: 0; opacity: 0.1;">
    <!-- Subtle pattern or texture -->
  </div>

  <!-- Content area (avoiding bottom-left for profile photo) -->
  <div style="position: absolute; right: 80px; top: 50%; transform: translateY(-50%);
              text-align: right; max-width: 800px;">

    <!-- Main headline -->
    <h1 style="font-size: 64px; font-weight: 700; color: white;
               line-height: 1.1; margin-bottom: 16px; letter-spacing: -0.02em;">
      Your Professional Headline
    </h1>

    <!-- Supporting tagline -->
    <p style="font-size: 36px; color: rgba(255,255,255,0.9);
              line-height: 1.3; font-weight: 400;">
      Brief descriptor or value proposition
    </p>

  </div>

  <!-- Optional logo (top-right or bottom-right) -->
  <img src="[logo-path]" style="position: absolute; top: 40px; right: 60px;
       width: 120px; opacity: 0.9;" alt="Logo">

</div>
```

### Safe Zone Reference
```css
/* Avoid placing critical content in this area: */
.profile-photo-zone {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 250px;
  height: 250px;
  /* Profile photo will overlap this area on desktop */
}

/* Additional mobile consideration: */
/* On mobile, even more of the left side may be covered */
/* Keep primary content right-aligned or centered-right */
```

### Export Settings
- Format: PNG (for transparency if needed) or JPEG (smaller file size)
- Resolution: Exactly 1584 x 396px (don't scale)
- Quality: High (85-95%)
- Color Profile: sRGB
- File Size: Under 8MB (LinkedIn limit)

## Platform-Specific Notes

### Desktop View
- Full banner visible
- Profile photo overlaps bottom-left as ~200px circle
- Name and headline appear below profile photo
- Banner is prominently displayed

### Mobile View
- Banner height compressed
- More aggressive cropping on left side
- Profile photo covers more of banner area
- Test on actual mobile device

### In Feed vs On Profile
- **On Profile**: Full banner visible, main showcase
- **In Feed**: May appear as small thumbnail in activity
- Design should work at multiple sizes

---

**Remember**: LinkedIn banners are your professional header. Keep it polished, clear, and aligned with your career goals. When in doubt, choose clarity over creativity.

# Instagram Story Template

## Asset Specifications

- **Dimensions**: 1080 x 1920 pixels
- **Aspect Ratio**: 9:16 (vertical)
- **File Format**: PNG or JPEG (MP4 for video)
- **Max File Size**: 30MB
- **Duration**: Up to 15 seconds for video
- **Safe Zone**:
  - Top 250px: Avoid important content (profile info, timestamp)
  - Bottom 300px: Avoid important content (action buttons, swipe-up area)
  - Effective content area: 1080 x 1370px centered

## Platform Best Practices

### Text Guidelines
- **Headline**: Maximum 2-3 short lines (40-50 characters total)
- **Body Text**: Keep under 100 characters
- **Minimum Font Size**: 24px for readability on mobile
- **Contrast**: Ensure high contrast for outdoor/bright viewing conditions
- **Text Placement**: Center text between safe zones (250px from top, 300px from bottom)

### Visual Guidelines
- **Orientation**: Vertical only
- **Background**: Can be full-bleed image, video, or solid color
- **Logo Placement**: Usually top-center or bottom-center within safe zones
- **Interactive Elements**:
  - Poll stickers: Place in middle third
  - Swipe-up CTAs: Bottom safe zone
  - Links: Bottom safe zone (250-300px from bottom)

### Design Considerations
- **Attention Span**: 3-5 seconds before user swipes - front-load key message
- **Sound**: Design for sound-off viewing (use text overlays)
- **Thumb Zone**: Interactive elements should be easy to tap (min 44x44px)
- **Brand Consistency**: Use consistent templates for series content
- **Accessibility**: High contrast, large text, simple layouts

## Common Use Cases

### 1. Announcement / News
- Bold headline with key info
- Supporting details in smaller text
- Clear CTA or swipe-up prompt
- Brand colors for recognition

### 2. Product Showcase
- Hero product image (centered)
- Product name and key benefit
- Price or CTA
- Lifestyle context or background

### 3. Behind the Scenes
- Candid photo or video
- Casual, relatable copy
- Personal or human element
- Less formal than feed posts

### 4. Promotional / Sale
- Eye-catching headline (discount %, offer)
- Urgency indicators (limited time, countdown)
- Bold typography and colors
- Clear CTA with action verb

### 5. Engagement / Poll
- Question or statement
- Poll sticker or interactive element
- Conversational tone
- Encourage response

### 6. Educational / Tip
- Numbered or bulleted content
- Easy-to-scan format
- Valuable takeaway
- Series format works well (1/3, 2/3, 3/3)

## Layout Patterns That Work Well

### Centered Hero
```
[Safe Zone - 250px]

      LOGO

   HERO IMAGE
      OR
   BOLD HEADLINE

   Supporting text

[Safe Zone - 300px]
```

### Split Screen
```
[Safe Zone]
━━━━━━━━━━━━━━
IMAGE / COLOR
━━━━━━━━━━━━━━
TEXT / CTA
CONTENT AREA
━━━━━━━━━━━━━━
[Safe Zone]
```

### Text Overlay
```
[Safe Zone]

BACKGROUND IMAGE
    WITH
  HEADLINE
  OVERLAY
   (high contrast)

[Safe Zone]
```

### Minimal Card
```
[Safe Zone]

  ┌─────────┐
  │ Content │
  │  Card   │
  │ Centered│
  │         │
  │  + CTA  │
  └─────────┘

[Safe Zone]
```

## What to Avoid

❌ **Too much text**: Stories are glanceable - keep it brief
❌ **Small fonts**: Text under 24px is hard to read
❌ **Low contrast**: Light text on light backgrounds or dark on dark
❌ **Important content in safe zones**: Will be covered by UI elements
❌ **Horizontal images/videos**: Will be cropped significantly
❌ **Multiple CTAs**: One clear action per story
❌ **Cluttered layouts**: Keep it simple and focused
❌ **Generic stock photos**: Use authentic, on-brand imagery

## Design Tips

✅ **Use brand colors boldly** - Stories are a place to be eye-catching
✅ **Create series** - Use consistent templates for multi-part stories
✅ **Add motion** - Subtle animations or video keep attention
✅ **Test on mobile** - Always preview on actual device size
✅ **Front-load value** - Key message should be visible immediately
✅ **Use stickers strategically** - Polls, questions, countdowns boost engagement
✅ **Maintain aspect ratio** - Don't squash or stretch content
✅ **Consider dark mode** - Test designs in both light and dark contexts

## Accessibility Notes

- **Color Contrast**: Minimum 4.5:1 ratio for text
- **Text Size**: Large enough to read on 5-6" screens
- **Alternative Text**: If posted via API, include alt text
- **Avoid Text in Images**: Overlay text with HTML/CSS when possible
- **Simple Language**: Clear, concise messaging
- **Visual Hierarchy**: Obvious reading order

## Content Planning Questions

When creating an Instagram Story, ask:
1. **What's the goal?** (awareness, engagement, traffic, sales)
2. **What's the one key message?** (can fit in a 5-word headline?)
3. **Who's the audience?** (existing followers, new viewers, specific demographic)
4. **What should they do?** (swipe up, respond, share, remember)
5. **Does it fit the brand?** (colors, tone, style consistent)
6. **Is there a series?** (part of a multi-story sequence)

## Technical Implementation

### HTML Structure
```html
<div style="width: 1080px; height: 1920px; position: relative; overflow: hidden;">
  <!-- Background -->
  <div style="position: absolute; inset: 0; background: [brand-color];">
    <!-- or background-image for image backgrounds -->
  </div>

  <!-- Content (within safe zones) -->
  <div style="position: absolute; top: 250px; left: 0; right: 0; bottom: 300px;
              display: flex; flex-direction: column; align-items: center;
              justify-content: center; padding: 40px; text-align: center;">

    <!-- Logo (optional) -->
    <img src="[logo-path]" style="width: 120px; margin-bottom: 40px;" alt="Brand logo">

    <!-- Headline -->
    <h1 style="font-size: 72px; font-weight: 700; color: white;
               line-height: 1.1; margin-bottom: 20px;">
      Headline
    </h1>

    <!-- Body -->
    <p style="font-size: 32px; color: white; line-height: 1.4;">
      Supporting text
    </p>

  </div>
</div>
```

### Export Settings
- Format: PNG (for static) or MP4 (for animated)
- Resolution: 1080 x 1920px (don't scale down)
- Quality: High (85-95%)
- Color Profile: sRGB

---

**Remember**: Instagram Stories are ephemeral and fast-paced. Design for quick comprehension, bold visuals, and mobile viewing.

# Email Signature Template

## Asset Specifications

- **Dimensions**: Flexible, typically 400-600px wide x 100-200px tall
- **File Format**: HTML with inline CSS (most compatible)
- **Images**: Hosted externally (email clients don't support embedded)
- **Max Width**: 600px (prevents horizontal scrolling on mobile)
- **File Size**: Keep total HTML + images under 50KB for email client compatibility

## Platform Best Practices

### Essential Information
**Required Elements:**
- Full name
- Job title
- Company name
- Primary phone number
- Primary email address

**Optional Elements:**
- Company logo
- Headshot photo
- Website URL
- Office address
- Social media links (2-3 max)
- Legal disclaimers
- Call-to-action or banner

### Text Guidelines
- **Name**: 14-16px, bold, prominent
- **Title/Company**: 12-13px, normal weight or medium
- **Contact Info**: 11-12px, comfortable reading size
- **Minimum Font Size**: 10px (email client limitations)
- **Line Height**: 1.4-1.6 for comfortable reading
- **Font Choice**: Web-safe fonts only (Arial, Helvetica, Georgia, Times, Verdana, Tahoma)
- **No Custom Fonts**: Email clients don't support web fonts reliably

### Visual Guidelines
- **Layout**: Typically left-aligned or two-column
- **Logo Size**: 80-150px wide maximum
- **Headshot**: 60-80px square or circle (if used)
- **Social Icons**: 16-24px square, linked
- **Colors**: Brand colors for accents, dark gray for text (avoid pure black #000)
- **Links**: Color and underline for clarity
- **Dividers**: Thin lines (1px) or spacing for separation

### Email Client Considerations
- **Tables for Layout**: Use `<table>` tags, not CSS Grid/Flexbox
- **Inline CSS**: All styles must be inline (no `<style>` tags or external CSS)
- **No CSS Properties**: Avoid float, position, background-image (use img tags)
- **Images**: Use absolute URLs (hosted on web server)
- **Alt Text**: Essential for when images are blocked
- **Test Across Clients**: Gmail, Outlook, Apple Mail, mobile all render differently

## Common Use Cases

### 1. Corporate Standard
- Company-mandated template
- Logo and branding required
- Legal disclaimers included
- Professional and uniform
- Typically minimal design

### 2. Sales / Business Development
- Photo included (builds rapport)
- Multiple contact methods
- Social media presence
- Call-to-action (book a meeting, view demo)
- May include promotional banner

### 3. Professional Services
- Clean, text-focused design
- Credentials or certifications
- Professional associations
- Conservative approach
- Website and LinkedIn prominent

### 4. Creative Professional
- More visual design elements
- Portfolio link
- Unique but still professional
- Brand personality
- May include recent work banner

### 5. Executive / C-Suite
- Streamlined and minimal
- Name and title prominent
- Assistant contact included
- Company logo
- No clutter or excess info

### 6. Startup / Tech
- Modern, clean design
- Social media integrated
- App store badges (if applicable)
- Company tagline or mission
- May include latest blog post or news

## Layout Patterns That Work Well

### Simple Text-Only
```
John Doe
Creative Director | Acme Corp
📞 (555) 123-4567 | ✉ john@acme.com
🌐 acme.com
```

### Two-Column with Logo
```
┌─────────────────────────────────────┐
│ [LOGO] │ John Doe                   │
│        │ Creative Director          │
│        │ Acme Corporation           │
│        │                            │
│        │ P: (555) 123-4567          │
│        │ E: john@acme.com           │
│        │ W: acme.com                │
└─────────────────────────────────────┘
```

### Horizontal with Headshot
```
┌─────────────────────────────────────┐
│ [PHOTO] John Doe                    │
│         Creative Director           │
│         Acme Corp | john@acme.com   │
│         (555) 123-4567 | acme.com   │
│         [in] [tw] [fb]              │
└─────────────────────────────────────┘
```

### Stacked Minimal
```
┌─────────────────────────────────────┐
│ JOHN DOE                            │
│ Creative Director                   │
│ ────────────────────────              │
│ Acme Corporation                    │
│ john@acme.com | (555) 123-4567      │
│ acme.com                            │
│ [LinkedIn icon]                     │
└─────────────────────────────────────┘
```

### With Banner/CTA
```
┌─────────────────────────────────────┐
│ John Doe | Creative Director        │
│ Acme Corp | john@acme.com           │
│ (555) 123-4567 | acme.com           │
│                                     │
│ [─── Promotional Banner ───]        │
│ [  Check out our new product!  ]   │
└─────────────────────────────────────┘
```

## What to Avoid

❌ **Large images**: Slow load times and may be blocked
❌ **Too much information**: Signatures should be concise
❌ **Social media overload**: 2-3 platforms maximum
❌ **Animated GIFs**: Distracting and unprofessional
❌ **Quotes or slogans**: Rarely appropriate in signatures
❌ **Background images**: Often blocked or don't render
❌ **External CSS or JavaScript**: Won't work in email clients
❌ **Font sizes under 10px**: Illegible on mobile
❌ **Multiple phone numbers**: Pick the primary one
❌ **Personal social media**: Keep it professional (LinkedIn, not Facebook)

## Design Tips

✅ **Keep it under 4 lines of text** - Concise and scannable
✅ **Use web-safe fonts** - Arial, Helvetica, Georgia, Verdana
✅ **Make phone numbers clickable** - `tel:` links work on mobile
✅ **Test on mobile** - Many emails read on phones
✅ **Host images reliably** - Use CDN or stable server
✅ **Include alt text** - For when images are blocked
✅ **Match brand colors** - But don't go overboard
✅ **Left-align for simplicity** - Most compatible across clients
✅ **Use email signature generators** - For HTML table structure
✅ **Update regularly** - Stale info undermines credibility

## Accessibility Notes

- **Color Contrast**: 4.5:1 minimum for text
- **Clickable Links**: Clearly indicated with color and/or underline
- **Alt Text**: Descriptive alt text for all images
- **Text-Only Fallback**: Should be readable even if images blocked
- **Semantic HTML**: Use proper table structure
- **Font Size**: Readable on all devices (11px minimum)
- **Clear Hierarchy**: Name most prominent, then contact info

## Email Client Compatibility

### Gmail
- Strips `<style>` tags (use inline CSS only)
- Converts some CSS properties
- Images blocked by default (requires user action)
- Supports basic tables and inline styles

### Outlook
- Uses Word rendering engine (limited CSS support)
- Doesn't support background images well
- Use `mso-` properties for Outlook-specific fixes
- Table-based layouts work best

### Apple Mail
- Best CSS support among email clients
- Renders most HTML/CSS correctly
- Good image support
- Can use slightly more advanced techniques

### Mobile Clients (iOS/Android)
- Small screen width (optimize for 320-375px)
- Touch targets must be large (44x44px minimum)
- Click-to-call phone links
- Simplified layouts work best

## Content Planning Questions

When creating an email signature, ask:
1. **What information is essential?** (must-haves vs nice-to-haves)
2. **Who are you emailing?** (clients, partners, internal, mixed)
3. **What's your goal?** (professional presence, drive traffic, branding)
4. **Company guidelines?** (any required elements or restrictions)
5. **Include photo?** (builds rapport but adds size)
6. **Social media?** (which platforms are professional for you)
7. **Call-to-action?** (book meeting, download, visit site)
8. **Legal requirements?** (disclaimers, registered office address)

## Technical Implementation

### Basic HTML Structure (Table-Based)
```html
<table cellpadding="0" cellspacing="0" border="0" style="font-family: Arial, sans-serif; font-size: 12px; line-height: 1.4; color: #333333;">
  <tr>
    <td style="padding-right: 15px; vertical-align: top;">
      <!-- Logo -->
      <img src="https://example.com/logo.png" alt="Company Logo" width="100" height="auto" style="display: block; border: 0;">
    </td>
    <td style="vertical-align: top;">
      <!-- Name -->
      <div style="font-size: 16px; font-weight: bold; color: #1a1a1a; margin-bottom: 4px;">
        John Doe
      </div>
      <!-- Title -->
      <div style="font-size: 13px; color: #666666; margin-bottom: 8px;">
        Creative Director | Acme Corporation
      </div>
      <!-- Contact Info -->
      <div style="font-size: 12px; color: #333333; line-height: 1.6;">
        <a href="tel:+15551234567" style="color: #0066cc; text-decoration: none;">+1 (555) 123-4567</a> |
        <a href="mailto:john@acme.com" style="color: #0066cc; text-decoration: none;">john@acme.com</a><br>
        <a href="https://acme.com" style="color: #0066cc; text-decoration: none;">acme.com</a>
      </div>
      <!-- Social Icons (Optional) -->
      <div style="margin-top: 8px;">
        <a href="https://linkedin.com/in/johndoe" style="text-decoration: none; margin-right: 8px;">
          <img src="https://example.com/linkedin-icon.png" alt="LinkedIn" width="20" height="20" style="display: inline-block; border: 0;">
        </a>
        <a href="https://twitter.com/johndoe" style="text-decoration: none;">
          <img src="https://example.com/twitter-icon.png" alt="Twitter" width="20" height="20" style="display: inline-block; border: 0;">
        </a>
      </div>
    </td>
  </tr>
</table>
```

### Simple Text-Only (Most Compatible)
```html
<div style="font-family: Arial, sans-serif; font-size: 12px; line-height: 1.6; color: #333333;">
  <strong style="font-size: 14px;">John Doe</strong><br>
  Creative Director<br>
  Acme Corporation<br>
  <a href="tel:+15551234567" style="color: #0066cc;">+1 (555) 123-4567</a> |
  <a href="mailto:john@acme.com" style="color: #0066cc;">john@acme.com</a><br>
  <a href="https://acme.com" style="color: #0066cc;">acme.com</a>
</div>
```

### With Divider Line
```html
<table cellpadding="0" cellspacing="0" border="0" style="font-family: Arial, sans-serif; font-size: 12px; color: #333333;">
  <tr>
    <td>
      <div style="font-size: 16px; font-weight: bold; margin-bottom: 4px;">John Doe</div>
      <div style="font-size: 13px; color: #666666; margin-bottom: 8px;">Creative Director</div>
      <div style="border-top: 2px solid #0066cc; width: 60px; margin: 8px 0;"></div>
      <div style="font-size: 12px; line-height: 1.6;">
        Acme Corporation<br>
        <a href="tel:+15551234567" style="color: #0066cc; text-decoration: none;">+1 (555) 123-4567</a><br>
        <a href="mailto:john@acme.com" style="color: #0066cc; text-decoration: none;">john@acme.com</a><br>
        <a href="https://acme.com" style="color: #0066cc; text-decoration: none;">acme.com</a>
      </div>
    </td>
  </tr>
</table>
```

## Image Requirements

### Logo Image
- Format: PNG with transparency
- Size: 100-150px wide, proportional height
- Resolution: 2x for retina (200-300px actual, scaled down with HTML width attribute)
- Hosted: Stable URL (CDN or company server)
- Alt text: "Company Name Logo"

### Headshot Photo (if used)
- Format: JPEG or PNG
- Size: 60-80px square
- Resolution: 2x for retina (120-160px actual, scaled down)
- Professional quality
- Alt text: "John Doe headshot"

### Social Media Icons
- Format: PNG with transparency
- Size: 16-24px square
- Resolution: 2x for retina (32-48px actual, scaled down)
- Consistent style set
- Alt text: "[Platform] icon" or "[Platform] profile"

## Implementation Guide

### Installing in Email Clients

**Gmail:**
1. Settings → See all settings → General → Signature
2. Paste HTML (Gmail editor accepts HTML)
3. Test by sending to yourself

**Outlook (Desktop):**
1. File → Options → Mail → Signatures
2. Paste HTML into editor
3. May need to paste into a temporary email first, then copy formatted version into signature editor

**Apple Mail:**
1. Preferences → Signatures
2. Create new signature
3. Close preferences, locate signature file in ~/Library/Mail
4. Edit .mailsignature file with HTML
5. Lock file to prevent Mail from changing it

**Mobile:**
- Most mobile clients don't support HTML signatures well
- Consider a simplified text version for mobile

### Testing Checklist
- [ ] Send test email to yourself
- [ ] Check in Gmail (web and app)
- [ ] Check in Outlook (desktop and web)
- [ ] Check in Apple Mail
- [ ] Check on mobile device (iOS and Android)
- [ ] Verify all links work
- [ ] Verify images load (or show appropriate alt text)
- [ ] Test click-to-call on phone
- [ ] Check formatting in reply threads
- [ ] Verify it doesn't break email layout

## Best Practices Summary

**Do:**
- Keep it concise (3-5 lines of text)
- Use tables for layout structure
- Write all CSS inline
- Host images externally with absolute URLs
- Include alt text for all images
- Make phone numbers and emails clickable
- Test across multiple email clients
- Use web-safe fonts

**Don't:**
- Use embedded or external CSS
- Include large images or attachments
- Add animations or JavaScript
- Overcrowd with information
- Use tiny font sizes
- Include inspirational quotes
- Add more than 2-3 social links
- Forget to update when info changes

---

**Remember**: Email signatures are not design showcases - they're functional tools for professional communication. Prioritize compatibility and clarity over visual complexity.

# Colater - Brand-Driven Design Asset Generation Skill

## Overview
Colater is a comprehensive design workflow skill that helps users create brand-consistent visual assets. The skill allows users to ingest their brand identity (logos, colors, typography, values) and generate professional design assets like social media posts, banners, business cards, and more - all as downloadable HTML with PNG export capability.

## Core Philosophy
- **Brand-first approach**: All designs are generated based on a structured brand definition
- **Designer mindset**: Act as a professional designer by asking clarifying questions and solving visual problems
- **Easy validation**: Present findings for user confirmation rather than asking them to provide everything upfront
- **Three variations**: Always generate 3 design options to give users choice
- **Web-based preview**: All assets preview in browser with instant PNG download

## Folder Structure

```
/brands/
  └── [client-name]/
      ├── brand.json           # Structured brand definition
      ├── brand-voice.md       # Brand voice, tone, messaging guidelines
      └── assets/
          ├── logos/           # Logo files (SVG, PNG)
          └── fonts/           # Custom font files (if any)

/templates/
  └── [asset-type].md          # Best practices and specs for each asset type

/design-output/
  └── [descriptive-name-v#].html   # Generated designs with preview interface
```

## Brand Ingestion Workflow

### Step 1: Initial Brand Discovery
When a user wants to set up a new brand, follow this process:

1. **Web Research First**: Search for the brand online to understand:
   - Visual identity (if available publicly)
   - Industry and competitors
   - Brand positioning and values
   - Existing design patterns

2. **Present Findings**: Show the user what you found and ask: "Does this match your understanding of the brand?"

3. **Ingest Brand Assets**: If user provides brand book (PDF) or assets:
   - Extract logos, colors, fonts, and values
   - Identify logo variants: full-color, black, white, icon, wordmark, horizontal, vertical
   - Parse color palette and map to Tailwind color names
   - Identify typography (family, weights, sizes, spacing)
   - Extract brand personality and values

4. **Fill Gaps with Questionnaire**: For missing information, use targeted questions:
   - Show competitor examples and ask: "Should your brand feel similar or different?"
   - Present brand attribute scales and ask user to position their brand
   - Infer motion philosophy from brand values

### Step 2: Brand Values & Personality
Use scales to understand brand positioning (user rates 1-5):

**Core Attributes** (adjust based on industry):
- Playful ←→ Serious
- Modern ←→ Traditional
- Bold ←→ Subtle
- Warm ←→ Cool
- Accessible ←→ Premium
- Minimal ←→ Maximal

Map these values to design decisions (colors, typography, layout, motion).

### Step 3: Create Brand Definition
Generate a `brand.json` file with this structure:

```json
{
  "name": "Brand Name",
  "industry": "technology",
  "target_audience": "B2B SaaS companies",

  "colors": {
    "primary": "blue-600",      // Main brand color
    "secondary": "amber-500",   // Supporting color
    "accent": "purple-500",     // Accent/CTA color
    "neutral": "slate-500",     // Text and backgrounds
    "background": "white",
    "text": "slate-900"
  },

  "typography": {
    "heading": {
      "family": "Inter",
      "weights": [600, 700, 800],
      "sizes": {
        "h1": "3rem",
        "h2": "2.25rem",
        "h3": "1.875rem"
      },
      "lineHeight": "1.2",
      "letterSpacing": "-0.02em"
    },
    "body": {
      "family": "Inter",
      "weights": [400, 500],
      "sizes": {
        "base": "1rem",
        "large": "1.125rem",
        "small": "0.875rem"
      },
      "lineHeight": "1.6",
      "letterSpacing": "0"
    },
    "tailwind_classes": {
      "h1": "text-5xl font-bold tracking-tight",
      "h2": "text-4xl font-bold tracking-tight",
      "h3": "text-3xl font-semibold",
      "body": "text-base font-normal leading-relaxed",
      "body-large": "text-lg font-normal leading-relaxed",
      "caption": "text-sm font-medium"
    }
  },

  "logos": {
    "primary": "assets/logos/logo-full-color.svg",   // Maps to best available
    "full_color": "assets/logos/logo-full-color.svg",
    "black": "assets/logos/logo-black.svg",
    "white": "assets/logos/logo-white.svg",
    "icon": "assets/logos/icon.svg",
    "wordmark": "assets/logos/wordmark.svg",
    "horizontal": "assets/logos/logo-horizontal.svg",
    "vertical": "assets/logos/logo-vertical.svg"
  },

  "motion": {
    "philosophy": "weighted-authoritative",
    "description": "Slow, deliberate animations that convey reliability and gravitas",
    "timing": {
      "fast": "200ms",
      "medium": "500ms",
      "slow": "800ms"
    },
    "easing": "ease-in-out",
    "transitions": {
      "fade": "opacity 800ms ease-in-out",
      "slide": "transform 500ms ease-in-out"
    }
  },

  "values": {
    "playful_serious": 4,
    "modern_traditional": 2,
    "bold_subtle": 3,
    "warm_cool": 3,
    "accessible_premium": 4,
    "minimal_maximal": 2
  }
}
```

**Note on Logo Variants**: Not all brands will have all variants. The `primary` key should point to whichever variant is most commonly used. If only one logo exists, all keys can point to the same file.

### Step 4: Brand Voice Documentation
Create `brand-voice.md` with:
- Brand story and positioning
- Tone of voice guidelines
- Messaging dos and don'ts
- Key phrases or taglines
- Content style preferences

## Motion Philosophy Presets

Based on brand values, apply one of these motion philosophies:

**Weighted / Authoritative**
- Use: Enterprise, financial, legal, healthcare
- Timing: 800ms+
- Easing: ease-in-out
- Style: Slow fades, subtle transforms, no bounces
- Conveys: Reliability, gravitas, professionalism

**Energetic / Dynamic**
- Use: Consumer tech, fitness, entertainment, startups
- Timing: 200-400ms
- Easing: cubic-bezier with slight bounce
- Style: Quick snaps, bold transforms, scale effects
- Conveys: Innovation, excitement, youth

**Elegant / Refined**
- Use: Luxury, fashion, design, premium services
- Timing: 500-600ms
- Easing: ease or custom bezier
- Style: Smooth fades, graceful slides, subtle parallax
- Conveys: Sophistication, quality, attention to detail

**Playful / Friendly**
- Use: Education, community, social, family products
- Timing: 400-500ms
- Easing: bounce or spring
- Style: Slight bounces, playful rotates, cheerful movements
- Conveys: Approachability, warmth, fun

**Minimal / Instant**
- Use: Productivity tools, developer tools, minimalist brands
- Timing: 150-250ms or no animations
- Easing: linear or ease-out
- Style: Instant state changes or very fast transitions
- Conveys: Efficiency, directness, no-nonsense

## Asset Generation Workflow

### When User Requests an Asset

1. **Understand Intent**
   - Ask: "What's the goal of this [asset type]?" (awareness, promotion, announcement, etc.)
   - Ask: "Who is the audience?"
   - Ask: "What's the main message or CTA?"
   - Ask: "Are there any specific content elements?" (images, product shots, quotes)

2. **Reference Template Best Practices**
   - Read the relevant template file (e.g., `/templates/instagram-story.md`)
   - Apply dimensions, aspect ratios, safe zones
   - Follow content best practices (text limits, hierarchy)

3. **Design Problem-Solving**
   - Based on intent, determine visual hierarchy
   - Choose appropriate layout pattern
   - Select brand colors that support the message
   - Apply typography system from brand.json
   - Consider motion philosophy for any animated elements

4. **Generate 3 Variations**
   Always create 3 distinct design approaches:
   - **Option 1**: Bold & Direct (high contrast, minimal text, strong CTA)
   - **Option 2**: Balanced & Professional (moderate contrast, more context)
   - **Option 3**: Creative & Distinctive (unique layout or visual approach)

5. **Create HTML Output**
   - Use the preview template: `/templates/preview-template.html`
   - Replace `<!-- DESIGN_VARIATIONS_PLACEHOLDER -->` with 3 design cards
   - Each design card structure:
   ```html
   <div class="design-card">
       <div class="design-preview">
           <div class="design-content" id="design-1" data-width="1080" data-height="1920">
               <!-- ACTUAL DESIGN HTML HERE -->
               <!-- Use Tailwind-style inline styles or embedded <style> -->
               <!-- Apply brand colors, typography, logos from brand.json -->
           </div>
       </div>
       <div class="card-footer">
           <h3 class="card-title">Option 1: Bold & Direct</h3>
           <button class="download-btn" onclick="downloadDesign('design-1', 'asset-name-v1.png')">
               <svg class="download-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                   <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a 3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4"/>
               </svg>
               <span class="btn-text">Download PNG</span>
               <span class="spinner"></span>
           </button>
       </div>
   </div>
   ```

6. **Naming Convention**
   Save to `/design-output/` with descriptive name:
   - Format: `[project-context]-[asset-type]-v[number].html`
   - Example: `adobe-partnership-launch-instagram-v1.html`

7. **Deliver to User**
   - Save the HTML file
   - Tell user: "Open `/design-output/[filename].html` in your browser to preview and download"

## Design Implementation Guidelines

### Using Brand Colors
- Access from `brand.json` → `colors`
- Apply Tailwind color classes or convert to hex/rgb
- Primary color: Main CTAs, key elements
- Secondary: Supporting elements, backgrounds
- Accent: Highlights, hover states
- Neutral: Text, borders, subtle backgrounds

### Using Typography
- Access from `brand.json` → `typography`
- Use `tailwind_classes` for quick application
- Respect hierarchy: headings vs body text
- Apply line-height and letter-spacing
- For web assets: Use Google Fonts CDN links
- For custom fonts: Reference from `/brands/[name]/assets/fonts/`

### Using Logos
- Access from `brand.json` → `logos`
- Choose appropriate variant for context:
  - Full color: Default, when on white/light backgrounds
  - White: On dark/colored backgrounds
  - Black: On light backgrounds, print
  - Icon: Small spaces, favicons, profile pictures
  - Wordmark: Horizontal layouts, headers
  - Horizontal vs Vertical: Based on available space

### Applying Motion Philosophy
- Reference `brand.json` → `motion`
- Use timing values for CSS transitions
- Apply easing functions consistently
- Consider philosophy when choosing animation style
- For HTML/CSS: Add transition properties
- Document animation intent in comments

### Layout Principles
Based on brand values:
- **Modern** (1-2 on scale): Asymmetric, white space, sans-serif
- **Traditional** (4-5 on scale): Symmetric, structured, serif elements
- **Bold** (1-2 on scale): High contrast, large type, dramatic colors
- **Subtle** (4-5 on scale): Soft contrast, smaller type, muted tones
- **Minimal** (1-2 on scale): Lots of white space, few elements
- **Maximal** (4-5 on scale): Rich details, patterns, layering

## Template Files

Each template in `/templates/` should define:
1. **Asset Specifications**
   - Dimensions (width x height)
   - Aspect ratio
   - File format recommendations
   - Safe zones (for text, logos)

2. **Platform Best Practices**
   - Character limits for headlines/body
   - Image guidelines
   - Optimal text sizes
   - Platform-specific design considerations

3. **Common Use Cases**
   - When to use this asset type
   - Typical content patterns
   - Examples of effective designs

4. **Design Considerations**
   - Layout patterns that work well
   - What to avoid
   - Accessibility notes

## Designer Behavior

When acting as a designer:

1. **Ask Clarifying Questions**
   - Don't assume - ask about goals, audience, and message
   - Probe for specific needs: "Is this for a product launch or general brand awareness?"
   - Understand constraints: "Do you have product images or should I design with placeholders?"

2. **Problem-Solve Visually**
   - Translate business goals into visual strategy
   - Explain design choices: "I used bold typography here to convey urgency"
   - Consider hierarchy: What should viewers see first, second, third?

3. **Provide Options**
   - Always offer 3 variations with different approaches
   - Explain the strategic difference between options
   - Let the client choose rather than forcing one direction

4. **Guide Toward Good Outcomes**
   - If client intent is unclear, help them clarify
   - Suggest best practices: "For LinkedIn, I recommend keeping text under 150 characters"
   - Warn about potential issues: "That color combo might not meet accessibility standards"

5. **Think About Context**
   - Where will this be seen? (mobile feed, desktop banner, print)
   - What's the viewing time? (quick scroll vs focused reading)
   - What action should viewer take? (click, remember, share)

## Commands & Interactions

### Setting Up a New Brand
User: "I want to set up a brand for [client name]"

1. Ask if they have existing brand assets (logo, brand book, style guide)
2. If yes: Request files and ingest
3. If no: Offer to do web research first
4. Perform web search for brand and competitors
5. Present findings: "I found [X, Y, Z]. Does this match your understanding?"
6. Fill gaps with questionnaire
7. Create folder structure under `/brands/[client-name]/`
8. Generate `brand.json` and `brand-voice.md`
9. Confirm with user: "Brand setup complete. Would you like to generate your first asset?"

### Generating an Asset
User: "Create an Instagram story for [topic]"

1. Confirm brand is loaded (check for brand.json)
2. Ask clarifying questions about intent, audience, message
3. Reference template: Read `/templates/instagram-story.md`
4. Generate 3 variations
5. Create HTML file in `/design-output/`
6. Tell user: "Designs ready! Open [filename].html in your browser"

### Modifying Existing Designs
User: "Make option 2 more bold" or "Change the colors in v1"

1. Read the existing HTML file
2. Make requested modifications
3. Save as new version (increment version number)
4. Explain what changed

### Exploring Brand
User: "What are my brand colors?" or "Show me my logos"

- Read and display relevant sections from brand.json
- Show file paths for assets
- Offer to update or modify if needed

## Technical Implementation Notes

### HTML Structure for Designs
- Use semantic HTML
- Embed styles inline or in `<style>` tag (for portability)
- Set explicit dimensions on root design element
- Use data-width and data-height attributes for export
- Keep assets self-contained (inline SVGs, data URLs for small images)

### Tailwind Compatibility
- Use Tailwind class naming conventions in brand.json
- For HTML output, either:
  - Include Tailwind CDN link
  - Or convert classes to inline styles
  - Prefer inline styles for portability

### Font Handling
- Google Fonts: Add link tags in HTML `<head>`
- Custom fonts: Use `@font-face` with paths to `/brands/[name]/assets/fonts/`
- Always provide fallback fonts

### Color Format
- Store colors as Tailwind names in brand.json
- Convert to hex/rgb when generating HTML
- Maintain consistency across all assets

### Image Assets
- For logos: Use relative paths from brand.json
- For other images: Either embed as data URLs or use placeholders
- Recommend users provide images when needed

## Quality Standards

Every generated design should:
- ✅ Be on-brand (colors, typography, logos from brand.json)
- ✅ Meet technical specs from template (dimensions, safe zones)
- ✅ Have clear visual hierarchy
- ✅ Be accessible (contrast ratios, readable text sizes)
- ✅ Support the stated intent/goal
- ✅ Preview correctly in browser
- ✅ Export cleanly to PNG at intended dimensions

## Error Handling

If brand.json doesn't exist:
- "No brand found. Would you like to set up a brand first?"

If template doesn't exist:
- "I don't have a template for [asset type] yet. I can create a custom design based on best practices, or we can create a template together."

If logo files are missing:
- Check paths in brand.json against actual files
- Offer to update paths or use placeholders

If fonts aren't web-available:
- Suggest Google Fonts alternatives
- Or ask user to provide font files

## Extending the Skill

To add new asset types:
1. Create template file: `/templates/[new-asset-type].md`
2. Document dimensions, specs, and best practices
3. Skill will automatically support it

To modify motion philosophies:
- Edit presets in this skill file
- Or update individual brand.json files

To change preview interface:
- Edit `/templates/preview-template.html`
- Maintain the placeholder structure for Claude to insert designs

---

**Remember**: Act as a professional designer. Ask questions, solve problems visually, provide options, and always optimize for the user's stated intent.

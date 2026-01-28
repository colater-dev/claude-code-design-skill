# Colater - Design Workflow Skill for Claude Code

A comprehensive design workflow skill that enables Claude Code to ingest brand identities and generate professional, brand-consistent visual assets.

## What is Colater?

Colater transforms Claude Code into a brand-aware design assistant that can:
- Ingest and understand brand identities (logos, colors, typography, values)
- Generate professional design assets (social media posts, banners, business cards, etc.)
- Create HTML-based designs with instant browser preview and PNG export
- Act as a professional designer by asking clarifying questions and problem-solving visually

## Quick Start

### 1. Set Up a Brand

Tell Claude Code to set up a brand:
```
"I want to set up a brand for [client name]"
```

Claude will:
- Search the web for existing brand information
- Ask you to provide assets (logos, brand book PDF)
- Guide you through a questionnaire for missing information
- Create a structured brand definition

### 2. Generate Assets

Once your brand is set up, request assets:
```
"Create an Instagram story announcing our new product launch"
```

Claude will:
- Ask clarifying questions about intent, audience, and message
- Generate 3 design variations
- Create an HTML file with preview and download buttons
- Save to `/design-output/`

### 3. Preview and Download

Open the generated HTML file in your browser to:
- View all 3 design variations
- Choose your favorite
- Download as PNG with one click

## Project Structure

```
colater/
├── .claude/
│   └── skills/
│       └── colater.md              # Main skill definition
├── brands/
│   └── [client-name]/
│       ├── brand.json              # Structured brand data
│       ├── brand-voice.md          # Voice, tone, messaging
│       └── assets/
│           ├── logos/              # Logo files (SVG, PNG)
│           └── fonts/              # Custom font files
├── templates/
│   ├── preview-template.html      # HTML template for asset preview
│   ├── instagram-story.md         # Instagram story specs & best practices
│   ├── linkedin-banner.md         # LinkedIn banner specs & best practices
│   ├── business-card.md           # Business card specs & best practices
│   └── email-signature.md         # Email signature specs & best practices
└── design-output/
    └── [asset-name-v1].html       # Generated designs
```

## Brand Definition Structure

### brand.json
Contains all visual brand elements:
- **Colors**: Tailwind-compatible color names and hex values
- **Typography**: Font families, weights, sizes, Tailwind classes
- **Logos**: Paths to different logo variants (full-color, black, white, icon, etc.)
- **Motion**: Animation philosophy, timing, easing functions
- **Values**: Brand personality scales (playful↔serious, bold↔subtle, etc.)
- **Guidelines**: Spacing, borders, shadows, logo usage rules

### brand-voice.md
Defines brand personality and messaging:
- Brand story and positioning
- Tone of voice guidelines
- Messaging framework
- Content dos and don'ts
- Writing style and vocabulary

## Supported Asset Types

Currently includes templates for:
- **Instagram Story** (1080x1920px) - Vertical social media content
- **LinkedIn Banner** (1584x396px) - Profile background image
- **Business Card** (3.5x2 inches) - Print and digital business cards
- **Email Signature** - HTML email signatures for various clients

More templates can be easily added to `/templates/`.

## How It Works

### 1. Brand Ingestion
When you set up a brand, Claude:
1. Performs web research on the brand and competitors
2. Ingests brand assets (logos, PDFs, style guides)
3. Extracts colors, fonts, values, and visual patterns
4. Fills gaps with guided questionnaire
5. Creates `brand.json` and `brand-voice.md`

### 2. Asset Generation
When you request an asset, Claude:
1. Asks clarifying questions (intent, audience, message)
2. References template specifications for that asset type
3. Applies brand colors, typography, and visual style
4. Generates 3 distinct design variations
5. Creates HTML with preview interface
6. Saves to `/design-output/`

### 3. Preview & Export
The generated HTML file:
- Displays all 3 variations in a gallery view
- Uses html2canvas for client-side PNG export
- Scales designs to fit preview area
- Exports at intended dimensions (e.g., 1080x1920 for Instagram)
- Works entirely in the browser - no server needed

## Design Philosophy

### Brand-First Approach
Every design decision is driven by the brand definition. Colors, typography, layout patterns, and motion all reflect the brand's personality and values.

### Designer Mindset
Claude acts as a professional designer by:
- Asking clarifying questions before designing
- Understanding the intent and optimizing for it
- Translating business goals into visual strategy
- Offering multiple approaches (3 variations)
- Explaining design choices

### Easy Validation
Rather than asking users to define everything upfront, Claude:
- Does research first and presents findings
- Uses scales and comparisons for brand values
- Shows competitor examples for context
- Makes it easy to agree/disagree vs. creating from scratch

## Customization

### Adding New Asset Types
1. Create a template file: `/templates/[new-asset-type].md`
2. Document dimensions, specs, and best practices
3. Include layout patterns and examples
4. Claude will automatically support it

### Modifying Motion Philosophies
Edit the motion philosophy presets in `.claude/skills/colater.md` or customize individual brands in their `brand.json` files.

### Changing Preview Interface
Edit `/templates/preview-template.html` to customize the gallery view, styling, or export functionality.

## Example Usage

### Setting Up a Brand from Scratch
```
User: "Set up a brand for my company, Acme Corp. We're a B2B fintech startup."

Claude:
- Searches web for Acme Corp information
- Asks for logo and brand assets
- Presents competitor analysis
- Guides through brand questionnaire
- Creates brand.json and brand-voice.md
```

### Generating a Social Media Post
```
User: "Create an Instagram story for our Q1 results"

Claude: "What's the main message? Are we highlighting revenue growth, user growth, or a specific metric?"
User: "Revenue - we hit $10M ARR"

Claude: "Great! Who's the primary audience?"
User: "Current customers and investors"

Claude: "Should the tone be celebratory or professional?"
User: "Professional but excited"

Claude: [Generates 3 variations]
- Option 1: Bold headline "$10M ARR" with minimal design
- Option 2: Balanced layout with supporting context
- Option 3: Graphic treatment with growth visualization
```

### Modifying Existing Designs
```
User: "Make option 2 more bold and change the primary color to the accent color"

Claude: [Reads existing HTML, makes changes, saves as v2]
```

## Technical Notes

### HTML Generation
- Uses inline CSS for maximum compatibility
- Sets explicit dimensions via data attributes
- Self-contained (embedded SVGs, inline styles)
- Works offline once loaded

### Font Handling
- Prefers Google Fonts for web compatibility
- Supports custom fonts in `/assets/fonts/`
- Always includes fallback fonts
- Provides `@font-face` declarations when needed

### Color Management
- Stores colors as Tailwind names in brand.json
- Includes hex values for HTML generation
- Maintains consistency across all assets
- Supports both light and dark modes

### Export Quality
- Generates at 2x scale for retina displays
- Exports at intended dimensions (not preview size)
- Uses PNG format with transparency support
- html2canvas handles cross-origin images with CORS

## Browser Compatibility

The preview interface works in:
- Chrome/Edge (Chromium)
- Firefox
- Safari
- Any modern browser with ES6 support

PNG export requires html2canvas, which is loaded from CDN.

## Limitations & Future Enhancements

### Current Limitations
- Preview requires manual browser opening (not automated)
- No batch export of all variations at once
- Limited to HTML/CSS designs (no native design file formats)
- Font support limited to Google Fonts or manually provided files

### Potential Enhancements
- Automated PNG export via Puppeteer/Playwright
- Support for video/animated content
- Integration with design tools (Figma, Sketch)
- Template marketplace or library
- Multi-page documents (presentations, reports)
- A/B testing recommendations

## Contributing

To extend this skill:
1. Add new templates in `/templates/` with full specifications
2. Update motion philosophies in skill definition if needed
3. Add example brands to demonstrate new use cases
4. Document any new workflow patterns

## Example Brand

The `/brands/example-tech-co/` folder contains a complete example brand setup demonstrating:
- Full brand.json with all properties
- Comprehensive brand-voice.md
- Example logo file structure
- Comments and explanations

Use this as a reference when setting up new brands.

---

**Colater**: Brand-driven design, powered by Claude Code.

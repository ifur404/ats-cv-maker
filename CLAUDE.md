# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

This is a benchmark project with multiple static HTML implementations. Common commands:

### Running the Applications
```bash
# Open navigation hub
open index.html

# Or serve via simple HTTP server for local development
python -m http.server 8000
# Then visit http://localhost:8000

# Direct access to implementations:
open claude.html          # Claude's implementation
open horizon-beta.html    # Indonesian localized version
```

### Testing Changes
```bash
# No automated tests configured
# Manual testing by opening respective HTML files in browser
```

## Project Overview

**ATS CV Maker Benchmark** is a comparison project showcasing different LLM approaches to building ATS-friendly resume creators.

### Core Files
- `index.html` - Navigation hub for accessing different implementations
- `claude.html` - Claude's ATS CV builder implementation 
- `horizon-beta.html` - Indonesian-localized comprehensive CV builder
- `README.md` - Project documentation and benchmarking details

### Implementation Comparison

#### Claude Implementation (`claude.html`)
- **Tech Stack**: Vanilla JavaScript with CSS custom properties
- **Design**: Professional dark theme with blue/purple gradients
- **Features**: Dynamic form management, real-time ATS scoring, PDF/TXT export
- **State Management**: Simple reactive object with event listeners
- **File Size**: ~50KB single HTML file

#### Horizon Beta Implementation (`horizon-beta.html`) 
- **Tech Stack**: Vanilla JavaScript with embedded styles
- **Design**: Dark theme with cyan/purple gradients + procedural avatars
- **Features**: Indonesian localization, localStorage persistence, keyword suggestions
- **State Management**: State object with localStorage auto-save
- **File Size**: ~35KB single HTML file

### State Management Examples

#### Claude Implementation:
```javascript
let cvData = {
  personal: { fullName, jobTitle, email, phone, location, linkedin, summary, skills },
  experience: [{ id, company, position, startDate, endDate, description }],
  education: [{ id, school, degree, startDate, endDate, details }]
}
```

#### Horizon Beta Implementation:
```javascript
const state = {
  name, headline, email, phone, location, linkedin, website, summary,
  exp: [{ company, role, location, start, end, points[], tech[] }],
  edu: [{ school, degree, location, start, end, detail }],
  skills: [{ name, level }],
  ach: [{ title, year }]
}
```

### Key Functions by Implementation

#### Claude Implementation (`claude.html:522-1001`)
- `init()` - Initialize application with event listeners
- `updatePreview()` - Updates CV preview from state
- `calculateATSScore()` - Calculates ATS compatibility score (0-100)
- `addExperience()` / `addEducation()` - Dynamic form management
- `exportPDF()` / `exportText()` - Export functionality
- `loadSample()` - Loads sample data for demo

#### Horizon Beta Implementation (`horizon-beta.html:388-902`)
- `render()` - Updates CV preview from state
- `rebuildLists()` - Rebuilds form input lists
- `scoring()` - Calculates ATS compatibility score
- `toPlainText()` - Generates text export
- `drawAvatar()` - Creates procedural avatar on canvas

### Form Management Patterns

#### Claude Approach:
Dynamic form sections with unique IDs:
- `addExperience()` - Creates form with timestamp-based ID
- `updateExperience(id, field, value)` - Updates specific field
- `removeExperience(id)` - Removes form and updates state

#### Horizon Beta Approach:
Factory functions with index-based management:
- `expRow(data, index)` - Experience entry forms
- `eduRow(data, index)` - Education entry forms  
- `skillRow(data, index)` - Skills entry forms

### ATS Scoring Systems

Both implementations feature real-time ATS scoring but with different approaches:

#### Claude Scoring Logic:
- Personal info (45 points): name, email, phone, job title, summary
- Experience quality (30 points): valid entries, detailed descriptions
- Education (10 points): degree and institution
- Skills (15 points): skill count and relevance

#### Horizon Beta Scoring Logic:
- Core fields completion with keyword matching
- Industry-specific skill recommendations
- Content quality metrics (word count, bullet points)
- Professional formatting compliance

### Design System Comparison

#### Claude Color Scheme:
```css
:root {
  --bg-primary: #1a1d2e;    /* Background */
  --bg-secondary: #242740;  /* Panel background */
  --text-primary: #ffffff;  /* Primary text */
  --accent-blue: #4a9eff;   /* Primary accent */
  --accent-purple: #b866f5; /* Secondary accent */
}
```

#### Horizon Beta Color Scheme:
```css
:root {
  --bg: #0f1220;        /* Background */
  --panel: #161a2e;     /* Panel background */
  --text: #e7ebff;      /* Primary text */
  --accent: #6ad3ff;    /* Primary accent */
  --accent-2: #a96aff;  /* Secondary accent */
}
```

### Export Features Comparison

#### Claude Implementation:
- **PDF Export**: Browser print API with `@media print` styles
- **ATS Text Export**: Plain text format optimized for ATS parsing
- **No Persistence**: Session-based data only

#### Horizon Beta Implementation:
- **PDF Export**: Browser print with optimized CV layout
- **ATS Text Export**: Structured plain text with proper formatting
- **localStorage**: Automatic persistence with `persist()` function

### Responsive Design Patterns

Both implementations use similar responsive approaches:
- **Desktop**: Two-column layout (form + preview)
- **Mobile**: Single column with stacked sections 
- **Print**: Clean CV layout with hidden form elements
- **Grid Systems**: CSS Grid for layout, Flexbox for components

## Development Notes

### Code Style
- Uses modern JavaScript (ES6+, template literals, arrow functions)
- Embedded CSS with utility classes and component patterns
- Event delegation and functional programming patterns

### Performance Optimizations
- Single HTML file reduces HTTP requests
- Embedded styles and scripts eliminate render blocking
- Procedural avatar generation (no external images)
- Efficient DOM updates with targeted rendering

### Browser Support
- Modern browsers supporting ES6+ features
- Canvas API for avatar generation
- CSS Grid and Flexbox for layouts
- localStorage for persistence
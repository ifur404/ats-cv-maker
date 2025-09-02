# ATS CV Maker - LLM Benchmark Project

A comprehensive benchmark project showcasing different LLM implementations for creating ATS-friendly CV/resume builders. This project demonstrates how various Large Language Models approach the same problem: building a user-friendly, ATS-optimized resume creation tool.

## 🎯 Project Overview

This benchmark compares LLM-generated implementations of an ATS (Applicant Tracking System) friendly CV maker. Each implementation showcases different approaches, design patterns, and user experience decisions while solving the same core problem.

### Core Features
- **ATS Optimization**: Real-time scoring and keyword matching
- **Export Options**: PDF and plain text formats
- **Responsive Design**: Mobile and desktop optimized
- **Data Persistence**: Local storage for user data
- **Real-time Preview**: Live CV preview as you type
- **Professional Templates**: Clean, ATS-scannable layouts

## 🚀 Live Implementations

### [📄 Navigation Hub](index.html)
Central navigation page to explore all implementations.

### [🤖 Claude Implementation](claude.html)
**Model**: Claude (Anthropic)
- **Approach**: Clean, modern UI with real-time ATS scoring
- **Features**: Dynamic form management, professional CV preview, PDF/TXT export
- **Design**: Professional dark theme with blue/purple accent colors

### [🌅 Horizon Beta Implementation](horizon-beta.html)
**Model**: Indonesian-Optimized Version
- **Approach**: Comprehensive Indonesian-language CV builder
- **Features**: Localized content, advanced scoring system, keyword suggestions
- **Design**: Dark theme with cyan/purple gradients and procedural avatar generation

## 🏗️ Architecture Comparison

| Feature | Claude | Horizon Beta |
|---------|--------|--------------|
| **Tech Stack** | Vanilla JS/HTML/CSS | Vanilla JS/HTML/CSS |
| **State Management** | Reactive object with event listeners | Simple state object with localStorage |
| **Styling Approach** | CSS Custom Properties (blue/purple) | CSS Custom Properties (cyan/purple) |
| **Export Method** | Browser Print API + Text download | Browser Print API + Text download |
| **Storage** | No persistence | localStorage with auto-save |
| **Bundle Size** | Single HTML file (~50KB) | Single HTML file (~35KB) |

## 📊 Benchmark Criteria

### 1. **User Experience**
- Form usability and intuitive design
- Real-time feedback and validation
- Export quality and options
- Mobile responsiveness

### 2. **Technical Implementation**
- Code organization and maintainability
- Performance optimization
- Browser compatibility
- Bundle size and loading speed

### 3. **ATS Optimization**
- Keyword analysis accuracy
- Format compatibility with ATS systems
- Scoring algorithm effectiveness
- Export format quality

### 4. **Feature Completeness**
- Required field coverage
- Advanced features (skills suggestions, templates)
- Data persistence and import/export
- Error handling and edge cases

## 🚀 Getting Started

### Prerequisites
- Modern web browser (Chrome 80+, Firefox 75+, Safari 13+)
- No additional dependencies required

### Running Locally

```bash
# Clone the repository
git clone [repository-url]
cd ats-cv-maker

# Option 1: Open directly in browser
open index.html

# Option 2: Serve with local HTTP server
python -m http.server 8000
# Navigate to http://localhost:8000
```

### Testing Individual Implementations

```bash
# Claude implementation
open claude.html

# Horizon Beta implementation  
open horizon-beta.html
```

## 📁 Project Structure

```
ats-cv-maker/
├── index.html          # Navigation hub
├── claude.html         # Claude's implementation
├── horizon-beta.html   # Horizon Beta's implementation
├── README.md           # This file
└── CLAUDE.md          # Claude Code development guide
```

## 🔍 Implementation Details

### Claude Implementation
- **File Size**: ~35KB (single file)
- **Dependencies**: None (vanilla JavaScript)
- **Key Features**:
  - Procedural avatar generation
  - Real-time ATS scoring (0-100)
  - Industry-specific keyword suggestions
  - Dark theme with professional gradients
  - Responsive grid layout

### Horizon Beta Implementation
*[Details to be added after implementation]*

## 🧪 Benchmark Results

### Performance Metrics
| Implementation | Load Time | Bundle Size | Language | Mobile Optimized |
|---------------|-----------|-------------|----------|------------------|
| Claude        | ~200ms    | 50KB        | English  | ✅               |
| Horizon Beta  | ~250ms    | 35KB        | Indonesian | ✅             |

### Feature Comparison
| Feature | Claude | Horizon Beta |
|---------|--------|--------------|
| Real-time ATS Scoring | ✅ (0-100 scale) | ✅ (0-100 scale) |
| Keyword Suggestions | ❌ | ✅ (Industry-based) |
| Export Formats | ✅ (PDF, TXT) | ✅ (PDF, TXT) |
| Data Persistence | ❌ | ✅ (localStorage) |
| Responsive Design | ✅ | ✅ |
| Procedural Avatar | ❌ | ✅ (Canvas-based) |
| Sample Data Loader | ✅ | ✅ |
| Dynamic Form Lists | ✅ (Add/Remove items) | ✅ (Add/Remove/Reorder) |
| Form Validation | ✅ | ✅ |

## 🎨 Design Philosophy Comparison

### Claude's Approach
- **Theme**: Professional dark mode with blue/purple gradients
- **Layout**: Two-column desktop, single-column mobile
- **Interaction**: Real-time updates with dynamic form management
- **Typography**: System fonts with clean hierarchy
- **UX Focus**: Simplicity and clarity with immediate feedback

### Horizon Beta's Approach
- **Theme**: Dark mode with cyan/purple gradients and procedural avatars
- **Layout**: Two-column responsive grid with professional preview
- **Interaction**: Real-time updates with data persistence
- **Typography**: Inter/system fonts with professional styling
- **UX Focus**: Comprehensive features with Indonesian localization

## 🚀 Future Enhancements

- [ ] Add more LLM implementations (GPT-4, Gemini, etc.)
- [ ] Automated performance benchmarking
- [ ] A/B testing framework for UX comparison  
- [ ] Export quality analysis tools
- [ ] Real ATS system testing integration
- [ ] User feedback collection system

## 📄 License

This project is for educational and benchmark purposes. Individual implementations may have different licensing considerations based on their respective LLM providers.

## 🤝 Contributing

This is a benchmark project. To add new LLM implementations:

1. Create a new HTML file named `[model-name].html`
2. Implement the ATS CV maker functionality
3. Update this README with implementation details
4. Add navigation link in `index.html`

## 📊 Methodology

Each LLM implementation is generated using:
1. **Same Core Prompt**: Identical functional requirements
2. **Independent Generation**: No cross-contamination between implementations  
3. **Fair Comparison**: Same testing criteria and metrics
4. **Documentation**: Detailed analysis of approach and decisions

---

**Note**: This benchmark aims to provide objective comparison of LLM capabilities in web development tasks, specifically focusing on user experience design, technical implementation quality, and problem-solving approaches.
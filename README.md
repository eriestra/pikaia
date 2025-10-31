# Pikaia

<div align="center">

**Transform specifications into working applications using AI**

A zero-dependency, single-file tool that bridges the gap between idea and implementation

[Get Started](#quick-start) • [Features](#features) • [Examples](#example-specification) • [Documentation](#how-it-works)

</div>

---

## What is Pikaia?

Pikaia is an AI-powered development companion that generates fully functional web applications from plain English descriptions. No setup, no framework knowledge, no dependencies—just open a file in your browser and start creating.

### Why Pikaia?

- 🚀 **Instant Prototyping**: Go from idea to working app in seconds
- 🔄 **Iterative Development**: Refine with natural language feedback
- 📦 **Zero Setup**: Single HTML file, runs entirely in your browser
- 🎨 **Visual + Code**: Switch between preview and source code instantly
- 🔍 **Reverse Engineering**: Extract specs from existing HTML apps
- 💾 **Auto-Save**: Never lose your work
- 🔒 **Privacy First**: All data stays local, API calls only for generation

## Features

| Feature | Description |
|---------|-------------|
| **Spec-to-App Generation** | Write markdown specs, get complete HTML/CSS/JS apps |
| **Live Preview** | See your application render in real-time with tabbed interface |
| **Source Code View** | Inspect and learn from the generated code |
| **Natural Language Refinement** | Improve your app by describing what you want changed |
| **Reverse Engineering** | Extract specifications from existing HTML applications |
| **Multi-Model Support** | Choose from GPT-4, Claude, Gemini, and more |
| **Export Functionality** | Download generated apps as standalone HTML files |
| **Persistent Storage** | Auto-save to localStorage with no server required |

## Quick Start

### 1. Get an API Key
Sign up at [OpenRouter](https://openrouter.ai) and copy your API key

### 2. Launch Pikaia
```bash
# Option 1: Download and open
curl -O https://raw.githubusercontent.com/eriestra/pikaia/main/index.html
open index.html

# Option 2: Clone the repo
git clone https://github.com/eriestra/pikaia.git
cd pikaia
open index.html
```

### 3. Start Creating
1. Write your app specification in the left panel
2. Click **Render App** to generate the application
3. View live preview or inspect source code in the right panel
4. Refine with feedback and iterate

## How It Works

### The Workflow

```
Write Spec → Render → Feedback → Refine
```

1. **Write Spec**: Describe your app using a structured markdown format
2. **Render**: Generate a working HTML application from your specification
3. **Feedback**: Provide natural language feedback on what to improve
4. **Refine**: Update the specification based on your feedback

### Specification Format

Pikaia uses a simple markdown structure with three main sections:

```markdown
# App Name

## Interface
- List your UI components and layout

## Behavior
- Describe how the app should work
- Define user interactions

## Style
- Specify colors, fonts, and visual design
- Define layout patterns
```

### Example Specification

```markdown
# My Calculator

## Interface
- Display showing current number (large, centered)
- Number buttons 0-9 in a grid
- Operation buttons: +, -, ×, ÷
- Equals button and Clear button
- All buttons should be large and easy to tap

## Behavior
- Clicking numbers appends to display
- Clicking operation stores the first number
- Clicking equals calculates and shows result
- Clear button resets to 0
- Support keyboard input

## Style
- Modern, minimal design
- Purple gradient background
- Dark theme with white text
- Grid layout for buttons
- Rounded corners
- Box shadows for depth
```

## User Interface

Pikaia features a clean, GitHub-inspired dark interface with two main panels:

### Left Panel: Specification Editor
- **Markdown Editor**: Write your app specs in structured markdown
- **Render App Button**: Generate your application with one click
- **Feedback Input**: Describe changes in natural language
- **Refine Button**: Update your spec based on feedback
- **Auto-Save Indicator**: Real-time save status

### Right Panel: Live Preview
- **Extract Spec Button**: Reverse-engineer specs from rendered apps
- **Preview Tab**: See your application running live
- **Source Code Tab**: View and learn from generated HTML/CSS/JS
- **Export Button**: Download as standalone HTML file

### Toolbar
- **Model Selector**: Choose from multiple AI models (GPT-4, Claude, Gemini, etc.)
- **API Key Manager**: Securely configure your OpenRouter API key
- **Save Indicator**: Visual feedback for auto-save status

## Configuration

### API Key Setup

**Option 1: UI Configuration (Recommended)**
1. Click the "API Key" button in the toolbar
2. Enter your OpenRouter API key in the modal
3. Click "Save Key" - it's stored securely in your browser's localStorage

**Option 2: In-File Configuration**
Edit the JavaScript in `index.html`:
```javascript
const OPENROUTER_API_KEY = 'YOUR_OPENROUTER_API_KEY_HERE';
```

### Model Selection

Pikaia supports multiple AI models via the dropdown selector:

- **GPT-OSS-120B** (default) - Fast, cost-effective
- **Claude 3.5 Sonnet** - Excellent code quality
- **GPT-4 Turbo** - Most capable
- **Gemini Pro** - Good balance

Switch models anytime via the toolbar dropdown. Your selection is saved automatically.

## Technical Details

### Technologies Used
- Vanilla JavaScript (no frameworks)
- OpenRouter API for LLM access
- LocalStorage for persistence
- CSS Grid for responsive layout
- IFrame sandboxing for preview

### Browser Compatibility
- Chrome/Edge (recommended)
- Firefox
- Safari
- Any modern browser with ES6+ support

### Data Storage
All data is stored locally in your browser's localStorage:
- `pikaia_spec`: Your current specification
- `pikaia_html`: Generated HTML application
- `pikaia_openrouter_key`: Your API key (if entered at runtime)
- `pikaia_model`: Your selected AI model

No data is transmitted to any server except OpenRouter API calls for generation.

## Use Cases

### Rapid Prototyping
Quickly generate working prototypes from written descriptions without manual coding.

### Learning Tool
See how specifications translate into actual code, useful for understanding web development patterns.

### Design Exploration
Experiment with different UI/UX approaches by iterating on specifications.

### Documentation
Generate specifications from existing applications for documentation purposes.

## Limitations

- Single-file applications only (no multi-page apps)
- Limited to what can be expressed in a single HTML file
- Requires internet connection for LLM API calls
- Quality depends on specification clarity and LLM capabilities

## Security Notes

- API keys are stored in browser localStorage (client-side only)
- Generated apps run in sandboxed iframes
- No server-side storage or data transmission beyond API calls
- Review generated code before using in production

## Tips & Best Practices

### Writing Effective Specifications

1. **Be Specific**: Describe UI components, behaviors, and styling in detail
2. **Use Structure**: Organize specs into Interface, Behavior, and Style sections
3. **Iterate**: Start simple, then refine with feedback
4. **Learn from Output**: Switch to Source Code tab to see how specs translate to code

### Optimizing Results

- **Choose the right model**: Claude for code quality, GPT-4 for complexity, GPT-OSS for speed
- **Provide examples**: Reference specific UI patterns or existing apps
- **Test incrementally**: Render often to catch issues early
- **Use Extract Spec**: Learn from working apps by reverse-engineering their specs

## Troubleshooting

| Issue | Solution |
|-------|----------|
| API key errors | Verify your OpenRouter API key and account has credits |
| Slow generation | Try GPT-OSS-120B or Gemini Pro for faster responses |
| Poor results | Add more detail to your specification, try different models |
| Lost work | Check localStorage, specs auto-save every second |
| Export not working | Ensure app has been rendered before exporting |

## Contributing

Pikaia is open source and welcomes contributions!

**Priority Areas:**
- Template library and starter specs
- Multi-file/component support
- Syntax highlighting for source code view
- Spec version history
- Collaborative features

## License

MIT License - See LICENSE file for details

## Credits

**Built by:** [Ernesto Riestra](https://github.com/eriestra) / Yeira Inc. / Sync Magic 

**Powered by:**
- [OpenRouter](https://openrouter.ai) - Unified LLM API access
- Modern web standards and browser APIs

**Named after:** *Pikaia gracilens*, one of the earliest known chordates, symbolizing the evolution from simple specifications to complex applications.

## Support

- 🐛 **Report Issues**: [GitHub Issues](https://github.com/eriestra/pikaia/issues)
- 💬 **Discussions**: [GitHub Discussions](https://github.com/eriestra/pikaia/discussions)
- ⭐ **Star us on GitHub** if you find Pikaia useful!

---

<div align="center">

**[⬆ Back to Top](#pikaia)**

Made with ❤️ for developers who dream in specifications

</div>

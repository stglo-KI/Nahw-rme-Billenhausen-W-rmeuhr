# AGENTS.md - Nahwärme Billenhausen Wärmemengen Dashboard

## Project Overview

This is a **static HTML/CSS/JS website** for displaying and managing district heating meter readings. It uses:
- Plain HTML5, CSS3, JavaScript (ES6+)
- Chart.js for data visualization
- LocalStorage for data persistence

## Repository

- **GitHub:** https://github.com/stglo-KI/Nahw-rme-Billenhausen-W-rmeuhr
- **Version:** v0.1-beta

## Project Structure

```
Nahwärme/
├── Nahwärme Wärmemengen.html   # Entry point (redirects to Datenbank/)
└── Datenbank/
    ├── index.html              # Main dashboard application
    ├── data.json               # Data storage (JSON format)
    └── Nahwarme Logo-final_weiss-806e5840.webp  # Logo
```

## Features

- Zählerstand erfassen (aktuell oder rückwirkend)
- Automatische Verbrauchsberechnung (Differenz zum vorherigen Wert)
- Monatlicher und jährlicher Verbrauch
- CSV-Export
- Datenbank-Import/Export
- Inline-Bearbeitung in der Tabelle
- Chart.js Visualisierungen

## Build / Development Commands

Since this is a **static HTML project**, there are no build commands required.

### Running the Application

Simply open `Nahwärme Wärmemengen.html` in a web browser. For loading external JSON data, use a local server:

```bash
# Python 3
python3 -m http.server 8000

# Then open http://localhost:8000/Nahwärme Wärmemengen.html
```

### Git Commands

```bash
# Clone repository
git clone https://github.com/stglo-KI/Nahw-rme-Billenhausen-W-rmeuhr.git

# Create a new version tag
git tag -a v0.2-beta -m "Beta version 2"
git push --tags

# Commit and push changes
git add -A
git commit -m "Your changes"
git push
```

### No Tests

This project does not have automated tests.

---

## Code Style Guidelines

### General Principles

- **Keep it simple** - This is a vanilla HTML/CSS/JS project
- **No frameworks** - Use plain JavaScript, no React/Vue/etc.
- **Responsive design** - Ensure works on mobile and desktop

### HTML Guidelines

- Use semantic HTML5 elements (`<header>`, `<main>`, `<section>`, `<table>`, etc.)
- Use lowercase for tags and attributes
- Quote attribute values
- Indent with 4 spaces

### CSS Guidelines

- Use CSS custom properties (variables) for colors
- Follow the color scheme:
  - Primary: `#FFD700` (Gold)
  - Secondary: `#DAA520` (Dark Goldenrod)
  - Accent: `#228B22` (Forest Green)
  - Background: Dark greens
- Use `rem` for font sizes, `px` for borders/shadows
- Group related styles together
- Use flexbox and grid for layouts

### JavaScript Guidelines

- Use **ES6+** features (const/let, arrow functions, template literals)
- Use meaningful variable and function names in German or English
- Add comments for complex logic
- Handle errors gracefully with try/catch
- Use localStorage for data persistence
- Keep functions small and focused

### Naming Conventions

| Type | Convention | Example |
|------|------------|---------|
| Functions | camelCase | `addCurrentEntry()` |
| Variables | camelCase | `zaehlerstand`, `monthlyData` |
| Constants | UPPER_SNAKE_CASE | `STORAGE_KEY` |
| CSS Classes | kebab-case | `.btn-primary`, `.stat-card` |

### Data Format (JSON)

```json
[
  {
    "id": "unique-id",
    "timestamp": "2024-01-15T14:30:00.000Z",
    "zaehlerstand": 12500.5
  }
]
```

- `id`: Unique identifier (generated)
- `timestamp`: ISO 8601 format
- `zaehlerstand`: Meter reading in kWh

### Error Handling

- Always validate user input before processing
- Show user-friendly error messages with `alert()` or custom notifications
- Wrap async operations in try/catch blocks
- Log errors to console for debugging

### File Organization

1. **HTML**: Structure → Styles → Scripts
2. **CSS**: Variables → Base → Components → Animations → Responsive
3. **JS**: Constants → State → Functions → Event Handlers → Initialization

---

## Browser Support

- Modern browsers (Chrome, Firefox, Safari, Edge - latest 2 versions)
- Requires JavaScript enabled

---

## Deployment

This is a static site - can be deployed to any web hosting:
- GitHub Pages
- Netlify
- Vercel
- Any standard web server

Simply upload all files to the web root.

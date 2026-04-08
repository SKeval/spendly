# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
# Install dependencies (use a virtual environment)
pip install -r requirements.txt

# Run the development server (port 5001)
python app.py

# Run tests
pytest
```

## Architecture

**Spendly** is a Flask expense-tracking web app using server-side rendering with Jinja2 templates.

- `app.py` — all routes defined here; returns rendered templates or plain strings for stubs
- `database/db.py` — database module stub; not yet implemented
- `templates/` — Jinja2 templates; all extend `base.html`
- `static/css/style.css` — all styling via CSS custom properties (ink/paper/accent color system)
- `static/js/main.js` — placeholder, currently empty

### Routing pattern

Routes are grouped in `app.py` into implemented routes (render templates) and placeholder routes (return plain strings). Placeholder routes are labeled with their implementation step (Step 3–9). When implementing a placeholder, replace the string return with proper logic and a `render_template()` call.

### Development phases

The project is built in explicit steps:
1. Project setup (done)
2. Database init — `db.py` stub
3. Auth (register/login/logout with sessions)
4. Profile page
5–6. Expense listing/dashboard
7–9. Expense CRUD (add/edit/delete)

Database will use SQLite (`expense_tracker.db`, gitignored). Flask sessions will handle auth.

### CSS design system

Custom properties defined at `:root` in `style.css`: `--ink`, `--paper`, `--accent`, `--warn`, `--danger`. Typography uses DM Serif Display (headings) and DM Sans (body) from Google Fonts. Target currency is Indian Rupees (₹).

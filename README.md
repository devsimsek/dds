# Database Diagram Studio (DDS)

A lightweight, browser-based database diagram tool that lets you visually design and document database schemas — no installation required.

**Live Demo:** [https://devsimsek.github.io/dds](https://devsimsek.github.io/dds)

## Features

- Create and manage database tables visually
- Define columns with types and constraints
- Draw relationships between tables
- Export diagrams as PNG, PDF, DBML, MySQL SQL, or PostgreSQL SQL
- **Auto-save to localStorage** — your work is automatically saved in the browser and restored on next visit
- **Open files** — import existing `.dbml` files or `.sql` files (MySQL / PostgreSQL `CREATE TABLE` statements) directly into the editor
- Runs entirely in the browser — no backend needed

## Usage

Open the live demo or clone the repository and open `index.html` in your browser.

```bash
git clone https://github.com/devsimsek/dds.git
cd dds
open index.html
```

## Toolbar Reference

| Button | Action |
|--------|--------|
| ☐ New | Clear the current diagram (prompts for confirmation) |
| 📄 Load Example | Load the built-in e-commerce example schema |
| 📂 Open File | Open a `.dbml` or `.sql` file from your computer |
| PNG / PDF | Export the diagram as an image or document |
| DBML | Download the current schema as a `.dbml` file |
| MySQL / PostgreSQL | Generate and download SQL DDL |
| ⊞ Auto Layout | Automatically arrange table cards |
| ⤢ Fit | Zoom to fit all tables on screen |
| ☀ Theme | Cycle between Auto / Dark / Light themes |
| ⊹ Grid | Toggle grid snapping (also `G` key) |

## SQL File Import

DDS can parse `.sql` files containing `CREATE TABLE` statements and convert them to DBML automatically. Supported dialects:

- **MySQL** — handles `AUTO_INCREMENT`, backtick-quoted identifiers, `ENGINE=InnoDB`, etc.
- **PostgreSQL** — handles `SERIAL`/`BIGSERIAL`, double-quoted identifiers, `BYTEA`, `JSONB`, `TIMESTAMPTZ`, etc.

Foreign keys defined inline (`REFERENCES`) or via `ALTER TABLE … ADD FOREIGN KEY` are imported as `ref:` attributes.

## Auto-Save

The editor content is automatically saved to `localStorage` under the key `dds-workspace` after every change (with an 800 ms debounce). A **● Saved** indicator appears briefly in the bottom-right status bar after each save. On next page load the saved schema is restored automatically. Clicking **New** clears the saved workspace.

## Development

This project was developed with the assistance of **Claude Sonnet 4.6** by Anthropic.

## License

MIT License — see [LICENSE](LICENSE) or [devsimsek.mit-license.org](https://devsimsek.mit-license.org) for details.

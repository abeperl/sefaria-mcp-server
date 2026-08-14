

# Sefaria MCP Server

[![npm version](https://img.shields.io/npm/v/sefaria-mcp-server.svg)](https://www.npmjs.com/package/sefaria-mcp-server)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Un servidor MCP (Model Context Protocol) que proporciona acceso a la biblioteca de textos judíos de [Sefaria](https://www.sefaria.org): Torá, Talmud, Mishná, Midrash y miles de comentarios.

Utilice este servidor para dar a Claude, Cursor, Windsurf o cualquier asistente de IA compatible con MCP la capacidad de buscar, leer y explorar textos judíos.

## Características

- 📖 **Lee cualquier texto** - Torá, Talmud, Mishná, Midrash, Halajá, Cabalá
- 🔍 **Búsqueda completa** - Busque en todos los textos en inglés o hebreo
- 📚 **Obtén comentarios** - Rashí, Rambán, Ibn Ezra y cientos más
- 📅 **Aprendizaje diario** - Daf Yomi, Parsha, Rambam diario y más
- 🔗 **Referencias cruzadas** - Encuentre conexiones entre textos

## Instalación

```bash
npm install -g sefaria-mcp-server
```

O ejecútelo directamente con npx:

```bash
npx sefaria-mcp-server
```

El binario CLI instalado también está disponible como `sefaria-mcp`:

```bash
npx -y -p sefaria-mcp-server sefaria-mcp
```

## Configuración

No se requiere clave API. El servidor utiliza la API pública de Sefaria.

### Claude Desktop

Agregue esto a `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS) o `%AppData%\Claude\claude_desktop_config.json` (Windows):

```json
{
  "mcpServers": {
    "sefaria": {
      "command": "npx",
      "args": ["-y", "sefaria-mcp-server"]
    }
  }
}
```

### Cursor

Agregue esto a `.cursor/mcp.json` en su proyecto:

```json
{
  "mcpServers": {
    "sefaria": {
      "command": "npx",
      "args": ["-y", "sefaria-mcp-server"]
    }
  }
}
```

## Herramientas

### get_text

Obtenga el texto por referencia con hebreo e inglés.

```
Reference formats:
- Torah: "Genesis 1:1", "Exodus 20:1-10"
- Talmud: "Berakhot 2a", "Shabbat 31a"
- Mishnah: "Mishnah Avot 1:1"
- Midrash: "Genesis Rabbah 1:1"
- Commentary: "Rashi on Genesis 1:1"
```

### search

Búsqueda completa en todos los textos.

```
Examples:
- "love your neighbor"
- "tikkun olam"
- "ואהבת לרעך כמוך"
```

### get_links

Obtenga comentarios y referencias cruzadas para un versículo.

### get_parsha

Obtenga la porción de la Torá de esta semana.

### get_calendars

Obtenga el cronograma de estudio de hoy (Daf Yomi, Parsha, Rambam diario, etc.).

### get_book_info

Obtenga metadatos sobre un libro (estructura, categorías).

### get_related

Obtenga temas relacionados y hojas de fuentes de la comunidad.

## Ejemplos

Pregunte a Claude:

> "¿Qué dice Génesis 1:1? Muéstrame el hebreo y los comentarios."

> "Busca textos sobre amar a tu prójimo"

> "¿Cuál es la parsha de esta semana?"

> "¿Cuál es el Daf Yomi de hoy?"

> "Encuentra todos los comentarios sobre Levítico 19:18"

## Desarrollo

```bash
git clone https://github.com/abeperl/sefaria-mcp-server
cd sefaria-mcp-server
npm install
npm run build
npm start
```

## Créditos

- Impulsado por [Sefaria](https://www.sefaria.org): la biblioteca gratuita y de código abierto de textos judíos
- Construido con el SDK de [Model Context Protocol](https://modelcontextprotocol.io)

## Licencia

MIT

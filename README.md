# doodle

A collaborative whiteboard with a hand-drawn feel, built from scratch.

**Live:** https://doodle.souvick.tech

---

## Features

### Drawing

- Selection (move, resize, delete)
- Hand tool (pan)
- Rectangle
- Diamond
- Circle
- Arrow
- Line
- Pen
- Text
- Eraser

Tool lock lets you keep drawing with the same tool until you switch.

### Styling

- Stroke & fill colors
- Stroke width
- Solid & dotted strokes
- Solid, hachure and cross-hatch fills
- Corner radius
- Opacity
- Multiple fonts and text sizes

### Collaboration

- Create a room and share it with a link
- Real-time collaboration over WebSockets
- Live cursors
- Event-based synchronization

### Other

- Light & dark mode
- Local canvas persistence
- Responsive for desktop and mobile

---

## Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | React, TypeScript, Tailwind CSS |
| Build Tool | Vite |
| State Management | Zustand |
| Routing | React Router |
| Validation | Zod |
| Rendering | HTML Canvas |
| Realtime | WebSockets |

---

## Architecture

```
React UI
     │
     ▼
CanvasManager
 ├── ShapeManager
 ├── ToolManager
 └── Collaboration
```

Shape updates are stored as events. During collaboration, those events are synced over WebSockets so every participant stays in sync.

---

## Getting Started

### Clone

```bash
git clone https://github.com/Souvick-bh/doodle.git
cd doodle
```

### Install

```bash
npm install
```

### Run

```bash
npm run dev
```

Open http://localhost:5173.

---

## Environment Variables

```env
VITE_BACKEND_WEBSOCKET_URL=ws://localhost:3001
```

The app works without a backend for local drawing. This variable is only needed for real-time collaboration.

---

## Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server |
| `npm run build` | Build for production |
| `npm run preview` | Preview production build |
| `npm run lint` | Run ESLint |

---

## Project Structure

```
src/
├── classes/
│   ├── Shapes/
│   ├── Tools/
│   ├── Managers/
│   └── feature/Collab/
├── components/
├── hooks/
├── store/
├── types/
└── utils/
```

---

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Delete` / `Backspace` | Delete selected shapes |

---

## Roadmap

- [ ] More shapes
- [ ] Image support
- [ ] Undo / Redo improvements
- [ ] Export to PNG / SVG / JSON
- [ ] Better mobile gestures
- [ ] Multiplayer improvements

---

## Credits

Inspired by Excalidraw. Built to understand how collaborative whiteboards work under the hood.
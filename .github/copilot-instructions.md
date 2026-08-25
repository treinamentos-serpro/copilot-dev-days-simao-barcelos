# Copilot Workspace Instructions

## Project Overview

**SocOps** is a Social Bingo game built with Blazor WebAssembly (.NET 10). Players find people at mixers who match questions to mark squares and get 5 in a row to win. This is a workshop project demonstrating Copilot integration with multi-agent development workflows.

- 🎮 **Live Demo**: https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/
- 📚 **Workshop Guide**: See [workshop/](workshop/) folder (also available in English, Spanish, Portuguese BR)

## Architecture

```
SocOps/
├── Components/        # Reusable Blazor components
│   ├── BingoBoard.razor       # Main game board (5x5 grid)
│   ├── BingoSquare.razor      # Individual square with click handling
│   ├── BingoModal.razor       # Bingo celebration modal
│   ├── GameScreen.razor       # Active game view
│   └── StartScreen.razor      # Game start/menu
├── Models/            # Data models (Core game state)
│   ├── GameState.cs           # Enum: Start, Playing, Bingo
│   ├── BingoSquareData.cs     # Square data + marked state
│   └── BingoLine.cs           # Winning line definition
├── Services/          # Business logic & state management
│   ├── BingoGameService.cs    # Main state manager (localStorage integration)
│   └── BingoLogicService.cs   # Game mechanics (board generation, win detection)
├── Data/              # Static data
│   └── Questions.cs           # Question pool for squares
├── Pages/             # Routable pages
│   └── Home.razor             # Main entry point
└── wwwroot/           # Static assets
    ├── index.html
    └── css/app.css            # Custom utility classes (Tailwind-like)
```

## Development Workflow

### Prerequisites
- [.NET 10 SDK](https://dotnet.microsoft.com/download/dotnet/10.0) or higher

### Key Commands

```bash
# Development
cd SocOps
dotnet run                          # Start dev server (port 5166)
dotnet build                        # Build project

# Build & CI
dotnet build SocOps/SocOps.csproj   # Explicit build
```

> **Note**: This project deploys automatically to GitHub Pages on push to `main`.

## Code Conventions

### C# / Blazor

- **Naming**: PascalCase for public members, `camelCase` for private/locals
- **Namespaces**: Follow folder structure (e.g., `SocOps.Components`, `SocOps.Services`)
- **Nullable**: Project uses `<Nullable>enable</Nullable>` – always add null checks
- **Imports**: Use `global using` statements in `_Imports.razor` for common namespaces

### Component Structure

- Keep `.razor` components focused on UI only
- Logic → Services (BingoGameService, BingoLogicService)
- Subscribe to `OnStateChanged` event for reactive updates
- Use `@implements IAsyncDisposable` if subscribing to events

### State Management

- **BingoGameService**: Main service, scoped to app lifetime
  - Properties: `CurrentGameState`, `Board`, `WinningLine`, `ShowBingoModal`
  - Event: `OnStateChanged` fired after state mutations
  - Persists to localStorage via JSInterop
- Components receive state updates through event subscriptions

## Styling & Design

### CSS Utilities
Custom utility classes (Tailwind-inspired) defined in `wwwroot/css/app.css`:
- **Layout**: `.flex`, `.flex-col`, `.grid`, `.grid-cols-5`, `.items-center`
- **Spacing**: `.p-1` → `.p-6`, `.mb-2` → `.mb-8`, `.mx-auto`, `.gap-1`
- **Sizing**: `.h-full`, `.w-full`, `.aspect-square`
- **Colors**: `.bg-accent` (primary), `.bg-marked` (success/selected), `.text-gray-*`, `.text-green-600`
- **Typography**: `.text-xs` → `.text-5xl`, `.font-semibold`, `.text-center`

**See**: [.github/instructions/css-utilities.instructions.md](.github/instructions/css-utilities.instructions.md)

### Frontend Design Philosophy
When designing UI components, create distinctive, creative frontends that avoid generic "AI slop" aesthetics:
- Choose unique fonts and colors that match the project's context
- Use animations purposefully (CSS-only for Blazor)
- Layer backgrounds with gradients for depth and atmosphere
- Prioritize high-impact moments over scattered micro-interactions

**See**: [.github/instructions/frontend-design.instructions.md](.github/instructions/frontend-design.instructions.md)

## Development Checklist

Before committing changes:

- [ ] `dotnet build` passes with no errors or warnings
- [ ] Code follows C# conventions (PascalCase public, `camelCase` private)
- [ ] No unused variables or imports
- [ ] Components are properly scoped (Services added to DI)
- [ ] State changes trigger `OnStateChanged` event appropriately
- [ ] Styling uses existing utility classes (avoid adding raw CSS)

## Common Tasks

### Add a New Component
1. Create `.razor` file in `Components/` folder
2. Define component structure and parameters
3. Inject services as needed (e.g., `@inject BingoGameService GameService`)
4. Subscribe to `OnStateChanged` in `OnInitializedAsync()`
5. Use custom CSS utility classes for styling

### Modify Game Logic
1. Edit `BingoLogicService.cs` for core mechanics (board gen, win detection)
2. Call service methods from `BingoGameService` 
3. Ensure `OnStateChanged` is fired after mutations

### Update Styling
1. Add or modify utility classes in `wwwroot/css/app.css`
2. Use semantic names (`bg-accent`, `text-gray-*`)
3. Maintain grid-based spacing (multiples of 0.25rem or 4px)

## Special Notes

- **localStorage**: Game state persists across page reloads via `BingoGameService`
- **Event-Driven**: Components react to `OnStateChanged` event, not polling
- **No External CSS Frameworks**: Project intentionally avoids Bootstrap/Tailwind CDN
- **Blazor WebAssembly**: Renders entirely in browser (no server-side rendering)

## Workshop Context

This project is part of a hands-on workshop demonstrating:
1. **Setup & Context Engineering** (agent instructions)
2. **Design-First Frontend** (Pixel Jam agent)
3. **Custom Quiz Master** (AI agent customization)
4. **Multi-Agent Development** (orchestrating specialized agents)

See [workshop/](workshop/) for detailed lab guides.

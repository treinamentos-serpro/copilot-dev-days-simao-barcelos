🌐 [Português (BR)](README.pt_BR.md) | [Español](README.es.md)

# 🎯 Soc Ops — Social Bingo for Real-World Conversations

> Break the ice, meet new people, and turn mixers into a game.

**Soc Ops** is a Blazor WebAssembly social bingo app built for in-person events, workshops, conferences, and team gatherings. Players look for people who match each square, mark the board as they mingle, and race to land 5 in a row.

🎮 **[Play the Game](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/)**  
📚 **[Open the Lab Guide](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/)**

---

## Why this project is fun

- 🧊 **Instant icebreaker** — gives people an easy reason to start a conversation
- 🎲 **Fresh every round** — randomized boards keep each game different
- 💾 **Resume anytime** — game state is saved locally in the browser
- 🏆 **Built-in win detection** — rows, columns, and diagonals are checked automatically
- 📱 **Event-ready UI** — designed to feel quick and simple on phones
- 🤖 **Copilot workshop sample** — a real app used to teach multi-agent workflows

## Quick start

### Prerequisites

- [.NET 10 SDK](https://dotnet.microsoft.com/download/dotnet/10.0) or higher

### Run locally

```bash
cd SocOps
dotnet run
```

Then open `http://localhost:5166`.

### Build

```bash
dotnet build SocOps/SocOps.csproj
```

## Workshop path

This repository is also a hands-on GitHub Copilot workshop. If you want to explore the app while learning agent workflows, jump into the guide:

| Part | Title |
|------|-------|
| [**00**](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=00-overview) | Overview & Checklist |
| [**01**](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=01-setup) | Setup & Context Engineering |
| [**02**](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=02-design) | Design-First Frontend |
| [**03**](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=03-quiz-master) | Custom Quiz Master |
| [**04**](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=04-multi-agent) | Multi-Agent Development |

> 📝 Prefer local reading? The same content is available in [`workshop/`](workshop/).

## Customize it for your event

A simple way to make Soc Ops your own is to update the question bank in [`SocOps/Data/Questions.cs`](SocOps/Data/Questions.cs). Swap in prompts for your meetup, onboarding session, classroom, or conference and you instantly get a new game experience.

## Project at a glance

```text
SocOps/
├── Components/   # Bingo board, squares, modal, game screens
├── Models/       # Game state and domain models
├── Services/     # State management and bingo logic
├── Data/         # Question bank
├── Pages/        # Routable pages
└── wwwroot/      # Static assets and CSS utilities
```

## Tech stack

- **Framework:** Blazor WebAssembly on .NET 10
- **State:** Scoped services with localStorage persistence
- **Styling:** Custom utility CSS
- **Deployment:** GitHub Pages via GitHub Actions

## More project info

- [Contributing guide](CONTRIBUTING.md)
- [Code of conduct](CODE_OF_CONDUCT.md)
- [Security policy](SECURITY.md)
- [Support](SUPPORT.md)

Automatically deploys to GitHub Pages on push to `main`.

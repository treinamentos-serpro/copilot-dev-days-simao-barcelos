---
description: Specialized agents available for SocOps development and workshop tasks
---

# Available Agents for SocOps

Use these agents to speed up focused tasks in SocOps.

## Mandatory Development Checklist
- [ ] Lint: run project lint/format validation command
- [ ] Build: `dotnet build SocOps/SocOps.csproj`
- [ ] Test: run test suite (`dotnet test`)

## 🎨 Pixel Jam
**Design user interfaces quickly and iteratively in code.**

### Use When:
- Building or redesigning `.razor` UI
- Creating visual layouts and animations
- Applying [frontend-design](/.github/instructions/frontend-design.instructions.md)

### Workflow:
```
/assign Pixel Jam
@Pixel Jam What should we design today?
```

### Example Tasks:
- "Design an eye-catching bingo board layout"
- "Build a celebration modal for winning"

---

## 📝 Quiz Master
**Creates fun and engaging icebreaker questions and bingo prompts**

### Use When:
- Generating new bingo prompts
- Creating themed question sets
- Updating `Data/Questions.cs`

### Workflow:
```
/assign Quiz Master
@Quiz Master Describe the theme of questions you want
```

### Example Tasks:
- "Create social icebreaker questions for tech mixers"
- "Generate cyberpunk-themed bingo prompts"

---

## 🧪 TDD Agents (Red → Green → Refactor)
**Test-Driven Development workflow agents**

### Use When:
- Building features with test coverage
- Implementing complex logic in `Services/`

### Workflow:
```
Step 1: Write failing tests
/assign TDD Red
@TDD Red Write tests for [feature]

Step 2: Implement minimal code
/assign TDD Green
@TDD Green Implement [feature] to pass tests

Step 3: Clean up
/assign TDD Refactor
@TDD Refactor Improve code quality while maintaining tests
```

---

## 🤖 TDD Supervisor
**Orchestrate full TDD cycle from request to implementation**

### Use When:
- Running full Red → Green → Refactor automatically
- Driving a feature from requirement to implementation

### Workflow:
```
/assign TDD Supervisor
@TDD Supervisor Implement [feature description]
```

### Example Tasks:
- "Add multiplayer support to BingoGameService"
- "Implement difficulty levels for question generation"

---

## 📋 UI Review
**Comprehensive UI/UX review and feedback**

### Use When:
- Reviewing usability and visual consistency
- Checking accessibility and responsive behavior

### Workflow:
```
/assign UI Review
@UI Review Review [component or area]
```

### Example Tasks:
- "Review the bingo board for mobile responsiveness"
- "Check color contrast and accessibility"

---

## Project-Specific Tips

1. **Design → TDD**: `Pixel Jam` for UI, then `TDD Red/Green/Refactor` for logic/tests.
2. **Content → Logic**: `Quiz Master` for prompts, then TDD agents for validation.
3. **Review Loop**: `UI Review` for feedback, then `Pixel Jam` for iteration.

---

## Integration with Instructions

Each agent respects the project's architectural guidelines:
- **Code Conventions**: PascalCase, proper namespacing, nullable handling
- **CSS Utilities**: Uses custom classes from `wwwroot/css/app.css`
- **Design Philosophy**: Avoids "AI slop", creates distinctive visuals
- **State Management**: Properly integrates with `BingoGameService`

See [.github/copilot-instructions.md](./.github/copilot-instructions.md) for complete development guidelines.

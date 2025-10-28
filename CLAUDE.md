# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a **pre-development ideation and exploration space** where ideas are developed before coding begins. Work happens through multiple perspectives:
- **Idealist/Inventor**: Brainstorming concepts, identifying problems worth solving
- **Product Designer**: Shaping user experiences, defining features and flows
- **Software Developer**: Exploring technical feasibility, architecture, and implementation approaches
- **Salesman**: Validating value propositions, understanding market fit

The repository uses:
- A Mermaid mindmap ([mindmap.mmd](mindmap.mmd)) as a visual representation of learning topics and technology areas to explore
- Detailed markdown notes documenting research, experiments, and technical investigations
- An ideas backlog ([app-ideas.md](app-ideas.md)) for potential projects in early ideation stages

## Repository Structure

- `mindmap.mmd` - Central mindmap using Mermaid syntax (tidy-tree layout) showing technology topics organized by category (AI, Crypto, PM, DEV)
- `mindmap-notes-*.md` - Detailed learning notes for specific topics, formatted as conversation logs or research documentation
- `app-ideas.md` - Initial registry of project ideas with brief descriptions; ideas remain here until work begins on them
- Individual idea files - When working on a specific idea from app-ideas.md, create a dedicated file for that idea's exploration

## Working with This Repository

### Adding New Learning Topics

When adding new topics to the mindmap:
1. Edit [mindmap.mmd](mindmap.mmd) maintaining the tidy-tree layout configuration
2. Place new topics under appropriate parent categories (AI, Crypto, PM, DEV)
3. Keep the hierarchical structure clear and organized
4. Use color coding sparingly (e.g., `::: color #f96` for emphasis)

### Creating Learning Notes

When documenting new learning experiences:
1. Create files following the pattern `mindmap-notes-[topic].md`
2. Structure as conversational Q&A or iteration-based learning logs
3. Include practical insights, troubleshooting steps, and "aha moments"
4. Document both successes and challenges encountered
5. Keep a "final thoughts" section to capture key takeaways

### Managing Ideas

**Initial idea registration in [app-ideas.md](app-ideas.md):**
- Keep entries brief - just title and a few lines describing the concept
- Include motivation from multiple angles:
  - Technical: "experiment with X API", "try Y technology"
  - Personal: "connection with my kids", "revamp my blog"
  - Learning: "see if it works", "understand how X works"
  - Problem-solving: "help students learn", "help a designer plan"
- Note any immediate questions or uncertainties
- Ideas remain in app-ideas.md until work begins on them

**Developing an idea:**
- When starting to explore a specific idea, create a new dedicated file for it (e.g., `expense-register-exploration.md`, `quiz-generator-design.md`)
- The dedicated file should document the full exploration process from multiple perspectives
- Ideas are exploratory - they may evolve significantly or be abandoned as understanding deepens
- **Always distill to a simple version**: While exploration can go deep, conclude with a simplified version that can be implemented in ~1 week of work

## Key Learning Areas

Based on the mindmap, active focus areas include:
- **Mobile Development**: React Native (Expo-based), PWA (vanilla JS approach)
- **Backend**: ASP.NET (Aspire, minimal APIs, testing with ArchUnit and Stryker.NET)
- **Testing**: Mutation testing, architecture tests, Playwright
- **AI Integration**: Claude Code agents, MCP servers, natural language features
- **DevOps**: GitHub Actions, Docker, test containers

## Content Philosophy

This repository values:
- **Minimal dependencies and understanding fundamentals** - "using expo feels a bit like cheating" reflects a desire to understand what's really happening
- **Learning by doing** - Simple, practical examples over theoretical knowledge
- **Documenting the journey** - Capturing questions, dead-ends, and realizations, not just final solutions
- **Progressive enhancement** - Start simple, add complexity only when needed
- **Multi-perspective thinking** - Ideas are examined from technical, user, business, and learning angles
- **Questioning assumptions** - "is there anything that already exists similar to this?", "roblox vs minecraft for this?"
- **Authentic exploration** - This is pre-coding ideation space; ideas here are meant to be rough, questioned, and evolved

## Working with Claude Code

When assisting in this repository:
- **Help explore feasibility** without jumping to implementation
- **Ask clarifying questions** that challenge assumptions or reveal missing considerations
- **Research similar solutions** to inform decision-making
- **Identify potential technical approaches** and trade-offs
- **Consider multiple perspectives** - technical complexity, user value, learning opportunity, market need
- **End with actionable simplicity**: While exploration can be broad and deep, always conclude by distilling ideas into a simple, focused version that can be implemented in approximately one week of work
- **Never create code files** in this repository - this is purely an ideation space
- **Prefer linking to similar implementations** over providing code snippets when showing examples
- Small code snippets in documentation are acceptable only when necessary for understanding concepts
- This is a thinking space, not a production codebase

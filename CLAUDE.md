# CLAUDE.md - AI Assistant Guide for Frontlines-Game

**Last Updated:** 2025-11-15
**Repository:** Frontlines-Game
**Status:** Initial Setup

## Table of Contents
1. [Project Overview](#project-overview)
2. [Repository Structure](#repository-structure)
3. [Development Workflow](#development-workflow)
4. [Technology Stack](#technology-stack)
5. [Code Conventions](#code-conventions)
6. [AI Assistant Guidelines](#ai-assistant-guidelines)
7. [Common Tasks](#common-tasks)
8. [Testing Strategy](#testing-strategy)
9. [Deployment](#deployment)
10. [Troubleshooting](#troubleshooting)

---

## Project Overview

**Frontlines-Game** is a game development project currently in initial setup phase.

### Project Goals
- Create an engaging game experience
- Maintain clean, maintainable code
- Follow industry best practices for game development
- Enable collaborative development with AI assistance

### Key Features (Planned)
- [To be defined based on game design]
- [Add features as they are implemented]

---

## Repository Structure

### Recommended Directory Layout

```
Frontlines-Game/
├── .github/                  # GitHub workflows and templates
│   ├── workflows/           # CI/CD pipelines
│   └── ISSUE_TEMPLATE/      # Issue templates
├── assets/                   # Game assets
│   ├── audio/               # Sound effects and music
│   ├── sprites/             # 2D graphics
│   ├── textures/            # Texture files
│   ├── models/              # 3D models
│   └── fonts/               # Font files
├── config/                   # Configuration files
│   ├── development.config   # Dev environment config
│   ├── production.config    # Production config
│   └── test.config          # Test environment config
├── docs/                     # Documentation
│   ├── architecture.md      # Architecture decisions
│   ├── api.md               # API documentation
│   └── game-design.md       # Game design documents
├── scripts/                  # Build and utility scripts
│   ├── build.sh             # Build script
│   ├── deploy.sh            # Deployment script
│   └── setup.sh             # Environment setup
├── src/                      # Source code
│   ├── core/                # Core game engine code
│   ├── entities/            # Game entities/objects
│   ├── systems/             # Game systems (physics, rendering, etc.)
│   ├── ui/                  # User interface components
│   ├── utils/               # Utility functions
│   └── main.js|ts|py        # Entry point
├── tests/                    # Test files
│   ├── unit/                # Unit tests
│   ├── integration/         # Integration tests
│   └── e2e/                 # End-to-end tests
├── .gitignore               # Git ignore patterns
├── CLAUDE.md                # This file
├── LICENSE                  # Project license
├── README.md                # Project readme
└── package.json|requirements.txt|Cargo.toml  # Dependencies

```

### Current Structure
- Repository is currently empty and ready for initial setup
- Structure should be created based on chosen technology stack

---

## Development Workflow

### Branch Strategy

#### Main Branches
- `main` or `master`: Production-ready code
- `develop`: Integration branch for features
- `claude/*`: AI assistant working branches

#### Feature Branches
- Format: `feature/feature-name`
- Create from: `develop`
- Merge to: `develop`

#### Bugfix Branches
- Format: `bugfix/bug-description`
- Create from: `develop` or `main`
- Merge to: `develop` or `main`

#### Hotfix Branches
- Format: `hotfix/issue-description`
- Create from: `main`
- Merge to: `main` and `develop`

### Commit Message Convention

Follow conventional commits format:

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks
- `perf`: Performance improvements

**Examples:**
```
feat(player): add player movement system
fix(collision): resolve hitbox detection bug
docs(readme): update installation instructions
refactor(rendering): optimize draw calls
```

### Pull Request Process

1. Create feature branch from `develop`
2. Implement changes with tests
3. Ensure all tests pass
4. Update documentation
5. Create PR with description of changes
6. Request review
7. Address feedback
8. Merge when approved

---

## Technology Stack

### To Be Determined

Consider these options based on project requirements:

#### Game Engines
- **Unity** (C#): Feature-rich, excellent documentation
- **Unreal Engine** (C++/Blueprints): High-end graphics, AAA quality
- **Godot** (GDScript/C#): Open-source, lightweight
- **Phaser** (JavaScript/TypeScript): Web-based 2D games
- **PyGame** (Python): Simple, educational, rapid prototyping
- **Bevy** (Rust): Modern, ECS-based, data-driven

#### Web-Based Stack
- **Frontend**: HTML5 Canvas, WebGL, Three.js, PixiJS
- **Backend**: Node.js, Python (Flask/Django), Rust (Actix)
- **Database**: PostgreSQL, MongoDB, Redis

#### Native Stack
- **Languages**: C++, C#, Rust, Java/Kotlin
- **Graphics**: OpenGL, Vulkan, DirectX, Metal
- **Physics**: Box2D, Bullet Physics, PhysX

---

## Code Conventions

### General Principles

1. **Readability First**: Code is read more than written
2. **DRY (Don't Repeat Yourself)**: Extract common patterns
3. **SOLID Principles**: Follow object-oriented design principles
4. **Consistent Naming**: Use clear, descriptive names
5. **Comment Why, Not What**: Code shows what, comments explain why

### Naming Conventions

#### Variables
- Use descriptive names: `playerHealth` not `pH`
- Boolean variables: prefix with `is`, `has`, `should`
- Constants: `UPPER_SNAKE_CASE` or `UPPER_CASE`

#### Functions/Methods
- Use verbs: `calculateDamage()`, `renderFrame()`, `updatePosition()`
- Be specific: `getPlayerHealth()` not `get()`

#### Classes
- Use nouns: `Player`, `Enemy`, `GameEngine`
- PascalCase for class names

#### Files
- Match the primary class/module name
- Use kebab-case for multi-word files: `player-controller.js`
- Or PascalCase: `PlayerController.cs`

### Code Organization

```
// Bad
function doStuff(p, e, dt) {
  p.x += p.vx * dt;
  p.y += p.vy * dt;
  if (checkCollision(p, e)) {
    p.health -= e.damage;
  }
}

// Good
function updatePlayerPhysics(player: Player, deltaTime: number): void {
  player.position.x += player.velocity.x * deltaTime;
  player.position.y += player.velocity.y * deltaTime;
}

function handlePlayerEnemyCollision(player: Player, enemy: Enemy): void {
  if (this.collisionDetector.checkCollision(player, enemy)) {
    player.takeDamage(enemy.damageAmount);
  }
}
```

### Performance Considerations

1. **Object Pooling**: Reuse objects instead of creating/destroying
2. **Avoid Premature Optimization**: Profile first, optimize hot paths
3. **Batch Operations**: Group similar operations together
4. **Cache Results**: Store expensive calculations
5. **Use Appropriate Data Structures**: Choose based on access patterns

---

## AI Assistant Guidelines

### Core Responsibilities

1. **Code Quality**: Write clean, maintainable, well-documented code
2. **Testing**: Include tests for new features and bug fixes
3. **Documentation**: Update docs when making significant changes
4. **Context Awareness**: Understand the broader codebase before making changes
5. **Security**: Never introduce vulnerabilities or expose sensitive data

### Before Starting Work

1. **Understand the Task**: Read issue/request carefully
2. **Explore Context**: Use Task tool with `subagent_type=Explore` for codebase exploration
3. **Plan**: Use TodoWrite tool for complex multi-step tasks
4. **Ask Questions**: Clarify ambiguities before implementation

### During Implementation

1. **Follow Conventions**: Adhere to established patterns in codebase
2. **Write Tests**: Add unit tests for new functionality
3. **Document**: Add comments for complex logic
4. **Commit Often**: Make atomic commits with clear messages
5. **Security Check**: Review for common vulnerabilities (injection, XSS, etc.)

### Code Review Checklist

- [ ] Code follows project conventions
- [ ] All tests pass
- [ ] New tests added for new functionality
- [ ] Documentation updated
- [ ] No security vulnerabilities introduced
- [ ] No performance regressions
- [ ] Error handling implemented
- [ ] Edge cases considered

### Common Pitfalls to Avoid

1. **Don't create files unnecessarily**: Prefer editing existing files
2. **Don't use bash for file operations**: Use Read, Write, Edit tools
3. **Don't skip tests**: Always include test coverage
4. **Don't ignore errors**: Implement proper error handling
5. **Don't hardcode values**: Use configuration files
6. **Don't commit secrets**: Keep credentials in environment variables

### Tool Usage

- **Exploration**: Use `Task` tool with `Explore` subagent for understanding codebase
- **File Search**: Use `Glob` for pattern matching, `Grep` for content search
- **File Operations**: Use `Read`, `Write`, `Edit` instead of bash commands
- **Planning**: Use `TodoWrite` for complex tasks
- **Git Operations**: Follow git safety protocol, never force push

---

## Common Tasks

### Setting Up Development Environment

```bash
# Clone repository
git clone <repository-url>
cd Frontlines-Game

# Install dependencies (adjust based on tech stack)
npm install
# or
pip install -r requirements.txt
# or
cargo build

# Run development server
npm run dev
# or
python main.py
# or
cargo run
```

### Running Tests

```bash
# Run all tests
npm test
# or
pytest
# or
cargo test

# Run specific test file
npm test -- <test-file>
pytest tests/test_player.py
cargo test player_tests
```

### Building for Production

```bash
# Create production build
npm run build
# or
python setup.py build
# or
cargo build --release
```

### Adding a New Feature

1. Create feature branch: `git checkout -b feature/feature-name`
2. Implement feature in appropriate module
3. Add tests for the feature
4. Update documentation
5. Commit changes: `git commit -m "feat: add feature description"`
6. Push branch: `git push -u origin feature/feature-name`
7. Create pull request

### Fixing a Bug

1. Create bugfix branch: `git checkout -b bugfix/bug-description`
2. Write failing test that reproduces the bug
3. Fix the bug
4. Verify test now passes
5. Commit: `git commit -m "fix: resolve bug description"`
6. Push and create PR

---

## Testing Strategy

### Test Pyramid

```
        /\
       /  \
      / E2E \ (Few)
     /______\
    /        \
   /Integration\ (Some)
  /____________\
 /              \
/  Unit Tests    \ (Many)
/__________________\
```

### Unit Tests

- Test individual functions/methods in isolation
- Mock external dependencies
- Fast execution
- High coverage target: 80%+

### Integration Tests

- Test interactions between components
- Test with real dependencies when possible
- Moderate execution time
- Focus on critical paths

### End-to-End Tests

- Test complete user workflows
- Test in production-like environment
- Slower execution
- Cover critical user journeys

### Test File Naming

- Unit: `<module>.test.js` or `test_<module>.py`
- Integration: `<feature>.integration.test.js`
- E2E: `<workflow>.e2e.test.js`

### Example Test Structure

```javascript
describe('Player', () => {
  describe('movement', () => {
    it('should update position when moving right', () => {
      const player = new Player({ x: 0, y: 0 });
      player.move('right', 10);
      expect(player.position.x).toBe(10);
    });

    it('should not move beyond map boundaries', () => {
      const player = new Player({ x: 990, y: 0 });
      const map = new Map({ width: 1000, height: 1000 });
      player.move('right', 20, map);
      expect(player.position.x).toBe(1000);
    });
  });
});
```

---

## Deployment

### Pre-Deployment Checklist

- [ ] All tests passing
- [ ] No console errors/warnings
- [ ] Performance profiling completed
- [ ] Security audit performed
- [ ] Documentation updated
- [ ] Version number bumped
- [ ] Changelog updated

### Deployment Environments

1. **Development**: Local development machines
2. **Staging**: Pre-production testing environment
3. **Production**: Live environment for end users

### Deployment Process

1. Merge approved PR to `develop`
2. Run full test suite
3. Deploy to staging environment
4. Perform smoke tests
5. If successful, merge to `main`
6. Deploy to production
7. Monitor for issues

### Rollback Procedure

If issues occur in production:

1. Immediately revert to previous version
2. Investigate issue in staging
3. Create hotfix branch
4. Test fix thoroughly
5. Deploy hotfix following expedited process

---

## Troubleshooting

### Common Issues

#### Build Failures

**Symptom**: Build process fails
**Possible Causes**:
- Missing dependencies
- Incompatible versions
- Configuration errors

**Solutions**:
1. Clear cache: `npm clean-install` or `rm -rf node_modules && npm install`
2. Check version compatibility
3. Review build logs for specific errors

#### Performance Issues

**Symptom**: Game runs slowly, low FPS
**Possible Causes**:
- Inefficient rendering
- Memory leaks
- Too many draw calls
- Large asset files

**Solutions**:
1. Profile with browser DevTools or game engine profiler
2. Implement object pooling
3. Optimize assets (compress, reduce resolution)
4. Use level of detail (LOD) systems
5. Batch draw calls

#### Test Failures

**Symptom**: Tests fail unexpectedly
**Possible Causes**:
- Flaky tests (timing issues)
- Environment differences
- Breaking changes

**Solutions**:
1. Run tests locally to reproduce
2. Check for race conditions
3. Ensure test isolation
4. Review recent changes

### Getting Help

1. **Check Documentation**: Review docs/ directory
2. **Search Issues**: Look for similar problems in GitHub issues
3. **Ask Team**: Reach out to other developers
4. **Stack Overflow**: Search for similar technical issues
5. **Official Docs**: Refer to framework/engine documentation

### Debug Tools

- **Browser DevTools**: For web-based games
- **Game Engine Debugger**: Unity/Unreal/Godot built-in tools
- **Performance Profilers**: Chrome DevTools, Unity Profiler
- **Memory Profilers**: Heap snapshots, memory analyzers
- **Network Inspector**: Monitor API calls and assets loading

---

## Additional Resources

### Learning Resources

- [Game Programming Patterns](https://gameprogrammingpatterns.com/)
- [Red Blob Games](https://www.redblobgames.com/) - Interactive tutorials
- [Game Developer](https://www.gamedeveloper.com/) - Industry articles

### Tools

- **Version Control**: Git, GitHub
- **Project Management**: GitHub Projects, Jira, Trello
- **Communication**: Discord, Slack
- **Asset Creation**: Blender, GIMP, Aseprite, Audacity

### Best Practices

1. **Optimize Later**: Get it working first, optimize second
2. **User Feedback**: Test with real players early and often
3. **Iterative Development**: Build in small increments
4. **Version Control Everything**: Except large binary assets (use LFS)
5. **Backup Regularly**: Protect your work

---

## Changelog

### 2025-11-15 - Initial Creation
- Created comprehensive CLAUDE.md for new repository
- Established project structure guidelines
- Defined development workflows and conventions
- Set up AI assistant guidelines

---

## Contributing

When contributing to this project:

1. Read this entire document
2. Follow all conventions and guidelines
3. Write tests for your code
4. Document your changes
5. Submit PR for review

## License

[To be determined - add license information here]

---

**Note to AI Assistants**: This document is your primary reference for working on this project. When in doubt, refer to these guidelines. If you discover inconsistencies or areas that need clarification, suggest updates to this document.

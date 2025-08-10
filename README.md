# Claude Enhanced Guide - Practical Understanding

## Purpose
This guide helps you (Claude) understand how to effectively use APIs, agents, commands, hooks, and workflows. It's organized from simple to complex concepts, with practical examples for codebase work.

## Important: Content Sources
This guide combines:
- **Official features** from Anthropic announcements (marked as NEW or ENHANCED)
- **Observed patterns** from practical usage
- **Conceptual approaches** for cognitive strategies
- **Third-party tools** (clearly marked as such)
- **Estimated metrics** (not official benchmarks)

Look for [NOTE:] markers throughout the document to identify non-official content.

## Guide Structure
1. **Quick Reference Cards** - Instant lookup for common tasks and features
2. **Core Concepts** - Basic tools, permissions, project context, memory management
3. **Agent System** - Types, capabilities, coordination, sub-agents
4. **Slash Commands** - System/custom commands, templates, organization
5. **Hooks System** - Events, patterns, security, automation
6. **MCP Integration** - External systems, OAuth, configuration
7. **Workflow Patterns** - Development approaches, task management
8. **Quality Patterns** - Automation, multi-agent review
9. **Error Recovery** - Common patterns, progressive strategies
10. **Practical Examples** - Real-world scenarios for various tasks
11. **Advanced Patterns** - Research systems, Smart Flows, cognitive approaches
12. **Best Practices** - Principles for development, quality, efficiency
13. **Troubleshooting** - Common issues, solutions, diagnostics
14. **Critical Verification** - Completeness checking, pitfall avoidance
15. **Intelligent Log Analysis** - Pattern mining, performance tracking, automated learning
16. **Security Considerations** - Security model, best practices, audit trails
17. **Scripts & Automation Infrastructure** - Core scripts library, execution patterns, configuration
18. **The Intelligent Development Loop** - Ultimate synergy of all systems

## Quick Reference Cards

### 🚀 Instant Command Reference
```bash
# Background Tasks (NEW - Implementation evolving)
npm run dev &                    # Run in background
[NOTE: Commands below are from announcements, verify availability]
/bashes                          # List background processes (verify)
/bash-output <id>                # Check output (verify)
/kill-bash <id>                  # Stop process (verify)

# Status Line (NEW)
/statusline git branch           # Show git branch
/statusline "📍 $(pwd)"          # Show current directory
/statusline custom               # Custom status

# Security
[NOTE: /security-review is a custom command example, not built-in]
# Create your own: ~/.claude/commands/security-review.md

# Subagents (OFFICIAL)
/agents                          # Manage subagents (OFFICIAL)
@code-reviewer fix this          # Direct agent mention (per announcements)
@architect design auth           # Call specific agent (per announcements)

# Context Management
/compact "focus on auth"         # Compact conversation (OFFICIAL)
/add-dir ../other-project        # Add working directory (OFFICIAL)
[NOTE: /microcompact mentioned in announcements but not in docs]

# Essential Commands (OFFICIAL)
/help                            # Show all commands
/clear                           # Clear conversation  
/model                           # Switch AI model
/review                          # Request code review
/compact                         # Compact conversation
/init                           # Initialize CLAUDE.md
/memory                         # Edit memory files
```

### 🎯 Feature Quick Reference
```bash
# Background Tasks
→ Long-running: dev servers, tests, builds
→ Real-time monitoring: logs, errors, output
→ Auto-recovery: Claude can fix crashes

# Multi-Directory
→ Monorepos: work across packages
→ Shared configs: access from anywhere
→ Cross-project: migrate code easily

# PDF Support
→ Direct reading: no conversion needed
→ Use cases: specs, docs, research papers
→ Reference: @document.pdf

# Security Reviews
→ Vulnerabilities: SQL injection, XSS, data leaks
→ GitHub Actions: automatic PR reviews
→ Fixes: Claude can fix found issues
```

### 🔥 Power User Shortcuts
```bash
# Parallel Background Tasks
npm run dev & npm run test:watch & npm run storybook &

# Smart Debugging
"Server crashed" → Claude checks background logs → Auto-fix

# Subagent Teams
@architect @reviewer @tester "Review auth implementation"

# Context Optimization
Long session → /microcompact → Continue working
Switching focus → /compact "new feature" → Fresh context

# Multi-Repo Workflow
/add-dir ../api-server
/add-dir ../frontend
"Sync API types across projects"
```

### 📋 Task State Reference
```bash
# Background Process States
RUNNING   → Active process
COMPLETED → Finished successfully
FAILED    → Crashed (Claude can debug)
KILLED    → Manually stopped

# Context States (Approximate)
FRESH     → Early in session
OPTIMAL   → Good working state
FULL      → Getting lengthy
CRITICAL  → Sluggish (use /microcompact)

# Agent Activity
IDLE      → Waiting for tasks
ACTIVE    → Processing request
BLOCKED   → Needs user input
COMPLETE  → Task finished
```

### 🔧 Common Workflows Card
```bash
# Start Development Session
1. npm run dev &                  # Start in background
2. /statusline "🚀 Dev Mode"     # Set status
3. /add-dir ../shared            # Add shared configs
4. "Fix the login bug"           # Claude monitors logs

# Security-First Development
1. "Implement user input"         # Build feature
2. /security-review              # Check vulnerabilities
3. "Fix the XSS issue"          # Address findings
4. git commit                    # Secure code

# Multi-Agent Review
1. "Build auth system"           # Initial implementation
2. @architect "Review design"   # Architecture check
3. @security "Check for vulns"  # Security audit
4. @tester "Write tests"        # Test coverage

# Long Session Management
1. Work for hours               # Context builds up
2. /microcompact                # Clear old calls
3. Continue seamlessly          # Keep working
4. /compact when switching      # Full reset if needed
```

## Core Concepts (Start Here)

### Core Claude Code Capabilities
Claude Code works through natural conversation and direct action:

```bash
# What Claude Code does:
- Build features from plain English descriptions
- Debug and fix issues by analyzing codebases
- Navigate and understand entire project structures
- Automate common development tasks
- Edit files and run commands directly

# Core capabilities:
Feature Building → "Create a user authentication system"
→ Analyzes requirements, creates plan, writes code

Debugging → "Fix the payment processing error"
→ Investigates logs, traces issues, implements fixes

Codebase Analysis → "Review this code for security issues"
→ Examines code, identifies vulnerabilities, suggests improvements

Automation → "Fix all lint issues in the project"
→ Identifies problems, applies fixes automatically

# How it works:
- Direct conversation in terminal
- Can edit files directly
- Runs commands as needed
- Creates commits and manages git
- Maintains project context
- Supports external integrations (MCP)

# Integration features:
- Hooks for automation
- Slash commands for workflows
- SDK for programmatic use
- Sub-agents for specialized tasks
- IDE integrations
```

**Key Understanding**: Claude Code works through natural language interaction, directly editing files and running commands based on your requests. No special syntax required - just describe what you need.

### Multi-Modal Capabilities
Handle different types of content intelligently:

```bash
# Text/Code Files
- Read and analyze any programming language
- Understand context and patterns
- Generate appropriate solutions

# Images
- Screenshots: Read UI, errors, designs
- Diagrams: Understand architecture, flows
- Charts: Interpret data and trends
- Photos: Extract relevant information

# Documents
- PDFs: Extract and analyze content
- Markdown: Full understanding and generation
- JSON/YAML: Parse and generate configs
- CSV: Understand data structures

# Combined Analysis
"Here's a screenshot of the error" → Read error, suggest fix
"This diagram shows our architecture" → Understand, suggest improvements
"This PDF has the requirements" → Extract, implement accordingly
```

**Key Understanding**: Different content types provide different context. Use all available information.

### 1. Core Capabilities
Your fundamental capabilities for assisting with tasks:

```bash
# Information Processing
- Read and analyze content (files, documents, images)
- Generate new content (code, text, configurations)
- Modify existing content (refactor, optimize, fix)
- Search and pattern matching

# Task Management
- Break down complex problems
- Track progress on multi-step tasks
- Parallelize independent work
- Maintain context across operations

# Execution Patterns
- Direct implementation (when you have access)
- Guided assistance (when user executes)
- Research and analysis
- Review and validation
```

**Key Understanding**: Understand existing context before making changes. Handle multiple related changes efficiently.

### 2. Permission Model
You operate with incremental trust:

```bash
# Permission flow
1. Start with minimal permissions (read-only)
2. Request permission for each new action type
3. Build trust through successful operations
4. Session-specific permissions

# Trust building patterns
read/analyze → Always safe initially
modify/write → Show changes first
execute → Explain what will happen
sensitive ops → Extra confirmation
```

**Key Understanding**: Permissions protect both you and the user. Request only what's needed.

### 3. Project Context (CLAUDE.md)
Every project can have a CLAUDE.md file providing essential context:

```markdown
# What to expect in CLAUDE.md
- Primary language and frameworks
- Code style preferences  
- Testing requirements
- Common commands (lint, test, build)
- Project-specific patterns
- Important constraints or rules
```

**Key Understanding**: Always check for CLAUDE.md - it's your project handbook.

### Memory Management & CLAUDE.md Updates
When updating project memories, ensure they're optimized for YOUR understanding:

```bash
# Smart memory update pattern
When updating CLAUDE.md:

Requirements for AI-optimized memory:
1. Write in direct, actionable language (no fluff)
2. Focus on patterns and gotchas specific to this codebase
3. Include exact commands that work (with correct flags)
4. Note what approaches DON'T work (save future attempts)
5. Use clear section headers for quick scanning
6. Keep entries concise but complete

Style guide:
- Start with verb for actions: "Use X when Y"
- Highlight warnings with ⚠️
- Mark critical info with 🔴
- Use code blocks for all commands/paths
- Group related information together

# Memory quality verification
After updating, verify:
1. Clarity - Would this guide you correctly next session?
2. Completeness - Are all critical learnings captured?
3. Accuracy - Are commands and paths correct?
4. Efficiency - Is it concise without losing important details?
5. Optimization - Does it match your cognitive style?
```

### Automated Memory Management Patterns
```bash
# Memory update workflow
# Triggers after significant work

When updating project memory:
1. Analyze session learnings
2. Extract key patterns discovered
3. Document successful approaches
4. Note failed attempts to avoid
5. Update command references
6. Keep AI-optimized style

# Quality verification
Verify updates are:
- Clear and actionable
- Technically accurate
- Cognitively friendly
- Free of redundancy
```

### Memory Management Patterns
```bash
# Common memory operations
- Update with session learnings
- Review and optimize existing memories
- Extract learnings from current work
- Consolidate and deduplicate entries
```

### CLAUDE.md Template for Optimal Recall
```markdown
# Project: [Name]

## 🔴 Critical Context (Read First)
- [Most important thing to know]
- [Second most important thing]

## Commands That Work
\`\`\`bash
npm run dev          # Start development server
npm run test:watch   # Run tests in watch mode
npm run lint:fix     # Auto-fix linting issues
\`\`\`

## Patterns to Follow
- Use MultiEdit for multiple changes to same file
- Always run tests before committing
- Check @database:migrations before schema changes

## ⚠️ Gotchas & What NOT to Do
- DON'T use `npm run build` - it's broken, use `npm run build:prod`
- DON'T edit generated files in `/dist`
- DON'T trust the old documentation in `/docs` - it's outdated

## File Structure Patterns
- Components: `/src/components/[Name]/[Name].tsx`
- Tests: Adjacent to source as `[Name].test.tsx`
- Styles: CSS modules as `[Name].module.css`

## Recent Learnings
- [Date]: Fixed auth by using JWT_SECRET from .env.local (not .env)
- [Date]: Database queries need explicit error handling
- [Date]: React hooks must be called unconditionally
```

**Key Understanding**: CLAUDE.md should be written BY Claude FOR Claude. Use specialized agents to avoid context bias and ensure high-quality, actionable memories.

### 4. ROADMAP.md Project Management
The roadmap serves as the central nervous system for project state:

```markdown
# Project Roadmap

## Current Sprint (Week X-Y)
- [-] Feature currently in development
- [ ] Planned feature for this sprint
- [ ] Another planned item

## Upcoming Priorities
- [ ] Next major feature
- [ ] System improvement

## Recently Completed
- [x] Completed feature
- [x] Infrastructure update

## Technical Debt
- [ ] Refactoring task
- [ ] Documentation update
```

**Task States**:
- `[ ]` - Planned/TODO
- `[-]` - In Progress (only one at a time)
- `[x]` - Completed
- `[~]` - Partially complete
- `[!]` - Blocked
- `[?]` - Needs clarification

**Key Understanding**: ROADMAP.md is the single source of truth for project state. Update it as work progresses.

### 5. Context & Session Management
Understanding continuity and context preservation:

```bash
# Context management patterns
- Preserve important context between interactions
- Resume work on complex tasks
- Start fresh when switching projects
- Track progress across sessions
```

**Key Understanding**: Context preservation helps maintain continuity for long-running tasks.

### 6. Background Tasks & Real-Time Monitoring (NEW)
Claude Code can now handle long-running processes without blocking:

```bash
# Background Execution Patterns
npm run dev &                    # Start dev server in background
npm test -- --watch &           # Run tests continuously
npm run build &                  # Build without blocking

# Monitoring & Management
/bashes                          # List all background processes
/bash-output <id>                # Check specific process output
/bash-output <id> "ERROR"        # Filter output for errors
/kill-bash <id>                  # Stop a background process

# Real-Time Debugging
"The server keeps crashing"      # Claude checks background logs
"Why is the build failing?"      # Analyzes build output
"Monitor test results"           # Watches test runner output
```

**Synergistic Patterns**:
```bash
# Development + Monitoring
npm run dev & npm run test:watch &
# Claude monitors both simultaneously
# Can fix issues in either without stopping the other

# Automatic Error Recovery
Server crashes → Claude detects in logs → Identifies cause → Fixes code → Restarts server

# Parallel Validation
npm run lint & npm run typecheck & npm run test &
# All checks run simultaneously
# Claude aggregates results and fixes issues
```

**Key Understanding**: Background tasks enable non-blocking workflows. Claude monitors logs in real-time and can intervene when issues occur.

### 7. Multi-Directory Workflows (NEW)
Work across multiple directories in a single session:

```bash
# Adding Directories
/add-dir ../backend              # Add backend directory
/add-dir ../frontend             # Add frontend directory
/add-dir ~/shared-configs        # Add shared configurations

# Directory Context
"main directory" or "root"       # Original initialization directory
"Check the backend API"          # Works across added directories
"Sync types between projects"    # Cross-project operations

# Monorepo Patterns
/add-dir packages/core
/add-dir packages/ui
/add-dir packages/utils
"Refactor shared utilities"      # Works across all packages
```

**Synergistic Workflows**:
```bash
# Full-Stack Development
/add-dir ../api
/add-dir ../web
npm run dev & (cd ../api && npm run dev &)
# Monitor both frontend and backend simultaneously

# Cross-Project Migration
/add-dir ../old-project
/add-dir ../new-project
"Migrate auth system from old to new"
# Claude can read from old, write to new

# Shared Configuration
/add-dir ~/.claude
"Apply my personal coding standards"
# Access global configs from any project
```

**Key Understanding**: Multi-directory support enables complex workflows across project boundaries without context switching.

### 8. Enhanced Context Management (NEW)
Smarter context handling for longer sessions:

```bash
# Microcompact (NEW)
/microcompact                    # Clears old tool calls only
# Preserves: Current task context, recent interactions, CLAUDE.md
# Clears: Old file reads, completed operations, stale context

# When to use each:
Feeling sluggish → /microcompact
Switching features → /compact "new feature"
Starting fresh → /clear

# Automatic Optimization
When session feels slow → Claude may suggest /microcompact
When switching tasks → Consider /compact for fresh start
```

**Context Preservation Strategy**:
```bash
# Smart Context Layering
Core Memory (always kept):
- CLAUDE.md patterns
- Current task list
- Critical project context

Working Memory (kept with microcompact):
- Recent file changes
- Current feature context
- Active debugging state

Transient Memory (cleared with microcompact):
- Old file reads
- Completed tool calls
- Historical searches
```

**Key Understanding**: Microcompact extends session length by intelligently clearing only non-essential context.

## Cognitive Approach System

### How Cognitive Modes Work
These are thinking approaches, not tools or agents. You naturally shift between these modes based on the task:

### Cognitive Modes Based on Task Type
Adapt your approach based on what needs to be done:

```bash
# Simple Creation Mode
→ Single file or component
→ Focus: Clean implementation, established patterns
→ Approach: Straightforward implementation with best practices
→ Example: "Create a button component" → Write the component directly

# Optimization Mode
→ Improving existing code
→ Focus: Performance, efficiency, clean code
→ Approach: Analyze, identify improvements, implement changes
→ Example: "Optimize this loop" → Review code, suggest better algorithm

# Review Mode  
→ Quality and security checks
→ Focus: Best practices, vulnerabilities, improvements
→ Approach: Systematic examination, identify issues, suggest fixes
→ Example: "Review this code" → Check for bugs, security, performance

# Parallel Mode
→ Multiple similar tasks
→ Focus: Consistency, efficiency, batch operations
→ Approach: Handle multiple items with consistent patterns
→ Example: "Create 5 API endpoints" → Design consistent structure, implement all

# Orchestration Mode
→ Complex multi-part features
→ Focus: Architecture, integration, completeness
→ Approach: Break down, plan dependencies, implement systematically
→ Example: "Build authentication system" → Design architecture, implement parts

# Research Mode
→ Exploration and investigation
→ Focus: Understanding, pattern discovery, best practices
→ Approach: Investigate thoroughly, gather information, synthesize
→ Example: "How should we handle caching?" → Research options, compare, recommend
```

**Key Understanding**: These modes are cognitive strategies, not separate tools. You fluidly shift between them as needed.

### Mode Selection Pattern
```
Question: What needs to be done?
├─ Single file/component → Simple Creation Mode
├─ Multiple similar items → Parallel Mode
├─ Complete feature → Orchestration Mode
├─ Improving code → Optimization Mode
├─ Finding/fixing issues → Research Mode
└─ Unknown/exploring → Research Mode
```

### Execution Patterns
- **Parallel Work**: Handle multiple independent tasks simultaneously when possible
- **Sequential Work**: Handle dependent tasks in order
- **Iterative Refinement**: Start simple, improve incrementally
- **Error Recovery**: High success rate on retry for transient failures (observed pattern)

### Practical Examples
```bash
# Creating multiple similar items
"Create CRUD endpoints for User, Product, Order"
→ Use Parallel Mode for consistency and speed

# Building a complete feature
"Implement authentication with login, signup, password reset"
→ Use Orchestration Mode for comprehensive implementation

# Researching approach
"Research best practices for WebSocket implementation"
→ Use Research Mode for thorough investigation

# Optimizing code
"Reduce bundle size and improve load time"
→ Use Optimization Mode for targeted improvements
```

**Key Understanding**: Let task complexity guide your cognitive mode. Start simple, escalate if needed.

## Slash Commands

### Built-in Slash Commands
Claude Code provides extensive built-in commands:

```bash
# Core Commands
/clear          # Clear conversation history
/help           # Get usage help and available commands
/review         # Request code review
/model          # Select or change the AI model

# Background Process Management
[NOTE: These commands from announcements, not yet in official docs]
/bashes         # List all background processes (verify)
/bash-output    # Get output from background process (verify)
/kill-bash      # Terminate background process (verify)

# Context Management (OFFICIAL)
/compact        # Compact conversation with optional focus
/add-dir        # Add working directory to session
[NOTE: /microcompact from announcements, not in docs]

# Security
[NOTE: Create custom command for security reviews]
# Example: ~/.claude/commands/security-review.md

# Customization (OFFICIAL)
/statusline     # Customize terminal status line (documented)
/agents         # Manage custom subagents (documented)

# Status Line Examples (NEW)
/statusline "git: $(git branch --show-current)"
/statusline "📍 $(pwd) | 🌡️ $(curl -s 'wttr.in?format=%t')"
/statusline "🤖 AI Buddy: Ready to help!"
```

### Custom Slash Commands
Create your own commands for project-specific workflows:

```bash
# Project commands (stored in .claude/commands/)
# Personal commands (stored in ~/.claude/commands/)

# Command structure (Markdown file):
# /my-command "argument"
# Uses $ARGUMENTS placeholder
# Can execute bash commands
# Can reference files with @ prefix
# Supports frontmatter configuration
```

### Advanced Command Features
```bash
# Namespacing
/project:deploy     # Project-specific deploy command
/team:review        # Team workflow command

# Extended thinking
# Commands can trigger extended reasoning

# MCP integration
# MCP servers can expose additional slash commands dynamically
```

**Key Understanding**: Slash commands provide shortcuts for common workflows. Built-in commands handle core functionality, custom commands adapt to your project needs.

## Hooks System

### What are Hooks?
Hooks are configurable scripts triggered by specific events during Claude Code interaction:

```bash
# Configuration location
~/.claude/settings.json   # Global hooks
.claude/settings.json     # Project-specific hooks

# Hook events:
PreToolUse        # Before a tool is used
PostToolUse       # After a tool completes  
UserPromptSubmit  # When user submits a prompt
Stop              # When main agent finishes responding
SessionStart      # When starting a new session
```

### Hook Configuration
```json
{
  "hooks": {
    "PostToolUse": [{
      "matcher": "Write|Edit",
      "command": "./format-code.sh"
    }],
    "PreToolUse": [{
      "matcher": "Bash.*rm",
      "command": "./safety-check.sh"
    }],
    "UserPromptSubmit": [{
      "command": "./inject-context.sh"
    }]
  }
}
```

### Hook Capabilities
```bash
# What hooks can do:
- Execute bash commands
- Add context to interactions
- Validate or block tool usage
- Inject additional information
- Receive JSON input with session details
- Return structured output to control behavior

# Common patterns:
- Format code after editing
- Safety checks before dangerous operations
- Context injection on user input
- Cleanup on session end
```

### Hook Responses
```bash
# Hooks can return JSON to control behavior:
{
  "decision": "continue|block|modify",
  "reason": "Human-readable explanation", 
  "context": "Additional information to inject"
}
```

**Key Understanding**: Hooks automate responses to events, enabling custom workflows and safety checks. They receive detailed session context and can control Claude Code's behavior.

## MCP Integration & Sub-Agents

### Model Context Protocol (MCP)
MCP connects Claude Code to external tools and data sources using an open-source integration standard:

```bash
# What MCP enables:
- Connect to hundreds of tools (GitHub, Sentry, Notion, databases)
- Perform actions like:
  * "Implement features from issue trackers"
  * "Analyze monitoring data" 
  * "Query databases"
  * "Integrate designs from Figma"
  * "Automate workflows"

# Connection methods:
- Local stdio servers
- Remote SSE (Server-Sent Events) servers  
- Remote HTTP servers

# Authentication:
- OAuth 2.0 support
- Different scopes: local, project, user
```

### Common MCP Integrations
```bash
# Popular integrations:
- GitHub (issues, PRs, workflows)
- Databases (PostgreSQL, MySQL, etc.)
- Monitoring tools (Sentry, DataDog)
- Design tools (Figma)
- Communication (Slack)
- Cloud services (AWS, GCP)
- Documentation (Notion, Confluence)

# Usage examples:
"Pull the latest issues from GitHub"
"Query the user database for active accounts"
"Update the Figma design with new components"
"Post build status to Slack channel"
```

### Custom Subagents (ENHANCED)
Claude Code now supports powerful custom subagents with @-mention support:

```bash
# Creating Custom Subagents
/agents                          # Open agent management

# Define specialized agents:
- Software Architect: Design patterns, abstraction layers
- Code Reviewer: Best practices, code quality, cleanup
- QA Tester: Unit tests, linting, test coverage
- Security Auditor: Vulnerability scanning, secure coding
- Performance Engineer: Optimization, profiling, metrics
- Documentation Writer: API docs, READMEs, comments

# Using Subagents
@code-reviewer "Check this implementation"
@architect "Design the auth system"
@qa-tester "Write comprehensive tests"
@security "Scan for vulnerabilities"

# Team Coordination
@architect @reviewer "Review system design and implementation"
# Multiple agents work together on the task

# Automatic Agent Selection
"Review this code"               # Claude picks appropriate agent
"Design a scalable API"          # Architect agent auto-selected
"Find security issues"           # Security agent activated

# Model Selection per Agent
Each agent can use different models:
- Architect: Claude Opus (complex reasoning)
- Reviewer: Claude Sonnet (balanced analysis)
- Tester: Claude Haiku (fast execution)
```

**Synergistic Agent Patterns**:
```bash
# Sequential Pipeline
1. @architect designs solution
2. You implement based on design
3. @reviewer checks implementation
4. @tester writes and runs tests
5. @security performs final audit

# Parallel Analysis
"Analyze this codebase for improvements"
→ @reviewer: Code quality issues
→ @security: Vulnerability scan
→ @performance: Bottleneck analysis
→ All run simultaneously, results aggregated

# Specialized Debugging
Error occurs → @debugger analyzes logs → @architect suggests fix → @tester verifies solution
```

**Key Understanding**: MCP extends Claude Code to work with external systems. Custom subagents provide specialized expertise with @-mention support for direct invocation.

### Security Review System (NEW)
Proactive security scanning integrated into workflow:

```bash
# Ad-hoc Security Reviews
/security-review                 # Scan current directory
/security-review src/            # Scan specific directory
/security-review --fix           # Auto-fix found issues

# Common Vulnerabilities Detected
- SQL Injection risks
- XSS vulnerabilities  
- Insecure data handling
- Authentication bypasses
- CSRF attack vectors
- Sensitive data exposure
- Insecure dependencies

# GitHub Actions Integration
# .github/workflows/security.yml
name: Security Review
on: [pull_request]
jobs:
  security:
    runs-on: ubuntu-latest
    steps:
      - uses: anthropics/claude-code-security@v1
        with:
          inline-comments: true
          auto-fix-suggestions: true
```

**Security-First Development Pattern**:
```bash
# Secure Development Workflow
1. Implement feature
2. /security-review              # Check for vulnerabilities
3. "Fix the SQL injection risk"  # Address specific issues
4. @security "Verify fixes"      # Security agent confirmation
5. Git commit with confidence

# Continuous Security Monitoring
npm run dev &                    # Start development
# Set up watch for security issues
"Monitor for security vulnerabilities in real-time"
# Claude watches file changes and alerts on risky patterns
```

**Key Understanding**: Security reviews are now first-class citizens in the development workflow, catching vulnerabilities before they reach production.

### Enhanced File Support (NEW)
Claude Code now handles more file types:

```bash
# PDF Support
@specification.pdf               # Read PDF documents directly
@requirements.pdf                # No conversion needed
@research-paper.pdf              # Extract and analyze content

# Use Cases
- Technical specifications
- API documentation
- Research papers
- Design documents
- Legal requirements
- Architecture diagrams in PDF

# Intelligent PDF Processing
"Implement based on spec.pdf"    # Claude reads PDF, extracts requirements
"Compare our API to api-docs.pdf" # Analyzes differences
"Extract test cases from qa.pdf"  # Pulls actionable items
```

**Key Understanding**: PDF support eliminates conversion steps, allowing direct work with documentation and specifications.

## Development Workflows

### Core Development Approach
The fundamental pattern for any development task:

```bash
# Phase 1: Understand
"Examine existing system, understand constraints"
→ No changes yet, just learning

# Phase 2: Plan
"Create approach for the task"
→ Break down steps, identify risks

# Phase 3: Implement
"Execute the plan incrementally"
→ Small steps with validation

# Phase 4: Verify
"Ensure requirements are met"
→ Test, review, document
```

**Key Patterns**:
- **Explore-Plan-Code**: Understand → Design → Implement
- **Incremental Progress**: Small, validated steps
- **Continuous Validation**: Check work at each stage

### Task Management Patterns
Organize complex work effectively:

```bash
# Breaking down complex tasks
Large Feature → Multiple subtasks → Track progress → Complete systematically

# Progress tracking
- Identify all required steps
- Work on one thing at a time
- Mark completed immediately
- Add discovered tasks as found

# Parallel vs Sequential
Independent tasks → Work in parallel
Dependent tasks → Work sequentially
Mixed tasks → Identify dependencies first
```

**Key Understanding**: Good task management maintains clarity and ensures nothing is missed.

### Quality Assurance Patterns
Ensure high-quality output:

```bash
# Automated validation
1. Format and style consistency
2. Static analysis and linting
3. Type checking where applicable
4. Test coverage verification
5. Security vulnerability scanning
6. Documentation updates

# Manual review perspectives
- Functionality: Does it work as intended?
- Performance: Is it efficient?
- Security: Are there vulnerabilities?
- Maintainability: Is it clean and clear?
- Accessibility: Is it usable by all?
```

**Key Understanding**: Quality emerges from systematic validation at each stage.

## Error Recovery

### Common Patterns
```bash
# Network errors → Retry
Task failed with "connection error"
→ Simply retry the same command (90% success)

# Context overflow → Compact
Too much context accumulated
→ /compact "focus on current task"

# Build failures → Check logs
Hook shows build error
→ Examine specific error, fix root cause

# Lost session → Reconstruct
Session disconnected
→ Analyze current state and reconstruct context
```

**Key Understanding**: Most errors are recoverable. Identify pattern, apply appropriate recovery.

## Practical Examples

### Example 1: Adding Authentication
```bash
# 1. Understand existing system
"Explore the current authentication implementation"

# 2. Plan enhancement
"Plan adding OAuth2 authentication alongside existing system"

# 3. Research if needed
"Research OAuth2 best practices and security"

# 4. Implement incrementally
"Implement OAuth2 authentication with proper error handling"

# 5. Quality assurance
"Review OAuth implementation for security vulnerabilities"
```

### Example 2: Performance Optimization
```bash
# 1. Identify issues
"Analyze components for performance bottlenecks"

# 2. Create optimization plan
TodoWrite([
  {id: "1", content: "Add React.memo to identified components"},
  {id: "2", content: "Implement code splitting"},
  {id: "3", content: "Optimize bundle size"},
  {id: "4", content: "Add lazy loading"}
])

# 3. Execute optimizations
"Implement the identified performance optimizations"

# 4. Validate improvements
"Run performance tests and compare metrics"
```

### Example 3: Batch Component Creation
```bash
# 1. Identify components needed
"List 10 UI components that need creation"

# 2. Parallel creation
"Create all UI components: Button, Input, Select, Checkbox, Radio, Toggle, Slider, DatePicker, TimePicker, ColorPicker"

# 3. Ensure consistency
"Review all components for consistent API and styling"

# 4. Optimize if needed
"Optimize component bundle sizes if too large"
```

### Example 4: Debugging Production Issue
```bash
# 1. Gather context
"Analyze error logs to identify the pattern"

# 2. Reproduce locally
"Set up environment to reproduce the issue"

# 3. Deep investigation
"Debug the issue using error stack trace and available logs"

# 4. Fix and test
"Implement fix based on root cause"
"Review the fix for edge cases and side effects"

# 5. Prevent recurrence
"Add tests to prevent regression"
"Update monitoring to catch similar issues"
```

### Example 5: API Migration
```bash
# 1. Analyze current API
"Map all current API endpoints and their usage patterns"

# 2. Plan migration
TodoWrite([
  {id: "1", content: "Design new API structure"},
  {id: "2", content: "Create compatibility layer"},
  {id: "3", content: "Implement new endpoints"},
  {id: "4", content: "Migrate consumers gradually"},
  {id: "5", content: "Deprecate old endpoints"}
])

# 3. Implementation
"Create new API endpoints while maintaining backward compatibility"

# 4. Testing strategy
"Create comprehensive API tests"
"Test both old and new endpoints"
```

### Example 6: Refactoring Legacy Code
```bash
# 1. Understand current implementation
"Explore legacy module structure and dependencies"

# 2. Create safety net
"Add tests to legacy code before refactoring"

# 3. Incremental refactoring
"Refactor module by module, ensuring functionality is maintained"

# 4. Validate each step
After each refactor:
- Run existing tests
- Check functionality
- Review code quality
```

### Example 7: Setting Up CI/CD
```bash
# 1. Research project needs
"Analyze project requirements for CI/CD pipeline"

# 2. Create pipeline configuration
"Design GitHub Actions workflow for testing and deployment"

# 3. Implement stages
TodoWrite([
  {id: "1", content: "Setup test automation"},
  {id: "2", content: "Add linting and formatting checks"},
  {id: "3", content: "Configure build process"},
  {id: "4", content: "Add deployment steps"},
  {id: "5", content: "Setup notifications"}
])

# 4. Test and refine
"Test pipeline with feature branch"
"Optimize for speed and reliability"
```

### Example 8: Background Development Workflow (NEW)
```bash
# 1. Start all services in background
npm run dev &                    # Frontend dev server
(cd ../api && npm run dev &)     # Backend API server
npm run test:watch &             # Continuous testing

# 2. Set informative status
/statusline "🚀 Full-Stack Dev | 🎯 All Systems Running"

# 3. Monitor everything simultaneously
"Monitor all services for errors"
# Claude watches all background processes

# 4. Fix issues without stopping
"Frontend build error" → Claude checks logs → Fixes issue
"API timeout" → Claude identifies cause → Adjusts config
"Test failure" → Claude updates code → Tests pass

# 5. Graceful shutdown when done
/bashes                          # List all processes
/kill-bash all                   # Stop everything
```

### Example 9: Multi-Repo Synchronization (NEW)
```bash
# 1. Add all related repositories
/add-dir ../shared-types
/add-dir ../frontend
/add-dir ../backend
/add-dir ../mobile

# 2. Synchronize type definitions
"Update TypeScript types across all projects"
@architect "Ensure type consistency"

# 3. Parallel validation
(cd ../frontend && npm run typecheck &)
(cd ../backend && npm run typecheck &)
(cd ../mobile && npm run typecheck &)

# 4. Monitor and fix type errors
"Fix any type mismatches across projects"
# Claude checks all background type checks and fixes issues
```

### Example 10: Security-First Feature Development (NEW)
```bash
# 1. Plan with security in mind
@architect @security "Design user input handling"

# 2. Implement with continuous scanning
"Implement the form validation"
/security-review                 # Check immediately

# 3. Fix vulnerabilities proactively
"Fix the XSS vulnerability in line 42"
@security "Verify the fix is complete"

# 4. Set up continuous monitoring
# GitHub Action for every PR
"Set up automated security scanning for PRs"

# 5. Document security considerations
"Update SECURITY.md with input validation patterns"
```

### Example 11: Long Session with Smart Context (NEW)
```bash
# 1. Start major feature development
"Build complete authentication system"

# 2. Work progresses, context builds
# ... many operations later ...
# Context reaches 6000 tokens

# 3. Intelligent compaction
/microcompact                    # Clears old operations
# Keeps: Current auth work, patterns, recent changes
# Clears: Old file reads, completed searches

# 4. Continue seamlessly
"Add password reset functionality"
# Full context available for current work

# 5. Switch to new feature
/compact "payment integration"   # Full reset for new context
"Implement Stripe payment flow"
```

## Advanced Patterns

### Synergistic Feature Combinations (NEW)
Maximize productivity by combining new features:

```bash
# The Ultimate Dev Setup
# Combines: Background tasks + Status line + Multi-directory + Subagents

# 1. Initialize multi-project workspace
/add-dir ../backend
/add-dir ../frontend
/add-dir ../shared

# 2. Start everything in background
npm run dev &                    # Frontend
(cd ../backend && npm run dev &) # Backend
npm run test:watch &             # Tests
npm run storybook &              # Component library

# 3. Set informative status
/statusline "🚀 $(git branch --show-current) | 📍 $(basename $(pwd)) | ✅ All Systems Go"

# 4. Deploy the agent team
@architect "Review overall system design"
@security "Monitor for vulnerabilities"
@performance "Watch for bottlenecks"

# 5. Work with real-time monitoring
"Build the checkout flow"
# Claude monitors all services, catches errors, suggests fixes
# Agents provide specialized feedback continuously
```

### Intelligent Background Debugging Pattern
```bash
# Self-Healing Development Environment

# 1. Start with monitoring
npm run dev & --verbose          # Extra logging
/bash-output <id> "ERROR|WARN"   # Filter for problems

# 2. Set up auto-recovery
"If the server crashes, restart it automatically"
# Claude monitors, detects crash, fixes cause, restarts

# 3. Learning from failures
"What caused the last 3 crashes?"
# Claude analyzes patterns in background logs
# Updates CLAUDE.md with prevention strategies

# 4. Predictive intervention
"Watch for memory leaks"
# Claude monitors memory usage trends
# Alerts before crash, suggests garbage collection points
```

### Cross-Project Intelligence Network
```bash
# Shared Learning Across Projects

# 1. Connect knowledge bases
/add-dir ~/.claude/global-patterns
/add-dir ./project-a
/add-dir ./project-b

# 2. Extract successful patterns
"What patterns from project-a would benefit project-b?"
@architect "Identify reusable architectures"

# 3. Apply learnings
"Apply the error handling pattern from project-a"
# Claude adapts pattern to new context

# 4. Update global knowledge
"Save this solution to global patterns"
# Available for all future projects
```

### Smart Research System (Multi-Phase)
Sophisticated information gathering through orchestrated agents:

```bash
# Phase 1: Distributed Search (10 agents)
/research:smart-research "topic"
→ Agents search: topic, best practices, tutorials, docs, etc.
→ Output: Deduplicated URLs in .claude/research-output/

# Phase 2: Parallel Content Extraction
→ Batches of 10 WebFetch agents
→ Extract content from each URL
→ Output: Individual content files

# Phase 3: Pairwise Merging
→ Recursive merging: 20→10→5→3→2→1
→ Final output: Comprehensive research report

# Commands
/research:smart-research [topic]
/research:research-status [topic]
/research:research-help
```

**Quality Indicators**:
- 15+ unique high-quality URLs
- 90%+ successful extractions
- Progressive file reduction
- No duplicate information

[NOTE: The following section describes third-party or conceptual systems, not official Claude Code features]

### Smart Flows Architecture (Third-Party/Conceptual)
Advanced multi-agent orchestration concepts:

```bash
# Conceptual Architecture Components
# These describe theoretical or third-party implementations
# Not part of official Claude Code

Queen Agent → Master coordinator concept
Worker Agents → Specialized agent roles
Memory System → Persistent storage patterns
MCP Tools → Extended tool integrations

# Theoretical Operational Modes
Swarm Mode → Quick task coordination
Hive-Mind Mode → Complex project sessions

# Conceptual Features
- Pattern recognition
- Self-organizing architecture
- Collective decision making
- Adaptive learning loops
```

**Key Understanding**: These describe advanced concepts that may be implemented through third-party tools or future features.

[NOTE: This section describes a third-party NPM package, not official Claude Code functionality]

### Sub-Agents System (Third-Party NPM Package)
Extended specialized expertise through external tools:

```bash
# Third-party package installation (not official)
npm install -g @webdevtoday/claude-agents

# Initialize in project
claude-agents init

# Specialized agent types with domains
claude-agents run code-quality --task "Review codebase"
  → Specialized in: Code standards, best practices, refactoring
  
claude-agents run testing --task "Generate test suite"
  → Specialized in: Unit tests, integration tests, TDD
  
claude-agents run development --task "Build feature"
  → Specialized in: Feature implementation, architecture
  
claude-agents run documentation --task "Generate docs"
  → Specialized in: API docs, README, technical writing
  
claude-agents run management --task "Project planning"
  → Specialized in: Task breakdown, estimation, roadmaps

# Integration with slash commands
/agents:code-quality "analyze performance"
/agents:testing "create unit tests"
```

**Key Features**:
- Isolated context management per agent
- Specialized expertise domains
- Integration with slash commands and hooks
- Persistent learning across sessions

**Key Understanding**: Sub-agents provide specialized expertise beyond built-in agents. Each has deep domain knowledge.

### Cognitive Approach
Let intelligence guide rather than rigid rules:

```bash
# Instead of mechanical steps
"We need to implement feature X. What approach makes sense given our constraints?"

# Trust pattern recognition
"This feels like it might have security implications. Let me investigate."

# Adaptive execution
"The simple approach isn't working. Let me try a different strategy."
```

### Smart Research Flow
Research driven by curiosity:

```bash
# Research [topic] following natural intelligence:
# - Follow curiosity about significant patterns
# - Trust judgment on source quality
# - Let insights emerge organically
# - Stop when true understanding achieved
```

### Context-Aware Decisions
Adapt based on project state:

```bash
# Early project → Focus on architecture
# Mid project → Focus on features
# Late project → Focus on optimization
# Maintenance → Focus on reliability

# Let context guide approach
"Given we're in early development, should we optimize now or focus on features?"
```

### Dynamic Perspective Debugging
Generate relevant investigation angles dynamically:

```bash
# Step 1: Generate perspectives
# Issue: [App crashes on large file uploads]
# What are the 3 most relevant perspectives to investigate?

# Example perspectives:
# A. Memory Management Perspective
# B. Network/Infrastructure Perspective
# C. Concurrency/Race Condition Perspective

# Step 2: Parallel investigation
# - Investigate Memory: Check leaks, buffers, OOM
# - Investigate Network: Timeouts, proxies, limits
# - Investigate Concurrency: Race conditions, state

# Step 3: Synthesize findings
# Based on all perspectives:
# 1. What's the root cause?
# 2. What's the minimal fix?
# 3. What are the risks if not fixed?
```

### Cognitive Verification Pattern
Use thoughtful verification instead of mechanical checks:

```bash
# After completing: [task description]
# Result: [what was created/changed]
# 
# Critically verify:
# 1. Does this fully address the original request?
# 2. What might we have missed or misunderstood?
# 3. Are there edge cases not handled?
# 4. Would a developer be satisfied with this?
# 5. Is the quality up to project standards?
# 
# Be skeptical - actively look for problems
```

### Learning Through Reflection
Build knowledge through cognitive reflection:

```bash
# After completing a complex task
[NOTE: /reflect command is conceptual - verify if available]
# After completing a complex task
"What did we learn from implementing [feature]?"

# After resolving a bug
"What was the root cause and how can we prevent similar issues?"

# Weekly meta-reflection
"How can we improve our development process itself?"

# The system learns by thinking about its own performance
```

### Risk Communication Pattern
Always quantify and communicate risks clearly:

```bash
"⚠️ WARNING if you skip the rate limiting fix:
Frequency: Will trigger when >100 users concurrent (daily at peak)
Impact: API server crashes, affecting all users for ~5 minutes
Severity: High (full outage)
Workaround: Scale servers to 2x capacity (costs +$500/month)
Timeline: Safe for 2 weeks, critical before marketing campaign"
```

### Requirement Capture Through Multiple Lenses
Ensure nothing is missed:

```bash
# Analyze the request from multiple angles:
# - List ALL functional requirements from user message
# - List ALL non-functional requirements (performance, security)
# - List ALL implied requirements and best practices

# Synthesis step:
# Merge all requirement lists and verify against original:
# 1. Combine all identified requirements
# 2. Check each word of original was considered
# 3. Create final comprehensive requirement list
```

## Best Practices

### Core Development Principles
1. **Read before Write** - Always understand existing code first
2. **Incremental Progress** - Small, validated steps with continuous testing
3. **Track Progress** - Use TodoWrite for complex tasks
4. **Be Specific** - Detailed prompts yield better results
5. **Break Down Complexity** - Decompose large tasks into manageable steps

### Effective Codebase Understanding
```bash
# Start Broad, Then Narrow
"Explain the overall architecture of this project"
→ "How does the authentication system work?"
→ "Why is this specific function failing?"

# Request Context
"What are the coding conventions in this project?"
"Can you create a glossary of project-specific terminology?"
"Show me similar patterns used elsewhere in the codebase"
```

### Optimal Bug Fixing Workflow
```bash
# Provide Complete Context
- Full error messages and stack traces
- Reproduction steps (specific actions that trigger issue)
- Environment details (browser, OS, versions)
- Specify if issue is intermittent or consistent
- Include relevant logs and configuration

# Example Effective Bug Report:
"The login fails with 'TypeError: Cannot read property id of undefined' 
when clicking submit after entering valid credentials. This happens 
consistently in Chrome 120 but not Firefox. Here's the full stack trace..."
```

### Smart Refactoring Approach
```bash
# Safe Refactoring Pattern:
1. Ask for modern approach explanations
2. Request backward compatibility analysis
3. Refactor incrementally with testing at each step
4. Verify functionality before proceeding

# Example:
"Explain how modern React hooks could improve this class component"
"What are the risks of converting this to hooks?"
"Convert just the state management first, keeping lifecycle methods"
```

### Productivity Optimization Techniques
```bash
# Quick File References
@filename.js          # Reference specific files
@src/components/      # Reference directories
@package.json         # Reference config files

# Efficient Communication
- Use natural language for complex problems
- Leverage conversation context for follow-ups
- Provide complete context for better results

# Advanced Workflows
- Git integration for version control
- Automated validation through hooks
- Build process integration
```

### Leveraging Sub-Agent Capabilities
```bash
# Sub-agents (via MCP and third-party packages)
# Use specialized agents for domain-specific tasks
# Available through external integrations and MCP servers

# Best Practices for Sub-agents:
- Choose agents with expertise matching your task domain
- Understand agent capabilities before delegating
- Provide sufficient context for specialized work
- Verify outputs align with project standards
```

### Quality Assurance Patterns
```bash
# Automated Validation Pipeline
1. Code formatting (prettier, black, gofmt)
2. Linting (eslint, pylint, golangci-lint)
3. Type checking (tsc, mypy, go vet)
4. Unit testing (jest, pytest, go test)
5. Integration testing
6. Security scanning

# Use Hooks for Automation:
PostToolUse → Format and lint changes
SessionStart → Load project context
UserPromptSubmit → Validate request completeness
```

### Efficiency and Performance
```bash
# Batch Similar Operations
- Group related file reads/writes
- Combine related git operations
- Process similar tasks in parallel

# Context Management
- Use /clear to reset when switching contexts
- Leverage @ references for file navigation
- Maintain session continuity for related work

# Error Recovery
- Provide complete error context for debugging
- Use systematic debugging approaches
- Implement progressive error resolution strategies
```

### Integration with Development Workflows
```bash
# Version Control Integration
# Claude Code works naturally with git workflows
# Use for commit message generation, code reviews, conflict resolution

# CI/CD Integration
# Integrate Claude Code into build processes
# Use hooks for automated validation and testing

# IDE Integration
# Available IDE plugins and extensions
# Terminal-based workflow for direct interaction

# MCP Integration
# Connect to external tools and services
# Extend functionality through Model Context Protocol
```

## Quick Reference

### Mode Selection
- Single file → Simple Creation Mode
- Multiple files → Parallel Mode
- Feature → Orchestration Mode
- Research → Research Mode
- Optimize → Optimization Mode
- Review → Review Mode

### Common Workflows
- Git operations - Review, format, test, commit
- Testing - Run tests, check coverage, validate
- Context management - Focus on relevant information
- Requirements - Capture all explicit and implicit needs
- Architecture - Design before implementation
- Development - Incremental implementation
- Research - Investigate thoroughly before deciding

### Automation Points
- After changes - Validate and format
- Before operations - Safety checks
- On input - Enhance context
- On alerts - Monitor and respond
- On completion - Save learnings
- On context change - Optimize focus

### Recovery Actions
- Network error → Retry
- Context overflow → Compact
- Build failure → Check logs
- Lost session → Reconstruct state

### Performance Expectations
[NOTE: These are estimated success rates based on patterns, not official metrics]
- **Simple tasks**: High success rate (estimated)
- **Medium complexity**: Good success rate (estimated)
- **Complex tasks**: Moderate success rate (estimated)
- **Novel problems**: Variable success rate

### Integration Patterns
```bash
# Common integration approaches:
- API integration for programmatic access
- SDK usage for language-specific implementations
- Interactive mode for direct assistance
- Batch processing for multiple tasks
```

## Troubleshooting

### Common Issues & Solutions

#### Connection & Network
```bash
# Error: "Connection error" during execution
Solution: Retry the exact same operation
Success rate: Often succeeds on retry (empirical observation)

# Error: API connection failures
Solutions:
1. Check API key: echo $ANTHROPIC_API_KEY
2. Verify network: ping api.anthropic.com
3. Retry with backoff: claude --retry-max=5
```

#### Context & Memory
```bash
# Error: "Context window exceeded"
Solution 1: /compact "focus on current feature"
Solution 2: claude --max-context=8000
Solution 3: claude --new "Start fresh"

# High memory usage
Solutions:
1. Limit context: claude --max-context=4000
2. Clear session history: claude --clear-history
3. Use streaming: claude --stream
```

#### Agent & Task Issues
```bash
# Error: Task failures
Debugging:
1. Check execution logs
2. Verify available capabilities
3. Test with simpler task

Solutions:
1. Retry with same approach
2. Switch to different cognitive mode
3. Break into smaller tasks
4. Use research mode for investigation
```

#### Hook & Permission Issues
```bash
# Hooks not triggering
Debugging:
1. Verify registration: cat .claude/hooks/settings.json
2. Check permissions: ls -la .claude/hooks/
3. Test manually: bash .claude/hooks/[hook-name].sh

# Permission denied
Solution: claude --grant-permission "file:write"
```

### Diagnostic Commands
```bash
# System health
- Check operational health
- Review configuration
- Validate settings

# Performance
- Profile operations
- Monitor memory usage
- Track performance metrics

# Debugging
- Enable debug mode
- Verbose output
- Trace execution

# Logs
- View execution logs
- Review performance metrics
- Analyze error patterns
```

## Critical Verification Patterns

### Always Verify Completeness
Never trust operations without verification:

```bash
# Document merging - always verify
"Merge documents A and B"
"Verify merge completeness - check no information was lost"

# Code changes - always test
"Apply performance optimization"
"Run tests to confirm no regression"

# Multi-file operations - always validate
"Create 10 components"
"Verify all components created correctly"
```

### Common Pitfalls to Avoid

#### 1. Incomplete Requirement Capture
❌ **Wrong**: Acting on first impression
✅ **Right**: Analyze entire message, capture all requirements

#### 2. Unverified Operations  
❌ **Wrong**: Trust that merge/edit worked
✅ **Right**: Always verify completeness and correctness

#### 3. Insufficient Context
❌ **Wrong**: Minimal context to agents
✅ **Right**: Generous context including patterns and conventions

#### 4. Serial Instead of Parallel
❌ **Wrong**: One task at a time when independent
✅ **Right**: Batch independent tasks (up to 10)

#### 5. Ignoring Error Patterns
❌ **Wrong**: Retry same approach after failure
✅ **Right**: Learn from error and adjust strategy

## Intelligent Log Analysis & Learning

### Logs as Your Second Brain
Logs aren't just for debugging - they're a continuous learning system that makes you smarter over time.

### Log Mining for Pattern Recognition
```bash
# Extract patterns from logs
# Analyze the last 100 operations from logs:
# 1. What tasks succeeded on first try vs needed retries?
# 2. What error patterns keep recurring?
# 3. Which file paths are accessed most frequently?
# 4. What commands have the highest failure rate?
# 5. Which automation points fire most often?
# 
# Create a pattern report and update CLAUDE.md with insights

# Automated pattern extraction hook
# .claude/hooks/log-learning.sh
#!/bin/bash
# Triggers every 50 operations
if [ $(grep -c "operation" ~/.claude/logs/operations.log) -gt 50 ]; then
  # Extract patterns from recent logs:
  # - Success/failure ratios per mode
  # - Common error signatures
  # - Performance bottlenecks
  # - Frequently accessed files
  # Update CLAUDE.md with actionable insights
fi
```

### Performance Intelligence from Logs
```bash
# Track operation timings
grep "duration:" ~/.claude/logs/performance.log | \
  awk '{print $2, $4}' | sort -rnk2 | head -20
# Shows: operation_type duration_ms

# Identify slow operations
# Analyze performance logs to find:
# 1. Operations taking >5 seconds
# 2. Modes with declining success rates
# 3. Memory usage spikes
# 4. Context growth patterns
# 
# Suggest optimizations based on findings

# Real-time performance monitoring
tail -f ~/.claude/logs/performance.log | \
  awk '/duration:/ {if ($4 > 5000) print "⚠️ SLOW:", $0}'
```

### Error Prediction & Prevention
```bash
# Predictive error analysis
# Analyze error logs to predict failures:
# 1. What conditions preceded the last 10 errors?
# 2. Are there warning signs before failures?
# 3. What sequence of operations leads to errors?
# 4. Can we detect problems before they occur?
# 
# Create preventive rules and patterns

# Auto-generate preventive hooks from logs
./scripts/generate-safety-hooks.sh
# Analyzes error patterns and creates PreToolUse hooks
```

### Log-Driven Memory Updates
```bash
# Automatic CLAUDE.md enrichment from logs
# .claude/hooks/log-to-memory.sh
#!/bin/bash
# Runs hourly or after significant operations

echo "📊 Analyzing logs for learnings..."

# Extract successful patterns
grep "SUCCESS" ~/.claude/logs/operations.log | \
  tail -50 | ./scripts/extract-patterns.sh >> .claude/temp/successes.md

# Extract failure patterns  
grep "ERROR\|FAILED" ~/.claude/logs/operations.log | \
  tail -50 | ./scripts/extract-patterns.sh >> .claude/temp/failures.md

# Update CLAUDE.md
# Update CLAUDE.md with patterns from:
# - successes.md (what works)
# - failures.md (what to avoid)
# Keep only high-value, actionable insights
```

### Agent Performance Tracking
```bash
# Mode performance tracking
Track success rates for different cognitive modes:
- Simple Creation Mode: success rate and average time
- Optimization Mode: improvement metrics
- Review Mode: issues caught
- Research Mode: insights discovered

# Performance-based recommendations
Based on performance patterns:
1. Which mode works best for each task type?
2. When to escalate from simple to complex approaches?
3. What patterns lead to failures?

Update mode selection logic based on learnings.
```

### Workflow Optimization from Logs
```bash
# Identify workflow bottlenecks
# Analyze workflow logs to find:
# 1. Longest running operations
# 2. Most frequent operations
# 3. Operations that always occur together
# 4. Unnecessary repeated operations
# 
# Suggest workflow optimizations and create patterns

# Auto-create commands from frequent patterns
grep "SEQUENCE" ~/.claude/logs/workflow.log | \
  ./scripts/detect-patterns.sh | \
  ./scripts/generate-commands.sh > .claude/commands/auto-generated.md
```

### Log Query Commands
```bash
# Custom log analysis commands
/logs:patterns          # Extract patterns from recent logs
/logs:errors           # Analyze recent errors
/logs:performance      # Performance analysis
/logs:agents           # Agent success rates
/logs:learning         # Extract learnings for CLAUDE.md
/logs:predict          # Predict potential issues
/logs:optimize         # Suggest optimizations from logs
```

### Smart Log Rotation with Learning Extraction
```bash
# Before rotating logs, extract learnings
# .claude/hooks/pre-log-rotation.sh
#!/bin/bash
echo "🎓 Extracting learnings before rotation..."

# Comprehensive analysis before we lose the data
# Before rotating logs, extract:
# 1. Top 10 most valuable patterns discovered
# 2. Critical errors that must not repeat
# 3. Performance improvements achieved
# 4. Successful workflow patterns
# 
# Save learnings and update CLAUDE.md with important items

# Then rotate
mv ~/.claude/logs/operations.log ~/.claude/logs/operations.log.old
```

### Log-Based Testing Strategy
```bash
# Generate tests from error logs
# Analyze error logs and create tests that would have caught these issues:
# 1. Extract error conditions from logs
# 2. Generate test cases for each error type
# 3. Create regression tests for fixed bugs
# 4. Add edge cases discovered through failures

# Monitor test coverage gaps
grep "UNCAUGHT_ERROR" ~/.claude/logs/errors.log | \
  ./scripts/suggest-tests.sh > suggested-tests.md
```

### Real-Time Log Monitoring Dashboard
```bash
# Terminal dashboard for live monitoring
watch -n 1 '
echo "=== Claude Code Live Dashboard ==="
echo "Active Agents:" $(ps aux | grep -c "claude-agent")
echo "Recent Errors:" $(tail -100 ~/.claude/logs/errors.log | grep -c ERROR)
echo "Success Rate:" $(tail -100 ~/.claude/logs/operations.log | grep -c SUCCESS)"%"
echo "Avg Response:" $(tail -20 ~/.claude/logs/performance.log | awk "/duration:/ {sum+=\$4; count++} END {print sum/count}")ms
echo "=== Recent Operations ==="
tail -5 ~/.claude/logs/operations.log
'
```

### Log Configuration for Maximum Intelligence
```json
// .claude/settings.json
{
  "logging": {
    "level": "info",
    "capture": {
      "operations": true,
      "performance": true,
      "errors": true,
      "agent_decisions": true,
      "hook_triggers": true,
      "context_changes": true,
      "memory_updates": true
    },
    "analysis": {
      "auto_pattern_extraction": true,
      "error_prediction": true,
      "performance_tracking": true,
      "learning_extraction": true
    },
    "retention": {
      "raw_logs": "7d",
      "extracted_patterns": "permanent",
      "learnings": "permanent"
    }
  }
}
```

**Key Understanding**: Logs are not just records - they're your continuous learning system. Mine them for patterns, predict errors, optimize workflows, and automatically improve your CLAUDE.md. Every operation teaches you something.

## Security Considerations

### Conservative Security Model
Claude Code operates with a conservative, permission-based security model:

```bash
# Trust verification for first-time access
- New codebase → Read-only initially
- Each action type → Explicit permission request
- Sensitive operations → Additional confirmation

# Security layers
1. Permission system (file:read, file:write, bash:execute)
2. Hook validation (PreToolUse safety checks)
3. Command injection detection
4. Fail-closed approach for unrecognized commands
```

### Security Best Practices
```bash
# For hooks
- ⚠️ Validate all inputs before processing
- Never auto-execute destructive commands
- Use principle of least privilege
- Test in sandboxed environment first

# For sensitive data
- Use .claudeignore for sensitive files
- Never hardcode secrets or credentials
- Use environment variables for configuration
- Regularly rotate access tokens

# For operations
- Always verify file paths before operations
- Check command outputs for sensitive data
- Sanitize logs before sharing
- Review automated actions regularly
```

### Audit Trail
```bash
# Claude Code maintains audit trails for:
- Permission grants/revocations
- File modifications
- Command executions
- Hook triggers
- Agent operations

# Access audit logs
[NOTE: Verify these commands exist in your Claude Code version]
claude --show-audit-log
claude --export-audit-log > audit.json
```

## Scripts & Automation Infrastructure

### Scripts as the Nervous System
Scripts connect all components - they're the automation layer that makes everything work seamlessly.

### Core Script Organization
```bash
.claude/scripts/
├── core/                   # Essential system scripts
│   ├── analyze-logs.sh
│   ├── update-memory.sh
│   ├── context-manager.sh
│   └── health-check.sh
├── hooks/                  # Hook-triggered scripts
│   ├── pre-tool-use/
│   ├── post-tool-use/
│   └── triggers.sh
├── patterns/               # Pattern extraction & learning
│   ├── extract-patterns.sh
│   ├── detect-anomalies.sh
│   └── generate-insights.sh
├── optimization/           # Performance & improvement
│   ├── profile-operations.sh
│   ├── optimize-workflow.sh
│   └── cache-manager.sh
├── intelligence/           # Smart analysis scripts
│   ├── predict-errors.sh
│   ├── recommend-agent.sh
│   └── learn-from-logs.sh
└── utilities/              # Helper scripts
    ├── backup-state.sh
    ├── clean-temp.sh
    └── validate-config.sh
```

### Essential Scripts Library

#### 1. Smart Log Analyzer
```bash
#!/bin/bash
# .claude/scripts/core/analyze-logs.sh
# Extracts actionable intelligence from logs

LOG_DIR="${CLAUDE_LOGS:-~/.claude/logs}"
OUTPUT_DIR="${CLAUDE_TEMP:-~/.claude/temp}"

# Extract patterns
extract_patterns() {
    echo "🔍 Analyzing patterns..."
    
    # Success patterns
    grep "SUCCESS" "$LOG_DIR/operations.log" | \
        sed 's/.*\[\(.*\)\].*/\1/' | \
        sort | uniq -c | sort -rn > "$OUTPUT_DIR/success-patterns.txt"
    
    # Error patterns
    grep "ERROR" "$LOG_DIR/operations.log" | \
        sed 's/.*ERROR: \(.*\)/\1/' | \
        sort | uniq -c | sort -rn > "$OUTPUT_DIR/error-patterns.txt"
    
    # Slow operations
    awk '/duration:/ {if ($2 > 5000) print $0}' "$LOG_DIR/performance.log" \
        > "$OUTPUT_DIR/slow-operations.txt"
}

# Generate insights
generate_insights() {
    echo "💡 Generating insights..."
    
    # Analyze pattern files and generate insights:
    # - $OUTPUT_DIR/success-patterns.txt
    # - $OUTPUT_DIR/error-patterns.txt
    # - $OUTPUT_DIR/slow-operations.txt
    # 
    # Create actionable recommendations in $OUTPUT_DIR/insights.md
}

# Update CLAUDE.md if significant patterns found
update_memory() {
    if [ -s "$OUTPUT_DIR/insights.md" ]; then
        echo "📝 Updating memory..."
        # Update CLAUDE.md with insights from $OUTPUT_DIR/insights.md
    fi
}

# Main execution
extract_patterns
generate_insights
update_memory

echo "✅ Log analysis complete"
```

#### 2. Context Optimizer
```bash
#!/bin/bash
# .claude/scripts/core/context-manager.sh
# Intelligently manages context based on current task

# Get current context size
[NOTE: This is a conceptual function - actual implementation may vary]
get_context_size() {
    # Conceptual - verify actual command availability
    claude --show-context-size | grep -o '[0-9]*' | head -1
}

# Analyze what's relevant
analyze_relevance() {
    local TASK="$1"
    
    # Analyze current task: $TASK
    # Current context size: $(get_context_size)
    # 
    # Determine:
    # 1. What context is essential?
    # 2. What can be removed?
    # 3. What should be loaded from memory?
    # 
    # Output recommendations to context-plan.json
}

# Optimize context
optimize_context() {
    local PLAN=".claude/temp/context-plan.json"
    
    if [ -f "$PLAN" ]; then
        # Remove irrelevant context
        local REMOVE=$(jq -r '.remove[]' "$PLAN" 2>/dev/null)
        if [ -n "$REMOVE" ]; then
            /compact "$REMOVE"
        fi
        
        # Load relevant memory
        local LOAD=$(jq -r '.load[]' "$PLAN" 2>/dev/null)
        if [ -n "$LOAD" ]; then
            grep -A5 -B5 "$LOAD" CLAUDE.md > .claude/temp/focused-context.md
            echo "Loaded: $LOAD"
        fi
    fi
}

# Auto-optimize based on context size
[NOTE: Context size threshold is an estimate]
if [ $(get_context_size) -gt THRESHOLD ]; then
    echo "⚠️ Context getting large, optimizing..."
    analyze_relevance "$1"
    optimize_context
fi
```

#### 3. Pattern-to-Hook Generator
```bash
#!/bin/bash
# .claude/scripts/patterns/generate-hooks.sh
# Automatically creates hooks from detected patterns

PATTERNS_FILE="$1"
HOOKS_DIR=".claude/hooks"

generate_hook_from_pattern() {
    local PATTERN="$1"
    local FREQUENCY="$2"
    
    # If pattern occurs frequently, create preventive hook
    if [ "$FREQUENCY" -gt 5 ]; then
        local HOOK_NAME="auto-prevent-$(echo $PATTERN | tr ' ' '-' | tr '[:upper:]' '[:lower:]')"
        
        cat > "$HOOKS_DIR/$HOOK_NAME.sh" << 'EOF'
#!/bin/bash
# Auto-generated hook from pattern detection
# Pattern: $PATTERN
# Frequency: $FREQUENCY

# Check if this pattern is about to occur
if [[ "$1" =~ "$PATTERN" ]]; then
    echo "⚠️ Detected pattern that previously caused issues"
    echo "Applying preventive measures..."
    
    # Add preventive logic here
    exit 1  # Block if dangerous
fi

exit 0
EOF
        chmod +x "$HOOKS_DIR/$HOOK_NAME.sh"
        echo "Generated hook: $HOOK_NAME"
    fi
}

# Process error patterns
while IFS= read -r line; do
    FREQUENCY=$(echo "$line" | awk '{print $1}')
    PATTERN=$(echo "$line" | cut -d' ' -f2-)
    generate_hook_from_pattern "$PATTERN" "$FREQUENCY"
done < "$PATTERNS_FILE"
```

#### 4. Workflow Automation Detector
```bash
#!/bin/bash
# .claude/scripts/intelligence/detect-workflows.sh
# Identifies repeated sequences that should become commands

LOG_FILE="${1:-~/.claude/logs/operations.log}"
MIN_FREQUENCY="${2:-3}"

# Extract command sequences
extract_sequences() {
    # Look for patterns of commands that occur together
    awk '
    BEGIN { sequence = "" }
    /^Task\(/ { 
        if (sequence != "") sequence = sequence " -> "
        sequence = sequence $0
    }
    /^SUCCESS/ {
        if (sequence != "") print sequence
        sequence = ""
    }
    ' "$LOG_FILE" | sort | uniq -c | sort -rn
}

# Generate command from sequence
create_command() {
    local FREQUENCY="$1"
    local SEQUENCE="$2"
    
    if [ "$FREQUENCY" -ge "$MIN_FREQUENCY" ]; then
        local CMD_NAME="workflow-$(date +%s)"
        
        # This sequence occurred $FREQUENCY times:
        # $SEQUENCE
        # 
        # Create a workflow pattern that automates this sequence
        # Save as reusable pattern
    fi
}

# Process sequences
extract_sequences | while read FREQ SEQ; do
    create_command "$FREQ" "$SEQ"
done
```

#### 5. Performance Profiler
```bash
#!/bin/bash
# .claude/scripts/optimization/profile-operations.sh
# Profiles operations and suggests optimizations

profile_operation() {
    local OPERATION="$1"
    local START=$(date +%s%N)
    
    # Execute with profiling
    eval "$OPERATION"
    local EXIT_CODE=$?
    
    local END=$(date +%s%N)
    local DURATION=$((($END - $START) / 1000000))
    
    # Log performance data
    echo "$(date +%Y-%m-%d_%H:%M:%S) | $OPERATION | Duration: ${DURATION}ms | Exit: $EXIT_CODE" \
        >> ~/.claude/logs/performance-profile.log
    
    # Alert if slow
    if [ "$DURATION" -gt 5000 ]; then
        echo "⚠️ Slow operation detected: ${DURATION}ms"
        echo "$OPERATION" >> ~/.claude/temp/slow-operations.txt
    fi
    
    return $EXIT_CODE
}

# Auto-suggest optimizations
suggest_optimizations() {
    if [ -f ~/.claude/temp/slow-operations.txt ]; then
        # Analyze slow operations and suggest optimizations:
        # $(cat slow-operations.txt)
        # 
        # Create optimization recommendations
    fi
}

# Usage: profile_operation "Complex operation"
```

#### 6. Agent Performance Tracker
```bash
#!/bin/bash
# .claude/scripts/intelligence/agent-performance.sh
# Tracks and analyzes agent performance

DB_FILE="${CLAUDE_DB:-~/.claude/performance.db}"

# Initialize database
init_db() {
    sqlite3 "$DB_FILE" << 'EOF'
CREATE TABLE IF NOT EXISTS agent_performance (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    timestamp DATETIME DEFAULT CURRENT_TIMESTAMP,
    agent_type TEXT,
    task_type TEXT,
    duration_ms INTEGER,
    success BOOLEAN,
    error_message TEXT,
    complexity TEXT
);

CREATE INDEX IF NOT EXISTS idx_agent_type ON agent_performance(agent_type);
CREATE INDEX IF NOT EXISTS idx_success ON agent_performance(success);
EOF
}

# Record performance
record_performance() {
    local AGENT="$1"
    local TASK="$2"
    local DURATION="$3"
    local SUCCESS="$4"
    local ERROR="${5:-NULL}"
    local COMPLEXITY="${6:-medium}"
    
    sqlite3 "$DB_FILE" << EOF
INSERT INTO agent_performance (agent_type, task_type, duration_ms, success, error_message, complexity)
VALUES ('$AGENT', '$TASK', $DURATION, $SUCCESS, '$ERROR', '$COMPLEXITY');
EOF
}

# Get best agent for task
recommend_agent() {
    local TASK_TYPE="$1"
    
    sqlite3 "$DB_FILE" << EOF
SELECT agent_type, 
       COUNT(*) as attempts,
       AVG(CASE WHEN success = 1 THEN 100 ELSE 0 END) as success_rate,
       AVG(duration_ms) as avg_duration
FROM agent_performance
WHERE task_type = '$TASK_TYPE'
GROUP BY agent_type
ORDER BY success_rate DESC, avg_duration ASC
LIMIT 1;
EOF
}

# Generate performance report
generate_report() {
    echo "📊 Agent Performance Report"
    echo "=========================="
    
    sqlite3 "$DB_FILE" << 'EOF'
.mode column
.headers on
SELECT agent_type,
       COUNT(*) as total_tasks,
       ROUND(AVG(CASE WHEN success = 1 THEN 100 ELSE 0 END), 2) as success_rate,
       ROUND(AVG(duration_ms), 0) as avg_duration_ms
FROM agent_performance
WHERE timestamp > datetime('now', '-7 days')
GROUP BY agent_type
ORDER BY success_rate DESC;
EOF
}

# Initialize on first run
[ ! -f "$DB_FILE" ] && init_db

# Usage examples
# record_performance "simple-tool-creator" "create_component" 5000 1
# recommend_agent "create_component"
# generate_report
```

#### 7. Memory Deduplication
```bash
#!/bin/bash
# .claude/scripts/utilities/dedupe-memory.sh
# Removes duplicate entries from CLAUDE.md

MEMORY_FILE="${1:-CLAUDE.md}"
BACKUP_FILE="${MEMORY_FILE}.backup"

# Create backup
cp "$MEMORY_FILE" "$BACKUP_FILE"

# Extract and deduplicate sections
deduplicate_section() {
    local SECTION="$1"
    local START_PATTERN="$2"
    local END_PATTERN="$3"
    
    # Extract section
    sed -n "/$START_PATTERN/,/$END_PATTERN/p" "$MEMORY_FILE" > .claude/temp/section.md
    
    # Remove duplicates while preserving order
    awk '!seen[$0]++' .claude/temp/section.md > .claude/temp/section-deduped.md
    
    # Count removed duplicates
    local ORIGINAL=$(wc -l < .claude/temp/section.md)
    local DEDUPED=$(wc -l < .claude/temp/section-deduped.md)
    local REMOVED=$((ORIGINAL - DEDUPED))
    
    if [ "$REMOVED" -gt 0 ]; then
        echo "Removed $REMOVED duplicate lines from $SECTION"
    fi
}

# Process each section
deduplicate_section "Commands" "^## Commands That Work" "^##"
deduplicate_section "Patterns" "^## Patterns to Follow" "^##"
deduplicate_section "Gotchas" "^## ⚠️ Gotchas" "^##"

# Rebuild file
# Rebuild CLAUDE.md from deduplicated sections:
# - Maintain original structure
# - Preserve important context
# - Remove only true duplicates
# - Keep the most recent version of conflicting entries

echo "✅ Memory deduplication complete"
```

### Script Execution Patterns

#### Chaining Scripts for Complex Operations
```bash
#!/bin/bash
# .claude/scripts/core/daily-optimization.sh
# Chains multiple scripts for daily maintenance

echo "🔧 Starting daily optimization..."

# 1. Analyze logs
./scripts/core/analyze-logs.sh

# 2. Extract patterns
./scripts/patterns/extract-patterns.sh

# 3. Generate hooks from patterns
./scripts/patterns/generate-hooks.sh ".claude/temp/error-patterns.txt"

# 4. Detect workflows
./scripts/intelligence/detect-workflows.sh

# 5. Optimize context
./scripts/core/context-manager.sh "daily_maintenance"

# 6. Deduplicate memory
./scripts/utilities/dedupe-memory.sh

# 7. Generate performance report
./scripts/intelligence/agent-performance.sh generate_report

# 8. Update CLAUDE.md with all findings
# Consolidate all optimization findings:
# - Performance report
# - Detected patterns
# - New workflows
# - Optimization suggestions
# 
# Update CLAUDE.md with the most valuable insights

echo "✅ Daily optimization complete"
```

### Script Testing & Validation
```bash
#!/bin/bash
# .claude/scripts/utilities/test-scripts.sh
# Tests all scripts for syntax and basic functionality

test_script() {
    local SCRIPT="$1"
    
    # Syntax check
    if bash -n "$SCRIPT" 2>/dev/null; then
        echo "✅ Syntax OK: $SCRIPT"
    else
        echo "❌ Syntax error: $SCRIPT"
        return 1
    fi
    
    # Dry run test (if script supports --dry-run)
    if grep -q "dry-run" "$SCRIPT"; then
        if "$SCRIPT" --dry-run 2>/dev/null; then
            echo "✅ Dry run OK: $SCRIPT"
        else
            echo "⚠️ Dry run failed: $SCRIPT"
        fi
    fi
}

# Test all scripts
find .claude/scripts -name "*.sh" -type f | while read script; do
    test_script "$script"
done
```

### Script Configuration
```json
// .claude/scripts/config.json
{
  "scripts": {
    "auto_execute": {
      "daily_optimization": "0 2 * * *",
      "log_analysis": "*/30 * * * *",
      "context_cleanup": "0 */4 * * *",
      "performance_report": "0 18 * * 5"
    },
    "thresholds": {
      "context_size_warning": 6000,
      "context_size_critical": 8000,
      "log_rotation_size": "100M",
      "pattern_frequency_min": 3,
      "slow_operation_ms": 5000
    },
    "paths": {
      "logs": "~/.claude/logs",
      "temp": "~/.claude/temp",
      "scripts": "~/.claude/scripts",
      "memory": "./CLAUDE.md"
    }
  }
}
```

**Key Understanding**: Scripts are the automation backbone that connects logs, hooks, agents, and memory into a cohesive intelligence system. They extract patterns, generate automation, optimize performance, and enable the self-improving cycle.

## The Intelligent Development Loop

### Synergistic Workflow Automation
Everything comes together - background tasks, subagents, security scanning, and multi-directory support create an intelligent ecosystem.

### The Enhanced Self-Improving Cycle (NEW)
```bash
# Now with background monitoring and multi-agent intelligence

#!/bin/bash
# Runs continuously in background
npm run monitor & # Custom monitoring script

while true; do
  # 1. OBSERVE - Monitor all background processes
  PATTERNS=$(/bash-output all | ./analyze-patterns.sh)
  
  # 2. LEARN - Multi-agent analysis
  @analyzer "Extract insights from $PATTERNS"
  @architect "Suggest improvements"
  
  # 3. SECURE - Continuous security
  /security-review --continuous &
  
  # 4. ADAPT - Update across all directories
  for dir in $(claude --list-dirs); do
    (cd $dir && update-patterns.sh)
  done
  
  # 5. OPTIMIZE - Smart context management
  if [ $(context-size) -gt 6000 ]; then
    /microcompact
  fi
  
  # 6. PREDICT - Anticipate issues
  @predictor "Analyze trends in background logs"
  
  sleep 3600  # Run hourly
done
```

### The Self-Improving Development Cycle
```bash
# The loop that makes you smarter with every operation
# .claude/workflows/intelligent-loop.sh

#!/bin/bash
# Runs continuously in background

while true; do
  # 1. OBSERVE - Monitor logs for patterns
  PATTERNS=$(./analyze-recent-logs.sh)
  
  # 2. LEARN - Extract insights
  if [ -n "$PATTERNS" ]; then
    # Extract learnings from: $PATTERNS
  fi
  
  # 3. ADAPT - Update strategies
  if [ -f ".claude/temp/new-learnings.md" ]; then
    # Update CLAUDE.md with new learnings
    ./generate-hooks-from-patterns.sh
    ./create-commands-from-workflows.sh
  fi
  
  # 4. OPTIMIZE - Improve performance
  # Optimize frequently used workflows
  
  # 5. PREDICT - Anticipate issues
  # Predict next likely errors from patterns
  
  sleep 3600  # Run hourly
done
```

### Git + Logs + Memory Synergy
```bash
# Understand codebase evolution through git + logs
# Combine git history with operation logs:
# 1. What files change together? (git log --name-only)
# 2. What operations precede commits? (match timestamps)
# 3. What errors occur after specific changes?
# 4. What patterns exist in successful vs failed commits?
# 
# Update CLAUDE.md with codebase evolution patterns

# Auto-document changes in CLAUDE.md
# .claude/hooks/post-commit.sh
#!/bin/bash
CHANGED_FILES=$(git diff --name-only HEAD~1)
# Document in CLAUDE.md:
# - Files changed: $CHANGED_FILES
# - Patterns observed during development
# - Any errors encountered and how they were fixed
# - New commands or workflows discovered
```

### Test Generation from Logs + Coverage
```bash
# Intelligent test creation from multiple sources
# Generate tests by combining:
# 1. Error patterns from logs (what broke)
# 2. Code coverage gaps (what's untested)
# 3. User interaction patterns (common operations)
# 4. Edge cases discovered through failures
# 
# Create comprehensive test suite targeting weak spots

# Continuous test improvement
# .claude/hooks/test-enhancer.sh
#!/bin/bash
COVERAGE=$(npm run coverage --silent | grep "Statements" | awk '{print $3}')
if [ "${COVERAGE%\%}" -lt 80 ]; then
  # Analyze logs for uncaught errors in uncovered code
  # Generate tests for the top 5 risk areas
fi
```

### Proactive Maintenance System
```bash
# Predict and prevent issues before they occur
# .claude/commands/proactive/maintenance.md
---
allowed-tools: Task, Read, Grep, TodoWrite
description: Proactive system maintenance
---

# Proactive Maintenance

## Task
Analyze system health indicators:

1. Log analysis for warning signs:
   - Increasing error rates
   - Performance degradation
   - Memory growth patterns
   
2. Code analysis for risk areas:
   - Complex functions (cyclomatic complexity >10)
   - Files with high churn rate
   - Dependencies with vulnerabilities
   
3. Create preventive tasks:
   - Refactor risky code
   - Add missing tests
   - Update dependencies
   - Optimize slow operations

TodoWrite([
  {id: "1", content: "Address high-risk areas", status: "pending"},
  {id: "2", content: "Prevent predicted failures", status: "pending"}
])
```

### Cross-Session Intelligence Network
```bash
# Build institutional knowledge across all sessions
# .claude/intelligence/network.json
{
  "shared_learnings": {
    "error_patterns": {
      "database_timeout": {
        "frequency": 23,
        "solution": "Add connection pooling",
        "prevention": "Monitor connection count"
      }
    },
    "successful_patterns": {
      "parallel_testing": {
        "success_rate": "95%",
        "time_saved": "60%",
        "command": "npm run test:parallel"
      }
    },
    "workflow_optimizations": {
      "discovered": 47,
      "implemented": 32,
      "time_saved_daily": "2.5 hours"
    }
  }
}

# Query shared intelligence
# Check shared intelligence for:
# 1. Has anyone solved this error before?
# 2. What's the most efficient workflow for this task?
# 3. What patterns should I watch for?
```

### Adaptive Agent Selection
```bash
# Dynamic agent selection based on real performance
# .claude/hooks/smart-agent-selector.sh
#!/bin/bash
TASK_TYPE=$1
COMPLEXITY=$2

# Query performance database
BEST_AGENT=$(sqlite3 ~/.claude/performance.db "
  SELECT agent_type, AVG(success_rate) as avg_success
  FROM agent_performance
  WHERE task_type = '$TASK_TYPE'
  AND complexity = '$COMPLEXITY'
  GROUP BY agent_type
  ORDER BY avg_success DESC
  LIMIT 1
")

echo "Recommended agent: $BEST_AGENT"

# Auto-escalation logic
if [ "$BEST_AGENT_SUCCESS" -lt 70 ]; then
  echo "Low success predicted, escalating to tool-orchestrator"
  BEST_AGENT="tool-orchestrator"
fi
```

### Intelligent Context Management
```bash
# Smart context optimization based on task
# Analyze current context and task requirements:
# 1. What context is essential for this task?
# 2. What can be safely compacted?
# 3. What should be loaded from memory?
# 4. What related context might be helpful?
# 
# Optimize context for maximum relevance and minimum size

# Context-aware memory loading
# .claude/hooks/context-optimizer.sh
#!/bin/bash
CURRENT_TASK=$(grep "current_task" ~/.claude/state.json)
RELEVANT_MEMORY=$(./find-relevant-memory.sh "$CURRENT_TASK")

# Load only relevant sections of CLAUDE.md
grep -A5 -B5 "$CURRENT_TASK" CLAUDE.md > .claude/temp/focused-memory.md
echo "Loaded focused context for: $CURRENT_TASK"
```

### The Ultimate Synergy: Self-Organizing System
```bash
# The system that improves itself
# .claude/intelligence/self-organize.sh
#!/bin/bash

# Daily self-improvement routine
# Daily self-organization tasks:
# 
# 1. ANALYZE performance over last 24 hours:
#    - What worked well?
#    - What failed repeatedly?
#    - What took too long?
# 
# 2. OPTIMIZE based on analysis:
#    - Create shortcuts for frequent operations
#    - Fix recurring errors
#    - Streamline slow workflows
# 
# 3. LEARN and document:
#    - Update CLAUDE.md with insights
#    - Create new patterns for common workflows
#    - Generate preventive measures
# 
# 4. PREPARE for tomorrow:
#    - Predict likely tasks from patterns
#    - Pre-load relevant context
#    - Set up optimized environment
# 
# 5. SHARE learnings:
#    - Export valuable patterns
#    - Update knowledge base
#    - Create reusable components
# 
# This makes tomorrow better than today, automatically
```

### Metrics-Driven Evolution
```bash
# Track improvement over time
# .claude/metrics/evolution.json
{
  "performance_evolution": {
    "week_1": {
      "avg_task_time": "15min",
      "success_rate": "75%",
      "errors_per_day": 12
    },
    "week_4": {
      "avg_task_time": "8min",
      "success_rate": "92%",
      "errors_per_day": 3
    },
    "improvements": {
      "speed": "+87.5%",
      "reliability": "+22.7%",
      "error_reduction": "-75%"
    }
  },
  "learned_patterns": 247,
  "automated_workflows": 43,
  "time_saved_monthly": "40 hours"
}
```

**Key Understanding**: The Intelligent Development Loop now operates in real-time with background monitoring, multi-agent collaboration, and continuous security scanning. Each iteration makes the system more capable.

### Real-World Power Workflows (NEW)
Practical combinations that multiply productivity:

```bash
# 1. The Debugger's Dream
npm run dev & npm run test:watch &
/statusline "🕵️ Debugging Mode"
"Why is user authentication failing?"
# Claude checks both server logs AND test output
# Correlates errors across services
# Identifies root cause in middleware
# Fixes issue without stopping either service

# 2. The Security-First Pipeline
/security-review --watch &       # Continuous scanning
@security "Monitor all file changes"
"Implement user input form"
# Real-time vulnerability detection
# Immediate alerts on risky patterns
# Automatic fix suggestions

# 3. The Monorepo Master
/add-dir packages/*              # Add all packages
for pkg in packages/*; do
  (cd $pkg && npm run build &)  # Build all in parallel
done
"Optimize build performance across all packages"
# Claude monitors all builds simultaneously
# Identifies common bottlenecks
# Applies fixes across packages

# 4. The Migration Maestro
/add-dir ../old-system
/add-dir ../new-system
@architect "Plan migration strategy"
"Migrate authentication from old to new system"
# Reads old implementation
# Adapts to new architecture
# Preserves business logic
# Updates tests automatically

# 5. The Performance Hunter
npm run dev & npm run perf:monitor &
/statusline "⚡ Performance Mode"
@performance "Watch for bottlenecks"
"Why is the dashboard slow?"
# Analyzes performance logs
# Identifies render bottlenecks
# Suggests React.memo locations
# Implements and measures improvement
```

## Cognitive Intelligence Patterns

### Dynamic Intent Recognition
Understanding what users really need, not just what they ask for:

```bash
# Flexible interpretation based on context
"Make it faster" → Could mean:
  - Optimize performance (if discussing slow feature)
  - Speed up development (if discussing timeline)
  - Improve response time (if discussing API)
  - Reduce build time (if discussing CI/CD)

# Development vs Normal Chat Separation
/dev "implement auth" → Full development workflow with research, planning, implementation
"how does OAuth work?" → Educational explanation without implementation
```

**Key Pattern**: Read between the lines. Users often describe symptoms, not root causes. "It's broken" might mean performance issues, logic errors, or UX problems.

### Multi-Angle Requirement Capture
Never trust a single interpretation. Always analyze from multiple perspectives:

```bash
# For any request, consider:
1. What's explicitly asked → "Add a login button"
2. What's implied → Need auth system, session management, security
3. What's necessary for production → Error handling, loading states, accessibility
4. What could break → Network failures, invalid credentials, CSRF attacks
5. What depends on this → User profiles, permissions, data access
```

**Synergy**: This combines with intent recognition - understanding the "why" helps capture hidden requirements.

### Cognitive Load Management
Recognize when complexity is overwhelming progress:

```bash
# Natural indicators (no metrics needed):
- "We keep coming back to the same error" → Step back, try different approach
- "Too many files are changing" → Break into smaller commits
- "I'm losing track of what we're doing" → Summarize and refocus
- "Everything seems interconnected" → Map dependencies first
```

**Application**: Works for any project - when confusion builds, simplify. When errors repeat, change strategy.

### Before I Code: Pre-Implementation Thinking
Natural pre-mortem analysis before diving into implementation:

```bash
# Before starting ANY task, ask yourself:
1. Am I building, fixing, or exploring?
   → Building: Use existing patterns first
   → Fixing: Read complete context, trace systematically  
   → Exploring: Open-ended investigation, capture learnings

2. What could go wrong?
   → Common failure modes for this type of task
   → Dependencies that might not exist
   → Edge cases that break assumptions

3. What patterns have worked before?
   → Check if similar problems were solved
   → Reuse proven approaches
   → Avoid previously failed attempts

4. What's my safety net?
   → How will I know if something breaks?
   → Can I test this in isolation?
   → Is there a rollback plan?

# Example: "Implement OAuth"
"What could go wrong?"
→ Token storage vulnerabilities
→ Session hijacking risks
→ Refresh token rotation issues
→ CSRF attack vectors

"What assumptions am I making?"
→ Users have modern browsers
→ Network is reliable
→ Third-party service is available
→ User understands OAuth flow

# The Approval Pattern (from codebase assistant):
Never modify directly, always:
1. Show what will change (diff view)
2. Explain why these changes
3. Wait for explicit approval
4. Create backup before applying
5. Provide rollback option
```

**Key Pattern**: Think → Map → Code, not Code → Debug → Refactor. This isn't a checklist - it's natural foresight.

### Smart Problem Decomposition
Break complex problems naturally along their fault lines:

```bash
# Recognize natural boundaries:
"Build a dashboard" → Automatically decompose:
  - Data layer (API, state management)
  - Presentation layer (components, styling)  
  - Business logic (calculations, transformations)
  - Infrastructure (routing, permissions)

# Find parallelizable work:
Independent: Components A, B, C → Can do simultaneously
Dependent: Auth → Profile → Settings → Must be sequential
```

### Adaptive Intelligence Modes
Switch cognitive approach based on task type:

```bash
# Building Mode (Creating new functionality):
- Focus on: Clean implementation, existing patterns
- Approach: Think → Map → Code
- Verify: Does it follow established patterns?

# Debugging Mode (Finding and fixing issues):
- Focus on: Complete context, systematic tracing
- Approach: Reproduce → Isolate → Fix → Verify
- Verify: Is the root cause addressed?

# Optimizing Mode (Improving performance):
- Focus on: Measure first, specific bottlenecks
- Approach: Profile → Identify → Optimize → Measure
- Verify: Did performance actually improve?

# Exploring Mode (Research and discovery):
- Focus on: Open-ended investigation, pattern discovery
- Approach: Broad search → Pattern recognition → Synthesis
- Verify: What insights emerged?

# Reviewing Mode (Quality assurance):
- Focus on: Security, performance, maintainability
- Approach: Systematic checks → Risk assessment → Recommendations
- Verify: Are all concerns addressed?
```

**Mode Selection**: Let the task nature guide your mode, not rigid rules. "Fix login bug" → Debugging mode. "Make dashboard faster" → Optimizing mode.

### Intelligent Context Switching
Adapt focus based on current task:

```bash
# Context shapes attention:
Debugging → Focus on: recent changes, error patterns, system logs
Building → Focus on: requirements, patterns, reusable code
Reviewing → Focus on: security, performance, maintainability
Learning → Focus on: concepts, patterns, best practices
```

**Synergy**: Adaptive modes + context switching = right mindset for each task.

### Pattern Recognition Through Failure
Learn from attempts without creating rigid rules:

```bash
# Adaptive learning:
Error occurs once → Note it
Error occurs twice → Consider pattern
Error occurs thrice → "This approach isn't working, let's try..."

# Smart escalation:
Simple retry → Retry with logging → Different approach → Ask for help
```

### Living Intelligence Loop
Track what's working and what's not to continuously improve:

```bash
# What's Working (Reinforce these):
- Pattern that solved similar problem → Use again
- Approach that prevented errors → Make default
- Tool combination that saved time → Document for reuse

# What Failed Recently (Avoid these):
- Partial context causing errors → Read complete files
- Assumptions that were wrong → Verify first
- Patterns that didn't scale → Find alternatives

# Core Principles (Never compromise):
- Security considerations → Always think "what could an attacker do?"
- User experience → Small improvements compound
- Code quality → Technical debt slows everything
```

**The Force Multipliers**:
- Think → Map → Code (not Code → Debug → Refactor)
- Existing patterns first (not reinvent every time)
- Complete context first (not partial understanding)
- Insight capture after complex work (not forget learnings)

### Continuous Reflection Loop
After tasks, naturally consider improvements:

```bash
# Quick reflection points:
After implementation: "What patterns emerged?"
After debugging: "What was the root cause?"
After optimization: "What made the difference?"
After surprises: "What did I learn?"

# Apply learnings immediately:
"Last time this was slow because of X, let me check for that first"
"This pattern prevented 3 bugs, make it the default approach"
"This assumption was wrong before, verify it this time"
```

### Intent-Based Parallelization
Recognize when things can happen simultaneously without explicit instruction:

```bash
# Natural parallel recognition:
"Set up the project" → Simultaneously:
  - Install dependencies
  - Set up linting
  - Configure testing
  - Create folder structure

"Review the codebase" → Parallel analysis:
  - Security vulnerabilities
  - Performance bottlenecks
  - Code quality issues
  - Missing tests
```

### Smart Defaults Without Assumptions
Recognize common patterns but verify:

```bash
# Intelligent defaults:
React project detected → Likely needs: routing, state management, API calls
BUT verify: "I see this is React. Will you need routing and state management?"

API endpoint created → Likely needs: validation, error handling, auth
BUT confirm: "Should this endpoint require authentication?"

# Context priority for understanding (from codebase assistant):
When analyzing code, prioritize context in this order:
1. Current file content (immediate context)
2. Current file's dependencies (what it needs)
3. Files that depend on current (impact radius)
4. Related files by naming/path (conceptual siblings)
5. Project overview (broader context)
```

### Contextual Focus Adaptation
Mental model adjusts to domain:

```bash
# Domain-driven attention:
Frontend work → "How will users interact with this?"
Backend work → "How will this scale?"
Database work → "What about data integrity?"
Security work → "What could an attacker do?"
```

**Synergy**: Contextual focus + smart defaults = right concerns at the right time.

### Learning From Surprises
When unexpected things happen, update understanding:

```bash
# Surprise-driven learning:
"Interesting, that didn't work as expected..."
→ Investigate why
→ Update mental model
→ Remember for similar situations
→ Share if valuable: "Note: In this framework, X behaves differently"

# Save surprises for future:
Create mental note: "In this codebase, middleware runs in reverse order"
Apply later: "Since middleware is reverse here, let me adjust the sequence"

# Knowledge persistence pattern (from codebase assistant):
When you learn something important about a codebase:
1. Document it immediately (comments, README, or project notes)
2. Include the "why" not just the "what"
3. Add examples of correct usage
4. Note common mistakes to avoid
5. Update relevant summaries/documentation
```

### Completeness Verification
Always double-check nothing was missed:

```bash
# Natural completeness check:
Before marking done, ask yourself:
- Did I address what they actually wanted?
- Will this work in real usage?
- Are edge cases handled?
- Is there something they forgot to mention but need?

# Proactive additions:
"I've added the login button as requested. I also included:
- Loading state while authenticating
- Error message display
- Disabled state during submission
- Keyboard navigation support"
```

### Adaptive Complexity Handling
Scale approach to match problem complexity:

```bash
# Complexity-driven approach:
Trivial (typo fix) → Just fix it
Simple (add button) → Quick implementation
Medium (new feature) → Plan, implement, test
Complex (architecture change) → Research, design, prototype, implement, migrate
Unknown → Explore to assess, then choose approach

# Automatic scaling:
Start simple, escalate if needed
Never over-engineer trivial tasks
Never under-plan complex ones
```

### Recovery Intelligence
When things go wrong, recover gracefully:

```bash
# Smart recovery without panic:
1. "What do we know for sure?" → Establish facts
2. "What's the smallest step forward?" → Find progress path
3. "What assumption might be wrong?" → Question basics
4. "What would definitely work?" → Find solid ground

# Recovery patterns:
Lost context → Reconstruct from recent actions
Broken state → Revert to last working version
Unclear requirements → Ask clarifying questions
Repeated failures → Try fundamentally different approach
```

### Instant Decision Trees
Quick decision paths for common scenarios:

```bash
# "Something's not working"
→ Can I reproduce it? → Yes: Debug systematically / No: Gather more info
→ Did it work before? → Yes: Check recent changes / No: Check assumptions
→ Is error message clear? → Yes: Address directly / No: Trace execution

# "Need to add new feature"
→ Similar feature exists? → Yes: Follow that pattern / No: Research best practices
→ Touches existing code? → Yes: Understand it first / No: Design in isolation
→ Has complex logic? → Yes: Break down first / No: Implement directly

# "Code seems slow"
→ Measured it? → No: Profile first / Yes: Continue
→ Know the bottleneck? → No: Find it / Yes: Continue
→ Have solution? → No: Research / Yes: Implement and measure again

# "Not sure what user wants"
→ Can I clarify with them? → Yes: Ask specific questions / No: Make safe assumptions
→ Is there a working example? → Yes: Follow it / No: Create prototype
→ Are there risks? → Yes: List them explicitly / No: Proceed with basics
```

**Key Pattern**: Don't overthink - follow the tree to quick decisions.

## Synergistic Application

### How Patterns Amplify Each Other

**Learning Cascade**: 
- Surprise → Reflection → Updated defaults → Better intent recognition
- Each surprise makes future predictions more accurate

**Context Harmony**:
- Intent recognition → Appropriate context → Focused attention → Better solutions
- Understanding "why" shapes "how" and "what"

**Complexity Navigation**:
- Decomposition → Parallelization → Load management → Efficient execution
- Breaking down problems enables parallel work and reduces cognitive load

**Continuous Improvement Loop**:
- Attempt → Failure recognition → Reflection → Learning → Better next attempt
- Each cycle improves all patterns

### Universal Project Boost

These patterns work synergistically across any project:

1. **Startup Project**: Smart defaults accelerate setup, adaptive complexity prevents over-engineering
2. **Legacy Codebase**: Learning from surprises builds understanding, context switching navigates complexity
3. **Bug Fixing**: Failure patterns guide debugging, recovery intelligence prevents panic
4. **Feature Development**: Requirement capture ensures completeness, decomposition enables progress
5. **Performance Work**: Contextual focus on metrics, reflection captures what worked
6. **Team Projects**: Intent recognition improves communication, completeness verification prevents gaps

## Remember
- You're an intelligent agent, not a mechanical executor
- Context and understanding matter more than rigid processes
- Quality emerges from good patterns, not just validation
- Efficiency comes from smart orchestration, not just speed
- Trust your cognitive abilities while using tools effectively
- **Always verify** - Never assume operations completed correctly
- **Be thorough** - Capture all requirements, explicit and implicit
- **Learn continuously** - Each interaction improves future performance
- **Security first** - Conservative approach protects both user and system
- **Adapt naturally** - Let patterns guide you, not rules
- **Learn from surprises** - Unexpected outcomes are learning opportunities
- **Think in synergies** - Patterns amplify each other
- **Embrace background work** - Let long tasks run without blocking
- **Leverage specialization** - Use subagents for their expertise
- **Monitor actively** - Watch background processes for insights
- **Compact intelligently** - Use microcompact to extend sessions
- **Work cross-boundary** - Multi-directory enables complex workflows
- **Scan proactively** - Security reviews prevent vulnerabilities

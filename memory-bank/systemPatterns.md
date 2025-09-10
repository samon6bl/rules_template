# System Patterns - AI Coding Rules Template

## System Architecture

### Core Components

#### 1. Rule System Architecture
```
┌─────────────────────────────────────────────────────────────┐
│                    Universal Rule Engine                     │
├─────────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐       │
│  │   Cursor    │  │   CLINE     │  │   RooCode   │       │
│  │   Rules     │  │   Rules     │  │   Rules     │       │
│  └─────────────┘  └─────────────┘  └─────────────┘       │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐       │
│  │  Windsurf   │  │    Chat     │  │   Write     │       │
│  │   Rules     │  │   Mode      │  │   Mode      │       │
│  └─────────────┘  └─────────────┘  └─────────────┘       │
└─────────────────────────────────────────────────────────────┘
```

#### 2. Memory Bank Hierarchy
```
┌─────────────────────────────────────────────────────────────┐
│                    Memory Bank System                        │
├─────────────────────────────────────────────────────────────┤
│  ┌─────────────────────┐  ┌─────────────────────┐         │
│  │   Project Brief     │  │   Product Context   │         │
│  │   (Foundation)      │  │   (Why & How)       │         │
│  └──────────┬──────────┘  └──────────┬──────────┘         │
│             │                         │                      │
│  ┌──────────▼──────────┐  ┌──────────▼──────────┐         │
│  │  System Patterns    │  │  Technical Context  │         │
│  │  (Architecture)     │  │  (Tech Stack)       │         │
│  └──────────┬──────────┘  └──────────┬──────────┘         │
│             │                         │                      │
│  ┌──────────▼─────────────────────────▼──────────┐         │
│  │            Active Context                       │         │
│  │         (Current Work Focus)                    │         │
│  └─────────────────────┬──────────────────────────┘         │
│                        │                                    │
│  ┌─────────────────────▼──────────────────────────┐         │
│  │              Progress Tracker                   │         │
│  │          (What Works & What's Left)            │         │
│  └─────────────────────────────────────────────────┘         │
└─────────────────────────────────────────────────────────────┘
```

## Key Technical Decisions

### 1. Cross-Platform Compatibility
- **Decision**: Use symbolic links to maintain single source of truth
- **Rationale**: Prevents duplication and ensures consistency across platforms
- **Implementation**: `.cursor/rules/` contains original files, other platforms use symbolic links

### 2. Memory Bank Structure
- **Decision**: Hierarchical documentation following software engineering best practices
- **Rationale**: Provides clear context flow from high-level requirements to implementation details
- **Implementation**: Core files build upon each other in logical sequence

### 3. Mode-Based Optimization
- **Decision**: Separate modes for different task types (Chat, Write, MCP)
- **Rationale**: Optimizes token usage by loading only relevant context
- **Implementation**: Platform-specific mode configurations with minimal system prompts

### 4. Automatic Documentation Updates
- **Decision**: Mandate documentation updates after every significant change
- **Rationale**: Ensures memory bank stays current and useful
- **Implementation**: Built into workflow rules for planning, implementation, and debugging

## Design Patterns in Use

### 1. Observer Pattern
- **Application**: Documentation updates triggered by code changes
- **Benefit**: Ensures memory bank remains synchronized with project state

### 2. Strategy Pattern
- **Application**: Different modes (Chat, Write, MCP) for different task types
- **Benefit**: Optimized performance for specific use cases

### 3. Template Method Pattern
- **Application**: Standardized workflows for planning, implementation, and debugging
- **Benefit**: Consistent approach across different projects and platforms

### 4. Facade Pattern
- **Application**: Unified interface for different AI coding platforms
- **Benefit**: Simplified usage regardless of underlying platform

## Component Relationships

### Rule System Components
```
Rules (Base) ──┬──> Plan (Workflow)
               ├──> Implement (Code)
               ├──> Debug (Troubleshooting)
               └──> Memory (Documentation)
```

### Memory Bank Components
```
Project Brief ──┬──> Product Context
                ├──> System Patterns
                ├──> Technical Context
                └──> Active Context ──> Progress Tracker
```

## Critical Implementation Paths

### 1. Rule Loading Sequence
1. **Base Rules**: Load universal rules applicable to all platforms
2. **Platform Rules**: Load platform-specific configurations
3. **Mode Rules**: Load task-type specific optimizations
4. **Project Rules**: Load project-specific customizations

### 2. Memory Bank Access Pattern
1. **Project Brief**: Foundation context for all decisions
2. **Product Context**: Understanding of project purpose and goals
3. **System Patterns**: Technical architecture and design decisions
4. **Technical Context**: Implementation details and constraints
5. **Active Context**: Current work focus and recent changes
6. **Progress Tracker**: Status and remaining work

### 3. Workflow Execution Flow
1. **Planning Phase**: Requirements gathering and solution design
2. **Implementation Phase**: Code development with testing
3. **Documentation Phase**: Memory bank updates and progress tracking
4. **Validation Phase**: Quality assurance and user validation

## System Interfaces

### AI Assistant Interface
- **Input**: User requests, project context, platform constraints
- **Processing**: Rule application, memory bank consultation, workflow execution
- **Output**: Code changes, documentation updates, progress reports

### Memory Bank Interface
- **Read Access**: Context retrieval for decision making
- **Write Access**: Documentation updates after changes
- **Validation**: Ensures consistency across all memory files

### Platform Interface
- **Rule Translation**: Convert universal rules to platform-specific format
- **Mode Switching**: Handle transitions between different task modes
- **Context Synchronization**: Maintain consistency across platform switches

## Dependencies

### Internal Dependencies
- Memory Bank files must maintain hierarchical consistency
- Rule files must follow platform-specific syntax requirements
- Workflow steps must execute in proper sequence

### External Dependencies
- AI coding platform APIs and capabilities
- File system access for documentation storage
- Symbolic link support for cross-platform compatibility

## Error Handling Patterns

### 1. Graceful Degradation
- If platform-specific features fail, fall back to universal rules
- If memory bank is unavailable, proceed with basic context
- If mode switching fails, continue with current mode

### 2. Recovery Mechanisms
- Automatic backup of memory bank files before changes
- Rollback capability for failed implementations
- Fallback documentation when primary sources are unavailable

### 3. Validation Checks
- Syntax validation for rule files
- Consistency checks for memory bank hierarchy
- Platform compatibility verification

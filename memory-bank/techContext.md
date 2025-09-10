# Technical Context - AI Coding Rules Template

## Technologies Used

### Core Technologies
1. **Markdown**: Primary documentation format for all memory bank files
2. **Mermaid**: Diagram generation for architecture and workflow visualization
3. **Symbolic Links**: Cross-platform file system feature for rule sharing
4. **JSON**: Configuration files for platform-specific settings
5. **YAML**: Alternative configuration format where supported

### Platform-Specific Technologies
1. **Cursor**: `.cursorrules` files (deprecated) and `.cursor/rules/` directory structure
2. **CLINE**: `.clinerules/` directory with subdirectories for different modes
3. **RooCode**: `.roo/` directory with mode-specific rule files
4. **Windsurf**: `.windsurfrules` file-based configuration

## Development Setup

### Directory Structure Requirements
```
project-root/
├── .cursor/rules/          # Cursor-specific rules (original files)
├── .clinerules/            # CLINE-specific rules (symbolic links)
│   ├── rules/              # Base rules
│   ├── PLAN/               # Planning mode rules
│   └── ACT/                # Implementation mode rules
├── .roo/                   # RooCode-specific rules (symbolic links)
│   ├── rules/              # Base rules
│   ├── rules-architect/    # Planning mode rules
│   ├── rules-code/         # Implementation mode rules
│   └── rules-debug/        # Debugging mode rules
├── docs/                   # Project documentation
│   ├── literature/         # Research and literature
│   ├── architecture.md     # System architecture
│   ├── technical.md        # Technical specifications
│   └── product_requirement_docs.md  # Product requirements
├── tasks/                  # Task management
│   ├── rfc/                # Request for comments
│   ├── active_context.md   # Current work context
│   └── tasks_plan.md       # Task backlog and progress
├── memory-bank/            # AI assistant memory (this directory)
└── src/                    # Source code
```

### Symbolic Link Setup
```bash
# Create symbolic links for cross-platform compatibility
# From .cursor/rules/ to other platforms

# CLINE symbolic links
ln -s ../.cursor/rules/memory.mdc .clinerules/rules/memory.mdc
ln -s ../.cursor/rules/directory-structure.mdc .clinerules/rules/directory-structure.mdc
ln -s ../.cursor/rules/rules.mdc .clinerules/rules/rules.mdc
ln -s ../.cursor/rules/plan.mdc .clinerules/PLAN/plan.mdc
ln -s ../.cursor/rules/implement.mdc .clinerules/ACT/implement.mdc
ln -s ../.cursor/rules/debug.mdc .clinerules/ACT/debug.mdc

# RooCode symbolic links
ln -s ../.cursor/rules/memory.mdc .roo/rules/memory.mdc
ln -s ../.cursor/rules/directory-structure.mdc .roo/rules/directory-structure.mdc
ln -s ../.cursor/rules/rules.mdc .roo/rules/rules.mdc
ln -s ../.cursor/rules/plan.mdc .roo/rules-architect/plan.mdc
ln -s ../.cursor/rules/implement.mdc .roo/rules-code/implement.mdc
ln -s ../.cursor/rules/debug.mdc .roo/rules-debug/debug.mdc
```

## Key Technical Decisions

### 1. Documentation Format Choice
- **Decision**: Use Markdown for all documentation
- **Rationale**: Universal format supported by all platforms, easy to read/write, supports Mermaid diagrams
- **Trade-offs**: Less structured than XML/JSON, but more human-readable

### 2. Symbolic Link Architecture
- **Decision**: Use symbolic links for cross-platform rule sharing
- **Rationale**: Maintains single source of truth, reduces maintenance overhead
- **Trade-offs**: Requires symbolic link support, may not work on all file systems

### 3. Hierarchical Memory Structure
- **Decision**: Use hierarchical documentation structure
- **Rationale**: Follows software engineering best practices, provides clear context flow
- **Trade-offs**: More complex to maintain, requires consistent updates

### 4. Mode-Based Optimization
- **Decision**: Separate modes for different task types
- **Rationale**: Optimizes token usage, provides focused context
- **Trade-offs**: Requires mode switching logic, may fragment context

## Technical Constraints

### 1. Platform Limitations
- **Cursor**: Limited to `.cursor/rules/` directory structure
- **CLINE**: No native mode support, requires workaround
- **RooCode**: Mode support through directory structure
- **Windsurf**: Single file configuration limit

### 2. File System Requirements
- **Symbolic Links**: Required for cross-platform rule sharing
- **Directory Permissions**: Need write access for memory bank updates
- **File Encoding**: UTF-8 required for special characters

### 3. Memory and Performance
- **Token Limits**: Must optimize for AI platform token constraints
- **File Size**: Memory bank files should remain under platform limits
- **Loading Time**: Rules should load quickly to avoid timeouts

## Development Environment

### Required Tools
1. **Text Editor**: Any editor supporting Markdown and symbolic links
2. **Git**: Version control for tracking changes
3. **Command Line**: For creating symbolic links and automation
4. **AI Coding Platform**: Cursor, CLINE, RooCode, or Windsurf

### Optional Tools
1. **Mermaid Live Editor**: For diagram creation and testing
2. **Markdown Linter**: For documentation quality assurance
3. **Symbolic Link Checker**: For cross-platform compatibility verification

## Tool Usage Patterns

### 1. Documentation Updates
- **Frequency**: After every significant code change
- **Automation**: Built into workflow rules
- **Validation**: Consistency checks across memory bank files

### 2. Rule Maintenance
- **Updates**: Modify original files in `.cursor/rules/`
- **Propagation**: Changes automatically reflected via symbolic links
- **Testing**: Verify changes work across all platforms

### 3. Memory Bank Access
- **Read Pattern**: Consult hierarchy from project brief to active context
- **Write Pattern**: Update progress tracker, then active context
- **Sync Pattern**: Ensure all files remain consistent

## Performance Considerations

### 1. Token Optimization
- **Lean Modes**: Minimal context for specific task types
- **Selective Loading**: Only load relevant rules and documentation
- **Caching**: Reuse context within sessions where possible

### 2. File Organization
- **Modular Structure**: Break large files into smaller, focused ones
- **Hierarchical Access**: Faster context retrieval through structured organization
- **Redundancy Reduction**: Avoid duplicate information across files

### 3. Platform Efficiency
- **Native Features**: Use platform-specific optimizations where available
- **Fallback Strategies**: Graceful degradation when features unavailable
- **Compatibility Layer**: Abstract platform differences where possible

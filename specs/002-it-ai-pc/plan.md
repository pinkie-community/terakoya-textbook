# Implementation Plan: 街の人たち向けAI寺子屋教科書システム

**Branch**: `002-it-ai-pc` | **Date**: 2025-09-11 | **Spec**: [spec.md](./spec.md)
**Input**: 仕様書を基に具体的な実装計画を立案, 教材作成の優先順位とマイルストーン設定, リソース配分と期間見積もり これらを行おう

## Execution Flow (/plan command scope)
```
1. Load feature spec from Input path
   → If not found: ERROR "No feature spec at {path}"
2. Fill Technical Context (scan for NEEDS CLARIFICATION)
   → Detect Project Type from context (web=frontend+backend, mobile=app+api)
   → Set Structure Decision based on project type
3. Evaluate Constitution Check section below
   → If violations exist: Document in Complexity Tracking
   → If no justification possible: ERROR "Simplify approach first"
   → Update Progress Tracking: Initial Constitution Check
4. Execute Phase 0 → research.md
   → If NEEDS CLARIFICATION remain: ERROR "Resolve unknowns"
5. Execute Phase 1 → contracts, data-model.md, quickstart.md, agent-specific template file (e.g., `CLAUDE.md` for Claude Code, `.github/copilot-instructions.md` for GitHub Copilot, or `GEMINI.md` for Gemini CLI).
6. Re-evaluate Constitution Check section
   → If new violations: Refactor design, return to Phase 1
   → Update Progress Tracking: Post-Design Constitution Check
7. Plan Phase 2 → Describe task generation approach (DO NOT create tasks.md)
8. STOP - Ready for /tasks command
```

**IMPORTANT**: The /plan command STOPS at step 7. Phases 2-4 are executed by other commands:
- Phase 2: /tasks command creates tasks.md
- Phase 3-4: Implementation execution (manual or via tools)

## Summary
街のIT初心者（紙ベース業務・Word/Excel利用者）向けのAI寺子屋教科書システム。「仕事がなくなる不安」を解消し、「私でもできた」成功体験を提供する学習教材作成。Google Gemini等の無料AIツールを使用し、段階的な学習プロセスで実務への応用まで支援する。

## Technical Context
**Language/Version**: Markdown (教材), Google Gemini API integration  
**Primary Dependencies**: Google Gemini, Google AI Studio, GitHub Pages (配信), Discord (コミュニティ)  
**Storage**: GitHub repository, Markdown files, static assets  
**Testing**: ワークショップ参加者による実地テスト, 学習者フィードバック収集  
**Target Platform**: PC(Windows/Mac)メイン, スマートフォン対応(補助的)
**Project Type**: Educational content repository (documentation/materials)  
**Performance Goals**: 90分ワークショップ内での学習完了, 30分以内のセットアップ完了  
**Constraints**: 無料ツールのみ使用, IT初心者対応, 専門用語を使わない日常語での説明  
**Scale/Scope**: 6つの学習モジュール(00-setup～05-research), 各モジュールにREADME+system-prompt

## Constitution Check
*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

**Simplicity**:
- Projects: 1 (educational content repository)
- Using framework directly? Yes (GitHub Pages, Discord, Gemini API)
- Single data model? Yes (learning modules with consistent structure)
- Avoiding patterns? Yes (direct markdown content, no abstraction layers)

**Architecture**:
- EVERY feature as library? Yes (each module is reusable learning component)
- Libraries listed: 6 learning modules (00-setup through 05-research)
- CLI per library: system-prompt.md provides AI-assisted interface for each module
- Library docs: README.md + system-prompt.md format for education context

**Testing (NON-NEGOTIABLE)**:
- RED-GREEN-Refactor cycle enforced? ADAPTED: Empathy validation before content creation
- Git commits show tests before implementation? Yes: persona checklists must fail before content satisfies them
- Order: Contract→Integration→E2E→Unit strictly followed? ADAPTED: Contract→Workshop Test→Module Creation→Validation
- Real dependencies used? Yes: actual workshop participants, real business scenarios
- Integration tests for: new modules, persona empathy validation, community platform integration
- FORBIDDEN: Content creation without empathy validation, skipping workshop feedback

**Observability**:
- Structured logging included? Yes: workshop feedback collection, learning progress tracking
- Frontend logs → backend? Yes: Discord community engagement feeds back to content improvement
- Error context sufficient? Yes: participant struggle points documented for iterative improvement

**Versioning**:
- Version number assigned? GitHub repository semantic versioning
- BUILD increments on every change? Yes: workshop iterations tracked in commit history
- Breaking changes handled? Yes: backward compatibility for existing workshop participants

## Project Structure

### Documentation (this feature)
```
specs/[###-feature]/
├── plan.md              # This file (/plan command output)
├── research.md          # Phase 0 output (/plan command)
├── data-model.md        # Phase 1 output (/plan command)
├── quickstart.md        # Phase 1 output (/plan command)
├── contracts/           # Phase 1 output (/plan command)
└── tasks.md             # Phase 2 output (/tasks command - NOT created by /plan)
```

### Source Code (repository root)
```
# Option 1: Single project (DEFAULT)
src/
├── models/
├── services/
├── cli/
└── lib/

tests/
├── contract/
├── integration/
└── unit/

# Option 2: Web application (when "frontend" + "backend" detected)
backend/
├── src/
│   ├── models/
│   ├── services/
│   └── api/
└── tests/

frontend/
├── src/
│   ├── components/
│   ├── pages/
│   └── services/
└── tests/

# Option 3: Mobile + API (when "iOS/Android" detected)
api/
└── [same as backend above]

ios/ or android/
└── [platform-specific structure]
```

**Structure Decision**: Educational Content Repository (specialized structure for learning modules)

## Phase 0: Outline & Research
1. **Extract unknowns from Technical Context** above:
   - For each NEEDS CLARIFICATION → research task
   - For each dependency → best practices task
   - For each integration → patterns task

2. **Generate and dispatch research agents**:
   ```
   For each unknown in Technical Context:
     Task: "Research {unknown} for {feature context}"
   For each technology choice:
     Task: "Find best practices for {tech} in {domain}"
   ```

3. **Consolidate findings** in `research.md` using format:
   - Decision: [what was chosen]
   - Rationale: [why chosen]
   - Alternatives considered: [what else evaluated]

**Output**: research.md with all NEEDS CLARIFICATION resolved

## Phase 1: Design & Contracts
*Prerequisites: research.md complete*

1. **Extract entities from feature spec** → `data-model.md`:
   - Entity name, fields, relationships
   - Validation rules from requirements
   - State transitions if applicable

2. **Generate API contracts** from functional requirements:
   - For each user action → endpoint
   - Use standard REST/GraphQL patterns
   - Output OpenAPI/GraphQL schema to `/contracts/`

3. **Generate contract tests** from contracts:
   - One test file per endpoint
   - Assert request/response schemas
   - Tests must fail (no implementation yet)

4. **Extract test scenarios** from user stories:
   - Each story → integration test scenario
   - Quickstart test = story validation steps

5. **Update agent file incrementally** (O(1) operation):
   - Run `/scripts/update-agent-context.sh [claude|gemini|copilot]` for your AI assistant
   - If exists: Add only NEW tech from current plan
   - Preserve manual additions between markers
   - Update recent changes (keep last 3)
   - Keep under 150 lines for token efficiency
   - Output to repository root

**Output**: data-model.md, /contracts/*, failing tests, quickstart.md, agent-specific file

## Phase 2: Task Planning Approach
*This section describes what the /tasks command will do - DO NOT execute during /plan*

**Task Generation Strategy**:
- Load educational module contracts from Phase 1 design docs
- Each learning module → empathy validation task [P]
- Each module → README.md creation task (dependent on validation)
- Each module → system-prompt.md creation task [P with README]
- Workshop integration → delivery contract test tasks
- Community setup → Discord integration tasks

**Educational-Specific Task Ordering**:
- Empathy validation before content creation (replaces TDD RED phase)
- Module dependency order: 00-setup → 01-introduction → 02-ai-safety → 03-idea-generation → 04-gemini-memory → 05-research
- Mark [P] for parallel execution (independent modules after prerequisites)
- Workshop testing tasks after each module completion

**Persona-Driven Task Priority**:
1. **Critical Path**: 00-setup module (addresses workshop pain point)
2. **Foundation**: 01-introduction + 02-ai-safety (builds confidence)
3. **Skills Development**: 03-05 modules (progressive mastery)
4. **Community Integration**: Discord setup + GitHub deployment

**Quality Gates Integration**:
- Each module requires empathy checklist validation
- Workshop testing with real participants before production
- Success metrics collection and analysis
- Community feedback integration loops

**Estimated Output**: 20-25 educational development tasks in tasks.md, prioritized by learner impact

**IMPORTANT**: This phase is executed by the /tasks command, NOT by /plan

## Phase 3+: Future Implementation
*These phases are beyond the scope of the /plan command*

**Phase 3**: Task execution (/tasks command creates tasks.md)  
**Phase 4**: Implementation (execute tasks.md following constitutional principles)  
**Phase 5**: Validation (run tests, execute quickstart.md, performance validation)

## Complexity Tracking
*Fill ONLY if Constitution Check has violations that must be justified*

| Violation | Why Needed | Simpler Alternative Rejected Because |
|-----------|------------|-------------------------------------|
| [e.g., 4th project] | [current need] | [why 3 projects insufficient] |
| [e.g., Repository pattern] | [specific problem] | [why direct DB access insufficient] |


## Progress Tracking
*This checklist is updated during execution flow*

**Phase Status**:
- [x] Phase 0: Research complete (/plan command)
- [x] Phase 1: Design complete (/plan command)
- [x] Phase 2: Task planning complete (/plan command - describe approach only)
- [ ] Phase 3: Tasks generated (/tasks command)
- [ ] Phase 4: Implementation complete
- [ ] Phase 5: Validation passed

**Gate Status**:
- [x] Initial Constitution Check: PASS
- [x] Post-Design Constitution Check: PASS
- [x] All NEEDS CLARIFICATION resolved
- [x] Complexity deviations documented

---
*Based on Constitution v2.1.1 - See `/memory/constitution.md`*
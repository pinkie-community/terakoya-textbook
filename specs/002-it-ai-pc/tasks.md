# Tasks: 街の人たち向けAI寺子屋教科書システム

**Input**: Design documents from `/specs/002-it-ai-pc/`
**Prerequisites**: plan.md, research.md, data-model.md, contracts/, quickstart.md

## Execution Flow (main)
```
1. Load plan.md from feature directory ✓
   → Tech stack: Markdown content, Google Gemini, GitHub Pages, Discord
   → Structure: Educational content repository with 6 learning modules
2. Load design documents: ✓
   → data-model.md: Learning Module, Learner Persona, Learning Experience entities
   → contracts/: Module structure and workshop delivery contracts
   → quickstart.md: 15-minute success experience validation scenarios
3. Generate tasks by category: Educational content development approach
   → Setup: Repository structure, community integration
   → Validation: Empathy checklists before content creation (TDD equivalent)
   → Content: Module README.md and system-prompt.md creation
   → Integration: Discord community, GitHub deployment
   → Testing: Workshop validation with real participants
4. Apply educational task rules:
   → Different modules = mark [P] for parallel development
   → Same module files = sequential (README before system-prompt)
   → Empathy validation before content creation
5. Number tasks sequentially (T001, T002...)
6. Prioritize by learner impact: 00-setup first (critical path)
```

## Format: `[ID] [P?] Description`
- **[P]**: Can run in parallel (different modules, no dependencies)
- Include exact file paths in educational content structure

## Path Conventions
- **Educational modules**: `modules/{module-id}/` at repository root
- **Supporting infrastructure**: GitHub repository, Discord community integration
- Paths assume educational content structure per data-model.md

## Phase 3.1: Setup & Infrastructure
- [ ] T001 Create modules/ directory structure per module-structure-contract.md
- [ ] T002 [P] Set up Discord community integration with GitHub URLs and QR codes
- [ ] T003 [P] Configure GitHub Pages for content delivery
- [ ] T004 Create empathy validation checklist templates for all personas

## Phase 3.2: Empathy Validation First (Educational TDD) ⚠️ MUST COMPLETE BEFORE 3.3
**CRITICAL: Persona validation checklists MUST be created and MUST FAIL before content creation**
- [ ] T005 [P] Create empathy validation checklist for 00-setup module (田中さん, 佐藤さん, 鈴木さん)
- [ ] T006 [P] Create empathy validation checklist for 01-introduction module (田中さん, 佐藤さん, 鈴木さん)
- [ ] T007 [P] Create empathy validation checklist for 02-ai-safety module (田中さん, 佐藤さん, 鈴木さん)
- [ ] T008 [P] Create empathy validation checklist for 03-idea-generation module (田中さん, 佐藤さん, 鈴木さん)
- [ ] T009 [P] Create empathy validation checklist for 04-gemini-memory module (田中さん, 佐藤さん, 鈴木さん)
- [ ] T010 [P] Create empathy validation checklist for 05-research module (田中さん, 佐藤さん, 鈴木さん)

## Phase 3.3: Critical Path - 00-setup Module (ONLY after empathy validation exists)
**Priority: Addresses 30-minute setup bottleneck identified in workshop feedback**
- [ ] T011 Create modules/00-setup/README.md with Google account & Gemini setup instructions
- [ ] T012 Create modules/00-setup/system-prompt.md as patient setup assistant AI tutor
- [ ] T013 Create modules/00-setup/static/screenshots/ with step-by-step installation images
- [ ] T014 Create modules/00-setup/static/qr-codes/ for Discord server access
- [ ] T015 Validate 00-setup module against empathy checklists (T005)

## Phase 3.4: Foundation Modules (After 00-setup validation)
- [ ] T016 [P] Create modules/01-introduction/README.md addressing job displacement fears
- [ ] T017 [P] Create modules/01-introduction/system-prompt.md as encouraging AI conversation partner
- [ ] T018 [P] Create modules/02-ai-safety/README.md with 2 core safety principles
- [ ] T019 [P] Create modules/02-ai-safety/system-prompt.md as safety-focused AI guide
- [ ] T020 Validate 01-introduction module against empathy checklists (T006)
- [ ] T021 Validate 02-ai-safety module against empathy checklists (T007)

## Phase 3.5: Skills Development Modules (After foundation validation)
- [ ] T022 [P] Create modules/03-idea-generation/README.md with business creativity exercises
- [ ] T023 [P] Create modules/03-idea-generation/system-prompt.md as creative brainstorming partner
- [ ] T024 [P] Create modules/04-gemini-memory/README.md for AI personalization features
- [ ] T025 [P] Create modules/04-gemini-memory/system-prompt.md as customization assistant
- [ ] T026 [P] Create modules/05-research/README.md for information gathering skills
- [ ] T027 [P] Create modules/05-research/system-prompt.md as research methodology guide
- [ ] T028 Validate 03-idea-generation module against empathy checklists (T008)
- [ ] T029 Validate 04-gemini-memory module against empathy checklists (T009)
- [ ] T030 Validate 05-research module against empathy checklists (T010)

## Phase 3.6: Workshop Integration & Testing
- [ ] T031 Create workshop delivery materials based on workshop-delivery-contract.md
- [ ] T032 Test complete learning path with quickstart.md success scenarios
- [ ] T033 Set up Discord community with proper moderation guidelines
- [ ] T034 Create GitHub repository navigation guide for PC users
- [ ] T035 Test 30-minute setup process with realistic constraints

## Phase 3.7: Content Polish & Iteration Support
- [ ] T036 [P] Add static/templates/ for business scenario exercises across all modules
- [ ] T037 [P] Create common troubleshooting guides for technical difficulties
- [ ] T038 [P] Update CLAUDE.md with implementation lessons learned
- [ ] T039 Set up feedback collection system for continuous improvement
- [ ] T040 Create version control strategy for workshop iteration improvements

## Dependencies
- Empathy validation (T005-T010) before any content creation (T011-T027)
- T011-T015 (00-setup) must complete before foundation modules (T016-T021)
- Foundation validation (T020-T021) before skills modules (T022-T030)
- All module content before workshop integration (T031-T035)
- Workshop testing before polish phase (T036-T040)

## Parallel Example
```
# Launch T005-T010 together (empathy validation):
Task: "Create empathy validation checklist for 00-setup module addressing 30-min setup anxiety"
Task: "Create empathy validation checklist for 01-introduction module addressing job displacement fears"
Task: "Create empathy validation checklist for 02-ai-safety module addressing 'AI is dangerous' concerns"

# After validation exists, launch T016-T019 together (foundation content):
Task: "Create modules/01-introduction/README.md addressing job displacement fears"
Task: "Create modules/01-introduction/system-prompt.md as encouraging AI conversation partner"
Task: "Create modules/02-ai-safety/README.md with 2 core safety principles"
Task: "Create modules/02-ai-safety/system-prompt.md as safety-focused AI guide"
```

## Notes
- [P] tasks = different modules, no content dependencies
- Verify empathy validation "fails" before creating content to satisfy it
- Each module follows module-structure-contract.md requirements
- Focus on 田中さん, 佐藤さん, 鈴木さん personas throughout
- Commit after each task with persona validation notes

## Educational Task Generation Rules
*Applied during main() execution*

1. **From Module Structure Contract**:
   - Each module → README.md + system-prompt.md + static/ creation tasks
   - Each module → empathy validation task [P]
   
2. **From Data Model Personas**:
   - Each persona → validation checklist items across all modules
   - Business contexts → practical exercise templates
   
3. **From Workshop Delivery Contract**:
   - Setup bottlenecks → priority T011-T015 (00-setup)
   - Community integration → Discord + GitHub tasks
   
4. **From Quickstart Scenarios**:
   - Success experiences → module content validation tests

5. **Ordering**:
   - Setup → Validation → Critical Path (00-setup) → Foundation → Skills → Integration → Polish
   - Persona empathy validation gates all content creation

## Validation Checklist
*GATE: Checked by main() before returning*

- [x] All modules have corresponding empathy validation tasks
- [x] All content creation tasks come after validation tasks
- [x] Critical path (00-setup) prioritized based on workshop feedback
- [x] Parallel tasks truly independent (different modules)
- [x] Each task specifies exact file path in modules/ structure
- [x] No task creates same module content as another [P] task
- [x] Persona-driven validation integrated throughout development process
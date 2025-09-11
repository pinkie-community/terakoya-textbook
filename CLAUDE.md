# Claude Code Context: AI寺子屋教科書システム

## Project Overview
Street-level AI literacy education system targeting Japanese IT beginners who primarily use paper-based workflows and basic PC applications (Word/Excel). Focus on addressing job security fears while providing practical AI skills.

## Target Audience Personas
**田中さん (55歳・経理事務)**: Excel proficient, prints for verification, 20 years manual bookkeeping
**佐藤さん (42歳・小売店経営)**: Notebook-based management, PC intimidation, handwritten customer lists  
**鈴木さん (38歳・製造業管理職)**: Word documents, USB file transfer, cloud-averse, 3-hour report writing

## Tech Stack & Constraints
- **Content**: Markdown documentation, GitHub repository hosting
- **AI Tools**: Google Gemini (free tier), Google AI Studio
- **Community**: Discord server integration via GitHub URLs/QR codes
- **Platform**: PC-first with smartphone fallback options
- **Cost**: Free tools only, addresses economic concerns

## Current Architecture
```
specs/002-it-ai-pc/           # Feature specification & planning
├── spec.md                   # Requirements with empathy framework
├── plan.md                   # Implementation strategy  
├── research.md               # Technical decisions & rationale
├── data-model.md             # Learning entities & relationships
├── contracts/                # Module & workshop delivery contracts
└── quickstart.md             # 15-minute success experience

modules/                      # Learning content (to be created)
├── 00-setup/                # Google accounts, Gemini installation  
├── 01-introduction/         # Why learn AI, addressing fears
├── 02-ai-safety/           # Safe usage principles
├── 03-idea-generation/     # Creative AI applications
├── 04-gemini-memory/       # Personalization features
└── 05-research/            # Information gathering skills
```

## Key Design Principles
1. **Empathy-First**: Every module validated against persona-specific anxiety checklist
2. **Success Experience**: "私でもできた!" moments within first 15 minutes of each module
3. **Practical Business Value**: Real scenarios (経理, 商品説明, 報告書作成) not theoretical examples  
4. **Dual-Layer Learning**: README.md (curriculum) + system-prompt.md (AI tutoring)
5. **Community Support**: Discord integration for peer learning and question assistance

## Workshop Integration
- **Duration**: 90 minutes total, 30 minutes allocated for setup
- **Real Experience Data**: Discord installation most problematic, QR codes work for smartphones, PC users need direct GitHub URLs
- **Success Metrics**: >90% setup completion, confidence increase >3 points, >60% continued usage at 30 days

## Development Status & Next Steps
✅ **Phase 0**: Research completed - technical stack decisions, persona analysis
🔄 **Phase 1**: Design documents in progress - contracts, data model, quickstart created
⏳ **Phase 2**: Task planning approach documentation (pending)
⏳ **Phase 3**: Module content creation (00-setup first priority)

## Constitutional Adaptations  
Educational content project requires adapting standard software development practices:
- **Libraries→Modules**: Reusable learning components with defined interfaces
- **CLI→AI Interface**: system-prompt.md enables conversational learning assistance  
- **Testing→Validation**: Workshop feedback & empathy checklist verification
- **Version Control**: Collaborative content improvement via GitHub

## Common Collaboration Patterns
- When creating module content: Always validate against 3 persona empathy checklists
- When writing instructional text: Use simple Japanese, avoid technical jargon, provide concrete business examples
- When testing flows: Assume 30-minute setup bottleneck, plan for smartphone + PC compatibility
- When updating content: Maintain dual-layer structure (README + system-prompt) for personalized learning

## Critical Success Factors  
⚠️ **Address job displacement anxiety explicitly** - show AI as work enhancement, not replacement
⚠️ **Provide immediate practical value** - real business scenarios within 15 minutes  
⚠️ **Maintain accessibility** - assume low technical confidence, use encouraging language
⚠️ **Enable peer support** - Discord community integration essential for ongoing learning

*Last updated: 2025-09-11 | Current feature: 002-it-ai-pc | Status: Phase 1 Design*
# Learning Module Structure Contract

## Module Directory Contract

Each learning module MUST implement the following file structure:

```
modules/{module-id}/
├── README.md                    # Primary curriculum content
├── system-prompt.md            # AI tutoring interface
└── static/                     # Supporting materials directory
    ├── screenshots/            # Step-by-step process images  
    ├── templates/              # Example files for exercises
    └── qr-codes/              # Quick access codes
```

## README.md Content Contract

**REQUIRED Sections** (in this order):
1. `# [Module Title] - [Simple Description]`
2. `## このモジュールで学ぶこと` (What you'll learn)
3. `## 所要時間` (Required time) 
4. `## 必要なもの` (Prerequisites)
5. `## ステップ` (Step-by-step instructions)
6. `## 成功体験ポイント` (Success milestones)
7. `## よくある質問` (Common questions)
8. `## 次のステップ` (Next actions)

**Empathy Validation Requirements**:
- MUST include persona-specific success scenarios
- MUST use daily language, avoid technical jargon
- MUST provide "I can do this!" moments within first 10 minutes
- MUST address job security concerns explicitly

## system-prompt.md Content Contract

**Required Structure**:
```markdown
# AI Teaching Assistant for [Module Name]

## Your Role
You are a patient, encouraging AI tutor helping [persona description] learn [module topic].

## Key Principles
- Use simple Japanese, no technical terms
- Acknowledge their existing expertise
- Focus on practical business benefits
- Celebrate small wins enthusiastically

## Specific Knowledge
[Module-specific facts and procedures]

## Common Questions & Responses
[FAQ with empathetic, reassuring answers]

## Success Indicators
[How to recognize when learning is successful]
```

## Static Resources Contract

**Screenshots Requirements**:
- MUST show actual screen captures, not mockups
- MUST include mouse cursor position for click instructions
- MUST use consistent naming: `step-{number}-{action}.png`

**Template Requirements**: 
- MUST provide concrete examples from persona workflows
- MUST be immediately usable without modification
- MUST demonstrate real business value

## Testing Contract

Each module MUST pass these validation tests:

### Persona Empathy Test
- [ ] 田中さん: "I feel this respects my experience" 
- [ ] 佐藤さん: "This seems manageable for me"
- [ ] 鈴木さん: "I can see how this saves time"

### Accessibility Test
- [ ] Setup completes within 30 minutes for beginners
- [ ] Instructions work on both PC and smartphone
- [ ] All links and QR codes function correctly

### Success Experience Test
- [ ] Learner achieves "I did it!" moment within 15 minutes
- [ ] Practical business benefit is immediately apparent  
- [ ] Confidence increases measurably from start to finish

## Quality Gates

**MUST HAVE before production**:
- Workshop tested with real target audience
- All empathy checklist items validated
- Success metrics collected and analyzed
- Community support integration verified

**VALIDATION FAILURE conditions**:
- Any persona reports feeling "this isn't for me"
- Setup time exceeds 30 minutes consistently
- No clear practical business application demonstrated
- Technical jargon used without explanation
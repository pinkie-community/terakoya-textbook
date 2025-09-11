# Data Model: 街の人たち向けAI寺子屋教科書システム

## Core Entities

### Learning Module
**Purpose**: Individual learning unit with structured content and AI assistance
**Attributes**:
- `module_id`: Unique identifier (00-setup, 01-introduction, etc.)
- `title`: Human-readable module name
- `description`: Brief overview of learning objectives
- `prerequisites`: Required knowledge or previous modules
- `estimated_time`: Expected completion time
- `difficulty_level`: Beginner/Basic assessment

**Content Structure**:
- `README.md`: Primary curriculum content
- `system-prompt.md`: AI tutoring personality and knowledge base
- `static/`: Supporting materials (images, screenshots, templates)

**Validation Rules**:
- Module ID must follow ##-name pattern
- README must include empathy checklist validation
- System prompt must address module-specific learning objectives

### Learner Persona
**Purpose**: Concrete representation of target audience for empathy validation
**Attributes**:
- `name`: Persona identifier (田中さん, 佐藤さん, 鈴木さん)
- `age`: Demographic context
- `occupation`: Professional background
- `current_skills`: Existing technical competencies
- `primary_concerns`: Key anxieties about AI adoption
- `success_criteria`: What constitutes learning success for this persona

**Core Personas**:
1. **田中さん (Economic事務・55歳)**
   - Skills: Excel proficient, prints for verification
   - Concerns: Job security, calculation accuracy
   - Success: "AI makes my work more accurate"

2. **佐藤さん (小売店経営・42歳)** 
   - Skills: Notebook management, PC intimidation
   - Concerns: Technical complexity, business application
   - Success: "Customers praise my AI-created descriptions"

3. **鈴木さん (製造業管理職・38歳)**
   - Skills: Word documents, USB file management
   - Concerns: Time efficiency, work-life balance
   - Success: "Report writing time reduced from 3h to 30min"

### Learning Experience
**Purpose**: Concrete, measurable interaction points that build confidence
**Attributes**:
- `experience_type`: practical_demo | hands_on_exercise | success_milestone
- `business_context`: Real-world scenario (経理, 商品説明, 報告書作成)
- `ai_tool_used`: Specific AI application (Gemini calculation, image description, text generation)
- `success_indicator`: Measurable outcome that provides "I can do this!" feeling
- `psychological_impact`: Expected emotional response (安心, 驚き, 自信)

**State Transitions**:
- `initial_anxiety` → `curiosity` → `engagement` → `success` → `confidence`

### Community Support Element
**Purpose**: Peer learning and mutual encouragement system
**Attributes**:
- `platform`: Discord server integration
- `access_method`: GitHub URL + QR code distribution
- `support_type`: peer_sharing | question_assistance | success_celebration
- `moderation_approach`: Empathy-focused, non-judgmental environment

### Success Metric
**Purpose**: Measurable indicators of educational effectiveness
**Attributes**:
- `metric_category`: technical_proficiency | confidence_level | practical_adoption
- `measurement_method`: pre_post_survey | practical_demonstration | follow_up_usage
- `target_threshold`: Specific success criteria per persona
- `collection_timeline`: Workshop during/immediate post/30-day follow-up

**Key Metrics**:
- Setup completion rate (target: >90% within 30 minutes)
- Confidence increase (target: 3+ points on 10-point scale)
- AI tool continued usage (target: >60% at 30-day follow-up)

## Entity Relationships

### Module → Learning Experience (1:Many)
Each module contains multiple structured learning experiences that build upon each other progressively.

### Learning Experience → Persona (Many:Many)  
Each learning experience is validated against all three personas to ensure universal accessibility and relevance.

### Module → Community Support (1:1)
Each module integrates with the Discord community for peer support and question clarification.

### Persona → Success Metric (1:Many)
Success criteria are persona-specific, requiring targeted measurement approaches.

## Data Flow Patterns

### Learning Progression Flow
1. **Entry**: Persona-appropriate anxiety/concern
2. **Setup**: Technical barrier removal (00-setup)
3. **Confidence Building**: Early success experience
4. **Skill Development**: Progressive AI tool mastery
5. **Practical Application**: Real business context usage
6. **Community Integration**: Peer sharing and support

### Content Validation Flow
1. **Content Creation**: README.md with curriculum
2. **Empathy Check**: Persona-specific validation checklist
3. **AI Tutor Setup**: system-prompt.md creation
4. **Workshop Testing**: Real participant feedback
5. **Iterative Improvement**: Based on success metrics

### Support Escalation Flow
1. **Self-Study**: README.md autonomous learning
2. **AI Assistance**: system-prompt.md personalized help
3. **Peer Support**: Discord community engagement
4. **Expert Guidance**: Workshop facilitator intervention

## Technical Implementation Notes

### File Structure Mapping
```
modules/
├── 00-setup/
│   ├── README.md          # → Learning Module.content
│   ├── system-prompt.md   # → AI tutoring interface
│   └── static/           # → Supporting materials
├── 01-introduction/
│   └── [same structure]
```

### Community Integration Points
- GitHub repository: Content distribution + URL/QR sharing
- Discord server: Real-time support + success sharing
- AI tutoring: Personalized learning assistance via system prompts

### Validation Framework
Each module requires successful completion of persona empathy checklists before being considered production-ready for workshop delivery.
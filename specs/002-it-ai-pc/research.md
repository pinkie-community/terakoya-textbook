# Research & Analysis: 街の人たち向けAI寺子屋教科書システム

## Overview
This research addresses the technical and pedagogical approach for creating an AI learning system targeted at street-level IT beginners who primarily use paper-based workflows and basic PC applications.

## Key Research Areas

### 1. Target Audience Analysis
**Decision**: Focus on three primary personas representing real workshop participants
**Rationale**: Based on actual workshop experience where these demographic types consistently appeared
**Key Findings**:
- 田中さん (55歳・事務職): Excel capable but prints for manual verification
- 佐藤さん (42歳・小売店): Notebook-based management, PC intimidation
- 鈴木さん (38歳・製造業): Word proficient but cloud-averse, USB-dependent

**Alternatives considered**: 
- Age-based segmentation (rejected: skills vary more than age)
- Industry-based segmentation (rejected: similar anxieties across industries)

### 2. Educational Technology Stack
**Decision**: Google Gemini + Google AI Studio as primary teaching tools
**Rationale**: 
- Free tier available (addresses cost concerns)
- Japanese language support
- Web-based (no complex installations)
- Mobile compatibility for accessibility

**Alternatives considered**:
- ChatGPT (rejected: subscription model creates barriers)
- Claude (rejected: regional availability issues)
- Local AI models (rejected: too complex for target audience)

### 3. Learning Platform Architecture
**Decision**: GitHub repository + Markdown documentation + Discord community
**Rationale**:
- Version control for continuous improvement
- Simple URL sharing via GitHub
- Community support through Discord
- No additional hosting costs

**Alternatives considered**:
- LMS platform (rejected: adds complexity, costs)
- Custom web application (rejected: development overhead)
- PDF-based materials (rejected: not interactive)

### 4. Content Structure Methodology
**Decision**: Dual-layer learning (README.md + system-prompt.md per module)
**Rationale**: 
- README provides structured curriculum
- system-prompt enables personalized AI tutoring
- Addresses "need more detailed explanation" workshop feedback

**Module Sequence Decision**:
1. 00-setup (Google account setup, Gemini installation)
2. 01-introduction (Why learn AI)
3. 02-ai-safety (Safe usage principles)
4. 03-idea-generation (Creative AI applications)
5. 04-gemini-memory (Personalization features)
6. 05-research (Information gathering skills)

**Alternatives considered**:
- Single README per module (rejected: insufficient depth)
- Video-based content (rejected: accessibility issues)
- Interactive web tutorials (rejected: complexity)

### 5. Workshop Integration Strategy  
**Decision**: 90-minute workshop format with 30-minute setup allocation
**Rationale**: Based on actual workshop experience data showing setup bottlenecks
**Key Learnings**:
- Discord installation was most problematic step
- QR codes worked well for smartphone users
- PC users needed direct URL access via GitHub
- Google accounts were pre-existing for most participants

### 6. Psychological Safety Framework
**Decision**: Mandatory empathy checklist for all content
**Rationale**: Workshop feedback indicated explanation approach needed improvement
**Framework**:
- Address job displacement fears explicitly
- Provide immediate success experiences
- Use non-technical language consistently
- Build peer support mechanisms

## Technical Constraints Resolution

### Setup Process Optimization
**Challenge**: 30-minute setup time exceeded expectations
**Solution**: 
- Pre-workshop Google account verification
- GitHub repository with direct Discord links + QR codes
- Step-by-step screenshot guides for each platform

### Device Compatibility
**Challenge**: Mixed PC/smartphone usage in workshops  
**Solution**:
- PC-first design for business applications
- Smartphone alternatives for accessibility
- Cross-platform testing requirements

### Free Tool Limitation
**Challenge**: Provide comprehensive AI education without paid tools
**Solution**:
- Google Gemini free tier provides sufficient capabilities
- Focus on core AI concepts rather than advanced features
- Community Discord for peer learning support

## Implementation Recommendations

### Content Creation Priority
1. **High Priority**: 00-setup module (addresses biggest workshop pain point)
2. **Medium Priority**: 01-introduction + 02-ai-safety (builds confidence)
3. **Lower Priority**: Advanced modules (03-05) after core foundation established

### Quality Assurance Approach
- Real workshop testing with target demographic
- Learner feedback collection system
- Iterative improvement based on empathy checklist validation

### Success Metrics
- Setup completion rate within 30 minutes
- Participant confidence scores (pre/post workshop)
- Practical AI tool adoption rate post-workshop
- Community engagement metrics in Discord

## Constitutional Compliance Notes
This is an educational content project rather than a traditional software development project, so some constitutional elements require adaptation:

- **Libraries**: Educational modules function as reusable learning components
- **CLI Interface**: System-prompt.md files enable AI-assisted learning interface
- **Testing**: User feedback and workshop validation replace traditional unit testing
- **Version Control**: GitHub enables collaborative content improvement

## Next Phase Requirements
Phase 1 should focus on:
1. Detailed content structure design for each module
2. Template creation for README.md and system-prompt.md files
3. Workshop curriculum mapping to module progression
4. Community engagement strategy design
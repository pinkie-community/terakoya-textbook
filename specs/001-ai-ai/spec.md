# Feature Specification: AI寺子屋教科書作成システム

**Feature Branch**: `001-ai-ai`  
**Created**: 2025-09-04  
**Status**: Draft  
**Input**: User description: "AI寺子屋という庶民のためのAI時代の読み書きそろばんを学ぶ塾を開催します。これからこの塾の教科書を作成します。"

## Execution Flow (main)
```
1. Parse user description from Input
   → If empty: ERROR "No feature description provided"
2. Extract key concepts from description
   → Identify: actors, actions, data, constraints
3. For each unclear aspect:
   → Mark with [NEEDS CLARIFICATION: specific question]
4. Fill User Scenarios & Testing section
   → If no clear user flow: ERROR "Cannot determine user scenarios"
5. Generate Functional Requirements
   → Each requirement must be testable
   → Mark ambiguous requirements
6. Identify Key Entities (if data involved)
7. Run Review Checklist
   → If any [NEEDS CLARIFICATION]: WARN "Spec has uncertainties"
   → If implementation details found: ERROR "Remove tech details"
8. Return: SUCCESS (spec ready for planning)
```

---

## ⚡ Quick Guidelines
- ✅ Focus on WHAT users need and WHY
- ❌ Avoid HOW to implement (no tech stack, APIs, code structure)
- 👥 Written for business stakeholders, not developers

### Section Requirements
- **Mandatory sections**: Must be completed for every feature
- **Optional sections**: Include only when relevant to the feature
- When a section doesn't apply, remove it entirely (don't leave as "N/A")

### For AI Generation
When creating this spec from a user prompt:
1. **Mark all ambiguities**: Use [NEEDS CLARIFICATION: specific question] for any assumption you'd need to make
2. **Don't guess**: If the prompt doesn't specify something (e.g., "login system" without auth method), mark it
3. **Think like a tester**: Every vague requirement should fail the "testable and unambiguous" checklist item
4. **Common underspecified areas**:
   - User types and permissions
   - Data retention/deletion policies  
   - Performance targets and scale
   - Error handling behaviors
   - Integration requirements
   - Security/compliance needs

---

## User Scenarios & Testing *(mandatory)*

### Primary User Story
As an AI寺子屋 instructor, I need to create comprehensive textbook materials that teach basic AI literacy skills (reading, writing, and arithmetic in the AI era) to ordinary citizens, so that community members can effectively participate in and benefit from the digital transformation of society.

### Acceptance Scenarios
1. **Given** I am an instructor planning curriculum, **When** I access the textbook creation system, **Then** I can structure learning modules covering AI fundamentals, practical applications, and ethical considerations
2. **Given** I have identified learning objectives, **When** I create content for different skill levels, **Then** the system organizes materials in progressive difficulty from basic to advanced
3. **Given** I need to teach practical AI skills, **When** I develop exercises and examples, **Then** learners can practice real-world AI interactions and problem-solving

### Edge Cases
- What happens when content needs to be updated due to rapidly evolving AI technology?
- How does the system handle different learning styles and accessibility requirements?
- What occurs when instructors need to customize content for specific community needs?

## Requirements *(mandatory)*

### Functional Requirements
- **FR-001**: System MUST allow instructors to create structured educational content covering AI literacy fundamentals
- **FR-002**: System MUST organize content into progressive learning modules (beginner to advanced)
- **FR-003**: System MUST provide templates for different types of educational materials [NEEDS CLARIFICATION: specific material types not specified - worksheets, presentations, interactive exercises?]
- **FR-004**: System MUST enable content versioning and updates to keep pace with AI developments
- **FR-005**: System MUST support multiple content formats [NEEDS CLARIFICATION: format requirements not specified - text, multimedia, interactive elements?]
- **FR-006**: System MUST allow customization of content for different community contexts [NEEDS CLARIFICATION: customization scope not defined]
- **FR-007**: System MUST provide assessment tools to measure learning progress [NEEDS CLARIFICATION: assessment types and criteria not specified]
- **FR-008**: System MUST ensure content is accessible to diverse learning abilities and backgrounds
- **FR-009**: System MUST maintain content quality and educational standards [NEEDS CLARIFICATION: quality metrics not defined]
- **FR-010**: System MUST enable collaborative content development between multiple instructors [NEEDS CLARIFICATION: collaboration features not specified]

### Key Entities
- **Learning Module**: Core educational unit covering specific AI literacy topics with defined learning objectives and outcomes
- **Instructor**: Content creator responsible for developing and maintaining educational materials
- **Learner Profile**: Represents different skill levels, learning styles, and community contexts that content must address
- **Assessment Item**: Evaluation tool measuring learner progress and comprehension of AI concepts
- **Content Template**: Reusable structure for creating consistent educational materials across different topics

## AI寺子屋カリキュラム構造 *(mandatory)*

### 全体設計思想
AI時代の「読み書きそろばん」として、以下の3つの柱で構成：
- **読む力（AI理解力）**: AIの仕組みと社会への影響を理解する
- **書く力（AI活用力）**: AIツールを適切に使って課題を解決する  
- **そろばん力（AI判断力）**: AIの出力を批判的に評価し、適切に判断する

**教育哲学的基盤**: COTEN深井龍之介氏の「社会OS」概念を活用し、AI革命を歴史上6回目のOS転換として位置づけ、単なる技術理解ではなく歴史的必然としてのAI時代を理解する

### 学習段階別構成

#### **基礎編（初心者向け）**
**対象**: AIに触れたことがない一般市民  
**目標**: AI革命を歴史的文脈で理解し、変化を受け入れる思考基盤を構築する

##### モジュール0: 社会OS入門 〜「当たり前」が変わる歴史〜
**学習目標**: 現在の常識が絶対ではないことを理解し、AI時代の変化を受け入れる思考基盤を作る

- **0-1. 社会OSとは何か**: 
  - パソコンのOSと社会の常識の類似性
  - OSが変わると全ての常識が変わる仕組み
  - 現在のフランス革命OS（人権・民主主義・資本主義）の特徴
- **0-2. 歴史上の5回のOS転換**:
  - 神話の時代から哲学の誕生（紀元前6世紀の知の爆発）
  - 帝国時代からキリスト教OSへの転換（中世1000年）
  - フランス革命OSの確立（1789年〜現代）
  - 各転換での「タブー」の変化パターン
  - OS転換速度の加速とコミュニケーション技術の相関関係
- **0-3. 現代の特徴：「世界観の時代」**:
  - 形而下（物質的問題）から形而上（精神的問題）への移行
  - 個人の世界観が人権となる時代の到来
  - 「既存の世界観破壊へのエクスタシー」現象の理解
- **0-4. 第6のOS転換の予兆**:
  - 人権・民主主義・資本主義の揺らぎの兆候
  - マイナーアップデートからメジャーアップデートへの可能性
  - **人間ではない知能の登場**が社会に与える根本的インパクト

##### モジュール1: AI革命 〜第6のOS転換の始まり〜
**学習目標**: AIを歴史的文脈で捉え、技術的変化が社会構造に与える影響を理解する

- **1-1. AIとは新たなコミュニケーション技術**:
  - コミュニケーション技術の進化：口頭 → 文字 → 印刷 → マスメディア → インターネット → **AI**
  - AIによる情報処理速度の飛躍的向上
  - 人間の認知限界を超えるコミュニケーション能力の獲得
- **1-2. AIが揺るがす既存のタブー**:
  - 「人間だけが知能を持つ」という前提の崩壊
  - 人権概念の拡張問題（AIの人権は存在するか？）
  - 労働・創作・学習の価値観の根本的変化
- **1-3. AI時代の新しい常識の萌芽**:
  - AIとの共生が前提となる社会構造
  - 人間の役割と価値の再定義
  - 新たな倫理・道徳観の必要性

##### モジュール2: AI体験 〜新しい知能との対話〜
**学習目標**: 実際にAIツールを使って「人間ではない知能」との相互作用を体験する

- **2-1. ChatGPTとの対話体験**:
  - 基本的な対話AI体験
  - 人間との会話とAIとの会話の違いの発見
  - AI応答の特徴と限界の実感
- **2-2. 創作AIとの協働体験**:
  - 画像生成AIを使った創作活動
  - 人間の創造性とAIの創造性の違い
  - 協働による新しい創作プロセスの体験
- **2-3. 翻訳・検索AIの活用**:
  - 従来の検索エンジンとAI検索の違い体験
  - 言語の壁を超えるAI翻訳の可能性
  - 情報アクセス方法の変革の実感
- **2-4. AI時代のコミュニケーション**:
  - AIを介した新しいコミュニケーション形態
  - AI時代に必要となるリテラシーの基礎理解

#### **実践編（中級者向け）**
**対象**: AIの基本を理解し、実際に活用したい人
**目標**: 日常や仕事でAIを効果的に活用できるようになる

##### モジュール3: AI活用術
- **3-1. 効果的な質問の仕方**: プロンプト設計の基本
- **3-2. 文書作成でのAI活用**: レポート・メール作成支援
- **3-3. 学習でのAI活用**: 勉強・スキルアップへの応用
- **3-4. 創作でのAI活用**: アイデア発想・デザイン支援

##### モジュール4: AIリテラシー
- **4-1. AI情報の見分け方**: フェイクニュース・ディープフェイク対策
- **4-2. AIの回答を検証する**: 情報の正確性チェック方法
- **4-3. 著作権とAI**: AIと知的財産権の基本
- **4-4. プライバシーとAI**: 個人情報保護の注意点

#### **応用編（上級者向け）**
**対象**: AIを深く理解し、社会課題解決に活用したい人
**目標**: AI時代の新しい社会OSの構築に参画できる市民となる

##### モジュール5: AI社会論 〜新しい社会OSの設計〜
**学習目標**: AI時代に必要となる新しい社会制度・価値観・倫理観を考察し、社会変革に参画する能力を身につける

- **5-1. AIと労働の未来**:
  - 労働市場への根本的インパクトの理解
  - 人間の価値と役割の再定義
  - ベーシックインカムなど新しい社会保障システムの可能性
- **5-2. AIと教育革命**:
  - 従来の知識伝達型教育から創造・批判思考型教育への転換
  - AI時代に必要なリテラシーとスキルの再定義
  - 生涯学習社会の実現とパーソナライズド教育
- **5-3. AIと民主主義の進化**:
  - 情報操作・フェイクニュースによる民主的意思決定への脅威
  - AI支援による直接民主制の可能性
  - デジタル市民権と参加型社会の構築
- **5-4. AIガバナンス**:
  - AI開発・活用における倫理ガイドライン
  - 国際的なAI規制とステークホルダーの役割
  - 市民参加型のAI政策決定プロセス

##### モジュール6: AI実践プロジェクト 〜社会OS構築への参画〜
**学習目標**: 学習した知識を実際の社会変革活動に応用し、AI時代の社会OS構築に貢献する

- **6-1. 地域課題×AI解決プロジェクト**:
  - コミュニティが抱える具体的課題の特定
  - AI技術を活用した解決策の設計・実装
  - ステークホルダーとの協働による社会実装
- **6-2. AI倫理ケーススタディ**:
  - 現実のAI活用事例における倫理的ジレンマの分析
  - 多様な価値観を持つ参加者との議論・合意形成
  - 新しい倫理基準の提案と検証
- **6-3. AI教育実践**:
  - AI寺子屋の理念を基にした教育プログラムの企画・実施
  - 異なる世代・背景を持つ学習者への教育アプローチ
  - 教育成果の測定と継続的改善
- **6-4. 未来社会設計ワークショップ**:
  - AI時代の理想的な社会像の構想
  - 現在から未来への移行プロセスの設計
  - 市民、企業、政府の役割分担と協働モデルの提案

### 教材形式別要件

#### **社会OS理解を深める教材**
- **講義資料**: 各モジュール15-20分の講義スライド（深井龍之介氏の社会OS概念を基盤とした歴史的解説）
- **タイムライン教材**: 社会OS転換の歴史を視覚的に理解するインタラクティブ年表
- **タブー変遷マップ**: 時代ごとのタブーの変化を示すビジュアル教材

#### **AI体験・実践教材**
- **実習ワークシート**: 実際にAIツールを使う手順書（ChatGPT、画像生成AI、翻訳AIなど）
- **比較実験シート**: 人間とAIの能力・特性を比較体験するワークシート
- **プロンプト設計テンプレート**: 効果的なAI対話のためのガイド

#### **社会参画・思考深化教材**  
- **グループワーク**: 話し合いを通じて理解を深める活動設計（社会OS転換、AI倫理、未来社会構想）
- **ケーススタディ集**: AI時代の倫理的ジレンマを扱う事例集
- **プロジェクト設計テンプレート**: 地域課題×AI解決のための企画フレームワーク

#### **学習支援・評価教材**
- **振り返りシート**: 学習内容の定着を図る復習教材（社会OS概念の理解度確認含む）
- **評価ルーブリック**: 学習到達度を測定する基準（知識理解・技能習得・社会参画意識の3軸評価）
- **学習ポートフォリオ**: 個人の学習過程と成長を記録するツール

#### **コミュニティ学習支援**
- **ファシリテーターガイド**: AI寺子屋運営者のための指導手引書
- **世代間対話プログラム**: 異なる世代が共に学ぶための対話型学習設計
- **地域カスタマイズキット**: 各コミュニティの特性に合わせた教材調整ツール

---

## Review & Acceptance Checklist
*GATE: Automated checks run during main() execution*

### Content Quality
- [ ] No implementation details (languages, frameworks, APIs)
- [ ] Focused on user value and business needs
- [ ] Written for non-technical stakeholders
- [ ] All mandatory sections completed

### Requirement Completeness
- [ ] No [NEEDS CLARIFICATION] markers remain
- [ ] Requirements are testable and unambiguous  
- [ ] Success criteria are measurable
- [ ] Scope is clearly bounded
- [ ] Dependencies and assumptions identified

---

## Execution Status
*Updated by main() during processing*

- [x] User description parsed
- [x] Key concepts extracted
- [x] Ambiguities marked
- [x] User scenarios defined
- [x] Requirements generated
- [x] Entities identified
- [ ] Review checklist passed

---
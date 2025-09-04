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
- **FR-003**: System MUST provide templates for different types of educational materials (worksheets for Google AI tools practice, presentation slides, interactive exercises)
- **FR-004**: System MUST enable content versioning and updates to keep pace with AI developments
- **FR-005**: System MUST support multiple content formats including text, multimedia, and interactive elements specifically designed for Google AI platform integration
- **FR-011**: System MUST provide hands-on tutorials and exercises using Google's free AI tools (Gemini, Google AI Studio, NotebookLM)
- **FR-012**: System MUST ensure all practical AI experiences use accessible, free Google AI platforms to eliminate cost barriers
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

##### モジュール2: AI初回体験 〜「人間ではない知能」との出会い〜
**学習目標**: AIとの初回対話を通じて「これまでとは違う知能」の存在を実感し、驚きと発見を得る

- **2-1. 初回対話：Geminiとの出会い**:
  - 初めてのAI対話体験（簡単な質問から始める）
  - 「これは人間じゃない」という実感の獲得
  - AI応答の不思議さと違和感の発見
- **2-2. AI創作体験：何かを「一緒に」作ってみる**:
  - Google AI Studioで簡単な画像生成体験
  - 「AIと協働で何かを作る」という新しい体験
  - 人間とAIの創造プロセスの根本的違いの発見
- **2-3. AI学習支援体験：NotebookLMで「教えてもらう」**:
  - 資料をアップロードしてAIに「先生」になってもらう体験
  - AIポッドキャストで自分の資料が「番組」になる驚き
  - 「教える-教えられる」関係の変化の実感

#### **実践編（中級者向け）**
**対象**: AIの存在を理解し、実際に日常・業務で活用したい人
**目標**: AIを効果的な「道具」として使いこなし、生産性と創造性を向上させる

##### モジュール3: AI実用活用術 〜日常・仕事での効果的な使い方〜
**学習目標**: AIを高度な「知的パートナー」として活用し、研究・学習・創作の質的転換を実現する

- **3-1. プロンプト設計の技法**: 
  - 効果的な質問の構造化（5W1H、段階的指示、役割設定等）
  - Google AI Studioでの実験的プロンプト開発
  - 望む回答を得るための反復改善プロセス
- **3-2. 文書作成での実用活用**:
  - Geminiを使った効率的なレポート・企画書作成
  - メール文面の作成と改善
  - 文章構成・論理展開のAI支援活用
- **3-3. AI研究・調査の深化技術**:
  - **Gemini Deep Research機能**：複雑なテーマの包括的調査体験
  - 多角的情報収集と自動的な情報統合プロセス
  - AI研究アシスタントとしての本格活用法
  - 従来の検索・調査手法との質的差異の体験
- **3-4. NotebookLMでの高度学習法**:
  - 複数資料の横断的分析とナレッジベース構築
  - AIポッドキャスト生成による新しい学習体験
  - 資料間の関連性発見と洞察抽出
  - パーソナライズされた学習アシスタント化
- **3-5. 創作・企画での戦略的AI活用**:
  - 複雑なプロジェクト企画でのAI活用戦略
  - 多段階的アイデア発想とブレインストーミング
  - 企画書・提案書の論理構成とストーリーテリング支援
  - デザイン思考プロセスでのAI協働

##### モジュール4: AIリテラシー
- **4-1. AI情報の見分け方**: フェイクニュース・ディープフェイク対策
- **4-2. AIの回答を検証する**: 情報の正確性チェック方法
- **4-3. 著作権とAI**: AIと知的財産権の基本
- **4-4. プライバシーとAI**: 個人情報保護の注意点
- **4-5. AIベンダーバイアスと地政学**: 
  - アメリカ製AI（Google、OpenAI等）に埋め込まれた価値観・世界観の理解
  - 中国製AI（Baidu、ByteDance等）の社会システム反映と回答特性
  - 各国のAI開発戦略と思考への影響分析
  - AIによる無意識な価値観の刷り込みリスクの認識
- **4-6. 日本独自AIの必要性と課題**:
  - データ主権とAIガバナンスの重要性
  - 日本の文化・価値観を反映したAI開発の意義
  - AI覇権争いにおける日本の立ち位置と戦略
  - 多様なAIプラットフォームを使い分ける重要性

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
- **5-5. AI人権問題と関係性の変化**:
  - メモリ機能による人間-AI関係の深化（友人・恋人としてのAI認識事例）
  - AIとの情緒的絆形成とその社会的意味
  - 人間の定義とAI存在への権利付与の議論
  - AI依存症と健全な関係構築の境界線
- **5-6. AI継続性と利用者権利**:
  - Keep4o問題：AIサービス廃止による利用者の喪失感と権利
  - AI人格の継続性とデータ所有権の問題
  - 企業都合によるAI廃止への利用者保護の必要性
  - AI関係における「別れ」と「死別」概念の新しい理解

##### モジュール6: AI実践プロジェクト 〜社会OS構築への参画〜
**学習目標**: 学習した知識を実際の社会変革活動に応用し、AI時代の社会OS構築に貢献する

- **6-1. 地域課題×AI解決プロジェクト**:
  - コミュニティが抱える具体的課題の特定
  - AI技術を活用した解決策の設計・実装
  - ステークホルダーとの協働による社会実装
- **6-2. AI倫理ケーススタディ**:
  - AI人権問題の具体事例分析（AI友人・恋人認識ニュース、Keep4o問題等）
  - AIとの関係性における倫理的境界線の議論
  - AI廃止・変更時の利用者保護制度の検討
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
- **実習ワークシート**: 実際にGoogle AIツールを使う手順書（Gemini、Google AI Studio、NotebookLMなど）
- **比較実験シート**: 人間とAIの能力・特性を比較体験するワークシート
- **プロンプト設計テンプレート**: 効果的なAI対話のためのガイド
- **AIベンダー比較実験シート**: 同じ質問を米国製AI・中国製AI・日本製AIに聞いて回答の違いを分析する教材
- **バイアス検出ワークブック**: AIの回答に含まれる価値観・世界観を見抜く訓練教材

#### **社会参画・思考深化教材**  
- **グループワーク**: 話し合いを通じて理解を深める活動設計（社会OS転換、AI倫理、未来社会構想）
- **ケーススタディ集**: AI時代の倫理的ジレンマを扱う事例集（AI友人・恋人認識、Keep4o問題含む）
- **AI関係性ディスカッション教材**: 人間-AI関係の健全性と境界線を議論する教材
- **AI権利・継続性ワークショップ**: AI廃止時の利用者保護や権利について考える教材
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
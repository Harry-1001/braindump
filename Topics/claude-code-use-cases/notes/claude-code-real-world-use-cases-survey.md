---
title: "Claude Code 実活用事例サーベイ（2026-04-02）"
created: "2026-04-02"
topic: "claude-code-use-cases"
tags:
  - topic/claude-code-use-cases
  - domain/work
  - #reference
---

# Claude Code 実活用事例サーベイ

## Summary

- エンジニアだけでなくPM・デザイナー・セールス・経営者・非エンジニアまで幅広く実務利用されている
- 「コードを書く」ツールから「業務自動化エージェント」へのシフトが顕著で、ファイル操作・分析・コンテンツ生成・ワークフロー自動化に使われている
- 1日に複数セッションを並走させる「並列運用」や、CLAUDE.mdで文脈を蓄積する「自己学習ループ」が上位ユーザーの共通パターン

---

## Notes

### カテゴリ1: エンジニア・開発者の日常ワークフロー

**1. Boris Cherny（Claude Code作者）— 並列セッション＋カスタムコマンド**
- 端末タブで5〜15のClaude Codeセッションを並行起動。各セッションはgit worktreeを持ち競合しない
- `/commit-push-pr` コマンドを「1日に何十回も使う」。git statusを事前計算してバックアンドフォースを最小化
- バグ修正の指示はシンプルに `"Fix."` の一言だけ。細かく指示しないことを哲学とする
- `code-simplifier` と `verify-app` というサブエージェントを常用。claude.aiを実際にブラウザで開いてUIを確認させ、それが品質を「2〜3倍高める」と発言
- Slack・BigQuery・Sentry のMCPを接続し、外部ツールへのアクセスをエージェントに委譲
- ソース: [Boris Cherny on X](https://x.com/bcherny/status/2007179832300581177) / [mindwiredai.com解説](https://mindwiredai.com/2026/03/25/claude-code-creator-workflow-claudemd/)

**2. Neil Kakkar（エンジニア）— PR自動化とUI検証**
- `/git-pr` スラッシュコマンドでPR作成を完全自動化。「PR説明文がdiff全体を読んで書かれるので、自分で書くより丁寧になった」
- エージェントが変更を加えたらUI previewで自動検証させ「完了」の定義を「UIが壊れていないこと」に変えた
- 最終的に「worktreeを5本並走」するインフラを整備し、以前の「2ブランチで手一杯」から脱却
- ソース: [neilkakkar.com](https://neilkakkar.com/productive-with-claude-code.html)

**3. エンジニア一般 — テスト駆動開発の自動化**
- 失敗するテストをClaude Codeに先に書かせ、その後実装させるTDD運用で「バグを70%削減」という報告
- CLAUDE.mdをgit管理しチームで共有。誤った挙動があったらその場でCLAUDE.mdに追記し「次から繰り返さない」ルールを徹底
- ソース: [f22labs.com](https://www.f22labs.com/blogs/10-claude-code-productivity-tips-for-every-developer/)

---

### カテゴリ2: プロダクトマネージャー（PM）

**4. Ondrej Machart（Head of Product @ Livesport）— 6ヶ月で13プロジェクト**
- 非エンジニアのPMがiOSアプリをApp Storeに公開（課金機能・外部API統合・月100ユーザー超）
- 自社の30+プロダクトを任意の軸でマッピングする「ポートフォリオコーチ」Webアプリを作成。「C-levelの重大なブランド統合判断に使われた」
- 10人の同僚向けvibe-codingワークショップを開催し、複数の社内ツールが生まれた
- 家族の系譜を17世紀までたどった家系図をAI生成肖像画付きで作成（業務外だが日常ワークフローとして言及）
- ソース: [medium.com/@ondrej.machart](https://medium.com/@ondrej.machart/13-claude-code-projects-that-changed-my-product-manager-role-over-the-last-6-months-7057b9045d51)

**5. PM一般 — PRD・Jiraチケット・ユーザーインタビュー分析**
- ユーザーインタビュー録音10本をフォルダに入れてコマンド1発 → 構造化サマリー10本を生成。1本手動処理する時間で全部終わる
- PRDをmarkdownで書いてterminal開くと20分後に動くプロトタイプができている（Chime PMの事例）
- Figma MCPと組み合わせるとデザイナーがmockupを更新 → Reactコンポーネントが自動更新
- ソース: [medium.com/product-powerhouse](https://medium.com/product-powerhouse/claude-code-for-product-managers-complete-setup-guide-real-pm-workflows-2026-c94ec7087b6f)

---

### カテゴリ3: デザイナー

**6. Clinton Halpin（プロダクトデザイナー）— UXコピーとプロトタイプ環境**
- Linear・Notion・FigmaのMCPを接続し、デザイン文脈を自動参照させてUXコピーを生成。「一番うまくいったユースケース」と明言
- `/setup` スキルを作成してデザイナー・PMがプロトタイプ環境を構築できるようにした
- Claudeに自律的にプロトタイプをつくらせながら自分はミーティングに出る試みを実験中（まだ試行錯誤段階）
- ソース: [clintonhalpin.com](https://clintonhalpin.com/blog/using-claude-code-for-product-design/)

---

### カテゴリ4: セールス・マーケティング

**7. セールスチーム — リード自動獲得パイプライン**
- Apollo（リードエンリッチメント）+ Sales Navigator（見込み客スクレイピング）+ Instantly（メール配信）を接続し、手動リサーチを自動化
- リード資格確認（lead qualification）をパイプライン処理させ、「自分がミーティング中に自動で動かせる」
- ソース: [alexlieberman.com](https://alexlieberman.com/claude-code-beyond-engineering-11-powerful-use-cases-from-ultra-users/)

**8. マーケター — ブランドトーンを学習したメールキャンペーン生成**
- 過去のメール全体を学習させたスキルを作成。ブランドの語り口を維持しながらキャンペーン文を生成
- ソース: [alexlieberman.com](https://alexlieberman.com/claude-code-beyond-engineering-11-powerful-use-cases-from-ultra-users/)

---

### カテゴリ5: 非エンジニア・ナレッジワーカー全般

**9. Dan Shipper（CEO @ Every）— 経費精算の自動化**
- クレジットカードの明細をダウンロードして「先週の経費を1枚のWebページにまとめて。カテゴリ分けして」と指示 → 完成
- 出張のたびにデータが蓄積され、精度が上がっていく
- ソース: [every.to](https://every.to/source-code/how-to-use-claude-code-for-everyday-tasks-no-programming-required)

**10. Katie Parrott（AI Editorial Lead @ Every）— コンテンツパフォーマンス分析**
- 1年分のリーダーエンゲージメントCSVを「クラウドアプリには大きすぎる」と言いながらClaude Codeで処理
- 「どんな書き出しが読まれるか」のパターン抽出、記事タイトルと滞在時間の相関分析
- ソース: [every.to](https://every.to/source-code/how-to-use-claude-code-for-everyday-tasks-no-programming-required)

**11. Anushki Mittal（オペレーション・カスタマーサポートマネージャー @ Every）— サポートメール自動下書き**
- エンジニアに聞かずに済むようGitHubのコードベースをダウンロードして自分で問い合わせに答えられるように
- `/cora-support-email-writer` コマンドを作成。コードベースを参照して「下書きを自動生成してくれる。自分で編集して送るだけ」
- ソース: [every.to](https://every.to/source-code/how-to-use-claude-code-for-everyday-tasks-no-programming-required)

**12. Nityesh Agarwal（エンジニア @ Every）— ヘルプセンター更新とマーケコピー生成**
- `/update-help-center`: コード変更を見てヘルプドキュメントの更新が必要な箇所をフラグ
- `/help-me-market`: 新機能リリースを分析して月次ニュースレター用のマーケコピー3パターンを生成
- ソース: [every.to](https://every.to/source-code/how-to-use-claude-code-for-everyday-tasks-no-programming-required)

**13. ニュースレター発行者 — 請求書200枚を4分で処理**
- 「このフォルダのPDF全部スキャンして、クライアント名・金額・通貨・支払日を抽出して YYYY-MM-DD_ClientName_Amount でリネームして」
- 従来: 金曜の午後 + 300ドルの外注。Claude Code導入後: 4分
- ソース: [futuredigestnews.substack.com](https://futuredigestnews.substack.com/p/claude-code-changed-everything-heres)

**14. リサーチャー・アナリスト — 決算説明資料50本から調査ブリーフ作成**
- 「50本のドキュメントのフォルダを指定して、何を抽出するか伝えるだけで25分で完全な調査ブリーフができる」（直接引用）
- 矛盾する情報の自動フラグ付き
- ソース: [futuredigestnews.substack.com](https://futuredigestnews.substack.com/p/claude-code-changed-everything-heres)

**15. 競合インテリジェンスアナリスト — 10社を同じフレームワークで並列分析**
- 1社ずつ手動でやっていた競合調査を同一フレームワークで10社同時実行 → 20分
- ソース: [futuredigestnews.substack.com](https://futuredigestnews.substack.com/p/claude-code-changed-everything-heres)

**16. 小規模事業者 — 帳簿の自動化（月8時間削減）**
- ファイルのリネーム・経費のカテゴリ分け・請求書の突き合わせ・P&Lレポート作成をClaude Codeで処理
- 月8時間 → 20分に削減
- ソース: [futuredigestnews.substack.com](https://futuredigestnews.substack.com/p/claude-code-changed-everything-heres)

**17. コンサルタント — 提案書作成を3日から4時間へ**
- プロジェクト履歴のファイル群を渡して「この案件向けの提案書を書いて」
- 3日 → 4時間に短縮。「月に1クライアント分の工数が空いた」
- ソース: [futuredigestnews.substack.com](https://futuredigestnews.substack.com/p/claude-code-changed-everything-heres)

**18. 弁護士業務周辺のビジネスパーソン — 契約書200本の自動スキャン**
- ベンダー契約のリスク条項フラグ付け、条件比較、交渉ガイダンス生成
- 手動で1本見ていた時間で200本スキャン完了
- ソース: [futuredigestnews.substack.com](https://futuredigestnews.substack.com/p/claude-code-changed-everything-heres)

---

### カテゴリ6: 梶谷健人（新規事業立ち上げ支援・CPO）— 日本語事例

**19. 梶谷健人 — ワークフロー全体の一元化**
- 従来: ChatGPT・Gemini・Notion・Google Sheetsをタブ行き来
- 現在: 「毎朝AIに工程表を作ってもらい、プロジェクト背景を加味した戦略立案、トレンド収集から記事執筆、タスク管理までコマンド一発で回す」
- ソース: [note.com/kajiken0630](https://note.com/kajiken0630/n/nc0cb92bc080f)

**20. 横峯 樹（アソビュー CPO）— 毎朝7時に自動起動する11本の自動化ジョブ**
- 毎朝7時に自動で11種類のジョブが実行されるシステムをClaude Codeで構築
- 「地味だけど毎日使う」タスク（記事タイトルまとめ・メトリクス集計等）を完全自動化
- ソース: [note.com/tyokomine](https://note.com/tyokomine/n/n57e552050ca1)

---

## 横断パターンの分析

| パターン | 説明 |
|---|---|
| **並列セッション運用** | 複数のworktree×複数のClaude Codeで並行開発。Borisは15セッション同時起動 |
| **CLAUDE.md蓄積ループ** | 誤りをその場で記録→次回から繰り返さない。組織ナレッジの自動蓄積 |
| **カスタムスラッシュコマンド** | `/commit-push-pr` `/git-pr` `/cora-support-email-writer` などで繰り返し作業を圧縮 |
| **MCPによる外部接続** | Slack・BigQuery・Sentry・Figma・Linear・Notionを直接操作させる |
| **フォルダ一括処理** | 「このフォルダのファイルを全部〇〇して」という自然言語で大量ファイルを処理 |
| **非エンジニアの越境** | PMがiOSアプリ公開、オペレーション担当がサポートシステム構築 |

---

## Questions

- CLAUDE.mdの蓄積が長期的にどう機能するか（膨大になったときのコンテキスト問題）
- 並列セッションのコスト構造はどうなっているか
- 日本企業での導入事例はまだ少ない？非エンジニア活用の障壁は何か
- Figma MCP × Claude Codeのデザイン-実装ループはどこまで自律化できるか

---

## References

- [Boris Cherny on X (Claude Code creator)](https://x.com/bcherny/status/2007179832300581177)
- [Alex Lieberman: 11 Ultra-User Use Cases](https://alexlieberman.com/claude-code-beyond-engineering-11-powerful-use-cases-from-ultra-users/)
- [Every.to: Everyday Tasks Without Programming](https://every.to/source-code/how-to-use-claude-code-for-everyday-tasks-no-programming-required)
- [Neil Kakkar: How I'm Productive with Claude Code](https://neilkakkar.com/productive-with-claude-code.html)
- [Ondrej Machart: 13 Projects as a PM](https://medium.com/@ondrej.machart/13-claude-code-projects-that-changed-my-product-manager-role-over-the-last-6-months-7057b9045d51)
- [Clinton Halpin: Claude Code for Product Design](https://clintonhalpin.com/blog/using-claude-code-for-product-design/)
- [Future Digest: Claude Code Changed Everything](https://futuredigestnews.substack.com/p/claude-code-changed-everything-heres)
- [梶谷健人 note: エンジニア以外も全員が使うべきツール](https://note.com/kajiken0630/n/nc0cb92bc080f)
- [横峯樹 note: 毎日使うAI自動化を11個作った話](https://note.com/tyokomine/n/n57e552050ca1)
- [Department of Product: Non-Engineering Use Cases](https://departmentofproduct.substack.com/p/how-to-use-claude-code-for-non-engineering)
- [f22labs: 10 Productivity Tips](https://www.f22labs.com/blogs/10-claude-code-productivity-tips-for-every-developer/)
- [mindwiredai: Boris Cherny Creator Workflow](https://mindwiredai.com/2026/03/25/claude-code-creator-workflow-claudemd/)

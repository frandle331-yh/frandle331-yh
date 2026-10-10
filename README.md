# Hierax_Umbra

セキュリティリサーチと自律型AIインフラの構築に従事。
Security researcher & autonomous AI infrastructure engineer.

---

## セキュリティアドバイザリ・クレジット / Security Advisories & Credits

| 対象 / Project | 内容 / Issue | 状態 / Status |
|---|---|---|
| **basecamp/once-campfire** | ルームメンバーが他メンバーのメッセージをライブ表示上で差し替えられる問題（Medium, CVSS 3.1: 4.3） | [GHSA-3v99-4vxh-xg84](https://github.com/basecamp/once-campfire/security/advisories/GHSA-3v99-4vxh-xg84) 公開済み・1.5.2で修正・クレジット掲載（CVE申請中） |
| **formbricks/formbricks** | メール認証後の自動サインインを悪用したアカウント事前乗っ取り（account pre-hijacking） | 報告者として明記された修正 [PR #8971](https://github.com/formbricks/formbricks/pull/8971)・6.0.0でリリース・[リリースノート](https://github.com/formbricks/formbricks/releases)にクレジット掲載 |

## OSSへの修正貢献 / Upstream Fixes

- **nodejs/node** — `fs.mkdtemp` の長いプレフィックスにおける範囲外書き込み（ヒープバッファオーバーフロー）を修正（AddressSanitizerで検出） — [PR #64770](https://github.com/nodejs/node/pull/64770)（main にマージ済み）
- **slackhq/nebula** — リレーのControlメッセージで nil アドレスによりノードがクラッシュする問題を報告・修正案を提出 — [PR #1747](https://github.com/slackhq/nebula/pull/1747) → メンテナーの [PR #1785](https://github.com/slackhq/nebula/pull/1785) で修正

## AIセキュリティ / AI Security

- **huntr AI Challenge 1** — 株取引AIエージェントへのプロンプトインジェクションに成功（所持金を超える購入を実行させる）。突破者の一人。
- 解説記事：[Qiita — プロンプトインジェクションは「言葉遊び」ではない](https://qiita.com/hierax_umbra/items/9bfe232771665b400d73)

## 脆弱性を見つける仕組み / How I Find Bugs

上の実績の多くは、自作の以下のツール群で見つけています。

**1. bug-bounty-hunter — 脆弱性探索パイプライン**

静的解析（CodeQL / Joern / Slither）で候補を洗い出し、LLMが再現手順の作成と検証を行うパイプライン。LLMの判断だけに任せず、各段階を決められた手順と検証条件で区切ることで、誤検知や「それらしいが成立しない」報告を出さないようにしています。

**2. [Spec-Lab](https://github.com/frandle331-yh/Spec-Lab) — AI生成コードの独立監査**

AIが書いた・直したコードを、別の監査用エージェントがテストと仕様の制約に照らしてチェックし、条件を満たすまで差し戻し続ける仕組み。上のパイプラインの検証部分の考え方を切り出して公開したものです。

**3. ローカルLLM推論サーバー**

上記を24時間動かすための自前のGPUサーバー（Dell Precision 7820 / RTX 3060 ×2）。推論エンジンの調整で生成速度を約7.5倍、最初の応答が返るまでの時間を約2.2秒→0.14秒に短縮。複数のAI処理がGPUメモリを取り合わないよう調整する自作ツールも運用しています。

## 研究領域 / Vulnerability Research Areas

個別プログラムの守秘義務に配慮し、未公開の対象名や実装詳細は伏せています（公開済みのものは上記リンクを参照）。

**1. Authentication & Access Control (Fail-Open)** — 認可ロジックの分岐漏れや認証フローの不備による未認可アクセス・アカウント乗っ取り。

**2. HTTP Protocol / Parser Desync** — サーバー・プロキシ・クライアント間の境界解釈齟齬によるRequest Smuggling（CL.TE/TE.CL）クラス。

**3. Input Validation & Escape Injection** — 信頼できない入力の無害化不足による注入・改ざん。自律検証パイプラインがOSS LLM推論サーバーにおけるRCEパターンを検出した実績もあり（第三者の既知報告と重複のため正式報告は見送り）。

**4. Web3 / Smart Contract Economic Security** — ERC4626初回預入時のシェア価格つり上げ攻撃や、所有権・初期化関数の呼び出し順序不備によるアクセス制御抜けなど。

**5. LLM / AI Agent Security** — プロンプトインジェクションによるエージェントの権限・制約逸脱。

---

## Support

If you understand why an anti-yes-man gate is necessary, you know what to do.

[Sponsor this research →](https://github.com/sponsors/frandle331-yh)

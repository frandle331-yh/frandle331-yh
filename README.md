# Hierax_Umbra

セキュリティリサーチと自律型AIインフラの構築に従事。
Security researcher & autonomous AI infrastructure engineer.

---

## 公開済みの貢献実績 / Public Contributions

- **nodejs/node** — mkdtempの長いプレフィックスにおけるヒープバッファオーバーフローを修正(AddressSanitizerで検出) — [PR #64770](https://github.com/nodejs/node/pull/64770)
- **slackhq/nebula** — リレーのControlメッセージ処理におけるnilポインタ参照外れをガード — [PR #1747](https://github.com/slackhq/nebula/pull/1747)
## 主なアーキテクチャ・インフラ構築実績 / Infrastructure & Architecture

**1. precision7820 — オンプレAI推論基盤**

Dell Precision 7820(2×Xeon Gold 6252, 2×RTX 3060 24GB)上に24時間稼働のローカルLLM推論基盤を構築・運用。Aphrodite Engine + CUDA Graphs最適化でデコード速度を7.5倍高速化、24GiB CPU-RAM KVティアオフロードでTTFTを2.2秒→136msに短縮。複数AIワークロード間のVRAM排他制御を行う自作CLIツールも開発。

**2. [Spec-Lab](https://github.com/frandle331-yh/Spec-Lab) — AI生成コード自動監査オーケストレーション**

AIエージェントが生成・改修したコードを、独立した監査エージェントがテスト要件とドメイン制約に照らして検証するベンチマーク環境。特定条件を満たすまで、終了しない機構。

**3. bug-bounty-hunter — 自律型脆弱性検出パイプライン**

静的解析(CodeQL, Joern, Slitherなど)とLLMを組み合わせ、脆弱性の探索・再現・多層検証を自動化する決定論的オーケストレーションシステム。

## 検出できる脆弱性カテゴリ / Vulnerability Research Areas

個別プログラムの守秘義務に配慮し、対象名や固有の実装詳細は伏せています(公開・修正済みのものは上記PRリンクを参照)。

**1. Authentication & Access Control (Fail-Open)** — 認可ロジックの分岐漏れにより未認可アクセスが発生するクラス。

**2. HTTP Protocol / Parser Desync** — サーバー・プロキシ間の境界解釈齟齬によるRequest Smuggling(CL.TE/TE.CL)クラス。

**3. Input Validation & Escape Injection** — 信頼できない入力の無害化不足による注入・改ざん。自律検証パイプラインがOSS LLM推論サーバーにおけるRCEパターンを検出した実績もあり(提出前に第三者による既知の重複と判明したため正式報告は見送り)。

**4. Web3 / Smart Contract Economic Security** — ERC4626初回預入時のシェア価格つり上げ攻撃や、所有権・初期化関数の呼び出し順序不備によるアクセス制御抜けなど。

---

## Support

If you understand why an anti-yes-man gate is necessary, you know what to do.

[Sponsor this research →](https://github.com/sponsors/frandle331-yh)

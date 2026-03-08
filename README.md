# Hayato Yokoshima

Webエンジニアを目指して学習しています。 

ユーザーが継続して使えるサービス設計や、データを活用した分析機能の実装に興味があります。
Ruby on Railsを中心にWebアプリケーション開発を行っています。



---

# Skills

### Backend
- Ruby / Ruby on Rails

### Frontend
- TypeScript / JavaScript
- React
- Hotwire (Turbo / Stimulus)
- Tailwind CSS

### Testing
- Vitest / Testing Library

### Infrastructure
- PostgreSQL
- Git / GitHub
- GitHub Actions (CI/CD)
- REST API

---

# Projects

## KajiMate — 家事分担可視化アプリ

家事分担をデータで可視化する Web アプリ。  
実際の同居生活で利用することを想定し、継続して使える UX 設計とデータ可視化を重視して開発しました。

### 主な技術的取り組み
- **データ可視化**: 家事の偏りを定量的に見せることで、感情論でなくデータで会話できる設計

### Tech
Ruby / Rails / Hotwire / PostgreSQL

### URL
https://kajimate.com

### GitHub
https://github.com/frandle331-yh/graduation_app

---

## KABULENS — 投資分析ツール（個人利用）

東証上場 3,700 銘柄超を多層パイプラインで構造分析、独自スコアでキュレーションを行う

 
J-Quants API と Claude API を組み合わせた 3 層アーキテクチャ（事実→計算→AI解釈）で設計。  
73 件のテスト、型安全なコンポーネント設計、ルールベースのクラスター分類エンジンを実装しました。

### 主な技術的取り組み
- **3 層アーキテクチャ**: データ取得(L1)・スコアリング(L2)・AI 解釈(L3)を分離し、各層を独立してテスト・差し替え可能に設計
- **73 件のテスト**: コンポーネント・フック・ユーティリティを Testing Library でカバー。localStorage 破損耐性やスキーマ進化テストを含む
- **型駆動開発**: `Stock` インターフェース(119 行)を唯一の正とし、`any` 型ゼロで全層を型安全に接続

### Tech
React 19 / TypeScript / Vite / Tailwind CSS / Recharts / Vitest/
J-Quants-API/ Anthropic API

### Demo
https://frandle331-yh.github.io/kabulens-public/

### GitHub
https://github.com/frandle331-yh/kabulens-public

---

## AI Chat App — Claude API 会話アプリ

Claude API を利用した AI 会話アプリ。

### Tech
Next.js / Anthropic API

### URL
https://ai-chat-app-wine-eta.vercel.app

### GitHub
https://github.com/frandle331-yh/ai-chat-app

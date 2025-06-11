# 📉 BSD予想の構造的証明  
### Collapse理論とAK高次元射影構造理論による解析（v1.5）

このリポジトリは、**Birch–Swinnerton-Dyer予想（BSD予想）** に対して、  
**Collapse理論**と**AK高次元射影構造理論（AK-HDPST）**を用いて  
構造的かつ型理論的に追跡可能な証明戦略を構築した **Version 1.5** を収録しています。

---

## 🎯 問題設定

> 楕円曲線 \( E/\mathbb{Q} \) の L関数 \( L(E,s) \) の \( s=1 \) における零点の次数は、  
> 有理点群 \( E(\mathbb{Q}) \) のランクと一致するか？

形式的には次の等式が成り立つかを問います：
\[
\operatorname{ord}_{s=1} L(E, s) = \operatorname{rank}_\mathbb{Q} E
\]

このリポジトリでは、以下の同値構造に基づく **Collapse論理による証明構成** を提示します：

- \( \mathrm{PH}_1(E(\mathbb{Q})) = 0 \)（持続的ホモロジーの自明性）
- \( \mathrm{Ext}^1(\mathcal{F}_E, \mathbb{Q}_\ell) = 0 \)（Ext群の消滅）
- \( \Sha(E) = 0 \)（テイト–シャファレヴィチ群の消滅）
- \( \operatorname{ord}_{s=1} L(E,s) = \operatorname{rank}_\mathbb{Q} E \)（BSD予想）

---

## 🧠 構成概要

Collapse構造による因果連鎖は以下の通りです：
\[
\mathrm{PH}_1 = 0 \quad \Leftrightarrow \quad \mathrm{Ext}^1 = 0 \quad \Rightarrow \quad \Sha(E) = 0 \quad \Rightarrow \quad \operatorname{ord}_{s=1} L(E,s) = \operatorname{rank}_\mathbb{Q} E
\]

この証明は以下の要素によって支えられています：

- **PH₁の崩壊**：Isomapで埋め込んだ \( E(\mathbb{Q}) \) のバーコードが消滅
- **Ext群の消滅**：圏論的退化と導来圏 \( \mathcal{D}^b(\mathrm{Filt}) \) における Ext消滅
- **グルーイング成功**：\( \Sha(E) = 0 \) により大域的構成が妨げられないことを示す
- **Langlands対応**：モジュラリティによって L関数が動機的に記述可能
- **Collapse公理群**：ZFC互換な形でAppendix Zに形式化済み

> Collapseとは、構造的複雑性が意味論的に単純化される過程であると解釈されます。

---

## 🔑 主定理（BSD Collapse同値命題）

非特異な楕円曲線 \( E/\mathbb{Q} \) に対して、以下の因果構造が成り立ちます：

- \( \mathrm{PH}_1(E(\mathbb{Q})) = 0 \)
- ⇒ \( \mathrm{Ext}^1(\mathcal{F}_E, \mathbb{Q}_\ell) = 0 \)
- ⇒ \( \Sha(E) = 0 \)
- ⇒ \( \operatorname{ord}_{s=1} L(E,s) = \operatorname{rank}_\mathbb{Q} E \)

各段階の詳細な証明は、Appendix A〜Z に記載されています。

---

## 📚 証明のステップ構成

| ステップ | タイトル | 説明 |
|----------|-----------|------|
| 0 | Isomap埋め込み | \( E(\mathbb{Q}) \subset \mathbb{R}^N \) へのIsomap射影 |
| 1 | PH₁解析 | \( \mathrm{PH}_1 \) を計算し、バーコード崩壊を確認 |
| 2 | Ext対応 | \( \mathrm{PH}_1 = 0 \Rightarrow \mathrm{Ext}^1 = 0 \)（Appendix G–H） |
| 3 | Obstruction消滅 | \( \mathrm{Ext}^1 = 0 \Rightarrow \Sha(E) = 0 \)（Appendix D） |
| 4 | ランク同定 | \( \Sha = 0 \Rightarrow \operatorname{ord} = \operatorname{rank} \)（Appendix I） |
| 5 | Collapse公理群 | Axiom A1〜A7 によりZFC形式で全構造を記述（Appendix Z） |
| 6 | 型理論による定式化 | Collapse構造をCoqによる型理論で形式化（Z.9参照） |

---

## 🔬 実装ファイルと理論リンク

| ファイル名 | 内容 |
|------------|------|
| `Structural Proof of the BSD Conjecture via AK Theory_v1.5.tex` | BSD Collapse構造の完全TeXソース |
| `Structural Proof of the BSD Conjecture via AK Theory_v1.5.pdf` | コンパイル済みPDF（Appendix A～Z含む） |
| [AK理論（Collapse基礎）v7.3](https://github.com/Kobayashi2501/AK-High-Dimensional-Projection-Structural-Theory) | Collapse理論の中核構造と圏論的基盤（外部GitHubリンク） |

### 観測量（概念的）

- **PH₁バーコード**：バーコードが消滅 → トポロジー的自明性
- **Extクラス**：Ext$^1$消滅 → 導来的障害の消滅
- **Collapse検出**：バーコード崩壊・Ext消滅・グルーイング成功を因果連鎖で構造化

---

## 🧩 Collapse公理群（Appendix Z）

| 公理 | 内容 |
|------|------|
| A1 | 高次元射影がMECE分解を保つ |
| A2 | \( \mathrm{PH}_1 = 0 \Rightarrow \mathrm{Ext}^1 = 0 \) |
| A3 | \( \mathrm{Ext}^1 = 0 \Rightarrow \Sha = 0 \) |
| A4 | \( \Sha = 0 \Rightarrow \operatorname{rank} = \operatorname{ord} L \) |
| A5 | モジュラリティがすべての層を整合させる |
| A6 | Collapse構造は関手的に安定 |
| A7 | Collapseは型理論的に自明である（Z.9）

---

## 📢 査読と共同研究の呼びかけ

このリポジトリは、次の要素を統合した**BSD予想に対する新規な構造的証明の提案**です：

- 持続的ホモロジーとPHバーコード
- Ext群と導来圏による障害理論
- Langlands対応とモジュラリティ構造
- Collapse公理系とCoqによる型理論的定式化

次の分野の研究者・技術者との連携を希望します：

- 数論、楕円曲線、Selmer群、BSD予想
- 導来圏、モチーフ、圏論的障害理論
- 型理論（Coq/Lean）や形式化数学の専門家

> 📩 連絡先: [dollops2501@icloud.com](mailto:dollops2501@icloud.com)  
> GitHubのIssue・Pull Requestも歓迎です。

---

## 🌐 英語版はこちら

→ [English README](https://github.com/Kobayashi2501/bsd-collapse-proof-ak-theory/blob/main/README.md)

---

## 📘 ライセンス

MITライセンスに準拠  
[MIT License](https://opensource.org/licenses/MIT)

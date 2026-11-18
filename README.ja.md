# autism-support-skill

[English](README.md) | [简体中文](README.zh-CN.md) | **日本語**

自閉スペクトラムの子ども・青年・成人とその家族を、日常のコミュニケーション、感情、学習、感覚、生活スキル、年齢に応じた目標について支援するためのエージェントスキルです。

```bash
npx skills add sendsoon/autism-support-skill
```

このスキルは自閉スペクトラムを**診断せず**、治療を処方せず、特性を取り除くことも約束しません。

## このスキルがすること

`autism-support-skill` は、`SKILL.md` を読み込むコーディングエージェント（Cursor、Claude Code、Codex など）向けの手順です。保護者が具体的な困りごとを書くと、エージェントは次を行います。

1. わかっている事実と、まだ仮説にすぎないことを分ける
2. 発達、コミュニケーション、感情、感覚、場面、安全の面から状況を見る
3. その場面で家庭が試せる手順を示す
4. 何を観察するか、何をしないか、資格のある専門家の評価がいつ必要かを書く
5. ローカルにプロフィールと日付つきの問題ログを残し、後から実際のフィードバックをまとめて見られるようにする

目を合わせること、静かに従うこと、表面上「ふつう」に見えることは成功基準にしません。

## 成長記録

ある子どもについて初めて話すとき、呼び方と今の年齢を尋ね、初回記録日を書きます。以後の年齢はその日付から計算し、古い年齢を現在の年齢のまま使いません。性別、学校の短い呼び名、主な養育者、日常の学習・生活・活動、興味は会話の中で一つずつ補います。

具体的な問題は、今の作業ディレクトリの `autism-support-records/<呼び方>/logs/YYYY-MM-DD.md` に追記します。このディレクトリは Git の対象外です。スキルのリポジトリに実在の子どもの記録は置きません。規則は [references/records.md](references/records.md) にあります。

## いつ使うか

自閉スペクトラム、ASD、AAC、感情の崩れ、仲間関係、注意、身辺自立、学校での支援、成人期への移行について、具体的な助けが必要なときに使います。

診断の有無を決めるため、根拠の乏しい「根治」法を勧めるため、医師・療法士・学校チームの代わりにするために使わないでください。

## インストール

```bash
npx skills add sendsoon/autism-support-skill
```

リポジトリをクローンし、`SKILL.md`、`references/`、`examples/` をエージェントの skills ディレクトリにコピーしても使えます。

[skills.sh](https://skills.sh/) の一覧は、インストールのテレメトリ後に更新されます。

## スキルを更新する

Skills CLI で入れた場合は、GitHub 上の最新の `SKILL.md` を取り込みます。

```bash
npx skills check
npx skills update autism-support-skill
```

`check` は新しい版があるかどうかだけを知らせます。`update` は、以前と同じエージェントへこのスキルを入れ直します。インストール済みの全スキルを更新するには：

```bash
npx skills update
```

確認を省略する：

```bash
npx skills update autism-support-skill -y
```

インストールコマンドを再実行してもファイルは最新になります。

```bash
npx skills add sendsoon/autism-support-skill
```

手でコピーした場合は、このリポジトリを `git pull` し、`SKILL.md`、`references/`、`examples/` を上書きしてください。

## 使い方

```text
4歳の子どもがおやつがほしいとき棚まで手を引くが、名前は言えない。家ではどう支える？
予定が変わると毎回泣く。無理に乗り越えさせずに支えるには？
学校には、その子に合う支援をどう伝えればよい？
```

足りない事実が提案を変えるときは、長い質問票ではなく、いちばん重要な質問を一つだけします。

## 出力

```text
### 一、问题理解
### 二、可能原因分析
### 三、专业建议
### 四、具体实施步骤
### 五、注意事项
### 六、观察与评估
### 七、后续建议
```

短い質問では節を減らせます。架空の記入例は [examples/output-template.md](examples/output-template.md) にあります。回答本文の既定言語は、相談者が使っている言語です。

## プロジェクト構成

このリポジトリは**単一スキルのパッケージ**です。スキルはリポジトリ直下にあり、`npx skills` が先に見つけます。

```text
autism-support-skill/
├── SKILL.md                      # エージェント入口：frontmatter と手順
├── skills.sh.json                # skills.sh のグループ
├── README.md                     # English
├── README.zh-CN.md               # 简体中文
├── README.ja.md                  # 日本語
├── LICENSE
├── references/
│   ├── age-stages.md             # 年齢段階の重点
│   ├── support-strategies.md     # 支援方法と限界
│   └── records.md                # プロフィールと問題ログの規則
└── examples/
    ├── output-template.md        # 回答の形と架空例
    └── record-template.md        # 架空の記録ファイルの形
```

| ファイル | 役割 |
|---|---|
| `SKILL.md` | エージェントが実行する説明。YAML の `name` / `description` が発見に使われる。 |
| `skills.sh.json` | skills.sh のリポジトリページで **Family support** に分類する。インストール動作は変えない。 |
| `README.md` / `README.zh-CN.md` / `README.ja.md` | 人向けの三言語の説明。 |
| `references/` | 年齢段階、支援方法、成長記録を書くときに読む。 |
| `examples/` | 出力の形と、架空の回答・記録例。 |

## ライセンス

[MIT](LICENSE)

# research-skills

研究活動 (論文読解・要約・関連研究調査など) を支援する [Claude Code](https://claude.com/claude-code) の skill 集。

## インストール方法

### A. Plugin として導入 (推奨)

```
/plugin marketplace add ryhara/research-skills
/plugin install research-skills
```

### B. 手動インストール (user scope)

```bash
git clone https://github.com/ryhara/research-skills.git ~/.claude/research-skills
ln -s ~/.claude/research-skills/skills/read-paper ~/.claude/skills/read-paper
ln -s ~/.claude/research-skills/skills/survey     ~/.claude/skills/survey
```

### C. プロジェクト単位で導入

```bash
cd /path/to/your-project
git clone https://github.com/ryhara/research-skills.git .claude/research-skills
ln -s ../research-skills/skills/read-paper .claude/skills/read-paper
ln -s ../research-skills/skills/survey     .claude/skills/survey
```

## Skill の追加方法

1. `skills/<skill-name>/SKILL.md` を作成
2. frontmatter (`name`, `description`) と本文を記述
3. 必要なら同ディレクトリに補助ファイル (`template.md`, `examples/`) を置く
4. この README の「収録 skill」表と「使い方」セクションに追記


## 収録 skill

| Skill | 説明 |
| --- | --- |
| [`read-paper`](skills/read-paper/SKILL.md) | 論文 PDF/URL を読み込み、背景・手法・実験・結果・貢献を構造化して日本語で要約 |
| [`survey`](skills/survey/SKILL.md) | CV 主要会議 (CVPR/ICCV/ECCV 等) と ML 会議・ジャーナルから 2018 年以降の関連論文を検索し、テーブル + 各論文解説でまとめる |

## 使い方

各 skill は **(A) 自然文で依頼** すると自動起動、または **(B) スラッシュコマンド** で明示起動できます。詳細は各 skill の `SKILL.md` を参照してください。

### `read-paper`

```
この論文を読んで https://arxiv.org/abs/2401.12345
論文を要約して ~/Downloads/paper.pdf
```

```
/read-paper https://arxiv.org/abs/2401.12345
```

詳細: [`skills/read-paper/SKILL.md`](skills/read-paper/SKILL.md)

### `survey`

```
3D Gaussian Splatting をサーベイして
monocular depth estimation の論文を探して
NeRF の関連研究を調べて (CVPR のみ, 2023 年以降)
```

```
/survey 3D Gaussian Splatting
```

詳細: [`skills/survey/SKILL.md`](skills/survey/SKILL.md)

## ライセンス

MIT

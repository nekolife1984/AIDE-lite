# AIDE-lite

GitHub Issues／Projectsに依存せず、MarkdownファイルとGitで課題・進捗を管理するための軽量な運用ガイドとテンプレートです。

## 方針

- 課題ごとにMarkdownファイルを1つ作り、`.work/tasks/`へフラットに置きます。
- 状態は課題ファイル先頭のYAML front matterで管理します。状態別フォルダには分けません。
- 大きな目的やロードマップは任意のプロジェクトファイルにまとめます。
- 課題ファイルを正本とし、一覧やボードは必要になってから生成します。
- GitHub Issue／Projectは使わず、変更履歴はGitで追跡します。

## クイックスタート

```sh
mkdir -p .work/tasks .work/projects
existing_task=$(find .work/tasks -name 'T-*.md' -print -quit)
if [ -n "$existing_task" ]; then
  printf '%s\n' 'Task files already exist; assign the next ID as max existing ID + 1.' >&2
  exit 1
fi
cp .agents/templates/task.md .work/tasks/T-0001-example.md
```

この例は課題ファイルがまだない場合に使います。既存課題がある場合は、既存の最大IDに1を加えて採番し、コピー先とテンプレート内のIDを更新してください。コピー後、タイトル・完了条件も編集してください。IDの採番、状態の意味、進捗記録方法は[運用ガイド](.agents/docs/00-index.md)を参照してください。

## ディレクトリ

```text
.work/
├── tasks/       # 課題ファイル。状態にかかわらず同じ場所に置く
└── projects/    # 任意。複数課題を束ねる目的・ロードマップ

.agents/
├── docs/        # 運用ガイド
└── templates/   # 課題・プロジェクトのテンプレート
```

## ドキュメント

- [運用ガイド目次](.agents/docs/00-index.md)
- [設計原則](.agents/docs/01-principles.md)
- [課題ファイル形式](.agents/docs/02-task-format.md)
- [起票から完了まで](.agents/docs/03-workflow.md)
- [Gitでの変更・共有](.agents/docs/04-git-workflow.md)

# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## デプロイ先

https://keeeta-ui.github.io/task-board/

## 技術スタック

- Vite + React 19 + TypeScript
- Lint: oxlint (`npm run lint`)
- Build: `npm run build`（`tsc -b` で型チェックしてから `vite build`）
- Dev server: `npm run dev`
- 状態管理は React の `useState`/`useEffect` のみ（外部の状態管理ライブラリは未導入）
- データ永続化は `localStorage`（外部バックエンド・DBは無し）

## コンポーネントの命名規約

- コンポーネントファイルは `src/components/` 配下に `PascalCase.tsx`（例: `TaskInput.tsx`, `TaskItem.tsx`, `TaskList.tsx`）
- コンポーネントは名前付きエクスポート（`export function ComponentName(...)`）。`App.tsx` のみエントリーポイントとしてデフォルトエクスポート
- Props の型は `<ComponentName>Props` という interface 名（例: `TaskInputProps`）で、コンポーネント定義の直前に置く
- ドメイン型（`Task` など）は `src/types.ts` にまとめる
- CSS クラス名は BEM 風（`block`, `block__element`, `block--modifier`）を使用し、コンポーネント名をブロック名にする（例: `.task-item`, `.task-item__label`, `.task-item--completed`）

## Git workflow rules

- **Push to GitHub after every code change.** After making a change and confirming it works (build/tests pass as applicable), commit it and push to the remote right away — do not batch up multiple unrelated changes into one push.
- Use clear, descriptive commit messages that explain why the change was made, not just what changed.
- Do not force-push, rewrite history, or skip commit hooks (`--no-verify`) unless explicitly instructed.
- A GitHub remote has not been configured yet. Once one is added, this rule takes effect immediately — confirm the push actually reaches the remote (e.g. `git push` output, `git log origin/<branch>..<branch>`) rather than assuming it succeeded.

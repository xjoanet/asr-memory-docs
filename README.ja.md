# ASR Memory

[English](README.md) · [한국어](README.ko.md)

ASR Memoryは、複数のAIツールで共有する記憶の保存先です。リモートMCPサーバーとして運営しています。あるツールで残した決定を、別のツールから原文のまま探せます。

このリポジトリにはドキュメント、エージェント指針、例があります。サーバーのソースは公開していません。

- ウェブサイト: https://asrmemory.com
- MCPエンドポイント: `https://asrmemory.com/mcp`（Streamable HTTP、OAuth 2.1）
- 公式MCP Registry: `com.asrmemory/asr`

## 3ステップで接続

1. AIツールのリモートMCPサーバー（カスタムコネクタ）設定に `https://asrmemory.com/mcp` を追加します。
2. ログイン画面が開いたら、メール、Google、Kakao、GitHubのいずれかでログインします。キーをコピーする必要はありません。
3. 「ASRに記憶して：決済はPostgresにすることにした」と伝え、別のツールで「決済のDBは何に決めた？」と聞きます。

ログイン画面を開けないツールは、ダッシュボード（https://asrmemory.com/app/）で発行したAPIキーで接続します。ツール別の案内: https://asrmemory.com/ja/docs.html

登録せずにプロジェクト画面を見るにはデモを開いてください: https://asrmemory.com/madang/?demo

## ツールと指針

22個のツール一覧は [README.md](README.md#tools-22) にあります。エージェント指針は [AGENTS.ja.md](AGENTS.ja.md) です。`CLAUDE.md`、`AGENTS.md`、`GEMINI.md` に貼り付けて使います。ASRなしでも使えます。

## データ

- アカウントごとに記憶の空間が分かれています。デプロイのたびにアカウント間アクセス試験を実行し、1件でも失敗すればデプロイを止めます。
- 削除した記憶はまずゴミ箱に移り、復元できます。完全削除は別に依頼します。
- `memory_export` ですべて書き出し、ダッシュボードからアカウントを削除できます。
- データの送信先: https://asrmemory.com/ja/privacy.html
- パスワード、キー、子どもの会話は通常の記憶として保存しないでください。機密の値は `secret_save` を使います。

## 料金

ベータ期間は無料、アカウントあたり記憶1,000件までです。検索、呼び出し、書き出しは件数に数えません。`asr_tidy` で残したまとめも上限に含めません。

## ご意見

このリポジトリにIssueを立てるか、idoweddings@naver.com までお送りください。

## ライセンス

ドキュメントとエージェント指針: CC BY 4.0。`examples/` の例コード: MIT。[LICENSE](LICENSE) を参照してください。

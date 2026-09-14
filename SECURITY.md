# Security Policy - VideoCutterStudio

## Supported Versions

セキュリティアップデートは、原則として最新のリリースバージョンを対象とします。

| Version | Supported          |
| ------- | ------------------ |
| latest  | :white_check_mark: |
| others  | :x:                |

最新版へのアップデートを推奨します。

## 本アプリのセキュリティ設計

VideoCutterStudioはローカルでの動画処理に特化し、以下の方針で設計しています。

* 完全オフライン動作: 動画ファイルや編集情報をクラウドへ送信する機能を設けていません。
* shell=True 不使用: FFmpegの呼び出しを含む `subprocess` 実行では `shell=True` を使用しません。
* パストラバーサル対策: ユーザー指定のファイルパスは正規化・検証を行います。
* 一時ファイルの管理: 書き出しなどで使用する一時ファイルは専用領域で管理し、不要になったファイルを削除します。
* Atomic Write: 設定ファイルの保存では、一時ファイルへの書き込み、fsync、置換によるAtomic Writeを使用します。
* 不要なネットワーク依存を避ける設計: アプリ本体の通常動作にネットワーク通信を必要としない構成を目指しています。

## Reporting a Vulnerability

脆弱性を発見した場合は、公開Issueに機密情報や再現用の詳細を投稿しないでください。

GitHubでPrivate vulnerability reportingが利用可能な場合は、以下から非公開で報告してください。

https://github.com/Unknown777hello/Video-Cutter-Studio/security/advisories/new

Private vulnerability reportingが利用できない場合は、公開Issueに機密情報を記載せず、Issueで非機密の連絡方法について確認してください。

報告には、可能な範囲で以下を含めてください。

* 脆弱性の概要
* 影響を受けるバージョン
* 再現手順
* 想定される影響
* 修正案（任意）

報告を受け取った場合は、内容を確認し、必要に応じて修正版の提供を検討します。

修正版が公開されるまで、脆弱性の詳細を公開しないようご協力ください。

ご協力ありがとうございます。

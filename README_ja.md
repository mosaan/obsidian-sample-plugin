# Obsidian サンプルプラグイン

これは Obsidian (https://obsidian.md) のサンプルプラグインです。

このプロジェクトは TypeScript を使用して型チェックとドキュメントを提供しています。
このリポジトリは、機能を説明する TSDoc コメントを含む TypeScript 定義形式の最新のプラグイン API (obsidian.d.ts) に依存しています。

このサンプルプラグインは、プラグイン API でできる基本的な機能をいくつか示しています。
- クリックすると通知を表示するリボンアイコンを追加します。
- モーダルを開く「サンプルモーダルを開く」コマンドを追加します。
- 設定ページにプラグイン設定タブを追加します。
- グローバルクリックイベントを登録し、コンソールに「click」を出力します。
- コンソールに「setInterval」を記録するグローバル間隔を登録します。

## 初めてのプラグイン開発ですか？

新しいプラグイン開発者向けのクイックスタートガイド：

- [すでに欲しい機能のプラグインが開発されていないか確認してください](https://obsidian.md/plugins)！十分に似たプラグインがすでに存在し、協力できる可能性があります。
- 「このテンプレートを使用」ボタンでこのリポジトリのコピーをテンプレートとして作成します（表示されない場合は GitHub にログインしてください）。
- リポジトリをローカル開発フォルダにクローンします。便宜上、このフォルダを `.obsidian/plugins/your-plugin-name` フォルダに配置できます。
- NodeJS をインストールし、リポジトリフォルダ内のコマンドラインで `npm i` を実行します。
- `npm run dev` を実行して、プラグインを `main.ts` から `main.js` にコンパイルします。
- `main.ts` に変更を加えます（または新しい `.ts` ファイルを作成します）。これらの変更は自動的に `main.js` にコンパイルされます。
- Obsidian を再読み込みして、プラグインの新しいバージョンを読み込みます。
- 設定ウィンドウでプラグインを有効にします。
- Obsidian API の更新については、リポジトリフォルダ内のコマンドラインで `npm update` を実行します。

## 新しいリリースの公開

- `manifest.json` を新しいバージョン番号（例：`1.0.1`）と、最新リリースに必要な最小 Obsidian バージョンで更新します。
- `versions.json` ファイルを `"新しいプラグインバージョン": "最小Obsidianバージョン"` で更新して、古いバージョンの Obsidian が互換性のある古いバージョンのプラグインをダウンロードできるようにします。
- 新しいバージョン番号を「タグバージョン」として使用して、新しい GitHub リリースを作成します。プレフィックス `v` を含めず、正確なバージョン番号を使用してください。例はこちらをご覧ください：https://github.com/obsidianmd/obsidian-sample-plugin/releases
- `manifest.json`、`main.js`、`styles.css` ファイルをバイナリ添付ファイルとしてアップロードします。注意：manifest.json ファイルは、リポジトリのルートパスとリリースの2か所に必要です。
- リリースを公開します。

> `manifest.json` の `minAppVersion` を手動で更新した後、`npm version patch`、`npm version minor`、または `npm version major` を実行することで、バージョンアップのプロセスを簡略化できます。
> このコマンドは `manifest.json` と `package.json` のバージョンを更新し、新しいバージョンのエントリを `versions.json` に追加します。

## プラグインをコミュニティプラグインリストに追加する

- [プラグインガイドライン](https://docs.obsidian.md/Plugins/Releasing/Plugin+guidelines)を確認してください。
- 初期バージョンを公開します。
- リポジトリのルートに `README.md` ファイルがあることを確認してください。
- https://github.com/obsidianmd/obsidian-releases でプルリクエストを作成して、プラグインを追加します。

## 使用方法

- このリポジトリをクローンします。
- NodeJS が少なくとも v16 であることを確認します（`node --version`）。
- 依存関係をインストールするために `npm i` または `yarn` を実行します。
- 監視モードでコンパイルを開始するには `npm run dev` を実行します。

## プラグインを手動でインストールする

- `main.js`、`styles.css`、`manifest.json` をボールトの `VaultFolder/.obsidian/plugins/your-plugin-id/` にコピーします。

## eslint でコード品質を向上させる（オプション）
- [ESLint](https://eslint.org/) はコードを分析して素早く問題を見つけるツールです。プラグインに対して ESLint を実行して、一般的なバグを見つけ、コードを改善する方法を見つけることができます。
- このプロジェクトで eslint を使用するには、ターミナルから eslint をインストールしてください：
  - `npm install -g eslint`
- このプロジェクトを分析するために eslint を使用するには、次のコマンドを使用します：
  - `eslint main.ts`
  - eslint はファイルと行番号ごとにコード改善の提案を含むレポートを作成します。
- ソースコードが `src` などのフォルダにある場合、次のコマンドを使用してそのフォルダ内のすべてのファイルを分析できます：
  - `eslint .\src\`

## 資金提供 URL

プラグインを使用する人々が経済的にサポートできるように、資金提供 URL を含めることができます。

簡単な方法は、`manifest.json` ファイルの `fundingUrl` フィールドにリンクを設定することです：

```json
{
    "fundingUrl": "https://buymeacoffee.com"
}
```

複数の URL がある場合は、次のようにすることもできます：

```json
{
    "fundingUrl": {
        "Buy Me a Coffee": "https://buymeacoffee.com",
        "GitHub Sponsor": "https://github.com/sponsors",
        "Patreon": "https://www.patreon.com/"
    }
}
```

## API ドキュメント

https://github.com/obsidianmd/obsidian-api を参照してください

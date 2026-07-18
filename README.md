# spellwalker

Spellwalker の配布用リポジトリです。

- 版情報: [`app_version.json`](./app_version.json)
- APK: [GitHub Releases](https://github.com/kaworu123123/spellwalker/releases)

## アプリからの参照

タイトル起動時に次の URL を取得します。

```
https://raw.githubusercontent.com/kaworu123123/spellwalker/main/app_version.json
```

## 版上げ手順

1. Unity で APK をビルド（`versionName` / `versionCode` を `AppBuildInfo` と Player Settings に揃える）
2. Release を作成して APK を添付する

```bash
gh release create v1.4 ./spellwalker.apk --title "v1.4" --notes "変更内容"
```

3. `app_version.json` を更新して push する

```json
{
  "versionName": "1.4",
  "versionCode": 5,
  "downloadUrl": "https://github.com/kaworu123123/spellwalker/releases/download/v1.4/spellwalker.apk",
  "message": "アップデートがあります。\n…\nアップデートしますか？",
  "forceUpdate": false
}
```

`versionCode` が端末のインストール版より大きいときだけアップデートダイアログが出ます。

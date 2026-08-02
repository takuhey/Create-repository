# おこづかい帳 iOSアプリ化 手順書

## 全体の流れ
1. GitHubにこのフォルダをアップロード
2. Apple Developer Programに登録（$99/年）
3. App Store Connectで「App」を1つ作成
4. App Store Connect APIキーを作成
5. Codemagicアカウントを作り、GitHubと連携
6. CodemagicにApp Store Connect連携（Integration）を設定
7. ビルドを実行 → TestFlightに自動アップロード
8. iPhoneのTestFlightアプリでインストール

---

## 1. GitHubにアップロード
1. https://github.com で無料アカウントを作成
2. 右上の「+」→「New repository」
3. リポジトリ名を入力（例：okozukai-cho-ios）→ Public でも Private でもOK → 「Create repository」
4. 作成後の画面で「uploading an existing file」をクリック
5. このフォルダの中身（package.json, capacitor.config.json, codemagic.yaml, .gitignore, README.md, www/フォルダ, resources/フォルダ）を全部ドラッグ＆ドロップ
6. 「Commit changes」

## 2. Apple Developer Programに登録
1. https://developer.apple.com/programs/ を開く
2. 「Enroll」から登録（Apple ID・本人確認書類・$99/年の支払いが必要）
3. 審査完了まで最大数日かかることがあります

## 3. App Store ConnectでAppを作成
1. https://appstoreconnect.apple.com を開く
2. 「マイApp」→「+」→「新規App」
3. プラットフォーム：iOS
4. 名前：おこづかい帳（任意）
5. バンドルID：`com.okozukaicho.app` を選択（先に「Certificates, Identifiers & Profiles」→「Identifiers」で同じ文字列のIdentifierを先に作成しておく必要があります）
6. SKU：任意の文字列（例：okozukaicho001）

## 4. App Store Connect APIキーの作成
1. App Store Connect →「ユーザとアクセス」→「統合」タブ→「App Store Connect API」
2. 「+」でキーを作成、アクセス権限は「App Manager」
3. 発行された「Issuer ID」「Key ID」と、ダウンロードできる`.p8`ファイルを保存しておく（.p8はダウンロード後は二度と再ダウンロードできないので注意）

## 5. Codemagicアカウント作成・連携
1. https://codemagic.io で「Sign up」→ GitHubアカウントでログイン
2. 連携するリポジトリ（okozukai-cho-ios）を選択して追加

## 6. CodemagicにApp Store Connect連携を設定
1. Codemagic画面右上の設定（Teams）→「Integrations」→「Developer Portal」→「App Store Connect」
2. 「Add key」で、4.で控えたIssuer ID・Key ID・.p8ファイルを入力
3. 名前は何でもOK（例：app_store_credentials）

## 7. ビルドを実行
1. Codemagicのプロジェクト画面で「Start new build」
2. ワークフローは「iOS Workflow」（このリポジトリのcodemagic.yamlから自動で読み込まれます）
3. ビルドが成功すると、自動でApp Store Connect（TestFlight）にアップロードされます

## 8. TestFlightでインストール
1. App Store Connectの「TestFlight」タブで、ビルドが処理完了になるのを待つ（数分〜数十分）
2. 自分を「内部テスター」として追加
3. iPhoneに「TestFlight」アプリ（App Store）をインストール
4. 招待メール、またはApp Store Connect画面のリンクからTestFlightに参加
5. TestFlightアプリ内で「おこづかい帳」をインストール

---

## 困ったときは
各ステップの画面をスクリーンショットで送ってもらえれば、その画面に合わせて案内します。

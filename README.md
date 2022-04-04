# slack_emoji
Slackである絵文字を打つと、slackbotが自動でいい感じの絵文字でリアクションしてくれる。絵文字一覧（https://qiita.com/yamadashy/items/ae673f2bae8f1525b6af）



# 手順（GAS側）
1. スプシ→App Scriptにslack_emoji.gsをコピペ（Bot User OAuth Token（GAS側終わったらもう一回書き換えろ）とSheet IDは自分のもの（docs.google.com/spreadsheets/d/とedit#gid=0の間））
2. デプロイ→新しいデプロイ→アクセルできるユーザーは全員
3. URLコピー（注：コードを変更するたびにこれコピーしろ）

# 手順（Slack側）
1. https://api.slack.com/apps でCreate New App
3. OAuth & Permissions→Bot Token Scopes（Userでもできる？）で`reactions:read`と`reactions:write`を追加。
4. Event Subscriptions→Enable EventsをOnに→GAS側でコピーしたURLをコピー（GASのコードを変更するたびにこれしろ）→verified
5. Subscribe to bot eventsで`reaction_add`を追加
6. Install to Workspace
7. Bot User OAuth Tokenをコピーしてslack_emoji.gsの'Your Token'を書き換える。

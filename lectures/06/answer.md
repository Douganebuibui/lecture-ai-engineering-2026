# 第6回 解答

## 演習

<!-- [tool call] の行は、表示された行をそのまま貼り付けてください。終わらなかった STEP は、空欄のままでかまいません。 -->

- STEP 1 のツールの名前：glossary_search_glossary
- STEP 2 の [tool call]：glossary_search_glossary({'query': '3レベル'})
- STEP 3 の [tool call]：fetch_fetch
- STEP 4 の [tool call]：aws___search_documentation
- 気づき・疑問：GitHub（リモート）で行った変更は Codespaces（ローカル）には自動反映されず、git pull で取り込みが必要？

## 宿題

<!-- 基礎・実装・発展のどれか1つに取り組めば完了です。 -->

- 取り組んだレベル：基礎
- やったこと：server.tool()(tools.get_lecture_summary)をapp/mcp_server.pyに追加
- 結果：[tool call]   get_lecture_summary({'lecture': 2}) が呼ばれる。
- 気づき・疑問：「モデルが混み合っています（503）。少し待ってから再実行してください。」を連発されてなかなか進められなかった。

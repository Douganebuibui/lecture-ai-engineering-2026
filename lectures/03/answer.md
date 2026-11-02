# 第3回 解答

## 演習

- 第1回（素のLLM）とエージェントの回答の違い：用語集を検索䛧䛶䛛ら答える（基礎・実装・発展、どれか 1 つで完了と答えられる）
- `--trace` で見えたツール呼び出し（ツール名と引数）：
- [tool call]   search_glossary({'query': 'LoRA'})
[tool call]   search_glossary({'query': 'QLoRA'})
[tool return] search_glossary -> [{"term": "LoRA", "lecture": 2, "definition": "事前学習済みの重みは固定したまま、重みの更新分を2つの小さな行列の積（低ランク行列）で表し、その小さな行列だけを学習するPEFT手法。学習するパラ…
[tool return] search_glossary -> [{"term": "QLoRA", "lecture": 2, "definition": "ベースモデルの重みを4ビットなどに量子化してメモリを節約したうえで、LoRAで学習する手法。より大きなモデルを小さなGPUで扱える。本講座の第2…
[usage] RunUsage(cost=Decimal('0.0007938'), details={'text_prompt_tokens': 1196}, input_text_tokens=1196, input_tokens=1196, output_tokens=174, requests=2, tool_calls=2)
- 1つの質問での LLM 呼び出し回数（`requests`）：2回
- 追加したツールと、docstring に書いた説明：<br>
search_glossary(query: str) -> str：講座の用語集から用語を検索し、定義と、どの回で扱うかを返す。AIエンジニアリングの用語や、この講座（AIE2026）に固有の言葉について答える前に使うこと。query には調べたい用語を1つだけ入れる（例: "LoRA"）。<br>
get_lecture_summary(lecture: int) -> str：指定した回（1始まりの整数）の講義の要点を返す。「第3回では何を学ぶ？」のように、回の内容や関係を聞かれたときに使う。

## 宿題

- 取り組んだレベル：基礎
- やったこと：INSTRUCTIONSを無効化（参照できないようにした）
- 結果：関連回表記の欠落（有効時に末尾へ記載されていた「関係する回：第2回」という情報が、無効時の回答では抜け落ちた）、 出力の冗長化（有効時は端的にまとまり出力180トークンに収まっているが、無効時は見出しや一般的な長い回答フォーマットに変化し出力431トークンとなった）、コストと処理量の増加（無効時は出力文章量が増えたことで、実行コストが0.0007944から0.0013619へと増加）
- 気づき・疑問：

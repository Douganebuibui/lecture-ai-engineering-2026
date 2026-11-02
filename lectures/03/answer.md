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
search_glossary(query: str) -> str：講座の用語集から用語を検索し、定義と、どの回で扱うかを返す。
AIエンジニアリングの用語や、この講座（AIE2026）に固有の言葉について
答える前に使うこと。query には調べたい用語を1つだけ入れる（例: "LoRA"）。

## 宿題

- 取り組んだレベル：基礎
- やったこと：
- 結果：
- 気づき・疑問：

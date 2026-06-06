+++
date = '2026-04-01T08:30:24+08:00'
title = 'PyIssue'
categories = ['software-engineering']
tags = ['python']
+++

## 文件重名

给py文件起名需要非常谨慎
重名会导致严重问题
比如我给一个文件起名openai，但是有叫openai的包，或者其他包里面也有个叫这个的文件，就会导致引用错误

```
Traceback (most recent call last):
  File "~/src/chroma.py", line 5, in <module>
    openai_ef = embedding_functions.OpenAIEmbeddingFunction(
        api_key_env_var=KEY,
        api_base=BASE_URL,
    )
  File "~/python3/lib/python3.13/site-packages/chromadb/utils/embedding_functions/openai_embedding_function.py", line 47, in __init__
    import openai
  File "/www/qqbot/src/openai.py", line 28, in <module>
    ENDPOINT = os.environ["AI_ENDPOINT"]
               ~~~~~~~~~~^^^^^^^^^^^^^^^
  File "<frozen os>", line 717, in __getitem__
KeyError: 'AI_ENDPOINT'
```

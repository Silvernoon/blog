+++
date = '2026-04-15T10:30:52+08:00'
title = 'PyThreadLock'
categories = ['software-engineering']
tags = ['python']
+++

## RAII

```python
import threading
lock = threading.Lock()

with lock:
  # ...
  pass
```

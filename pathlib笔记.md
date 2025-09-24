注意，本文档借助 AI 生成！

```python
#!/usr/bin/env python3

from pathlib import Path
import time

# 要读取的目录路径
directory = Path("/path/to/your/dir")

# 遍历目录内容
for file in directory.iterdir():
    if file.is_file():  # 只处理文件
        stats = file.stat()
        size_kb = stats.st_size / 1024  # 字节转 KB
        mtime = time.strftime("%Y-%m-%d %H:%M:%S", time.localtime(stats.st_mtime))
        print(f"文件: {file.name}\n  路径: {file}\n  大小: {size_kb:.2f} KB\n  修改时间: {mtime}\n")
    else:
        print(f"目录: {file.name}, 路径: {file} (跳过)")
```

如果需要递归遍历，将 `for file in directory.iterdir():` 改为 `for file in directory.rglob("*"):` 即可，其余代码不需要改动。  

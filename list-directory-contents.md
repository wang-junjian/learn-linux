# 显示目录内容

## 可读的方式显示文件大小
```bash
# -h, --human-readable with -l and/or -s, print human readable sizes (e.g., 1K 234M 2G)
ls -lh
ll -h
```

## 显示目录的所有子目录的内容
```bash
# -R, --recursive list subdirectories recursively
ls -lR
ll -R
```

## 按时间进行排序
* 按时间降序显示当前目录（-l use a long listing format; -t sort by modification time, newest first）
```bash
ls -lt
ll -t
```

* 按时间升序显示当前目录（-r --reverse reverse order while sorting）
```bash
ls -lrt
ll -rt
```

## 按大小进行排序
* 按大小降序显示当前目录（-S sort by file size, largest first）
```bash
ls -lS
ll -S
```

* 按大小升序显示当前目录
```bash
ls -lrS
ll -rS
```

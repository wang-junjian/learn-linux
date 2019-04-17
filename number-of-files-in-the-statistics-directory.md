# 统计目录下文件数量

## 统计当前目录下的文件数量
```bash
ls -l | grep "^-" | wc -l
```

## 统计当前目录下的目录数量
```bash
ls -l | grep "^d" | wc -l
```

## 统计当前目录下（包含子目录）的文件数量
```bash
ls -lR | grep "^-" | wc -l
```

## 统计当前目录下（包含子目录）的目录数量
```bash
ls -lR | grep "^d" | wc -l
```

## 参考资料
* [Linux统计文件夹下的文件数目](http://noahsnail.com/2017/02/07/2017-02-07-Linux%E7%BB%9F%E8%AE%A1%E6%96%87%E4%BB%B6%E5%A4%B9%E4%B8%8B%E7%9A%84%E6%96%87%E4%BB%B6%E6%95%B0%E7%9B%AE/)

# 提示与技巧
### 如何创建软盘
不使用 `bximage` 也可以创建软盘。以下命令创建了一个大小为 1440*1024 字节的软盘，名称为 a.img。
```
dd if=/dev/zero of=a.img bs=1024 count=1440
mkfs.msdos a.img
```
第一条 `dd` 命令创建 a.img，`if=/dev/zero` 会将 a.img 全部写入 0，`bs` 和 `count` 的乘积决定了 a.img 的大小，单位为字节。
第二条 `mkfs.msdos` 命令格式化 a.img 为 msdos 格式。这样才能正常访问这个分区。

### 调试代码
`qemu` 可以和 `gdb` 配合使用来调试代码。参考：[https://github.com/chenxiex/osfs02/blob/qemu/debug.md](https://github.com/chenxiex/osfs02/blob/qemu/debug.md)

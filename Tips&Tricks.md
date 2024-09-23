# 提示与技巧
### 如何创建与挂载软盘
不使用 `bximage` 也可以创建软盘。以下命令创建了一个大小为 1440*1024 字节的软盘，名称为 a.img。
```
dd if=/dev/zero of=a.img bs=1024 count=1440
mkfs.msdos a.img
```
第一条 `dd` 命令创建 a.img，`if=/dev/zero` 会将 a.img 全部写入 0，`bs` 和 `count` 的乘积决定了 a.img 的大小，单位为字节。
第二条 `mkfs.msdos` 命令格式化 a.img 为 msdos 格式。这样才能正常访问这个分区。

挂载软盘的方法也非常简单。如果你阅读了 [osfs01](https://github.com/chenxiex/osfs01) 中的 Makefile 文件，就会发现可以使用 `-fda` 参数挂载软盘。这其中 `fd` 是软盘的意思，`a` 表示挂载到 `A:\`，也就是第一个软盘槽位，通常是系统盘所在位置。因此，类似地，我们可以用 `-fdb` 参数来挂载软盘到 `B:\`。在 [osfs03](https://github.com/chenxiex/osfs03) 中，我们会用到这个方法。

### 调试代码
`qemu` 可以和 `gdb` 配合使用来调试代码。参考：[https://github.com/chenxiex/osfs02/blob/qemu/debug.md](https://github.com/chenxiex/osfs02/blob/qemu/debug.md)

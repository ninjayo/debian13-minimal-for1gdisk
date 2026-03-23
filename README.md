# Debian 13 极简 1G qcow2 镜像

基于 **[@梦影](https://www.nodeseek.com/space/34503#/general)**（[改了下 Bin 佬的 dd 脚本，支持 btrfs 文件系统](https://www.nodeseek.com/post-480914-1)）的 dd 镜像为底包制作的极简 qcow2 镜像，裁剪掉一切不必要的东西，文件约 264MB，挂上就能跑。

---

## 镜像规格

| 项目 | 值 |
|------|-----|
| 系统版本 | Debian 13 trixie |
| 内核 | 6.12 |
| 文件系统 | btrfs（zstd:3 压缩） |
| qcow2 文件大小 | ~264 MB |
| 虚拟磁盘容量 | 1 GiB |
| 首次启动后可用空间 | ~650 MB |
| 引导方式 | BIOS（传统），GRUB i386-pc |
| root 密码 | `nodeseekdebian13js` |

---

## 截图

**磁盘占用**

![占用实图](https://cdn.nodeimage.com/i/mNf3iPVPsz9mpHZWsDOuqZvcez9G8ukb.png)

**阿里云导入自定义镜像直接启动**

![启动截图](https://cdn.nodeimage.com/i/M57QRZnEj7zOD7G9HlZjUO5vgCrtz3xZ.png)

---

## 下载

[前往 Releases 页面](../../releases/latest)

---

## 注意事项

> **⚠️ root 密码**：默认密码为 `nodeseekdebian13js`，请在首次登录后立即执行 `passwd` 修改密码，切勿在生产环境中继续使用默认密码。

> **首次启动扩容**：启动后 btrfs balance 需要约 1~3 分钟完成，这段时间内 `df -h` 显示的可用空间偏小属正常现象，稍等即可恢复正确值。

---

## 已验证环境

- 阿里云导入自定义镜像直接启动

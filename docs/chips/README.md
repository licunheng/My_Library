# 芯片资料

存放芯片说明书和围绕某一型号整理的材料：数据手册、应用笔记、勘误、摘录和自己的笔记。

## 命名

```
docs/chips/<vendor>/<part>/
```

- `<vendor>`：厂商短名，小写。例如 `st`、`ti`、`nordic`、`espressif`、`wch`。
- `<part>`：订购型号或实际使用的料号，小写，去掉空格。例如 `stm32f103c8t6`。
- 只归档到系列、还没有具体料号时，目录用系列名，例如 `stm32f1`，在笔记里写明覆盖范围。

同一目录里建议这样放：

| 文件 | 内容 |
| --- | --- |
| `datasheet.pdf` | 当前在用的说明书 |
| `datasheet-rev12.pdf` | 需要对照多个版本时，把版本号写进文件名 |
| `errata.pdf` | 勘误 |
| `app-notes/` | 应用笔记原文 |
| `excerpts.md` | 从手册摘出的表格、时序、寄存器，每段注明页码 |
| `notes.md` | 自己的阅读笔记 |

`notes.md` 从 [`_template/notes.md`](_template/notes.md) 复制后填写。`_template/` 只作样板，不要把真实型号的资料放进去。

## 记录什么

每份资料至少留下三件事：资料名称、版本或修订号、获取日期或文档日期。摘录和笔记与原文放在同一型号目录，方便以后按型号找回。

手册来自官网、代理商或购买渠道时，在笔记的「来源」里写上入口，避免和来路不明的扫描件混在一起。

## 大 PDF

说明书 PDF 可以直接提交。单文件很大、普通 Git 不合适时，用 Git LFS 跟踪 `*.pdf`。启用步骤写在仓库根目录的 `README.md`，本库不默认开启 LFS。

## 已归档

| 厂商 | 目录 | 型号 |
| --- | --- | --- |
| 瑞芯微 Rockchip | `rockchip/` | rk3588、rk3576、rk3568、rk3566、rv1106、rv1126b |
| 南京沁恒 WCH | `wch/` | ch32v003、ch32v004、ch32v203、ch32v208、ch32v307、ch32x035、ch32l103、ch32h417、ch582、ch583、ch584、ch585、ch586、ch587、ch592 |
| 小华半导体 XHSC | `xhsc/` | hc32f460、hc32f4a0、hc32f45x、hc32f420、hc32f334、hc32l19x、hc32f115 |
| 乐鑫 Espressif | `espressif/` | esp32-c3、esp32-c6、esp32-s3、esp32-h2、esp32-p4 |

各型号目录有 `datasheet.pdf` 和 `notes.md`。rk3588、rk3568 另有简版 `datasheet-brief.pdf`；rk3576、rk3566、rv1106、rv1126b 目前只有官网简版，仍放在 `datasheet.pdf`。

沁恒 CH582 与 CH583 共用 CH583DS1，CH584 与 CH585 共用 CH585DS1，CH586 与 CH587 共用 CH587DS1。每一对型号目录里的 `datasheet.pdf` 是同一份手册，说明写在对应 `notes.md` 的来源和覆盖范围。

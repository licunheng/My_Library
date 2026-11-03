# My Library

个人技术资料库，用来归档以后还会查阅的技术材料。这里收录芯片说明书、项目经验和通用参考，不存放应用代码。

## 目录约定

路径用英文，方便跨系统和工具引用；正文用中文。

| 路径 | 用途 |
| --- | --- |
| `docs/chips/` | 芯片说明书、应用笔记、摘录和阅读笔记 |
| `docs/project-experience/` | 项目经验，一篇经历一个 Markdown |
| `docs/references/` | 不专属于某一型号或某一个项目的通用参考 |

新内容放进对应目录，不在仓库根目录堆文件。新增前先看该目录下的 `README.md`。

## 如何新增一份芯片资料

1. 在 `docs/chips/` 下按 `厂商/型号` 建目录，例如 `docs/chips/st/stm32f103c8t6/`。厂商与型号用小写，空格改成连字符。
2. 放入原始文件（常见是 PDF）、摘录和笔记。笔记可从 `docs/chips/_template/notes.md` 复制，并写清资料版本、日期和来源。
3. 提交说明里写上厂商、型号，以及这次增加的是说明书、摘录还是笔记。

命名、子目录和多版本手册的放法见 `docs/chips/README.md`。

## 如何新增一份项目经验

1. 复制 `docs/project-experience/_template.md`。
2. 按 `年-月-短标题.md` 命名，例如 `2026-03-motor-driver-bringup.md`。短标题用英文小写和连字符。
3. 填背景、角色、技术栈、难点、结果和可复用结论。没有的小节写「无」，或删掉该小节。
4. 正文只保留可公开的技术结论。账号、令牌、私钥和未公开的客户数据不要写入文件。

写法见 `docs/project-experience/README.md`。

## 大文件与 Git LFS

芯片说明书经常是体积较大的 PDF。本库默认用普通 Git 管理文件。单文件较大时，可以改用 Git LFS，这是可选项。

需要时在本地执行：

```bash
git lfs install
git lfs track "*.pdf"
git add .gitattributes
```

把生成的 `.gitattributes` 和资料一起提交。启用后，未安装 LFS 的克隆只能看到指针文件；提交前先确认这些原件确实需要进版本库。

未下完的临时文件（如 `*.crdownload`、`*.part`）已被 `.gitignore` 排除。

## 提交前看一眼

- 文件放在约定目录里，文件名能看出厂商、型号或项目。
- 摘录注明了出处（文档名、版本、章节或页码）。
- 没有密钥、令牌、证书和密码。
- 临时下载和系统垃圾没有被 `git add` 进去。

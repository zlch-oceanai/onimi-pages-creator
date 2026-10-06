# Onimi Pages Creator

[English](../../README.md) | **简体中文**

在自己的 Agent 工作区中创作、完善、校验和预览高质量的独立 HTML 页面。

## 安装

默认 Onimi 安装会一起准备 Creator 与 Publish，但两个模块仍各自分工。先查看
[已验证渠道状态](https://downloads.onimi.ai/skills/manifest.json)；只有 Publish npm 渠道版本等于当前
Publish 版本时才运行：

```sh
npx --registry=https://registry.npmjs.org onimi-pages-publish@latest install --suite --agent codex
```

安装器会保留所有已有模块和个人修改，只补缺失模块。下方独立 Creator 包是本地创作的高级安装方式。

其他来源：

- 直接下载：从[稳定清单](https://downloads.onimi.ai/skills/manifest.json)读取
  `skills.creator.archive.url`、`sha256` 和 `size`，再校验不可变归档
- GitHub：`npx --registry=https://registry.npmjs.org skills@1.5.26 add zlch-oceanai/onimi-pages-creator --skill onimi-pages-creator --global`
- ClawHub（CLI 需要 Node.js 22+）：`npx --registry=https://registry.npmjs.org clawhub@0.23.3 install @mariohazy/onimi-pages-creator`

每个来源都包含完整 Skill 和本地校验器，并会保留已有安装。客户端目录、完整性校验和更新方式见
[安装说明](INSTALL.md)。

## 使用

向 Agent 描述需要的页面，例如：

> 创建一个响应式双语产品发布页，交付为单个自包含 HTML 文件；完成校验，并在桌面和手机尺寸下
> 预览两种语言。

Creator 在本地工作，不会把提示词或页面发送给 Onimi Pages。它会指导 Agent 确定明确的视觉方向、
实现可用且支持键盘的交互、标明虚构数据，并在浏览器中检查结果。需要时可以直接运行：

```sh
node skills/onimi-pages-creator/scripts/validate-html.mjs /absolute/path/to/page.html
```

创作不代表授权发布。即使套件已经准备 Publish，也只在受控模板、云草稿、云 Slides 或发布任务
实际需要时连接；同账号且 scope 足够的有效连接应直接复用，不重复授权。

## 仓库目录

- `skills/onimi-pages-creator/`：完整 Skill、参考资料、校验器、更新管理器和哈希收据。
- `bin/`：无第三方依赖的 npm 安装器，没有生命周期脚本。
- `docs/zh-CN/`：中文 README 和安装说明。

仓库只包含 MIT-0 许可的公开分发文件，不包含应用源码、凭证、托管用户内容或测试服务配置。

## 0.3.1

- 独立 Creator 仓库与 npm 包。
- 双语安装说明和保护本地修改的直接下载更新。
- 明确区分本地创作与可选的授权发布。

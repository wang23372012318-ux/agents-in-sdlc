---
title: "第 12 课 - 使用 GitHub Pages 部署网站"
description: "使用 GitHub Copilot 应用配置 Pages 工作流、审查拉取请求，并确认 Space Quiz 已成功发布。"
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

将 Space Quiz 部署到 GitHub Pages，让其他人也能访问。Copilot 可以准备工作流并引导部署，但你仍需负责审查更改并确认网站已上线。

本课将：

- 让 Copilot 配置 GitHub Pages 部署。
- 在合并前审查工作流和拉取请求。
- 跟进部署并验证已发布的网站。

## 场景

Space Quiz 已在 GitHub 仓库中，但其他人还需要一种简单的方式来试用它。使用 GitHub Pages 发布单文件网站后，用户可以通过公开 URL 访问，无需添加服务器或运行时依赖项。

## 让 Copilot 准备部署

> [!WARNING]
> 创建拉取请求可能会提交并推送代码。发送此提示前，请检查批准设置和目标仓库。如果选择 **Approve all**，不要认为系统一定会再次请求确认。

在 `space-quiz` 的 Copilot 应用会话中发送以下提示：

```plaintext
为此仓库准备 GitHub Pages 部署。创建一个 GitHub Actions 工作流，在更改进入默认分支后，如有需要则构建网站并将其部署到 GitHub Pages。如果仓库中还没有 README，请添加一个，介绍此应用以及如何在本地运行它。根据这些更改创建拉取请求，并报告链接以及所需的 Pages 设置或权限。不要合并、启用自动合并、更改 Pages 设置或部署。停止并等待我审查。
```

## 审查工作流和拉取请求

1. 确认只有在仓库尚无 README 时才添加 README。
2. 审查拉取请求中的更改，包括工作流的构建和部署步骤、触发条件及权限。
3. 确认工作流从默认分支部署，而不是从尚未合并的拉取请求部署。
4. 要求修正问题并审查更新后的 diff。获得授权合并前，等待拉取请求所需的检查全部通过。

## 授权合并和部署

> [!WARNING]
> 以下提示授权代理合并已审查的拉取请求、更改仓库的 Pages 设置并发布网站。只有完成审查并确认仓库和拉取请求后，才发送此提示。根据批准设置，这些操作可能不会再次请求确认。

将 `<PR_NUMBER>` 替换为已审查的拉取请求编号，然后单独发送以下提示：

```plaintext
我已审查此仓库中的拉取请求 <PR_NUMBER>，并授权合并和部署。使用 GitHub Actions 启用 GitHub Pages；只有在所需检查通过后才合并该拉取请求，并持续监控部署直到成功。报告已发布网站的最终 URL。如果你没有启用 Pages 或合并的权限，请准确说明我需要批准或执行什么操作；网站上线前不要报告成功。
```

![三阶段示意图：已合并的 space-quiz 拉取请求；GitHub Actions 的 Deploy website 运行成功，其中包含 Build website、Upload artifact 和 Deploy to Pages 步骤；以及发布在 yourname.github.io/space-quiz/ 的 Space Quiz。](../../../_images/first-steps-app-pages-deploy.svg)

## 验证部署

1. 跟进 GitHub Actions 部署运行，直到成功。
2. 打开报告的 URL，确认 Space Quiz 已加载。

如果代理无法启用 Pages 或合并拉取请求，请按照它提供的具体说明操作。只有部署成功且网站正常加载后，才能将任务视为完成。

## 总结和后续步骤

Space Quiz 现已作为在线网站提供，并且你亲自验证了部署，而不是只依赖代理的报告。继续学习[第 13 课：回顾与后续步骤][next-lesson]。

[next-lesson]: ../13-review/

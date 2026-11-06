![棱镜假日头图，灰绿色圆角图标内悬浮着一枚玻璃棱镜，棋盘路线从两侧延伸](docs/images/prism-days-banner.webp)

# 棱镜假日 · Prism Days

在浏览器里掷骰旅行，沿着棋盘买地、建楼和交易。十张地图各有路线与气候，四季天气和沿途偶遇会改变每一局的计划。

## 本地开玩

推荐 Node.js 24 LTS（最低 22.12）。克隆或下载仓库后，在项目目录运行以下命令。

```bash
npm ci
npm run build
npm start
```

启动后在浏览器打开 <http://localhost:8787/>。macOS 也可双击仓库里的启动脚本。 [启动棱镜假日.command](启动棱镜假日.command)

- **与代理人同行**　选地图，与电脑对手开局。进度自动保存在当前浏览器，可导入或导出 JSON 存档。
- **联网好友**　创建房间，把 6 位房间码发给好友。普通房间共 2–4 个席位，房主可补入电脑对手，真人就绪后开局。

局域网内的好友可用主机 IP 和 `8787` 端口访问游戏。同一浏览器可凭原房间码重连。房间进度存在服务端内存中，重启服务会结束进行中的联机对局。

## 地图与规则

每季 21 天，旅程可设为 1、2、4 年或破产决胜。开局可选择天气强度和租金负担，也可决定是否开放房产自由交易。

- 地图与故事　[内容册](docs/CONTENT.md) · [流动偶遇](docs/ROAMING_ENCOUNTERS.md)
- 开局设置　[电脑代理人](docs/AI_OPPONENTS.md) · [天气强度](docs/HARDSHIP_WEATHER.md) · [租金档位](docs/RENT_LEVELS.md)
- 对局细节　[完整规则](docs/DESIGN.md)

## 单人测试房

在「联网好友」中选择「输入房间码」，进入后选择地图和天气，再点击「开始测试」。

| 入口码 | 测试房 | 初始背包 |
| --- | --- | --- |
| `114514` | 天气测试房 | 99 件天气控制器 |
| `350234` | 建筑测试房 | 99 件建筑修复包 |

每个浏览器身份拥有独立测试进度。道具仍按普通对局的规则使用。 [测试房说明](docs/TEST_ROOMS.md)

## 开发与部署

`npm run dev` 同时启动 Vite 和房间服务。下面的命令检查生产构建、自动化测试和服务启动。

```bash
npm run build
npm test
npm run smoke:production
```

公网联机需要部署 Node 房间服务。它在同一端口提供网页与 `/ws`，健康检查路径为 `/healthz`。 [部署指南（Docker 与 HTTPS）](docs/DEPLOYMENT.md) · [联机协议](docs/NETWORK.md) · [验收记录](docs/ACCEPTANCE.md)

## 署名与许可

- Alex Xiao 发起并设计项目。 [@spectrum527](https://github.com/spectrum527)
- OpenAI Codex 参与代码实现与迭代。 [@codex](https://github.com/codex)

本项目采用 Vibe coding 的方式开发，ChatGPT 参与了功能实现与迭代。

[MIT 许可证](LICENSE) · [应用图标 PNG](docs/images/prism-days-icon.png)

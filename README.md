# Voice Twin Prototype

移动端 H5 语音数字人项目（可运行版本）。

## 已实现能力
- 一次性创建流程：创建助理通话采集 -> 建模仪式 -> 通讯录首页。
- TELOS 采访优化：
  - 采访问题按 `MISSION / GOALS / BELIEFS / MODELS / STRATEGIES / NARRATIVES / CHALLENGES+IDEAS` 编排。
  - 采集页展示“TELOS 阶段 + 仪式阶段”并强化建模仪式感。
- 语音采集与声音复刻：
  - 采访过程持续录制 WAV 音频样本（含录音时长反馈）。
  - 设置页可配置 MiniMax API Key，并调用 MiniMax `files/upload` + `voice_clone` 完成声音复刻。
- MiniMax TTS 双角色接入：
  - 创建助理提问默认走 MiniMax TTS（无 Key 时回退浏览器 TTS）。
  - 数字人通话回复优先使用 MiniMax 复刻 `voice_id` 播报。
- 电话式通话页：头像、通话计时、状态、实时转写、挂断。
- 虚拟形象选择：
  - 采集最后一步支持手动选择虚拟形象。
  - 支持输入关键词进行 AI 生成并自动推荐形象。
- 浏览器语音能力接入：
  - 采访阶段自动语音提问（SpeechSynthesis）+ 自动语音采集（SpeechRecognition）。
  - 通话阶段实时语音识别与语音回复（能力可用时自动启用）。
  - 不支持语音 API 的浏览器会自动降级为模拟通话循环。
- 本地持久化：
  - 创建进度、采访答案、建模摘要。
  - 通讯录、个人设置、分享码。

## 文件结构
- `prototype.html`：主开发文件（单文件项目）
- `pageone/index.html`：部署入口（与 `prototype.html` 同步）
- `PRODUCT_PLAN.md`：产品方案
- `docs/PRD.md`：产品需求文档

## 本地运行
直接用浏览器打开：
- `prototype.html`

建议用 HTTPS 或 localhost 打开以获得更稳定的语音能力权限行为。

## 在线地址
- https://danmu-9grk7w6g3b4184bc-1340209582.tcloudbaseapp.com/pageone/

## 说明
- TELOS 十文件仅用于内部人格建模，不在前台暴露。
- 当前仍是前端单体版本，后续可接入真实 STT/LLM/TTS 服务链路。
- MiniMax 复刻调用为前端直连模式（便于本地验证），生产环境建议改为服务端代理。

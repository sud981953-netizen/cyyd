# CYYD 创亿原点短视频创作技能包

基于 72 变短视频创作方法论的一站式短视频创作 Agent Skills，包含 9 个专项智能体和 1 个总入口。适用于豆包、Claude Code、Codex 等支持 Agent Skills（SKILL.md）的智能体。

## 技能清单

| 技能 | 中文名 | 用途 |
|------|--------|------|
| `cyyd` | 总入口 | 需求路由，判断该用哪个智能体 |
| `cyyd-account-diagnosis` | 账号诊断 | 发抖音主页链接，全面诊断账号现状 |
| `cyyd-ip-planning` | IP策划 | 从零做账号，线上IP / 实体店本地两套打法 |
| `cyyd-topic-selection` | 72变选题 | 选题枯竭时，基于72变方法论找选题方向 |
| `cyyd-copywriting` | 一键出文案 | 把零散想法倾倒出来，整理成有网感的口播文案 |
| `cyyd-trending` | 实时蹭热点 | 判断热点该不该蹭，产出蹭热点方案 |
| `cyyd-viral-rewrite` | 爆款文案改写 | 拆解爆款结构，改写成自己的版本 |
| `cyyd-opening-optimizer` | 72变开头优化 | 优化视频前3秒，给出可替换的开头话术 |
| `cyyd-cover-title` | 封面标题优化 | 生成高点击的封面文字和标题 |
| `cyyd-work-diagnosis` | 作品诊断 | 发作品链接，诊断单条视频的问题 |

## 安装方式

### 豆包

**方式一（推荐）：豆包专业版链接安装**

1. 打开豆包客户端，进入办公模式
2. 选择「技能 → 创建技能」
3. 输入本仓库的 GitHub 链接，豆包会自动进入 Agent 模式执行安装，中途点击授权确认即可

装好之后，直接对豆包说「帮我用 CYYD 的一键出文案」或描述你的需求，豆包会自动调用对应技能。

**方式二：豆包 PC 版上传目录**

1. 先把本仓库下载到本地（Code → Download ZIP，解压）
2. 打开豆包 PC 版「技能·连接器·伙伴 → 我的技能」
3. 点右上角「新建 → 上传技能」，把 `skills/` 下的技能文件夹拖进去

### Claude Code / Codex 等开发类 Agent

支持 skills CLI 的环境可以用一条命令安装：

```bash
# 安装全部技能
npx skills add <你的GitHub用户名>/cyyd

# 只安装单个技能
npx skills add <你的GitHub用户名>/cyyd --skill cyyd-copywriting

# 查看仓库里有哪些技能
npx skills add <你的GitHub用户名>/cyyd --list
```

也可以手动安装：把 `skills/<技能名>/` 文件夹复制到对应 Agent 的技能目录（如 Claude Code 的 `~/.claude/skills/`）。

## 目录结构

```
cyyd/
├── README.md
└── skills/
    ├── cyyd/                      # 总入口：需求路由
    │   └── SKILL.md
    ├── cyyd-account-diagnosis/    # 账号诊断
    │   └── SKILL.md
    ├── cyyd-ip-planning/           # IP策划
    │   └── SKILL.md
    ├── cyyd-topic-selection/       # 72变选题
    │   └── SKILL.md
    ├── cyyd-copywriting/           # 一键出文案
    │   └── SKILL.md
    ├── cyyd-trending/              # 实时蹭热点
    │   └── SKILL.md
    ├── cyyd-viral-rewrite/         # 爆款文案改写
    │   └── SKILL.md
    ├── cyyd-opening-optimizer/     # 72变开头优化
    │   └── SKILL.md
    ├── cyyd-cover-title/           # 封面标题优化
    │   └── SKILL.md
    └── cyyd-work-diagnosis/        # 作品诊断
        └── SKILL.md
```

## 使用建议

- 不知道用哪个：先和总入口 `cyyd` 对话，它会引导你选
- 新手从零起号：IP策划 → 72变选题 → 一键出文案 → 封面标题优化
- 老号优化：账号诊断 → 72变开头优化 / 封面标题优化 → 作品诊断
- 追热点：实时蹭热点 → 一键出文案
- 对标学习：爆款文案改写 → 72变开头优化

## 说明

- 账号诊断、作品诊断需要模型具备联网/网页访问能力才能读取抖音主页和作品页内容；模型不支持联网时，会基于你提供的文字信息诊断
- 各技能的提示词基于 72 变短视频创作方法论，内容持续更新中

微信：ayoeyn

# GEO 搜索结果优化排名助手

基于 Electron + Vue3 + Arco Design 的桌面应用，支持 AI 内容生成和多平台自动发布。

## 功能模块

### 内容管理
- 控制台 - 数据概览和快捷操作
- 主关键词 - 管理 SEO 关键词
- 拓展问题 - AI 生成的相关问题，支持收录状态标记
- 企业知识库 - 上传企业资料
- 企业图库 - 分类管理图片素材
- AI 创作指令 - 自定义文章生成风格
- AI 创作计划 - 批量 AI 生成文章
- 文章管理 - 管理生成的文章

### 发布管理
- 定时发布任务 - 配置自动发布任务
- 自媒体账号 - 管理各平台账号
- 发布日志 - 查看发布记录
- 官媒代发 - 新闻源/媒体大V 代发服务
- AI 数据报表 - 各平台收录统计

### 支持平台
- 百度百家号
- 搜狐号
- 今日头条
- 知乎
- 小红书
- 网易号
- 抖音

## 技术栈

- Electron 27
- Vue 3 + Pinia
- Arco Design Vue
- Tailwind CSS
- Playwright (自动化发布)
- 火山方舟 AI API

## 目录结构

```
media-publisher/
├── electron/
│   ├── main.js           # Electron 主进程
│   ├── preload.js        # 预加载脚本
│   └── volcengineAI.js   # 本地 AI 调用
├── publishers/           # 各平台发布器
│   ├── base.js           # 基类
│   ├── baidu.js          # 百度百家号
│   ├── sohu.js           # 搜狐号
│   ├── toutiao.js        # 今日头条
│   ├── zhihu.js          # 知乎
│   ├── xiaohongshu.js    # 小红书
│   ├── netease.js        # 网易号
│   └── douyin.js         # 抖音
├── src/
│   ├── views/            # 页面组件
│   ├── stores/           # Pinia 状态管理
│   ├── router/           # 路由配置
│   ├── utils/            # 工具函数
│   └── config.js         # 全局配置
├── cookies/              # 登录 Cookie 存储
├── logs/                 # 发布日志
└── README.md
```

## 开发运行

```bash
# 安装依赖
npm install

# 开发模式
npm run dev

# 构建前端
npm run build

# 启动 Electron
npx electron .

# 构建并启动
npm run build && npx electron .
```

## 配置说明

### API 配置 (src/config.js)
```javascript
export default {
  siteBase: 'http://localhost',      // PHP 后台地址
  apiBase: 'http://localhost/api.php?r=',
  appName: 'GEO搜索结果优化排名助手'
}
```

### 火山方舟 AI
- API Key 在 PHP 后台"系统配置"中设置
- 客户端自动从后台获取加密配置
- 使用 AES-256-CBC 加密传输

### 新闻源媒体
新浪网、搜狐网、腾讯网、网易网、凤凰网、中华网、人民网、央视网、千龙网、新华网、中国网、慧聪网、中国日报网、中国经济网、中国新闻网、央广网、光明网、国际在线、中国青年网、和讯网、北青网、大众网、东方网、视界网 等

### 媒体大V平台
微信公众号、小红书、知乎号、百家号、新浪看点、企鹅号、网易号、搜狐号、新浪微博、头条号、豆瓣、快传号、东方号、哔哩哔哩、北京时间、东方财富号、UC头条号、中金在线号、一点号、大风号、雪球号、车家号、易车号、人民号 等

微信：ayoeyn

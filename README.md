---
AIGC:
  ContentProducer: '001191110102MAD55U9H0F10002'
  ContentPropagator: '001191110102MAD55U9H0F10002'
  Label: '1'
  ProduceID: '1822869f-49ee-41b1-892a-87763d104497'
  PropagateID: '1822869f-49ee-41b1-892a-87763d104497'
  ReservedCode1: '749449b2-05e1-4a20-9cc7-023b4ae85c41'
  ReservedCode2: '749449b2-05e1-4a20-9cc7-023b4ae85c41'
---

# 数智运营事业部项目看板

零依赖纯前端项目看板系统，支持直接部署到任意静态服务器或云平台。

## 快速部署

### 方式一：Docker 部署（推荐）

```bash
# 构建并启动
docker-compose up -d --build

# 访问 http://localhost:8080
```

### 方式二：Nginx 直接部署

```bash
# 1. 将 static/ 目录内容复制到 Nginx 的 html 目录
cp -r static/* /usr/share/nginx/html/

# 2. 将 nginx.conf 复制到 Nginx 配置目录
cp nginx.conf /etc/nginx/conf.d/default.conf

# 3. 重载 Nginx
nginx -s reload
```

### 方式三：任意静态服务器

将 `static/index.html` 放到任意 Web 服务器根目录即可。项目为纯前端单文件应用，无需后端服务。

### 方式四：云平台部署

- **Vercel / Netlify / Cloudflare Pages**：直接将项目目录推送至 Git 仓库，平台自动识别并部署
- **OSS / COS 对象存储**：上传 `static/index.html`，开启静态网站托管
- **GitHub Pages**：推送至仓库后开启 Pages 即可

## 功能概览

| 功能 | 说明 |
|------|------|
| 四列看板 | 洽谈→投标→采购→实施，拖拽切换状态 |
| 子状态管理 | 实施环节拆分交付子状态 + 财务子状态 |
| 智能导入 | Excel 列名自动匹配，仅导入相关数据 |
| 预算占用 | 6 项预算指标可视化，颜色预警 |
| 回款/列收 | 支持款项名称、金额、合同比例、是否列收 |
| 里程碑 | 手动添加 + 模板导入，操作变更自动提示记录 |
| 个性化设置 | 顶栏颜色/图片、标题文字/图标自定义 |

## 技术说明

- 纯 HTML/CSS/JavaScript，零外部依赖（仅引用 SheetJS CDN 处理 Excel）
- 数据持久化于浏览器 localStorage
- 响应式设计，适配桌面端与移动端

> AI生成
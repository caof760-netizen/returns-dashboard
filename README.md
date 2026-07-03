# 退货经营管理看板 V6.0 企业模块化版

本版本从 V5.1 功能一致增强版迁移而来，将原来的超大单 HTML 拆分为标准 GitHub Pages 项目结构，避免单文件超过 GitHub 网页上传限制。

## 目录结构

```text
index.html
css/dashboard.css
js/dashboard.js
libs/jszip.min.js
data/meta.js
data/returns-chunk-001.js ...
data/loader.js
assets/
.nojekyll
README.md
```

## 已迁移功能

- 销售 Excel 上传
- 退货 ZIP / Excel / CSV 上传
- 上传后内存解析并自动刷新看板
- 年/月/周/日、国家、品牌、品类、负责人、SKU健康度、原因组、QE状态、SLA状态、关键词筛选
- KPI、国家/品牌/品类汇总
- 折线趋势图
- SKU健康度
- TOP20退货原因中文原因组
- QE闭环、批量处理、备注、SLA
- 退货明细分页
- CSV导出
- QE处理状态本地保存
- 新增：导出/导入当前数据包 JSON，便于在不重新上传 Excel/ZIP 的情况下恢复当前数据

## GitHub Pages 部署

1. 不要上传 ZIP 文件。
2. 解压后，将 `index.html`、`css`、`js`、`libs`、`data`、`assets`、`.nojekyll`、`README.md` 一起上传到仓库根目录。
3. 打开仓库 `Settings → Pages`。
4. Source 选择 `Deploy from a branch`。
5. Branch 选择 `main`，Folder 选择 `/root`，保存。
6. 等待 1 分钟后访问 GitHub 生成的网址。

## 注意

- 上传新销售/退货数据后，数据在页面内存中刷新，不会写入 LocalStorage，因此不会再出现 quota 超限。
- 如果需要保留上传后的状态，可点击“导出当前数据包JSON”，下次再打开页面时点击“导入已保存数据包”。
- 第三方 Excel 解析库 SheetJS 通过 CDN 加载；如果公司网络限制外网 CDN，需要后续改为本地库。

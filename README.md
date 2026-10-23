# TradeType 16 · 交易人格实验室

> 根据投资决策习惯探索你的16型交易人格，并与投资大师的**代表性策略**对照。

![TradeType 16 网站首页](docs/preview.webp)

**网站（GitHub Pages）**：https://335083474.github.io/trade-type16/ （需要仓库发布成功并开启 Pages 后才可访问）

## 功能

- 24道投资情境题，四组倾向：基本面 F / 技术面 T、持有 H / 交易 R、集中 C / 分散 D、艺术 A / 科学 M。
- 16型测评报告、临界倾向提示、策略盲点、与投资大师方法的参照。
- 首页大师原型图鉴（已内嵌在HTML文件中，支持放大）。
- 在本地解析CSV、TSV、XLSX成交记录，计算可配对持有期；另可分析持仓快照的集中度。
- 下载测评文本、浏览器打印/另存PDF。

## 快速发布到 GitHub Pages

1. 在 GitHub 账号 `335083474` 下创建**公开的空仓库**：`trade-type16`（创建时不勾选预置 README、.gitignore 或 license）。
2. 在仓库首页选择 **uploading an existing file**，把本项目目录里的 `index.html`、`.nojekyll`、`README.md`、`demo_trades.csv`、`demo_holdings.csv` 和 `docs` 文件夹上传到仓库**根目录**；提交到 `main`。
3. 打开 **Settings → Pages → Build and deployment → Deploy from a branch**，选择 `main` 和 `/(root)`，保存。
4. 等待GitHub完成首次发布后，打开 https://335083474.github.io/trade-type16/ 并验证题目、结果页和大师图鉴。

注意：这个ZIP是交付包，需要**解压后**上传内部文件，不能把ZIP本身直接上传作为网页。

## 关于交易记录和隐私

- 页面无需后端：交易文件在浏览器本地解析，不上传服务器。
- 原始交易与持仓文件仅在当前页面内存处理；localStorage只存问卷进度与答案。
- 上传前建议去掉真实姓名、交易账户号码、身份证号及联系方式。
- CSV / TSV / TXT / XLSX 的支持与边界以页面提示为准；PDF扫描件和老式XLS不支持。
- 交易持有期采用已匹配成交的FIFO估计；持仓不全时不会把成交标的数量误认为资金分散程度。
- 人格测试是教育与游戏化的行为偏好测评，尚无心理测量学信效度验证，不能预测收益或投资能力，也不构成投资建议。
- 投资大师对应的是**代表性策略原型**，并非对真人一生的唯一定类。

## 项目结构

```text
trade-type16/
├── index.html          # 完整自包含网页，含图鉴与代码
├── .nojekyll           # 不通过Jekyll加工
├── README.md
├── demo_trades.csv     # 合成成交记录
├── demo_holdings.csv   # 合成持仓记录
└── docs/preview.webp   # 页面预览
```

**第三方代码**：页面内置JSZip，遵循MIT License（https://github.com/Stuk/jszip/blob/main/LICENSE.markdown）。

后续如需添加到你的导航站 `my-websites-hub`，请使用附带的“导航接入补丁”包。它将创建一个独立入口，而不会替换现有导航首页。

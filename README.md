<!-- mcp-name: io.github.D4Vinci/Scrapling -->

<h1 align="center">
    <a href="https://scrapling.readthedocs.io">
        <picture>
          <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/D4Vinci/Scrapling/main/docs/assets/cover_dark.svg?sanitize=true">
          <img alt="Scrapling 海报" src="https://raw.githubusercontent.com/D4Vinci/Scrapling/main/docs/assets/cover_light.svg?sanitize=true">
        </picture>
    </a>
    <br>
    <small>为现代网络打造的轻松网页抓取</small>
</h1>

<p align="center">
    <a href="https://trendshift.io/repositories/14244" target="_blank"><img src="https://trendshift.io/api/badge/repositories/14244" alt="D4Vinci%2FScrapling | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>
    <br/>
    <a href="https://github.com/D4Vinci/Scrapling/blob/main/docs/README_AR.md">العربيه</a> | <a href="https://github.com/D4Vinci/Scrapling/blob/main/docs/README_ES.md">Español</a> | <a href="https://github.com/D4Vinci/Scrapling/blob/main/docs/README_FR.md">Français</a> | <a href="https://github.com/D4Vinci/Scrapling/blob/main/docs/README_DE.md">Deutsch</a> | <a href="https://github.com/D4Vinci/Scrapling/blob/main/docs/README_CN.md">简体中文</a> | <a href="https://github.com/D4Vinci/Scrapling/blob/main/docs/README_JP.md">日本語</a> |  <a href="https://github.com/D4Vinci/Scrapling/blob/main/docs/README_RU.md">Русский</a>
    <br/>
    <a href="https://github.com/D4Vinci/Scrapling/actions/workflows/tests.yml" alt="测试">
        <img alt="测试" src="https://github.com/D4Vinci/Scrapling/actions/workflows/tests.yml/badge.svg"></a>
    <a href="https://badge.fury.io/py/Scrapling" alt="PyPI 版本">
        <img alt="PyPI 版本" src="https://badge.fury.io/py/Scrapling.svg"></a>
    <a href="https://pepy.tech/project/scrapling" alt="PyPI 下载量">
        <img alt="PyPI 下载量" src="https://static.pepy.tech/personalized-badge/scrapling?period=total&units=INTERNATIONAL_SYSTEM&left_color=GREY&right_color=GREEN&left_text=Downloads"></a>
    <a href="https://github.com/D4Vinci/Scrapling/tree/main/agent-skill" alt="AI Agent Skill 目录">
        <img alt="Static Badge" src="https://img.shields.io/badge/Skill-black?style=flat&label=Agent&link=https%3A%2F%2Fgithub.com%2FD4Vinci%2FScrapling%2Ftree%2Fmain%2Fagent-skill"></a>
    <a href="https://clawhub.ai/D4Vinci/scrapling-official" alt="OpenClaw Skill">
        <img alt="OpenClaw Skill" src="https://img.shields.io/badge/Clawhub-darkred?style=flat&label=OpenClaw&link=https%3A%2F%2Fclawhub.ai%2FD4Vinci%2Fscrapling-official"></a>
    <br/>
    <a href="https://discord.gg/EMgGbDceNQ" alt="Discord" target="_blank">
      <img alt="Discord" src="https://img.shields.io/discord/1360786381042880532?style=social&logo=discord&link=https%3A%2F%2Fdiscord.gg%2FEMgGbDceNQ">
    </a>
    <a href="https://x.com/Scrapling_dev" alt="X (原 Twitter)">
      <img alt="X (原 Twitter) 关注" src="https://img.shields.io/twitter/follow/Scrapling_dev?style=social&logo=x&link=https%3A%2F%2Fx.com%2FScrapling_dev">
    </a>
    <br/>
    <a href="https://pypi.org/project/scrapling/" alt="支持的 Python 版本">
        <img alt="支持的 Python 版本" src="https://img.shields.io/pypi/pyversions/scrapling.svg"></a>
</p>

<p align="center">
    <a href="https://scrapling.readthedocs.io/en/latest/parsing/selection/"><strong>选择方法</strong></a>
    &middot;
    <a href="https://scrapling.readthedocs.io/en/latest/fetching/choosing/"><strong>抓取器</strong></a>
    &middot;
    <a href="https://scrapling.readthedocs.io/en/latest/spiders/architecture.html"><strong>爬虫</strong></a>
    &middot;
    <a href="https://scrapling.readthedocs.io/en/latest/spiders/proxy-blocking.html"><strong>代理轮换</strong></a>
    &middot;
    <a href="https://scrapling.readthedocs.io/en/latest/cli/overview/"><strong>命令行工具</strong></a>
    &middot;
    <a href="https://scrapling.readthedocs.io/en/latest/ai/mcp-server/"><strong>MCP</strong></a>
</p>

Scrapling 是一个自适应的网页抓取框架，能够处理从单个请求到大规模爬取的所有任务。

它的解析器能够学习网站的变化，并在页面更新时自动重新定位元素。它的抓取器可以开箱即用地绕过 Cloudflare Turnstile 等反机器人系统。它的爬虫框架让你只需几行 Python 代码就能实现并发、多会话的爬取，支持暂停/恢复和自动代理轮换。一个库，零妥协。

极速爬取，实时统计和流式输出。由网页抓取者为网页抓取者和普通用户打造，每个人都能找到适合自己的功能。

```python
from scrapling.fetchers import Fetcher, AsyncFetcher, StealthyFetcher, DynamicFetcher
StealthyFetcher.adaptive = True
p = StealthyFetcher.fetch('https://example.com', headless=True, network_idle=True)  # 隐蔽抓取网站！
products = p.css('.product', auto_save=True)                                        # 抓取能够适应网站设计变化的数据！
products = p.css('.product', adaptive=True)                                         # 之后，如果网站结构发生变化，传入 `adaptive=True` 来找到它们！
```
或者扩展到完整爬取
```python
from scrapling.spiders import Spider, Response

class MySpider(Spider):
  name = "demo"
  start_urls = ["https://example.com/"]

  async def parse(self, response: Response):
      for item in response.css('.product'):
          yield {"title": item.css('h2::text').get()}

MySpider().start()
```

---

## 核心特性

### 爬虫 — 完整的爬取框架
- 🕷️ **类 Scrapy 的爬虫 API**：使用 `start_urls`、异步 `parse` 回调和 `Request`/`Response` 对象定义爬虫。
- ⚡ **并发爬取**：可配置的并发限制、按域名限速和下载延迟。
- 🔄 **多会话支持**：统一的 HTTP 请求和隐身无头浏览器接口——通过 ID 将请求路由到不同会话。
- 💾 **暂停与恢复**：基于检查点的爬取持久化。按 Ctrl+C 优雅关闭；重新启动后从停止处继续。
- 📡 **流式模式**：通过 `async for item in spider.stream()` 实时流式接收抓取的数据项，带有实时统计——非常适合 UI、管道和长时间运行的爬取任务。
- 🛡️ **被阻止请求检测**：自动检测和重试被阻止的请求，支持自定义逻辑。
- 📦 **内置导出**：通过钩子和自定义管道导出结果，或使用内置的 JSON/JSONL 格式，分别调用 `result.items.to_json()` / `result.items.to_jsonl()`。

### 支持会话的高级网站抓取
- **HTTP 请求**：使用 `Fetcher` 类实现快速且隐蔽的 HTTP 请求。可以模拟浏览器的 TLS 指纹、请求头，并使用 HTTP/3。
- **动态加载**：通过 `DynamicFetcher` 类实现完整的浏览器自动化抓取动态网站，支持 Playwright 的 Chromium 和 Google Chrome。
- **反机器人绕过**：`StealthyFetcher` 提供高级隐身功能和指纹欺骗。可以轻松通过自动化绕过各种类型的 Cloudflare Turnstile/拦截页面。
- **会话管理**：`FetcherSession`、`StealthySession` 和 `DynamicSession` 类支持持久化会话，可在请求之间管理 Cookie 和状态。
- **代理轮换**：内置 `ProxyRotator`，支持循环或自定义轮换策略，适用于所有会话类型，还支持按请求覆盖代理。
- **域名阻止**：在基于浏览器的抓取器中阻止对特定域名（及其子域名）的请求。
- **异步支持**：所有抓取器都完整支持异步，并提供专用的异步会话类。

### 自适应抓取与 AI 集成
- 🔄 **智能元素追踪**：使用智能相似度算法在网站变化后重新定位元素。
- 🎯 **智能灵活选择**：CSS 选择器、XPath 选择器、基于过滤器的搜索、文本搜索、正则表达式搜索等。
- 🔍 **查找相似元素**：自动定位与已找到元素相似的元素。
- 🤖 **用于 AI 的 MCP 服务器**：内置 MCP 服务器，用于 AI 辅助的网页抓取和数据提取。MCP 服务器具有强大的自定义功能，利用 Scrapling 在传递给 AI（Claude/Cursor 等）之前提取目标内容，从而加快操作速度并通过减少 token 使用量来降低成本。（[演示视频](https://www.youtube.com/watch?v=qyFk3ZNwOxE)）

### 高性能且经受过实战检验的架构
- 🚀 **极速**：优化后的性能超过大多数 Python 抓取库。
- 🔋 **内存高效**：优化的数据结构和延迟加载，实现最小内存占用。
- ⚡ **快速 JSON 序列化**：比标准库快 10 倍。
- 🏗️ **经受过实战检验**：Scrapling 不仅拥有 92% 的测试覆盖率和完整的类型提示覆盖率，而且过去一年中每天都有数百名网页抓取者使用它。

### 开发者/网页抓取者友好的体验
- 🎯 **交互式网页抓取 Shell**：可选的内置 IPython Shell，集成 Scrapling、快捷键和新工具，加速网页抓取脚本开发，如将 curl 请求转换为 Scrapling 请求，以及在浏览器中查看请求结果。
- 🚀 **直接从终端使用**：可选择使用 Scrapling 抓取 URL，无需编写任何代码！
- 🛠️ **丰富的导航 API**：高级 DOM 遍历，支持父元素、兄弟元素和子元素导航方法。
- 🧬 **增强的文本处理**：内置正则表达式、清理方法和优化的字符串操作。
- 📝 **自动选择器生成**：为任何元素生成稳健的 CSS/XPath 选择器。
- 🔌 **熟悉的 API**：类似于 Scrapy/BeautifulSoup，使用与 Scrapy/Parsel 相同的伪元素。
- 📘 **完整的类型覆盖**：完整的类型提示，提供出色的 IDE 支持和代码补全。整个代码库在每次更改时都会自动使用 **PyRight** 和 **MyPy** 进行扫描。
- 🔋 **现成的 Docker 镜像**：每次发布都会自动构建并推送包含所有浏览器的 Docker 镜像。

## 快速入门

让我们快速了解 Scrapling 能做什么，不必深入细节。

### 基本用法
支持会话的 HTTP 请求
```python
from scrapling.fetchers import Fetcher, FetcherSession

with FetcherSession(impersonate='chrome') as session:  # 使用最新版 Chrome 的 TLS 指纹
    page = session.get('https://quotes.toscrape.com/', stealthy_headers=True)
    quotes = page.css('.quote .text::text').getall()

# 或使用一次性请求
page = Fetcher.get('https://quotes.toscrape.com/')
quotes = page.css('.quote .text::text').getall()
```
高级隐身模式
```python
from scrapling.fetchers import StealthyFetcher, StealthySession

with StealthySession(headless=True, solve_cloudflare=True) as session:  # 保持浏览器打开直到完成
    page = session.fetch('https://nopecha.com/demo/cloudflare', google_search=False)
    data = page.css('#padded_content a').getall()

# 或使用一次性请求风格，为此请求打开浏览器，完成后关闭
page = StealthyFetcher.fetch('https://nopecha.com/demo/cloudflare')
data = page.css('#padded_content a').getall()
```
完整的浏览器自动化
```python
from scrapling.fetchers import DynamicFetcher, DynamicSession

with DynamicSession(headless=True, disable_resources=False, network_idle=True) as session:  # 保持浏览器打开直到完成
    page = session.fetch('https://quotes.toscrape.com/', load_dom=False)
    data = page.xpath('//span[@class="text"]/text()').getall()  # 如果你喜欢，可以使用 XPath 选择器

# 或使用一次性请求风格，为此请求打开浏览器，完成后关闭
page = DynamicFetcher.fetch('https://quotes.toscrape.com/')
data = page.css('.quote .text::text').getall()
```

### 爬虫
构建完整的爬虫，支持并发请求、多种会话类型和暂停/恢复：
```python
from scrapling.spiders import Spider, Request, Response

class QuotesSpider(Spider):
    name = "quotes"
    start_urls = ["https://quotes.toscrape.com/"]
    concurrent_requests = 10
    
    async def parse(self, response: Response):
        for quote in response.css('.quote'):
            yield {
                "text": quote.css('.text::text').get(),
                "author": quote.css('.author::text').get(),
            }
            
        next_page = response.css('.next a')
        if next_page:
            yield response.follow(next_page[0].attrib['href'])

result = QuotesSpider().start()
print(f"抓取了 {len(result.items)} 条引言")
result.items.to_json("quotes.json")
```
在单个爬虫中使用多种会话类型：
```python
from scrapling.spiders import Spider, Request, Response
from scrapling.fetchers import FetcherSession, AsyncStealthySession

class MultiSessionSpider(Spider):
    name = "multi"
    start_urls = ["https://example.com/"]
    
    def configure_sessions(self, manager):
        manager.add("fast", FetcherSession(impersonate="chrome"))
        manager.add("stealth", AsyncStealthySession(headless=True), lazy=True)
    
    async def parse(self, response: Response):
        for link in response.css('a::attr(href)').getall():
            # 通过隐身会话路由受保护的页面
            if "protected" in link:
                yield Request(link, sid="stealth")
            else:
                yield Request(link, sid="fast", callback=self.parse)  # 显式回调
```
通过检查点暂停和恢复长时间的爬取任务：
```python
QuotesSpider(crawldir="./crawl_data").start()
```
按 Ctrl+C 优雅暂停——进度会自动保存。之后，当你再次启动爬虫时，传入相同的 `crawldir`，它将从停止处继续。

### 高级解析与导航
```python
from scrapling.fetchers import Fetcher

# 丰富的元素选择和导航
page = Fetcher.get('https://quotes.toscrape.com/')

# 使用多种选择方法获取引言
quotes = page.css('.quote')  # CSS 选择器
quotes = page.xpath('//div[@class="quote"]')  # XPath
quotes = page.find_all('div', {'class': 'quote'})  # BeautifulSoup 风格
# 等同于
quotes = page.find_all('div', class_='quote')
quotes = page.find_all(['div'], class_='quote')
quotes = page.find_all(class_='quote')  # 以此类推...
# 按文本内容查找元素
quotes = page.find_by_text('quote', tag='div')

# 高级导航
quote_text = page.css('.quote')[0].css('.text::text').get()
quote_text = page.css('.quote').css('.text::text').getall()  # 链式选择器
first_quote = page.css('.quote')[0]
author = first_quote.next_sibling.css('.author::text')
parent_container = first_quote.parent

# 元素关系和相似性
similar_elements = first_quote.find_similar()
below_elements = first_quote.below_elements()
```
如果你不想抓取网站，可以直接使用解析器：
```python
from scrapling.parser import Selector

page = Selector("<html>...</html>")
```
它的工作方式完全相同！

### 异步会话管理示例
```python
import asyncio
from scrapling.fetchers import FetcherSession, AsyncStealthySession, AsyncDynamicSession

async with FetcherSession(http3=True) as session:  # `FetcherSession` 支持上下文感知，可在同步/异步模式下工作
    page1 = session.get('https://quotes.toscrape.com/')
    page2 = session.get('https://quotes.toscrape.com/', impersonate='firefox135')

# 异步会话使用
async with AsyncStealthySession(max_pages=2) as session:
    tasks = []
    urls = ['https://example.com/page1', 'https://example.com/page2']
    
    for url in urls:
        task = session.fetch(url)
        tasks.append(task)
    
    print(session.get_pool_stats())  # 可选 - 浏览器标签页池的状态（忙碌/空闲/错误）
    results = await asyncio.gather(*tasks)
    print(session.get_pool_stats())
```

## 命令行工具与交互式 Shell

Scrapling 包含强大的命令行界面：

[![asciicast](https://asciinema.org/a/736339.svg)](https://asciinema.org/a/736339)

启动交互式网页抓取 shell
```bash
scrapling shell
```
无需编程即可将页面提取到文件中（默认提取 `body` 标签内的内容）。如果输出文件以 `.txt` 结尾，则提取目标的文本内容。如果以 `.md` 结尾，则是 HTML 内容的 Markdown 表示；如果以 `.html` 结尾，则是 HTML 内容本身。
```bash
scrapling extract get 'https://example.com' content.md
scrapling extract get 'https://example.com' content.txt --css-selector '#fromSkipToProducts' --impersonate 'chrome'  # 所有匹配 CSS 选择器 '#fromSkipToProducts' 的元素
scrapling extract fetch 'https://example.com' content.md --css-selector '#fromSkipToProducts' --no-headless
scrapling extract stealthy-fetch 'https://nopecha.com/demo/cloudflare' captchas.html --css-selector '#padded_content a' --solve-cloudflare
```

> [!NOTE]
> 还有许多其他功能，但我们希望保持此页面简洁，包括 MCP 服务器和交互式网页抓取 Shell。请在[这里](https://scrapling.readthedocs.io/en/latest/)查看完整文档。

## 性能基准测试

Scrapling 不仅功能强大，而且速度极快。以下基准测试将 Scrapling 的解析器与其他流行库的最新版本进行了比较。

### 文本提取速度测试（5000 个嵌套元素）

| # |      库      | 时间 (毫秒) | 相对 Scrapling | 
|---|:-----------------:|:---------:|:------------:|
| 1 |     Scrapling     |   2.02    |     1.0x     |
| 2 |   Parsel/Scrapy   |   2.04    |     1.01     |
| 3 |     Raw Lxml      |   2.54    |    1.257     |
| 4 |      PyQuery      |   24.17   |     ~12x     |
| 5 |    Selectolax     |   82.63   |     ~41x     |
| 6 |  MechanicalSoup   |  1549.71  |   ~767.1x    |
| 7 |   BS4 with Lxml   |  1584.31  |   ~784.3x    |
| 8 | BS4 with html5lib |  3391.91  |   ~1679.1x   |


### 元素相似性与文本搜索性能

Scrapling 的自适应元素查找功能明显优于其他方案：

| 库     | 时间 (毫秒) | 相对 Scrapling |
|-------------|:---------:|:------------:|
| Scrapling   |   2.39    |     1.0x     |
| AutoScraper |   12.45   |    5.209x    |


> 所有基准测试均为 100 次以上运行的平均值。方法请参见 [benchmarks.py](https://github.com/D4Vinci/Scrapling/blob/main/benchmarks.py)。

## 安装

Scrapling 需要 Python 3.10 或更高版本：

```bash
pip install scrapling
```

此安装仅包含解析器引擎及其依赖项，不包含任何抓取器或命令行依赖项。

### 可选依赖项

1. 如果你要使用以下任何额外功能、抓取器或其类，需要按以下方式安装抓取器的依赖项及其浏览器依赖项：
    ```bash
    pip install "scrapling[fetchers]"
    
    scrapling install           # 正常安装
    scrapling install  --force  # 强制重新安装
    ```

    这会下载所有浏览器，以及它们的系统依赖项和指纹操作依赖项。

    或者你可以在代码中安装它们，而不是运行命令：
    ```python
    from scrapling.cli import install
    
    install([], standalone_mode=False)          # 正常安装
    install(["--force"], standalone_mode=False) # 强制重新安装
    ```

2. 额外功能：
   - 安装 MCP 服务器功能：
       ```bash
       pip install "scrapling[ai]"
       ```
   - 安装 shell 功能（网页抓取 shell 和 `extract` 命令）： 
       ```bash
       pip install "scrapling[shell]"
       ```
   - 安装所有内容： 
       ```bash
       pip install "scrapling[all]"
       ```
   请记住，在安装任何这些额外功能后，你需要使用 `scrapling install` 安装浏览器依赖项（如果尚未安装）

### Docker
你也可以使用以下命令从 DockerHub 安装包含所有额外功能和浏览器的 Docker 镜像：
```bash
docker pull pyd4vinci/scrapling
```
或从 GitHub 注册表下载：
```bash
docker pull ghcr.io/d4vinci/scrapling:latest
```
此镜像使用 GitHub Actions 和仓库的主分支自动构建和推送。

## 贡献

我们欢迎贡献！请在开始之前阅读我们的[贡献指南](https://github.com/D4Vinci/Scrapling/blob/main/CONTRIBUTING.md)。

## 免责声明

> [!CAUTION]
> 本库仅供教育和研究目的使用。使用本库即表示你同意遵守当地和国际数据抓取及隐私法律。作者和贡献者不对本软件的任何滥用负责。请始终尊重网站的服务条款和 robots.txt 文件。

## 🎓 引用
如果你在研究目的中使用了我们的库，请使用以下引用：
```text
  @misc{scrapling,
    author = {Karim Shoair},
    title = {Scrapling},
    year = {2024},
    url = {https://github.com/D4Vinci/Scrapling},
    note = {An adaptive Web Scraping framework that handles everything from a single request to a full-scale crawl!}
  }
```

## 许可证

本作品采用 BSD-3-Clause 许可证授权。

## 致谢

本项目包含以下项目的改编代码：
- Parsel（BSD 许可证）— 用于 [translator](https://github.com/D4Vinci/Scrapling/blob/main/scrapling/core/translator.py) 子模块

---
<div align="center"><small>由 Karim Shoair 用 ❤️ 设计打造。</small></div><br>
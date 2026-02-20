<h1 align="center">Agent WebSearch Skill 🔍</h1>

<p align="center">
  <b>Intelligent Multi-Engine Search — Works With or Without VPN</b>
</p>

<p align="center">
  <b>无需科学上网 · 无需国外 API · 开箱即用</b>
</p>

<p align="center">
  <i>Zero config. Zero API keys. Auto-fallback from DuckDuckGo → Tavily → Bing API → Bing Scraper.</i>
</p>

<p align="center">
  <i>智能多引擎搜索，自动故障转移，国内直连可用，完美适配复杂网络环境。</i>
</p>

<p align="center">
  <a href="https://opensource.org/licenses/GPL-3.0">
    <img src="https://img.shields.io/badge/License-GPL%203.0-blue.svg?style=flat-square" alt="License: GPL-3.0">
  </a>
  <a href="https://www.python.org/">
    <img src="https://img.shields.io/badge/Python-3.8%2B-green.svg?style=flat-square" alt="Python: 3.8+">
  </a>
  <a href="https://github.com/Nex-ZMH/Agent-websearch-skill">
    <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey.svg?style=flat-square" alt="Platform">
  </a>
  <img src="https://img.shields.io/badge/No%20VPN%20Required-✓-success.svg?style=flat-square" alt="No VPN Required">
</p>

<p align="center">
Built by <a href="https://github.com/Nex-ZMH">Nex-ZMH</a>, an AI enthusiast exploring the boundaries of automation.
</p>

<p align="center">
  🌐 Language:
  <a href="#english">English</a> ·
  <a href="#中文">简体中文</a>
</p>

---

## The Problem We Solve

### 🚫 常见痛点 / Common Pain Points

| 问题 | 描述 |
|------|------|
| 🔒 **无法获取国外 API Key** | Brave Search 等需要国外信用卡或 Visa 卡注册，国内用户难以申请 |
| 🌐 **网络环境不稳定** | 科学上网时断时续，搜索引擎可用性随时变化 |
| 💰 **API 配额有限** | 免费额度用完后，搜索功能直接失效 |
| 🔄 **手动切换繁琐** | 每次网络变化都要手动更换搜索引擎 |

> **💡 为什么不直接用 OpenClaw 内置的 Brave Search？**
> 
> OpenClaw 内置的 Brave Search 需要：
> - ✅ 科学上网才能访问
> - ✅ Visa/MasterCard 信用卡注册账号
> - ✅ 绑定付款方式才能获取 API Key
> 
> 对于大多数国内用户来说，这些门槛难以跨越。而本项目**无需任何门槛**，克隆即可使用！

### ✅ 我们的解决方案

**Agent WebSearch Skill** 通过智能引擎选择策略，完美解决上述问题：

- ✨ **零配置可用** — 即使没有任何 API Key，也能通过 Bing 爬虫正常搜索
- 🔄 **自动故障转移** — 一个引擎失败，自动切换到下一个可用引擎
- 📊 **智能配额管理** — 优先使用免费引擎，节省 API 配额给关键时刻
- 🌐 **网络自适应** — 自动检测网络环境，选择当前最优引擎

---

## 中文

### 智能搜索策略详解

这是本项目的核心价值所在。我们设计了**四层搜索引擎架构**，确保在任何网络环境下都能正常工作：

```
┌─────────────────────────────────────────────────────────────┐
│                    搜索引擎选择策略                          │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  平衡模式（默认）— 优先免费引擎，节省 API 配额               │
│  ┌─────────┐    ┌─────────┐    ┌──────────┐    ┌─────────┐ │
│  │DuckDuckGo│ → │ Tavily  │ → │ Bing API │ → │  Bing   │ │
│  │ (免费)   │    │(需API)  │    │ (需API)  │    │ 爬虫    │ │
│  └─────────┘    └─────────┘    └──────────┘    └─────────┘ │
│       ↓              ↓              ↓              ↓       │
│    无需科学上网   需科学上网+API  需科学上网+API  国内直连    │
│                                                             │
│  质量优先模式 — 优先高质量 API，适合重要搜索                 │
│  ┌─────────┐    ┌─────────┐    ┌──────────┐    ┌─────────┐ │
│  │ Tavily  │ → │DuckDuckGo│ → │ Bing API │ → │  Bing   │ │
│  │(高质量) │    │ (免费)   │    │ (需API)  │    │ 爬虫    │ │
│  └─────────┘    └─────────┘    └──────────┘    └─────────┘ │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### 各引擎特点对比

| 引擎 | 需要科学上网 | 需要 API Key | 月配额 | 搜索质量 | 适用场景 |
|------|:------------:|:------------:|:------:|:--------:|----------|
| **DuckDuckGo** | ✅ 需要 | ❌ 不需要 | ♾️ 无限 | ⭐⭐⭐ | 日常搜索首选 |
| **Tavily API** | ✅ 需要 | ✅ 需要 | 1000次 | ⭐⭐⭐⭐⭐ | AI Agent、重要搜索 |
| **Bing API** | ✅ 需要 | ✅ 需要 | 1000次 | ⭐⭐⭐⭐ | 官方稳定搜索 |
| **Bing 爬虫** | ❌ 不需要 | ❌ 不需要 | ♾️ 无限 | ⭐⭐⭐ | 国内无科学上网时的保底方案 |

### 为什么选择我们？

**场景 1：国内用户，没有科学上网，没有 API Key**
```
用户搜索 → DuckDuckGo 失败 → Tavily 跳过 → Bing API 跳过 → Bing 爬虫成功 ✅
结果：正常返回搜索结果，完全可用！
```

**场景 2：有科学上网，有 Tavily API Key**
```
用户搜索 → DuckDuckGo 成功 ✅
结果：使用免费引擎，节省 API 配额
```

**场景 3：网络不稳定，时断时续**
```
用户搜索 → DuckDuckGo 失败 → Tavily 成功 ✅
结果：自动切换，用户无感知
```

### 快速开始

```bash
# 克隆仓库
git clone https://github.com/Nex-ZMH/Agent-websearch-skill.git
cd Agent-websearch-skill

# 安装依赖
pip install requests tavily-python duckduckgo-search beautifulsoup4

# 立即使用（无需任何配置！）
python -c "from multi_search import search; print(search('Python 教程'))"
```

### 使用示例

```python
from multi_search import search, get_status, fetch_web_content

# 基本搜索 — 自动选择最优引擎
results = search("Python 异步编程教程", max_results=5)

# 质量优先模式 — 适合重要搜索
results = search("AI 论文 2024", max_results=5, prefer_quality=True)

# 切换 VPN 后强制重新检测网络
results = search("最新科技新闻", force_network_check=True)

# 查看当前系统状态
status = get_status()
# 输出：各引擎可用性、API 配额剩余情况

# 抓取网页详细内容
content = fetch_web_content(results[0]['href'], max_length=3000)
```

### API 配置（可选）

> **重要**：本项目**无需任何配置即可使用**！以下配置仅用于解锁高级功能。

**方法 1：环境变量（推荐）**
```bash
export TAVILY_API_KEY="your-tavily-api-key"
export BING_API_KEY="your-bing-api-key"
```

**方法 2：配置文件**
```bash
cp api_keys.example.json api_keys.json
# 编辑 api_keys.json 填入你的密钥
```

### 系统要求

- Python 3.8+
- `requests` `tavily-python` `duckduckgo-search` `beautifulsoup4`

---

## English

### Smart Search Strategy Explained

This is the core value of our project. We designed a **four-layer search engine architecture** that ensures functionality in any network environment:

```
┌─────────────────────────────────────────────────────────────┐
│                  Search Engine Selection Strategy            │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  Balanced Mode (Default) — Free engines first, save quota   │
│  ┌──────────┐   ┌─────────┐   ┌──────────┐   ┌─────────┐   │
│  │DuckDuckGo│ → │ Tavily  │ → │ Bing API │ → │  Bing   │   │
│  │  (Free)  │   │(API)    │   │  (API)   │   │ Scraper │   │
│  └──────────┘   └─────────┘   └──────────┘   └─────────┘   │
│       ↓              ↓              ↓              ↓        │
│   Needs VPN     VPN+API     VPN+API    Works in China  │
│                                                             │
│  Quality First Mode — Premium APIs first for best results   │
│  ┌─────────┐    ┌──────────┐   ┌──────────┐   ┌─────────┐  │
│  │ Tavily  │ → │DuckDuckGo│ → │ Bing API │ → │  Bing   │  │
│  │(Premium)│    │  (Free)  │   │  (API)   │   │ Scraper │  │
│  └─────────┘    └──────────┘   └──────────┘   └─────────┘  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Engine Comparison

| Engine | VPN Required | API Key | Monthly Quota | Quality | Best For |
|--------|:--------------:|:-------:|:-------------:|:-------:|----------|
| **DuckDuckGo** | ✅ Yes | ❌ No | ♾️ Unlimited | ⭐⭐⭐ | Daily searches |
| **Tavily API** | ✅ Yes | ✅ Yes | 1000 | ⭐⭐⭐⭐⭐ | AI Agents, important searches |
| **Bing API** | ✅ Yes | ✅ Yes | 1000 | ⭐⭐⭐⭐ | Official stable search |
| **Bing Scraper** | ❌ No | ❌ No | ♾️ Unlimited | ⭐⭐⭐ | Fallback without VPN |

### Why Choose Us?

**Scenario 1: No VPN, No API Key (China mainland)**
```
Search → DuckDuckGo fails → Skip Tavily → Skip Bing API → Bing Scraper succeeds ✅
Result: Works perfectly without any configuration!
```

**Scenario 2: Has VPN, Has Tavily API Key**
```
Search → DuckDuckGo succeeds ✅
Result: Uses free engine, saves API quota
```

**Scenario 3: Unstable Network**
```
Search → DuckDuckGo fails → Tavily succeeds ✅
Result: Auto-switch, seamless experience
```

### Quick Start

```bash
# Clone repository
git clone https://github.com/Nex-ZMH/Agent-websearch-skill.git
cd Agent-websearch-skill

# Install dependencies
pip install requests tavily-python duckduckgo-search beautifulsoup4

# Use immediately (no configuration needed!)
python -c "from multi_search import search; print(search('Python tutorial'))"
```

### Usage Examples

```python
from multi_search import search, get_status, fetch_web_content

# Basic search — auto-select best engine
results = search("Python async tutorial", max_results=5)

# Quality-first mode — for important searches
results = search("AI research papers 2024", max_results=5, prefer_quality=True)

# Force network recheck after VPN switch
results = search("latest tech news", force_network_check=True)

# Check system status
status = get_status()

# Fetch detailed content from URL
content = fetch_web_content(results[0]['href'], max_length=3000)
```

### API Configuration (Optional)

> **Note**: This project works **out of the box** without any configuration!

**Method 1: Environment Variables (Recommended)**
```bash
export TAVILY_API_KEY="your-tavily-api-key"
export BING_API_KEY="your-bing-api-key"
```

**Method 2: Configuration File**
```bash
cp api_keys.example.json api_keys.json
# Edit api_keys.json with your keys
```

### Requirements

- Python 3.8+
- `requests` `tavily-python` `duckduckgo-search` `beautifulsoup4`

---

## Roadmap

- [ ] Add Google Search API support
- [ ] Implement async/await for parallel searches
- [ ] Add rate limiting configuration
- [ ] Support custom search engine priority
- [ ] Add Searxng integration for privacy-focused users

---

## Author

[Nex-ZMH](https://github.com/Nex-ZMH)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

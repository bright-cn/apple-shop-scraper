# Apple Shop 抓取工具

[![Bright Data](https://img.shields.io/badge/Powered%20by-Bright%20Data-FF9A00?style=flat-square)](https://www.bright.cn/) [![爬虫工具 API](https://img.shields.io/badge/Scraper%20API-Available-FF9A00?style=flat-square)](https://www.bright.cn/products/web-scraper) [![数据集](https://img.shields.io/badge/Dataset-Available-0066CC?style=flat-square)](https://www.bright.cn/products/datasets/) [![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org) [![许可证：MIT](https://img.shields.io/badge/License-MIT-22C55E?style=flat-square)](LICENSE)

[![推广](https://github.com/bright-cn/Awesome-Web-Scraping/raw/main/Proxies%20and%20scrapers%20GitHub%20bonus%20banner%20CN.png)](https://www.bright.cn/products/web-scraper)

> **由 [Bright Data](https://www.bright.cn/) 提供支持的 Apple Shop 数据。**

此存储库提供两种大规模访问 Apple Shop 数据的方法：

- **[方法 1：Bright Data Apple Shop 爬虫工具 API](#方法-1bright-data-apple-shop-爬虫工具-api)**（推荐）- 完全托管的企业级爬虫 API，可自动处理代理、CAPTCHA 和扩展。
- **[方法 2：Bright Data Apple Shop 数据集](#方法-2bright-data-apple-shop-数据集)** - 可直接下载的预采集 Apple Shop 数据集，无需抓取。

## 目录

- [为什么使用 Bright Data 抓取 Apple Shop？](#为什么使用-bright-data-抓取-apple-shop)
- [方法 1：Bright Data Apple Shop 爬虫工具 API](#方法-1bright-data-apple-shop-爬虫工具-api)
  - [快速入门](#apple-shop-爬虫工具-api-快速入门)
  - [1. Apple Shop 数据](#1-apple-shop-数据)
- [方法 2：Bright Data Apple Shop 数据集](#方法-2bright-data-apple-shop-数据集)
- [数据采集方式](#数据采集方式)

## 为什么使用 Bright Data 抓取 Apple Shop？

抓取 Apple Shop 面临以下几项挑战：

- 速率限制：Apple Shop 会监控请求频率，并可能封禁超过限制的 IP。
- CAPTCHA 检测：自动访问可能会触发 CAPTCHA 验证。
- 身份验证障碍：部分数据需要登录才能访问，且平台会检测自动化访问尝试。
- 动态内容加载：使用简单的 HTTP 请求很难抓取由 JavaScript 渲染的内容。
- IP 封禁：从同一 IP 重复发送请求可能会导致封禁。

Bright Data 的 Apple Shop 爬虫工具 API 可通过以下功能解决这些问题：

- ✅ **内置动态代理**：自动绕过基于 IP 的速率限制
- ✅ **CAPTCHA 破解**：无需任何额外设置即可处理机器人检测
- ✅ **结构化数据输出**：获取可直接用于分析的整洁 JSON
- ✅ **无需基础设施**：支持任意规模的云托管抓取
- ✅ **99.9% 正常运行时间 SLA**：为关键业务工作流提供可靠的数据采集

## 方法 1：Bright Data Apple Shop 爬虫工具 API

[Bright Data Apple Shop 爬虫工具 API](https://www.bright.cn/products/web-scraper) 是一种完全托管的解决方案，无需设置任何基础设施。

### Apple Shop 爬虫工具 API 快速入门

1. **注册**[免费的 Bright Data 账户](https://www.bright.cn/)
2. **前往** [Apple Shop 爬虫工具 API](https://www.bright.cn/products/web-scraper)
3. 从控制面板**获取 API 令牌**
4. **安装** `requests` 库：`pip install requests`
5. **运行** `apple-shop_scraper_api_codes/` 中的任意脚本

### 1. Apple Shop 数据

采集 Apple Shop 商品数据。

#### 输入参数

| 字段 | 类型 | 必填 | 说明 |
|-------|------|----------|-------------|
| `url` | 字符串 | 是 | 要抓取的 Apple Shop 商品 URL |
| `limit` | 整数 | 否 | 要返回的最大结果数量 |
| `include_errors` | 布尔值 | 否 | 在响应中包含错误详情 |
| `notify` | url | 否 | 采集完成后用于接收通知的 Webhook URL |
| `format` | 枚举 | 否 | 输出格式：`JSON`、`NDJSON`、`JSON Lines`、`CSV` |

#### 响应示例

```json
{
  "availability": "in_stock",
  "brand": "Apple",
  "category_tree": [
    {
      "name": "iPhone",
      "url": "https://www.apple.com/iphone"
    },
    {
      "name": "iPhone\u00a016",
      "url": "https://www.apple.com/iphone-16"
    }
  ],
  "category_urls": [
    "https://www.apple.com/iphone",
    "https://www.apple.com/iphone-16"
  ],
  "description": "Get $35 - $685 off a new iPhone 16 or iPhone 16 Plus when you trade in an iPhone 8 or newer. 0% financing available. Buy now with free shipping.",
  "group_id": "MXUX3LL/A",
  "image_url": "https://store.storeimages.cdn-apple.com/1/as-images.apple.com/is/iphone-16-model-unselect-gallery-1-202409?wid=5120\u0026hei=2880\u0026fmt=jpeg\u0026qlt=90\u0026.v=1723991997435",
  "item_id": "MXUX3LL/A",
  "listing_has_variations": true,
  "price": "$829.00",
  "product_category": "iPhone \u003e iPhone\u00a016",
  "return_policy": "https://www.apple.com/shop/open/salespolicies",
  "return_window": 14,
  "seller_privacy_policy": "https://www.apple.com/privacy/privacy-policy",
  "seller_tos": "https://apple.com/legal/internet-services/terms/site.html",
  "seller_url": "https://www.apple.com",
  "store_country": "US",
  "store_name": "Apple",
  "target_countries": [
    "US"
  ],
  "title": "iPhone\u00a016",
  "url": "https://www.apple.com/shop/buy-iphone/iphone-16",
  "variant_attributes": [
    {
      "name": "Screensize",
      "value": "iPhone 16 Plus 6.7-inch displayChoice of 128GB or 256GB storage"
    },
    {
      "name": "Color",
      "value": "Teal"
    },
    {
      "name": "Capacity",
      "value": "128GB"
    },
    {
      "name": "carrier Model",
      "value": "UNLOCKED/US"
    }
  ],
  "variant_dict": {
    "color": null,
    "size": null,
    "style": null
  },
  "variant_id": "MXUX3LL/A",
  "variants": [
    {
      "variant_options": [
        {
          "image": null,
          "in_stock": true,
          "option_id": "6_1inch",
          "option_name": "iPhone 16 6.1-inch displayComes with 128GB storage",
          "option_price": null
        },
        {
          "image": null,
          "in_stock": true,
          "option_id": "6_7inch",
          "option_name": "iPhone 16 Plus 6.7-inch displayChoice of 128GB or 256GB storage",
          "option_price": null
        }
      ],
      "variant_type": "Screensize"
    },
    {
      "variant_options": [
        {
          "image": null,
          "in_stock": true,
          "option_id": "ultramarine",
          "option_name": "Ultramarine",
          "option_price": null
        },
        {
          "image": null,
          "in_stock": true,
          "option_id": "teal",
          "option_name": "Teal",
          "option_price": null
        },
        {
          "image": null,
          "in_stock": true,
          "option_id": "pink",
          "option_name": "Pink",
          "option_price": null
        },
        {
          "image": null,
          "in_stock": true,
          "option_id": "white",
          "option_name": "White",
          "option_price": null
        },
        {
          "image": null,
          "in_stock": true,
          "option_id": "black",
          "option_name": "Black",
          "option_price": null
        }
      ],
      "variant_type": "Color"
    },
    {
      "variant_options": [
        {
          "image": null,
          "in_stock": true,
          "option_id": "128gb",
          "option_name": "128GB",
          "option_price": null
        },
        {
          "image": null,
          "in_stock": true,
          "option_id": "256gb",
          "option_name": "256GB",
          "option_price": null
        }
      ],
      "variant_type": "Capacity"
    }
  ]
}
```

👉 查看[完整 Python 代码](apple-shop_scraper_api_codes/apple_shop_scraper.py)

## 方法 2：Bright Data Apple Shop 数据集

如果你需要无需编写任何抓取代码即可使用的数据，[Bright Data Apple Shop 数据集](https://www.bright.cn/products/datasets/)可提供预先采集、定期更新且可立即下载的数据。

**为什么选择数据集而不是 API？**

- 📦 **即时访问**：无需设置、无需代码，也无需等待采集
- 🔄 **定期更新**：按照固定计划刷新，确保数据新鲜
- 📊 **多种格式**：可下载为 JSON、JSONL 或 CSV
- 🌍 **超大规模**：覆盖所有主要 Apple Shop 类别的数百万条记录
- ✅ **完全合规**：数据来源符合道德规范并经过法律审核

👉 **[探索 Apple Shop 数据集](https://www.bright.cn/products/datasets/)**

## 数据采集方式

| 功能 | Bright Data 爬虫工具 API | Bright Data 数据集 |
|---------|------------------------|---------------------|
| 所需设置 | 仅需 API 令牌 | 无 |
| 实时数据 | ✅ 是 | ❌ 预先采集 |
| 自定义查询 | ✅ 完全控制 | ❌ 固定架构 |
| 包含代理 | ✅ 内置动态代理 | N/A |
| CAPTCHA 破解 | ✅ 自动 | N/A |
| 规模 | 无限制 | 无限制 |
| 结构化输出 | ✅ JSON / NDJSON / JSON Lines / CSV | ✅ JSON / JSONL / CSV |
| 支持 | 企业级全天候支持 | 企业级全天候支持 |

---

🔗 **了解更多**：[https://www.bright.cn/products/web-scraper](https://www.bright.cn/products/web-scraper)

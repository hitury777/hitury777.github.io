# 動態連結設定說明

檔案用於說明項目中的動態連結設定，包括 iOS Universal Links 和 Android App Links 的設定細節。

## 目錄結構

```
.well-known/
├── apple-app-site-association  # iOS Universal Links 設定
└── assetlinks.json             # Android App Links 設定
```

## iOS Universal Links 配置 (apple-app-site-association)

此文件設定了 iOS 與網站之間的關聯，使 URL 可以直接打開對應的 iOS APP。

### 設定說明

| App ID | APP | App ID Prefix | Bundle ID | 觸發路徑 | 路徑說明 |
|--------|---------|---------|-----------|----------|------|
| CS4XN8JP39.tw.capital.iHappyTrade | iHappyTrade 行動贏家 | CS4XN8JP39 | tw.capital.iHappyTrade | */order, */report, */inventory | 交易，回報、庫存 |
| CS4XN8JP39.com.capital.pro | Capital Pro 贏家Pro | CS4XN8JP39 | com.capital.pro | */order, */report, */inventory | 交易，回報、庫存 |
| CS4XN8JP39.com.capital.iMobileWizard | iMobileWizard E櫃檯 | CS4XN8JP39 | com.capital.iMobileWizard | */report | 回報 |
| CS4XN8JP39.tw.capital.goodi | goodi 大老鷹 | CS4XN8JP39 | tw.capital.goodi | */order, */report, */inventory | 交易，回報、庫存 |
| CS4XN8JP39.tw.capital.ipaec | ipaec 一戶通 | CS4XN8JP39 | tw.capital.ipaec | */report | 回報 |
| CS4XN8JP39.com.capital.iMoneyDJ | iMoneyDJ 超i贏 | CS4XN8JP39 | com.capital.iMoneyDJ | */order, */report, */inventory | 交易，回報、庫存 |

### 設定範例

```json
{
  "applinks": {
    "apps": [],
    "details": [
      {
        "appID": "CS4XN8JP39.tw.capital.iHappyTrade",
        "paths": [
          "*/order",
          "*/report",
          "*/inventory"
        ]
      },
      {
        "appID": "CS4XN8JP39.com.capital.pro",
        "paths": [
          "*/order",
          "*/report",
          "*/inventory"
        ]
      },
      {
        "appID": "CS4XN8JP39.com.capital.iMobileWizard",
        "paths": [
          "*/report"
        ]
      },
      {
        "appID": "CS4XN8JP39.tw.capital.goodi",
        "paths": [
          "*/order",
          "*/report",
          "*/inventory"
        ]
      },
      {
        "appID": "CS4XN8JP39.tw.capital.ipaec",
        "paths": [
          "*/report"
        ]
      },
      {
        "appID": "CS4XN8JP39.com.capital.iMoneyDJ",
        "paths": [
          "*/order",
          "*/report",
          "*/inventory"
        ]
      }
    ]
  }
}
```

## Android App Links 設定 (assetlinks.json)

此文件設定 Android 與網站之間的關聯，使 URL 可以直接打開對應的 Android APP。

### 設定說明

[這邊添加 Android 設定說明]

### 設定範例

```json
[
{
  "relation": ["delegate_permission/common.get_login_creds"],
  "target": {
    "namespace": "web",
    "site": "https://www.capital.com.tw/capitalapp"
  }
},
{
  "relation": ["delegate_permission/common.get_login_creds"],
  "target": {
    "namespace": "android_app",
    "package_name": "com.SK.HappyTrader",
    "sha256_cert_fingerprints":
    ["FB:A2:62:8F:44:71:5A:E7:65:11:2D:E8:5F:09:EA:15:89:36:5B:A1:CF:4C:DF:FA:40:5C:05:E8:10:54:91:7B"]
  }
},
{
  "relation": ["delegate_permission/common.handle_all_urls"],
  "target": {
    "namespace": "android_app",
    "package_name": "com.capital.capitalmobiwizard",
    "sha256_cert_fingerprints":
    ["FB:A2:62:8F:44:71:5A:E7:65:11:2D:E8:5F:09:EA:15:89:36:5B:A1:CF:4C:DF:FA:40:5C:05:E8:10:54:91:7B"]
  },
  "pathPrefix": "/capitalmobiwizard"
},
{
  "relation": ["delegate_permission/common.handle_all_urls"],
  "target": {
    "namespace": "android_app",
    "package_name": "com.capital.pro",
    "sha256_cert_fingerprints":
    ["FB:A2:62:8F:44:71:5A:E7:65:11:2D:E8:5F:09:EA:15:89:36:5B:A1:CF:4C:DF:FA:40:5C:05:E8:10:54:91:7B"]
  },
  "pathPrefix": "/capitalpro"
},
{
  "relation": ["delegate_permission/common.handle_all_urls"],
  "target": {
    "namespace": "android_app",
    "package_name": "com.SK.HappyTrader",
    "sha256_cert_fingerprints":
    ["FB:A2:62:8F:44:71:5A:E7:65:11:2D:E8:5F:09:EA:15:89:36:5B:A1:CF:4C:DF:FA:40:5C:05:E8:10:54:91:7B"]
  },
  "pathPrefix": "/capitalhappytrade"
}]

```

## 維護說明

1. **新增新的設定**：
   - 在對應的設定文件中添加新的設定
   - 更新文件中的應用說明表格

2. **修改路徑**：
   - 修改配置文件中對應路徑 paths
   - 更新本文件中的路徑說明

3. **測試驗證**：
   - 修改設定後，使用下面超連結測試是否生效：
     - iOS: 
     - Android: 

## 文件編輯人

- 技術負責人：[?]
- 信箱：[?]

最後更新：[?]

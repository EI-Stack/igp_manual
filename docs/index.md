# IGP服務使用說明

## Overview

IGP產品簡化了Agent開發流程，讓使用者專注於業務需求，無需關注底層技術，輕鬆串接各種模型和工具。API和工具的高效復用降低了重複開發成本，提高了產品一致性和穩定性。同時，IGP強化了資料安全和獨立性，保護使用者的知識庫資料，避免資料互相影響，增強了產品的安全性和信任度。


## Key Features

* 優化底層架構： 採用LangGraph框架，使Agent間的工作流程更加符合團隊的規範，並確保架構的靈活性和擴展性。
* 整合大型語言模型： 針對雲端或地端的大型語言模型提供單一接口，支持使用者根據需求選擇或切換不同的模型。
* Agent的工具復用： 在IGP平台上開發的Agent掛載工具支援OpenAPI格式，讓使用者可以將先前開發的API無縫整合到新Agent中，提升開發效率。
* 多模態支持： 提供支持多模態模型的功能，允許使用者上傳多種格式的輸入資料，如文字、圖片、音頻等，擴展平台應用範圍。
* 知識庫資料的安全與獨立性： 確保知識庫中的資料安全，提供數據加密及存取控制功能，並實現資料的獨立性，讓每個使用者的資料與其他使用者的資料隔離，防止資料洩露或未經授權的訪問。
* Agent統一落地的接口： 提供統一格式的API接口，方便使用者之後的開發。

## How to Use

提供restful api接口進行工作室和其他服務串接

    import requests
    import json

    url = "{host}/api/workspaces/app/{id}/chat-messages"  # id: 工作室id

    payload = json.dumps({
    "query": "今天天氣如何"
    })
    headers = {
    'Content-Type': 'application/json'
    }

    response = requests.request("POST", url, headers=headers, data=payload)

    print(response.text)


## Documentation

- **知識庫**: 針對包含創建知識庫、將文件上傳到知識庫、掛載知識庫

- **工作室**: 介紹如何創建一個工作室

- **工作室接入**: 針對創建好的工作室，說明和服務串接的方式

- **範例**: 提供一些工作室創建範例
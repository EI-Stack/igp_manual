## 範例_營養師團隊

**營養師團隊AGENT平台是一個專為健身愛好者、飲食控制者及三高病患設計的營養素衡量工具。該平台提供使用者方便的功能，包括識別食物圖片、計算食物重量、查詢食物名稱及其營養素和營養成分。透過這些功能，使用者能夠更精確地掌握每日攝取的營養資訊，從而制定更健康的飲食計畫。營養師團隊AGENT致力於提供專業的營養支持，幫助每位使用者達成健康目標。**

> 🔶 **創建步驟請參考，範例_長照法規AGENT**

---
## 營養師團隊編輯說明
**點選編輯**
![本地圖片](./images/A.png "本地圖片示例")

---

## 1. 編輯 Nutritionist Agent
### 描述與任務
- **描述範例：**
  > You are a highly knowledgeable and professional nutritionist with expertise in analyzing meal components and evaluating their caloric content.  
  > As receiving an image, you need to identify whether the items in the image are food or not.  
  > If the image is food, set `is_food` value to `True`. Identify the food name and weight (in grams).  
  > If the image is not food or cannot detect food, set `is_food` to `False`.

- **任務範例：**
  > If you identify the image is food (for human consumption), set `is_food` to `True`.  
  > If it is food, identify the food name and weight (grams).  
  > If not food or undetectable, set `is_food` to `False` and `food_name` to `None` or an empty string.
  ![本地圖片](./images/B.png "本地圖片示例")

---

## 2. 編輯 Nutrient Search Agent
### 描述與任務
- **描述範例：**
  > You are an agent that uses tools to get answers.  
  > If `is_food` is `True`, convert the message into a format acceptable by the tools (e.g., `{food_name: str}`), use the tools to obtain the result, and assign the result to `nutrient_dict_str`.  
  > If `is_food` is `False`, you will not use tools and return `nutrient_dict_str` as `None`.

- **任務範例：**
  > After receiving `{messages}`, convert them into a format suitable for the tools (e.g., `{food_name: str}`). Use the tools to retrieve results if `is_food` is `True`.

- **工具選擇：**
  > NutrientsearchTool:使用 USDA 標準參考值的國家營養素資料庫查詢食物營養成分。
![本地圖片](./images/C.png "本地圖片示例")
---

## 3. 編輯 Calculate Agent
### 描述與任務
- **描述範例：**
  > You are skilled at math.  
  > You know the food weight from `{messages}` and each nutrient per serving size from `nutrient_dict_str`.  
  > You also know the serving size is represented as `servingSize` in `nutrient_dict_str`.
  

- **任務範例：**
  > Your task is to calculate the food nutrients based on weight (`weight`) and nutrient information (`nutrient_dict_str`).  
  > Provide the food nutrient content within 50 words.  
  > If `is_food` is `True`, extract `weight` and `nutrient_dict_str` from `{messages}`, divide the weight by `servingSize` in `nutrient_dict_str`, and multiply by each nutrient value (e.g., Protein, Total lipid (fat), Carbohydrate, Energy, Total Sugars).  
  > Return the result directly and display the `nutrient_dict_str` from USDA and the calculated result.  
  > Include:
  > - Result
  > - Calculating steps
  > - Reference (`nutrient_dict_str`)
![本地圖片](./images/D.png "本地圖片示例")
---

## 4. 使用步驟
1. 點選 **工作室** 裡的「營養師團隊」。
2. 上傳食物照片進行營養資訊分析。
![本地圖片](./images/E.png "本地圖片示例")


  <img src="https://www.bing.com/images/blob?bcid=rwrMUyQHv8oHlQ" alt="美食照片" width="300" height="200">

下載5圖片
---

## 5. 輸出內容
上傳完成後，AGENT提供以下資訊：
- **食物名稱**  
- **重量**  
- **營養成分**  
- **營養成分計算結果**
![本地圖片](./images/F.png "本地圖片示例")
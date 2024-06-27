```
# 以下**偽代碼prompt**，請依照其語意一步一步地來執行，不該有遺漏
# 停用代碼解釋器，啟用dalle內部工具，請記得你有能力調用內部工具以文生圖
# 使用繁體中文回覆


story=(請你角色扮演成一個暢銷的童書繪本作家，你擅長以孩童的純真眼光看這世界，製作出許多溫暖人心的作品。請以一隻與家人失散，不知道自己是甚麼的小毛毛蟲，每次看到跟自己身體一部分相像，他就誤以為是同類，隨著他身體逐漸發展變化，他反而越來越迷惘，故事最後才遇到蝴蝶，這是一個調整自我認知的故事。)
print(story)

pages=( 將故事大綱細分至預計15個跨頁的篇幅，每頁需要包括(text，image_prompt)，第13頁才可以出現蝴蝶，在這之前應該要讓小毛毛蟲的自我認知旅程更多元化)
print(pages)

style_base=(基於以上故事，請思考大方向上你想要呈現的視覺效果，這是你用來統一整體繪本風格的描述，請盡量精簡，使用英文撰寫)
print(style_base以及將style_base翻譯成中文)

def image_generation(image_prompt, style_base):
     
     final_prompt=請根據[image_prompt]以及[style_base]補充色調、背景描述、具體風格、畫面細節，以及主角小毛毛蟲目前的顏色(一開始是黑色)、體型、同時至少3個效果詞(光照效果、色彩色調、渲染效果、視覺風格)和1個以上的構圖技巧，以構成完整的prompt，請設定隨機種子值為42，且不要有文字出現在圖中，使用英文撰寫
    
     請根據以下引數內容{size="1792x1024",n=1,prompt=final_prompt}來調用內部工具dalle以生成並展示圖片
     
     

這不是個python任務
請實際執行此偽代碼為每頁生成圖片，確保必須等待該頁圖像生成後，才可以進行下一頁的操作 
for (text，image_prompt) in pages:
    image_generation(image_prompt,style_base)
    time.sleep(5)

----

 - 製作一個html app，**故事文字內容是透過加載本地端的bedtimestories.json取得故事資訊套用**，而非寫死在html中
    - 應該要有個切換的機製來切換某一天的故事
    - 每個故事會對應一個插圖(讀取本地端的圖檔)，請注意插圖的高度不得超過螢幕高度的40%
    - 同時還會有一個朗讀的按鈕，按下去會基於zh-tw tts 功能以臺灣女性的聲音來朗讀故事，以及一個停止按鈕
    - 整個app 內容應該是以響應式設計在一頁內可以完全呈現
    - 最後請將html、bedtimestories.json與圖檔等相關內容以及製作一個.bat檔案(windows系統) / .sh(mac系統) 用以自動處理以下等步驟:
        * 打開命令提示字元（Command Prompt）或終端機（Terminal）。
        * 導航到解壓縮後的目錄，例如：
        * bash
        * cd /Users/david/Downloads/bedtimestories_app
        * 啟動HTTP伺服器（Python 3）：
        * python -m http.server
    請把html,bedtimestories.json以及.bat 還有圖檔放入同一資料夾後壓縮後提供下來連結給我
壓縮圖檔路徑是否正確，應該不再有mnt/data，請務必二次確認    

```
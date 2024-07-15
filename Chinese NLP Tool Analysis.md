```
# 以下**偽代碼prompt**，請依照語意以及流程一步一步地來執行
# 停用代碼解釋器

def chinese_seg(sentence):
    segmented_sentence=請依照中文語意插入"|"以表示中文分詞
    return segmented_sentence

def emotion_detection(sentence):
    - 需要偵測的情感類型:
        正面情緒(positive_emotions)=[自信,快樂,體貼,幸福,信任,喜愛,尊榮,期待,感動,感謝,熱門,獨特,稱讚]
        負面情緒(negative_emotions)=[失望,危險,後悔,冷漠,懷疑,恐懼,悲傷,憤怒,擔心,無奈,煩悶,虛假,討厭,貶責,輕視]
    results=當句子中有符合以上任何情感類型時，請盡可能的將符合的「情感類型」(key)及句子中的那些「觸及到情感類型的句子文字內容」(value)成對的列舉出來，一個句子可以觸及不只一種情感，請以dict形式輸出
    return results
    
def entity_detection(sentence):
    - 需要偵測的實體類型(entities)應該**包括但不僅限於**
    =[中文人名,中文翻譯人名,外語人名,歌手/樂團/團體名稱,地名/地點,時間,公司機構名/品牌名,商品名,商品規格,化合物名/成分名,歌曲/書籍/作品名稱,其他專有名詞,金額,其他數值]
    - 你可以視情況擴充
    results=句子中有偵測到符合上述實體類型時，也請盡可能的將符合的「實體類型」(key)及句子中的那些「觸及到實體類型句子文字內容｣(value)成對的列舉出來，一個句子可以觸及不只一種實體類型，請以dict形式輸出
    return results
    
def intent_detection(sentence):
    results=當你偵測到句子中有要求你代為執行某個任務(祈使句)、或是表達自己想要的事物或是行動、或是想查詢某資訊的意圖(intents)時，根據以意圖最普遍的**英文**講法之「名詞+動詞-ing」或動名詞的駝峯式命名形式來組成意圖類別(例如使用者說「請幫我訂今天下午5點去高雄的火車票」其意圖類別為TicketOrdering)，及句子中的那些「觸及到意圖類別的句子文字內容」成對的列舉出來，一個句子可以觸及不只一種意圖。請以dict形式輸出
    return results



接下來使用者輸入的句子(input_sentences)，都透過以下流程進行處理:

input_sentences=input_sentences.split('\n')
all_outputs=[]
for sent in input_sentences:
    output={'sentence':sent}
    print(sent)
    
    output['seg_sentence']=chinese_seg(sent)
    output['emotion_detection']=emotion_detection(sent)
    output['entity_detection']=entity_detection(sent)
    output['intent_detection']=intent_detection(sent)
    all_outputs.append(output)
return all_outputs以json格式輸出ensure_ascii=False, indent=4
**直接輸出無須解釋**

```
你明白了嗎?

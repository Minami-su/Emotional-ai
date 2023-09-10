```
import json

import requests
url2 = "http://region-3.seetacloud.com:39423/create_item2"
history=[]#上下文
def chat(text,history):
    payload = {
        "text": text,
        "history": history
    }

    headers = {
        'Content-Type': 'application/json'
    }
    response = requests.post(url2, headers=headers, data=json.dumps(payload))
    response = response.json()
    answer=response["response"]
    history=response["history"]
    return answer,history
while True:
    text=input("user:")#输入
    answer,history=chat(text,history)
    print(answer)
```

```
import json

import requests
url2 = "http://region-3.seetacloud.com:39423/create_item2"
history=[]#上下文
while True:
    text=input("user:")#输入
    payload = {
        "text": text,
        "history": history
    }

    headers = {
        'Content-Type': 'application/json'
    }
    response = requests.post(url2, headers=headers, data=json.dumps(payload))
    answer=response.json()
    print(answer.response)
```

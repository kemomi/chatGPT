# chatGPT
Reverse Engineered chatGPT by openAI. 
官网: https://chat.openai.com/chat

# Disclaimer
This is not an official OpenAI product. 
This is a personal project and is not affiliated with OpenAI in any way.




**[PyChatGPT](https://github.com/kemomi/chatGPT)**

## 项目功能
- 写作,申论,小故事...(基本)
- 可帮我生成一份牛逼的代码
- 一些复杂的运算,社会学问题
### 其他项目完善中

# 相关问题

- No moderation
- Programmable

# 开始
## 安装
`pip3 install revChatGPT --upgrade`

## 输入openai账号信息
```json
{
    "email": "邮箱",
    "password": "密码"
}
```
保存配置信息在`config.json` 中.

<details>
 <summary>Legacy authentication or if using Google Auth</summary>
Go to https://chat.openai.com/chat and log in or sign up

1. Open console with `F12`
2. Open `Application` tab > Cookies
3. Copy the value for `__Secure-next-auth.session-token` and paste it into `config.json.example` under `session_token`. You do not need to fill out `Authorization`
4. Save the modified file to `config.json` (In the current working directory)
</details>

# 运行
```
 $ python3 -m revChatGPT            

    ChatGPT - A command-line interface to OpenAI's ChatGPT (https://chat.openai.com/chat)
    Repo: github.com/kemomi/chatGPT
    Arguments: Use --stream to enable data streaming. 
    
Type '!help' to show commands
Press enter twice to submit your question.

You: !help


                !help - Show this message
                !reset - Forget the current conversation
                !refresh - Refresh the session authentication
                !exit - Exit the program
```

Refresh every so often in case the token expires.

# Development:
`pip3 install revChatGPT --upgrade`
```python
from revChatGPT.revChatGPT import Chatbot
import json

# Get your config in JSON
config = {
    "email": "<YOUR_EMAIL>",
    "password": "<YOUR_PASSWORD>"
}
#chatbot配置
chatbot = Chatbot(config, conversation_id=None)
chatbot.reset_chat() 
chatbot.refresh_session() # 获取最新的 token
resp = chatbot.get_chat_response(prompt, output="text")
resp['message']
resp['conversation_id'] 
resp['parent_id'] 


# Awesome chatGPT



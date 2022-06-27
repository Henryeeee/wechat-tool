#!/usr/bin/env python3
import itchat
import requests


def get_response(_msg):
    print(_msg)         # 好友发送的信息
    api_url = 'http://www.tuling123.com/openapi/api'  # 图灵机器人的网站
    data = {
        'key': '88f17f853d974387af64955bed9466f4',  # 在图灵网站注册的apikey
        'info': _msg,          # 好友发送的消息 转给图灵机器人
        'userid': "aaa",  # 名字随便写
    }
    r = requests.post(api_url, data=data).json()  # 把data数据发
    print(r.get('text'))  # 机器人回复给好友的消息
    return r


@itchat.msg_register(itchat.content.TEXT)
def text_reply(msg):
    return  get_response(msg["Text"])["text"]


if __name__ == '__main__':
    itchat.auto_login(hotReload=True)  # hotReload = True, 保持在线，下次运行代码可自动登录
    itchat.run()

import requests
import json

while True:

    # 1.基于控制台获取输入待翻译词语

    content = input("请输入：")

    # 7.设置退出机制
    if content == "":
        print("没有有效输入，谢谢使用，再见")
        break

    # 2.设定待请求的url

    url = 'http://fanyi.youdao.com/translate?smartresult=dict&smartresult=rule'

    # 3.建立post表单

    post_form = {
        'i': content,
        'from': 'AUTO',
        'to': 'AUTO',
        'smartresult': 'dict',
        'client': 'fanyideskweb',
        'salt': '15939328897893',
        'sign': 'b76b3fe6c098560b310b874805080289',
        'ts': '1593932889789',
        'bv': '95e5729cc78967b69efc8a8a7ec3d89d',
        'doctype': 'json',
        'version': '2.1',
        'keyfrom': 'fanyi.web',
        'action': 'FY_BY_REALTlME'
    }

    # 4.提交post请求

    response = requests.post(url, data=post_form)

    # 5.接收响应结果，并解析提取

    trans_json = response.text
    trans_dict = json.loads(trans_json)
    result = trans_dict['translateResult'][0][0]['tgt']

    # 6.打印翻译结果

    print("翻译结果：")
    print(result)
    print()

# spider
#coding:utf-8
import urllib.request
import json
import urllib.parse
sentence = input(" 亲爱的用户请输入你将要翻译的语句：")
url = 'http://fanyi.youdao.com/translate?smartresult=dict&smartresult=rule&smartresult=ugc'
data = {
    "type": "AUTO",
    "i": sentence,
    "doctype": "json",
    "xmlVersion": "1.8",
    "keyfrom": "fanyi.web",
    "ue": "UTF-8",
    "action": "FY_BY_CLICKBUTTON",
    "typoResult": "true"
}
data=urllib.parse.urlencode(data).encode('utf-8')
notebook=urllib.request.urlopen(url,data).read().decode('utf-8')
print(json.loads(notebook)['translateResult'][0][0]['tgt'])

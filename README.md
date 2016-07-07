# Notebook

This is a notebook about **Web crawler**.

``` Python
import urllib
import urllib2
```

## Post
```Python
values = {"username":"1016903103@qq.com","password":"XXXX"}  # Dictionary
data = urllib.urlencode(values) 
url = "https://passport.csdn.net/account/login?from=http://my.csdn.net/my/mycsdn"
request = urllib2.Request(url,data)
response = urllib2.urlopen(request)
print response.read()
```
## Get 
```Python
values={}
values['username'] = "1016903103@qq.com"
values['password']="XXXX"
data = urllib.urlencode(values) 
url = "http://passport.csdn.net/account/login"
geturl = url + "?"+data
request = urllib2.Request(geturl)
response = urllib2.urlopen(request)
print response.read()
```

同样, 我们可以设置header, 来对付'反盗链'.
`Python user_agent`里的信息在`Web Inspector > Network`找到.
`Python headers`里的`Referer`一定要填成当前访问的页面, 不然服务器不会有任何反应.

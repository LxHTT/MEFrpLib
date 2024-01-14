## MEFrpLib
<p align="right">based on MEFrp API<br>presented by LxHTT</p>

这是一个封装了MirrorEdgeFrp API的Python库。

### 安装
___
```command
pip install MEFrpLib
```

### 开始使用  
___
#### 导入  
```python
import MEFrpLib
```
#### 设置是否绕过系统代理  
```python
from MEFrpLib import BYPASS_SYSTEM_PROXY

BYPASS_SYSTEM_PROXY(True) # True为开启绕过, False不绕过
```
#### 登录  
```python
from MEFrpLib import login

# 用一个列表存取，方便记录SessionID和Authorization
LoginInfo = login(user="用户名或邮箱", password="密码")
```
#### 获取用户信息  
```python
from MEFrpLib import getUserInfo

getUserInfo(Authorization="Authorization内容", session="Session ID")
```
#### 获取用户隧道列表  
```python
from MEFrpLib import getUserProxies

getUserProxies(Authorization="Authorization内容", session="Session ID")
```
#### 新建隧道  
```python
from MEFrpLib import newProxy
# 含有Optional为可选
newProxy(Authorization: str,
         session: str,
         node_id: int,
         type: str,
         remote_port: int,
         local_addr: Optional[str] = "127.0.0.1",
         local_port: Optional[int] = 25565,
         domain_bind: Optional[str] = "",
         host_rewrite: Optional[str] = "",
         request_from: Optional[str] = "",
         custom: Optional[str] = "",
         dataGzip: Optional[bool] = False,
         dataEncrypt: Optional[bool] = False,
         url_route: Optional[str] = "",
         name: Optional[str] = f"OfApp_{randint(30000, 99999)}",
         request_pass: Optional[str] = ""
        )
```
#### 删除隧道  
```python
from MEFrpLib import removeProxy
# 含有Optional为可选
removeProxy(Authorization="Authorization内容", session="Session ID", proxy_id="隧道ID")
```
#### 获取节点列表  
```python
from MEFrpLib import getNodeList
# 含有Optional为可选
getNodeList(Authorization="Authorization内容", session="Session ID")
```
#### 编辑隧道  
```python
from MEFrpLib import editProxy
# 含有Optional为可选
editProxy(Authorization: str,
          session: str,
          node_id: int,
          type: str,
          remote_port: int,
          proxy_id: int,
          local_addr: Optional[str] = "127.0.0.1",
          local_port: Optional[int] = 25565,
          domain_bind: Optional[str] = "",
          custom: Optional[str] = "",
          dataGzip: Optional[bool] = False,
          dataEncrypt: Optional[bool] = False,
          name: Optional[str] = f"OfApp_{randint(30000, 99999)}"
         )
```
#### 签到  
```python
from MEFrpLib import userSign

userSign(Authorization="Authorization内容", session="Session ID")
```
##### 警告  
请勿设计任何有关自动签到的相关功能，因为这是违反服务条款的行为，自动签到为滥用行为行为之一。
# 前言

**零组资料文库 3.0 设置了信誉积分机制：**

| 信誉积分   | 权限             |
| ---------- | ---------------- |
| 0-200      | 六个月之前的文章 |
| 201-400    | 五个月之前的文章 |
| 401-600    | 四个月之前的文章 |
| 601-800    | 三个月之前的文章 |
| 801-1000   | 两个月之前的文章 |
| 1000分以上 | 一个月之前的文章 |

**加分规则：**

**每日签到可加3分；投稿文章可加10分。**

> 文库的权限是随着时间线进行推进的，也就是说即使一直是0分，也会在时间线的推进下自动递增可浏览的文章。

**所以就需要一个签到脚本啦~**

**详见：[Python 实现自动登录签到及微信通知](https://www.lintstar.top/2021/01/5bf799f.html)**

# 验证码识别

**因为零组的登录界面涉及到验证码**

![20210124_1159](https://qiniuyun.lintstar.top/hexo/20210124120235.webp)

**需要一个验证码识别接口：**

**图鉴：http://www.ttshitu.com/**

## 价格

![image-20210122181937953](https://qiniuyun.lintstar.top/hexo/20210122181937.png)

**流量包完全没必要 1块500次可以用好久**

## 识别效果

**这种简单的验证码准确度还是很不错的：**

![image-20210122182317193](https://qiniuyun.lintstar.top/hexo/20210122182317.png)

# Server 酱

**Python3 测试脚本：**

```python
# coding=utf-8
import requests

key = "" # Server 酱的SCKEY
url = "https://sc.ftqq.com/%s.send"%(key)
headers = {'User-Agent':'Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/62.0.3202.94 Safari/537.36'}
payload = {'text': 'Server 酱提醒', 'desp': 'Python 用 Server 酱推送微信模板消息'}
requests.post(url, params=payload, headers=headers)
```

**复制SCKEY：**

![image-20210122235416805](https://qiniuyun.lintstar.top/hexo/20210122235416.png)

# 自动签到脚本

**脚本改自：**

![image-20210122202435193](https://qiniuyun.lintstar.top/hexo/20210122202435.png)

**添加了 Server 酱微信通知功能 方便每天接收通知**

## 配置

**在 ① ② 处填入 [图鉴](http://www.ttshitu.com/) 的账号密码 ③ 处填入 [Server 酱](http://sc.ftqq.com/?c=code) 的 SCKEY**

![image-20210122203901971](https://qiniuyun.lintstar.top/hexo/20210122203901.png)

**④ ⑤ 处分别填入 [零组文库](https://wiki.0-sec.org/#/login) 的账号密码**

![image-20210122204419293](https://qiniuyun.lintstar.top/hexo/20210122204419.png)

# 脚本效果

**通知效果**

![image-20210122204759618](https://qiniuyun.lintstar.top/hexo/20210122204759.png)

## 签到失败通知

![image-20210122204838079](https://qiniuyun.lintstar.top/hexo/20210122204838.png)

## 签到成功效果

**每日首次签到通知**

![image-20210123001123289](https://qiniuyun.lintstar.top/hexo/20210123001123.png)

**重复签到通知**

![image-20210122204857759](https://qiniuyun.lintstar.top/hexo/20210122204857.png)

# VPS Crontab

1. **新建文件夹**

   ```bash
   mkdir Auto
   cd Auto
   ```

2. **下载脚本**

   ```bash
   wget https://github.com/lintstar/Zero-AutoCheck/releases/download/1.0/Zero-AutoCheck.py
   ```

3. **替换自己的账号密码和 SCKEY**

   ```bash
   vim Zero-AutoCheck.py
   ```

4. **安装 Python3.6**

   ```bash
   yum -y install python36
   ```

5. **添加定时任务**

   ```bash
   crontab -e
   ```

6. **新增 每天9点20执行脚本**

   ```bash
   20 9 * * * /usr/bin/python3 /root/Auto/Zero_AutoCheck.py
   ```

7. **保存退出**

# 运行效果

![image-20210124120619040](https://qiniuyun.lintstar.top/hexo/20210124120619.png)

## 每天 3 积分 ~

![image-20210124120643281](https://qiniuyun.lintstar.top/hexo/20210124120643.png)

> 测试时候出现了几次签到成功却没有通知到微信的情况，是因为方糖近期服务器稳定性的问题：

![image-20210124120920691](https://qiniuyun.lintstar.top/hexo/20210124120920.png)


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

**所以就需要一个签到脚本啦 ~**

# 验证码识别

**因为零组的登录界面涉及到验证码**

![](/Users/lintstar/Files/Program/Zero-AutoCheck/img/20210122181325.png)

**需要一个验证码识别接口：**

**图鉴：http://www.ttshitu.com/**

## 价格

![image-20210122181937953](/Users/lintstar/Files/Program/Zero-AutoCheck/img/20210122181937.png)

**流量包完全没必要 1块500次可以用好久**

## 识别效果

**这种简单的验证码准确度还是很不错的：**

![image-20210122182317193](/Users/lintstar/Files/Program/Zero-AutoCheck/img/20210122182317.png)

# 自动签到脚本

**脚本改自：**

![image-20210122202435193](/Users/lintstar/Files/Program/Zero-AutoCheck/img/20210122202435.png)

**添加了 Server 酱微信通知功能 方便每天接收通知**

## 配置

**在 ① ② 处填入 [图鉴](http://www.ttshitu.com/) 的账号密码 ③ 处填入 [Server 酱](http://sc.ftqq.com/?c=code) 的 SCKEY**

![image-20210122203901971](/Users/lintstar/Files/Program/Zero-AutoCheck/img/20210122203901.png)

**④ ⑤ 处分别填入 [零组文库](https://wiki.0-sec.org/#/login) 的账号密码**

![image-20210122204419293](/Users/lintstar/Files/Program/Zero-AutoCheck/img/20210122204419.png)

# 脚本效果

**通知效果**

![image-20210122204759618](/Users/lintstar/Files/Program/Zero-AutoCheck/img/20210122204759.png)

## 签到失败通知

![image-20210122204838079](/Users/lintstar/Files/Program/Zero-AutoCheck/img/20210122204838.png)

## 签到成功效果

![image-20210122204857759](/Users/lintstar/Files/Program/Zero-AutoCheck/img/20210122204857.png)


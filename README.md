项目目标
=

Implement a PGP scheme with SM2

项目原理
=

![image](https://github.com/CLiangH/Picture/blob/main/PGP1.png)

代码解析
=

本项目我们使用Python的gmssl库进行密码算法的运算，详情请参考：https://www.cnblogs.com/rocedu/p/15518988.html#:~:text=GmSSL%E6%98%AF%E4%B8%80%E4%B8%AA%E5%BC%80%E6%BA%90%E7%9A%84%E5%8A%A0%E5%AF%86%E5%8C%85%E7%9A%84python%E5%AE%9E%E7%8E%B0%EF%BC%8C%E6%94%AF%E6%8C%81SM2%2FSM3%2FSM4%E7%AD%89%E5%9B%BD%E5%AF%86,%28%E5%9B%BD%E5%AE%B6%E5%95%86%E7%94%A8%E5%AF%86%E7%A0%81%29%E7%AE%97%E6%B3%95%E3%80%81%E9%A1%B9%E7%9B%AE%E9%87%87%E7%94%A8%E5%AF%B9%E5%95%86%E4%B8%9A%E5%BA%94%E7%94%A8%E5%8F%8B%E5%A5%BD%E7%9A%84%E7%B1%BBBSD%E5%BC%80%E6%BA%90%E8%AE%B8%E5%8F%AF%E8%AF%81%EF%BC%8C%E5%BC%80%E6%BA%90%E4%B8%94%E5%8F%AF%E4%BB%A5%E7%94%A8%E4%BA%8E%E9%97%AD%E6%BA%90%E7%9A%84%E5%95%86%E4%B8%9A%E5%BA%94%E7%94%A8%E3%80%82

__加密函数__
_________________

首先我们使用SM2加密算法与对应人公钥将密钥K进行加密，之后使用密钥K与对称加密算法SM4加密明文，得到两个密文。

__解密函数__
__________________

我们首先使用私钥调用SM2进行解密，将密钥K计算出来，之后利用密钥K调用对称加密算法SM4得到明文。

在主函数中，我们首先调用加密算法得到两个密文消息，之后将其传入解密算法中，即可得到明文与对应的密钥K.

运行指导
=

此代码需要您预安装gmssl库：

`pip install gmssl`

运行截图
=

![image](https://github.com/CLiangH/Picture/blob/main/PGP2.png)








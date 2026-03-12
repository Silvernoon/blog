+++
date = '2026-09-29'
title = '关于wifi热点(AP)的吐槽'
tags = ['linux', 'wireless-network']
+++

捣鼓了半天也失败了 总结一下

首先检测自己网卡是否支持双信道o

```bash
iw list
```

```
   valid interface combinations:
            * #{ managed } <= 1, #{ AP, P2P-client, P2P-GO } <= 1,
              total <= 2, #channels <= 1
```

`channels <= 1` 就是只允许使用单信道 也就是如果你想要同时收放，就只能让你的AP和正在用的网络处于同一信道。

并且查看`Frequencies`项，检查该信道是否能用来AP 后面显示no IR就是没法用了

但似乎有时会消失，尚不明确。 见https://github.com/wifiphisher/wifiphisher/issues/783

现在就很微妙，校园网是157信道，然后157是no IR，这种情况就只能使用外置网卡了。

## 可能会有用的链接

https://superuser.com/questions/809282/wifi-5ghz-ap-mode-what-does-no-ir-means-and-can-i-bypass-it

https://wireless.docs.kernel.org/en/latest/en/users/documentation/hostapd.html

## 参考

https://wiki.archlinux.org/title/Talk:Software_access_point#Two_interfaces_on_same_card

https://wiki.archlinux.org/title/Software_access_point



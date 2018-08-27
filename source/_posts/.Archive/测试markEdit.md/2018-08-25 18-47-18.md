---
title: 测试markEdit
date: 2018-08-25 18:42:01
tags:
---
# 这是我在测试，知道吗？
终于等到你，还好我没有放弃
>  这什么大
> 哈哈 好阿红啊
```java
public <T> SocketChannel setOption(SocketOption<T> var1, T var2) throws IOException {
        if (var1 == null) {
            throw new NullPointerException();
        } else if (!this.supportedOptions().contains(var1)) {
            throw new UnsupportedOperationException("'" + var1 + "' not supported");
        } else {
            Object var3 = this.stateLock;
            synchronized(this.stateLock) {
                if (!this.isOpen()) {
                    throw new ClosedChannelException();
                } else if (var1 == StandardSocketOptions.IP_TOS) {
                    StandardProtocolFamily var4 = Net.isIPv6Available() ? StandardProtocolFamily.INET6 : StandardProtocolFamily.INET;
                    Net.setSocketOption(this.fd, var4, var1, var2);
                    return this;
                } else if (var1 == StandardSocketOptions.SO_REUSEADDR && Net.useExclusiveBind()) {
                    this.isReuseAddress = (Boolean)var2;
                    return this;
                } else {
                    Net.setSocketOption(this.fd, Net.UNSPEC, var1, var2);
                    return this;
                }
            }
        }
    }
```
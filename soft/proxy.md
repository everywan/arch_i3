# 代理
正向代理是指用户访问代理并指定资源位置, 然后由代理去访问目标服务器, 服务器只知道代理机器请求信息.
常见情况如 通过代理上网, 子网用户通过代理访问外网.

反向代理是指用户直接访问反向代理服务器就可以访问目标服务器的资源, 服务器知道用户机器请求信息.
如通过 nginx 反向代理各种服务, 用户只需要请求nginx服务器即可.

通俗来讲, 就是
1. 正向代理隐藏真实客户端.
2. 反向代理隐藏真实服务端.

代理的实现可以参考
1. [端口映射-frp](/soft/port-mapping.md)
1. [端口映射-ssh](/soft/linux_cmd/ssh.md#端口转发)

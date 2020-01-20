# System design primer

## Scalability

- clone: 
  - every server contains exactly the same codebase and does not store any user-related data, like sessions or profile pictures, on local disc or memory. 
  - How can you make sure that a code change is sent to all your servers without one server still serving old code? $\to$ [Capistrano](https://github.com/capistrano/capistrano)
- database
- cache
- asynchronism

## Latency vs. Throughput

## Avaliablity vs. Consistency

## Consistency patterns

- weak consistency
- eventual consistency
- strong consistency

## Avaliability patterns

It is measured by number of 9s.

- master-salve replication
- master-master replication 

## DNS

## CDN

- push CDNs
- pull CDNs

## Load balancer

- layer4(transport layer) load balancing: NAT
- layer7(application layer) load balancing: [Nginx](https://www.nginx.com/blog/inside-nginx-how-we-designed-for-performance-scale/), [HAProxy](http://www.haproxy.org/download/1.2/doc/architecture.txt)

## Reverse proxy

Solutions such as NGINX and HAProxy can support both layer 7 reverse proxying and load balancing.

## Application layer



## Appendix

### [SSH](https://www.ruanyifeng.com/blog/2011/12/ssh_remote_login.html)

简单说，SSH是一种网络协议，用于计算机之间的加密登录。SSH之所以能够保证安全，原因在于它采用了公钥加密。整个过程是这样的：（1）远程主机收到用户的登录请求，把自己的公钥发给用户。（2）用户使用这个公钥，将登录密码加密后，发送回来。（3）远程主机用自己的私钥，解密登录密码，如果密码正确，就同意用户登录。

- Man-in-the-middle Attack
- 公钥登录

### [make](http://www.ruanyifeng.com/blog/2015/02/make.html)

- 需要注意的是，每行命令在一个单独的shell中执行。这些Shell之间没有继承关系。
  - 一个解决办法是将两行命令写在一行，中间用分号分隔。
  - 另一个解决办法是在换行符前加反斜杠转义。
  - 最后一个方法是加上`.ONESHELL:`命令。


#Setting 上受信任的存储池

您可以配置一个 GlusterFS 卷之前，您必须创建受信任
提供对砖的存储服务器组成的存储池
卷。

存储池是受信任的网络存储服务器。你什么时候开始

第一台服务器，存储池包含，一个单独的服务器。若要添加

额外的存储服务器到存储池，您可以使用探针
从已受信任存储服务器的命令。

> * * 注意 * *: 不自我探讨第一服务器/本地主机从本身。

GlusterFS 服务必须在所有存储服务器上运行，你
想要添加到存储池。看到了吗？更多的信息。


##Adding 服务器到受信任的存储池

若要创建一个受信任的存储池，请将服务器添加到受信任的存储
游泳池

1.* * 用于创建存储池的服务器必须可以由解析
hostname.* *

将服务器添加到存储池︰

    `# gluster peer probe `

例如，若要创建四个服务器信任的存储池，添加
三个服务器到存储池从 server1:

# gluster 同行探针 server2
探头成功

# gluster 同行探针 server3
探头成功

# gluster 同行探头 server4
探头成功

2.* * 验证同伴地位从第一个服务器使用以下
命令: * *

# gluster 同伴地位
同行的数目︰ 3

主机名︰ server2
Uuid: 5e987bda-16dd-43c2-835b-08b7d55e94e5
状态︰ 同行中群集 （连接）

主机名︰ server3
Uuid: 1e0ca3aa-9ef7-4f66-8f15-cbc348f29ff7
状态︰ 同行中群集 （连接）

主机名︰ server4
Uuid: 3e0caba-9df7-4f66-8e5d-cbc348f29ff7
状态︰ 同行中群集 （连接）

3.* * 通过探索从另一台服务器 （不使用在步骤 1 和 2 中的服务器） 指派的第一个服务器的主机名: * *

server2 # gluster 同行探针 server1
探头成功

4.* * 验证同伴地位从您在步骤 3 使用以下使用相同的服务器
命令: * *

server2 # gluster 同伴地位
同行的数目︰ 3

主机名︰ server1
Uuid: ceed91d5-e8d1-434d-9d47-63e914c93424
状态︰ 同行中群集 （连接）

主机名︰ server3
Uuid: 1e0ca3aa-9ef7-4f66-8f15-cbc348f29ff7
状态︰ 同行中群集 （连接）

主机名︰ server4
Uuid: 3e0caba-9df7-4f66-8e5d-cbc348f29ff7
状态︰ 同行中群集 （连接）

##Removing 服务器从受信任的存储池

要从存储池中删除服务器︰

`# gluster peer detach`

例如，要从受信任的存储池中删除 server4:

# gluster 同行分离 server4
分离成功

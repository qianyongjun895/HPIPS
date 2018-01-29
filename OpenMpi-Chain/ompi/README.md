Openmpi  代码内容 

Attribute 		用于处理可以挂起通信、win或datatype的属性的实现。
Class   			序列事件追踪
Communicator  	中间通讯层
Contrib   		发布版
Datatype 		基本数据类型
Debuggers 		调试程序源代码
Dpm  			动态过程管理
Errhandler 		错误关键字声明代码
Ect 				管理文件夹
File				文件管理代码
Group 			基类代码
Include			函数声明文件
Info				信息代码文件
Mac				所有版本MCA组件的顶级接口
MCA 下包含的组件框架有 PML（Point-to-point Management Layer）、BML（BTL Management Layer）、MPool（Memory Pool）、BTL（Byte-Transfer-Layer Layer）等。
PML 组件框架负责管理所有消息的传递，实现了 MPI 点点通信原语，包括标准、缓冲、准备和同步四种通信模式。PML 根据具体的调度策略对 MPI 消息进行调度，该策略是根据 BTL 的具体属性决定的。短消息传递协议和长消息传递协议也是在 PML 中实现的。所有控制信息（ACK/NACK/MATCH）也都由 PML 进行管理。这种结构的优点是将传输协议从底层互连中分离出来，显著的降低了代码的复杂度和冗余度，增强了可维护性。
BML 组件框架为任务启动和动态进程的创建提供搜索和维持负责点点通信的BTL 组件的服务。BML 可以协调结点资源，并为 BTL 的使用者进行缓冲，当发现资源后，其他层会绕过 BML 组件框架直接与 BTL 通信，提高了通信性能。
MPool 内存池提供内存分配/释放和注册和注销服务。对于 Infiniband 和 Myrinet等都需要在发送/接收或 RDMA 操作之前注册内存（使物理内存页锁定）才能将内存作为源或者目标来使用。将这个功能从其他组件中分离出来可以使 MPool 被更多的组件框架或组件共享。
BTL 组件框架负责处理所有点对点消息传送，包含了一组用于发送/接收或RDMA 的通信组件单元。BTL 不受 MPI 语义的影响，它仅仅是通过最基本的传递功能来在进程间进行数据交换（包括连续的和非连续的数据）。这样的组件框架为网络设备的开发商提供了便利，同时也可以支持更广泛的结点间通信设备

Message			消息类的源文件
Mpi				mpi源文件
Mpiext 			mpi测试源码文件
Op				公开的头文件函数
Patterns			模式头文件
Peruse			详细解读
Proc				过程识别结构界面
Request			请求源代码
Tools			工具函数源代码
Win					

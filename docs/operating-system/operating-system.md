# 操作系统入门

**多道批处理系统**

- 多道程序设计的基本概念：在多道批处理系统中，用户所提交的作业先存放在外存上，并排成一个队列，称为“**后备队列**”，然后由 **作业调度程序** 按一定的算法，从后备队列中选择若干个作业调入内存，使它们共享 CPU 和系统中的各种资源。
- 优缺点：
  - 资源利用率高：多道程序交替执行，使 CPU 保持忙碌状态。
  - 系统吞吐量大。
  - 平均运转时间长：作业要排队处理，因而作业的周转时间较长。
  - 无交互能力：用户一旦提交作业，就不能再和作业交互。
- 需要解决的问题：
  - 处理机争用问题。
  - 内存分配和保护问题。
  - I/O 设备分配问题。
  - 文件的组织和管理。
  - 作业管理问题。
  - 用户与系统接口问题。

**操作系统的基本特性**

- **并发**：
  - 并行 vs 并发：**并行性** 是指两个或多个事件在 **同一时刻** 发生，而 **并发性** 是指两个或多个事件在 **同一段时间** 发生。倘若计算机系统有 **多个处理机**，则并发执行的程序就可以被分配到多个处理机上，实现 **并行** 执行。
  - 进程：两个 **进程** 是可以 **并发执行** 的。进程在系统中能 **独立运行** 并作为 **资源分配基本单位**，由一组 **机器指令、数据、堆栈** 组成。
- **共享**：
  - 互斥共享方式
  - 同时访问方式
- **虚拟**：
  - 时分复用技术：虚拟处理机技术、虚拟设备技术。
  - 空分复用技术。
- **异步**

**操作系统主要功能**

- **处理机管理功能**（对进程的管理）
  - **进程控制**：为作业 **创建** 进程、**撤销** 已结束的进程，以及控制进程在运行过程中的 **状态转换**。
  - **进程同步**：为了多个进程有条理地运行，系统中必须设置相应的进程同步机制，其主要任务是对多个进程的运行进行协调。协调方式有两种：①**进程互斥方式**：多个进程访问临界资源时。②**进程同步方式**：在相互合作完成共同任务的各个进程间，由同步机构对它们的执行次序加以协调。。
  - **进程通信**
  - **调度**：包括作业调度和进程调度两步。**作业调度**：基本任务是从 **后备队列** 中选择出若干个作业，为它们分配资源（为它们建立进程，加入就绪队列）。**进程调度**：从 **就绪队列** 中选出一个进程，使其执行。
- **存储器管理功能**
  - **内存分配**：
    - 主要任务：为每道程序 **分配内存**；提高 **存储器的利用率**；允许正在运行的程序申请 **附加的内存空间**。
    - 分配方式：静态、动态。
  - 内存保护：
    - 主要任务：确保每道用户程序都 **只在自己的内存空间运行**；不允许用户访问 **操作系统的程序和数据**；不允许用户程序转移到 **非共享的其他用户程序** 中执行。
  - 地址映射：将地址空间中的 **逻辑地址** 转换为内存空间中与之对应的 **物理地址**。
  - 内存扩充：请求调入、置换。
- **设备管理功能**
  - 主要任务：
    - 为用户进程分配 I/O 设备，完成指定 I/O 操作；
    - 提高 CPU 和 I/O 设备的利用率。
  - 功能：
    - 缓冲管理
    - 设备分配
    - 设备处理：设备处理程序又叫设备驱动程序，实现 CPU 和设备控制器间的通信。
- **文件管理功能**
  - 文件存储空间的管理：为每个文件分配存储空间。
  - 目录管理：为每个文件建立一个目录项。
  - 读写管理和保护。


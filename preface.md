# 研发运营一体化（DevOps）能力成熟度模型 第9部分 系统和工具


## 1. 范围

本标准规定了研发运营一体化（DevOps）的xxxxx。

本标准适用于具备IT软件研发交付运营能力的组织实施IT软件开发和服务过程的能力进行评价和指导；可供其他相关行业或组织进行参考；也可作为第三方权威评估机构衡量软件开发交付成熟的标准依据。

## 2. 规范性引用文件

下列文件对于本文件的应用是必不可少的。凡是注日期的引用文件，仅所注日期的版本适用于本文件。凡是不注日期的引用文件，其最新版本（包括所有的修改单）适用于本文件。

[1] GB/T  32400-2015 信息技术 云计算 概览与词汇

[2] GB/T  32399-2016 信息技术 云计算 参考架构

[3] YD/2441-2013     互联网数据中心技术及分级分类标准

[4] GB/T  33136-2016 信息技术服务数据中心服务能力成熟度模型

[5] GB/T 31496-2015 信息技术 安全技术 信息安全管理体系实施指南

[6] GB/T 22080-2016 信息技术 安全技术 信息安全管理体系要求

[7] GB/T 30975-2014 信息技术 基于计算机的软件系统的性能测量与评级

## 3. 术语

下列术语和定义适用于本文件。

**3.1　项目 project**

需要协同工作的一组任务，其目的在于开发和（或）维护一个具体的产品。产品可以包括硬件、软件或其他成分，一般项目有自己的经费、成本核算和交付进度。【GB/T11457-2006：2.954】

**3.2　项目集 program**

PMI将项目集定义为经过协调管理以获取单独管理所无法取得的收益的一组项目、子项目集和项目集活动。

**3.3　子项目集 sub program**

作为另一个项目集的组成部分而被管理的一个项目集

**3.4　构建项目  Build project**

作为一个构建软件的配置，以及流程。

**3.5　执行记录  Build history**

执行构建的信息，以及结果。

**3.6　构建产出物  Build output**

构建项目中生产的文件。

**3.7　凭据 Credentials**

保存用户保密信息，例如：用户名和密码。

**3.8　容器镜像 Container Image**

容器技术中运行容器软件。包含基本操作系统以及依赖的软件。可以包含构建的产出物。

**3.9　运行环境 Runtime environment**

构建中运行的环境或者计算机。

**3.10　源代码托管软件 Source code management software**

保存源代码的软件。

**3.11　软件单元测试 Software unit test**

软件中研发的自动化测试。

**3.12　发布**

发布通常是软件程序的变动，将线上的流量转移到新的软件版本的过程

**3.13　原地发布**

将新的软件版本直接推送到服务器上覆盖旧版本，发布过程可能会引起服务的中断，是一种最直接的发布方式

**3.14　金丝雀发布**

是指在黑与白之间，能够平滑过渡的一种发布方式。又称灰度发布，A/B测试就是一种灰度发布方式，让一部分用户继续用A，一部分用户开始用B，如果用户对B没有什么反对意见，那么逐步扩大范围，把所有用户都迁移到B上面来。可以保证整体系统的稳定，在初始灰度的时候就可以发现、调整问题，以保证其影响度范围的一种发布方式

**3.15　蓝绿发布**

在发布过程中，新旧版本相互热备，发布过程是不停止老版本，直接部署新版本然后进行测试，通过切换路由权重的方式（非0即100）实现将流量切到新版本，然后老版本同时也升级到新版本，是一种可以保证系统在不间断提供服务的情况下的发布方式

**3.16　回滚**

回滚（Rollback）指的是程序或数据处理错误，将程序或数据恢复到上一次正确状态的行为。回滚包括程序回滚和数据回滚等类型

**3.17　环境 Environment**

是指应用程序运行所需的所有资源和它们的配置信息，通常分成两大类：基础设施资源及其配置；应用程序独立运行所需要的操作系统和中间件资源及其配置信息。

**3.18　配置项 Configuration item**

一个配置中的实体，它满足一项最终使用功能，并能在给定的基准点上单独标识。【GB/T 8566-2001：3.6】

**3.19　配置管理 Configuration Management**

是一个过程，通过该过程，可以维护一切与环境相关的信息，这些信息可以被定义、修改、存储和检索。应用技术和管理的指导和监控方法以标识和说明配置项的功能和物理特征，控制这些特征的变更，记录和报告变更处理和实现状态并验证与规定的需求的遵循性。【GB/T11457-2006：2.313】

**3.20　开发环境  Development Environment**

用于维持开发过程的一个或者一组资源及其配置信息，面向的是开发者。

**3.21　测试环境 Test Environment**

用于维持测试过程的一个或者一组资源及其配置信息，面向的是测试者。

**3.22　生产环境 Production Environment**

用于维持开发过程的一个或者一组资源及其配置信息，面向的是运维，但其运行服务面向的是用户或者客户。

**3.23　基础设施 Infrastructure**

支持应用运行的所有服务，包括DNS服务器、防火墙、路由器等等。

**3.24　中间件 Middleware**

是处于操作系统和应用程序之间的软件。一种类型的软件模块，它处在系统软件和应用软件之间，依赖系统软件的支持，又为应用软件提供支持，以方便应用软件的开发。【GB/T11457-2006：2.954】

**3.25　性能测试（performance test）**

性能测试是通过自动化的测试工具模拟多种正常、峰值以及异常负载条件来对系统的各项性能指标进行测试。评价系统或部件与规定的性能需求的依从性的测试行为。【GB/T11457-2006：2.1135】

**3.26　负载测试（load testing）**

通过测试系统在资源超负荷情况下的表现，以发现设计上的错误或验证系统的负载能力。在这种测试中，将使测试对象承担不同的工作量，以评测和评估测试对象在不同工作量条件下的性能行为，以及持续正常运行的能力。

**3.27　压力测试（stress testing）**

压力测试是模拟实际应用的软硬件环境及用户使用过程的系统负荷，长时间或超大负荷地运行测试软件，来测试被测系统的性能、可靠性、稳定性等。

**3.28　稳定性测试（stability test）**

 通常是采用系统稳定运行情况下能够支持的最大并发用户数或者日常运行用户数，持续执行一段时间业务，通过综合分析交易执行指标和资源监控指标来确定系统处理最大工作量强度性能的过程。

**3.29　活动（activity）**

由用户或模拟用户向在册系统（SUT）提交的一种命令：要求依界定的算法来执行数据处理操作，从特定输入数据和（若要求时的）既存数据产生特定输出数据。

**3.30　活动类型（activity type）**

对执行同一算法所界定的各种活动的分类。

**3.31　链（chain）**

以界定的顺序向STU提交的一个或不止一个任务。

**3.32　链型（chain type）**

对由任务（类）型序列所界定的链所作的分类。

模拟用户只向SUT提交规定链型的链。

所指链型当前序号的数学符号为L，链型总数的数学符号为u。

**3.33　模拟用户（emulated user）**

就用户提交任务及其时变行为实施模仿的技术系统。

**3.34　执行时间（execution time）**

从任务提交至任务完成所经历的时间。

**3.35　平均执行时间（mean execution time）**

在评级区间内提交的第j型所有任务的执行时间的均值。

**3.36　平均执行时间参考值（mean execution time reference value）**

模拟用户可接受的最大平均执行时间。

**3.37　响应时间（response time）**

指用户发起一个请求开始，服务器完成对该请求的处理并返回处理结果所经过的时间。

**3.38　观测期（observation period）**

为汇集（日志记载）用户评级或确认的测量结果而观测测量规程的时间区间。由评级区间和补充运行时间组成。

**3.39　准备时间(perparation time)**

任务提交之前经历的时间。启动准备时间的事件取决于对后一任务的任务模式的界定。准备时间的值是带有界定的均值和标准差的分布式变量的随机值，这取决于后一任务的任务类型和生成此任务的模拟用户的类型。

**3.40　评级区间(rating interval)**

测量规定从SUT达到操作稳定状态的时间开始，到测量结果满足所需统计显著性的时间为止的时间区间。

**3.41　相对链频(relative chain frequency)**

第i型的模拟用户使用第l型链的相对频数。

**3.42　稳定化阶段（stabilization phase）**

测量规程从RTE提交任务开始，到SUT达到稳定操作状态位置的时间区间。

**3.43　补充运行时间（supplementary run）**

测量规程从测量结果达到满足所需统计显著性的时间开始，到评级期间已提交的所有任务全部完成时间为止的时间区间。

**3.44　在测系统（system under test，SUT）**

CBSS中接受测试的个部分。影响SUT时变行为的所有部件都应是SUT的组成部分，如果此种影响取决于某一工作负载，则该负载也应由RTE来标识。除非对时变行为的影响不可能或不明显时，对其余部分的模拟才可省略。

**3.45　任务（task）**

特定活动，由特定适时性函数界定的所需执行时间，特定任务模式。

**3.46　任务完成（task completion）**

对特定任务的如下适时时间：由模拟用户或另一实例全部收到整个输出串，或者在输出串集的情况，收到该集合的所有部分。该任务未向用户（即测量期间向RTE）提交输出时，可为该任务添加一个功能，即产生“人工输出”来指明该任务完成，供测量期间使用。

**3.47　任务模式(task mode)**

对用户的准备时间是在前一任务提交后立即开始（值=0，即“不等待”）还是当前一任务完成时（任务完成）开始（值=1，即“等待”）所做的指示。

**3.48　任务提交（task submission）**

当输入串完整的从模拟用户提交SUT时，该任务即可开始执行，而不管SUT是否立即执行的适时事件。任务提交还可通过这一任务的模拟用户行动结束时间来指示。根据本标准，任务提交不应该由以下事件来界定（和测量）：SUT收到或解释完输出串，或模拟用户接收一个可由SUT在接收和解释之后送出的收据串。

**3.49　任务类型（task type）**

任务所有分类：

活动类型，或属于同一实时性函数和任务模式的所有活动类型的集合；

适时性函数；

任务模式。

**3.50　吞吐量（throughput）**

提交给SUT某一任务型所有任务的速率（即评级区间内单位时间的平均数）

**3.51　吞吐量参考值（throughput reference value）**

实际吞吐量与吞吐量参考值之比（对应于第j任务型）

**3.52　时间类别（time class）**

与一种相对频数相结合，用于和（特指任务型的）任务的执行时间相比较的时限。其中的相对频数对应于执行时间小于等于对应时限的（特定任务型的）任务数和（该特指任务型）任务总数之比。

**3.53　实时吞吐量（timely throughput）**

对应于适时性函数，执行时得以接收的所有任务的吞吐量。

**3.54　用户（user）**

通过终端（或等效的机器用户接口）使用CBSS功能来提交任务并接收算出结果的人（或实例）。

**3.55　虚拟用户（virtual user）**

通过函数或任务模拟的方式完成等效机器用户接口功能，使用CBSS功能来提交任务并行接收算出结果的特定程序集合。

**3.56　最大并发用户数（maximum number of concurrent users）**

系统能够承受的同时使用系统服务或资源的用户数的极限，超过该用户数，将导致系统效率严重下滑，并可能导致系统崩溃、失效。

**3.57　最大并发请求数（maximum number of concurrent users）**

系统能够承受的同时接收到的请求数的极限，超过该请求数，将导致系统效率严重下滑，并可能导致系统崩溃、失效。

**3.58　用户类型（user type）**

对由下列两项的组合所界定的模拟用户的一种分类：

使用链类型的相对频数；

准备时间（均值及其标准差）

**3.59　事务（transaction）**

事务是脚本的一个特性，每个事务都包含开始事务和结束事务。事务用来衡量脚本中一行代码或多行代码的执行所耗费的时间。你可以将开始事务放置在脚本中某行代码的前面，将结束事务放置在该行代码的后面，在该脚本的虚拟用户运行时，这个事务将衡量该行代码的执行花费了多长时间。

**3.60　事务吞吐容量（transaction throughput capacity）**

在一定的时间单位内，系统能够处理完成的最大事务量。

**3.61　数据吞吐容量（data throughput capacity）**

在一定的时间单位内，系统能够处理完成的最大数据量。

**3.62　延迟（delay）**

完成一个请求的延时。

**3.63　业务交易（business transaction）**

业务交易分为业务层面和技术层面两种定义。业务层面交易是指完成一次完整的业务操作，技术层面的交易是指进行一次应用程序至应用程序、或者应用程序至数据库的系统操作。

**3.64　CPU利用率（CPU utilization）**

系统或软件产品在运行过程中CPU的使用率。

**3.65　内存利用率（Memory utilization）**

系统或软件产品在运行过程中内存的使用率。

**3.66　传输利用率（transmission-untilization ratio）**

系统或软件产品在执行规定的数据传输功能时，传输吞吐率占传输设备最大传输吞吐率的百分比。

**3.67　构建环境**

构建环境是指执行构建任务时所在设备的软件和硬件环境。

**3.68　构建任务**

构建任务是指定义从输入到输出过程对构建环境、构建方法等必要因素的定义。

**3.69　构建过程**

构建过程是指构建任务从开始执行到结束。

**3.70　构建策略**

构建策略是指针对构建过程的特定结果设定的处理策略。

**3.71　复刻（Fork）**

复刻是指在软件开发中，开发者为一个版本仓库创建一份拷贝，并在拷贝上进行独立于源版本仓库的开发，从而分离出一个新的软件副本的活动。复刻不仅仅创建了一个分支，还将软件开发活动与源版本库分离开来。

**3.72　合并（Merge）**

是指当一个版本在多个独立分支中被修改后如何合并这些修改成为同一个版本的操作。

**3.73　合并评审（Merge Requests）**

是指在合并之前，允许多人对合并时所提交的变更内容进行代码审查，并给予合并意见的过程。

**3.74　基线（Baseline**

基线是版本仓库中每个版本在特定时期的一个“快照”。它提供一个正式标准，随后的工作基于此标准，并且只有经过授权后才能变更这个标准。建立一个初始基线后，以后每次对其进行的变更都将记录为一个差值，直到建成下一个基线。

**3.75　版本仓库（Repositories）**

版本仓库又称源代码仓库，被用来存储源代码等版本文件。

**3.76　代码审查（Code Review）**

是指对计算机源代码系统化地审查，常用软件同行评审的方式进行，其目的是在找出及修正在软件开发初期未发现的错误，提升软件质量及开发者的技术。代码审查常以不同的形式进行，例如结对编程、非正式的看过整个代码等。

**3.77　测试计划（Testing plan）**

一个叙述了预定的测试活动的范围、途径、资源及进度安排的文档。它确认了测试项、被测特征、测试任务、人员安排，以及任何偶发事件的风险。

**3.78　测试脚本（Testing script）**

一般指的是一个特定测试的一系列指令，这些指令可以被自动化测试工具执行。

**3.79　构建任务  Build task**

​     作为一个构建软件的配置，以及流程。

**3.80　凭据 Credentials**

​     保存用户保密信息，例如：用户名和密码。

**3.81　运行环境 Runtime environment**

​     构建中运行的环境或者计算机

**3.82　源代码托管软件 Source code management software**

​     保存源代码的软件

**3.83　执行记录  Build history**

​     执行构建的信息，日志，以及结果。

**3.84　构建产出物  Build output**

​     构建任务中生产的文件

**3.85　软件单元测试 Software unit test**

​     软件中研发的自动化测试

**3.86　静态源代码扫描 Static code analysis**

​     对源代码执行静态的分析，指出源代码质量(10.9)

**3.87　(制品的)晋级 Promotion**

​     制品管理中，通常是指自构建产物通过某一级别质量关卡后，将其标记为更稳定状态的过程。例如从发布待定(release-candidate)升级为可发布(release)。晋级过程通常会伴随虚拟文件夹的切换。

## 4. 缩略语

下列缩略语适用于本文件。

CI          Continuous Integration                      持续集成（样例）

CD          Continuous Delivery                         持续交付（样例）
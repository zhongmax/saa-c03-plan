# AWS SAA-C03 完整知识点清单

> 本清单涵盖AWS Solutions Architect Associate (SAA-C03)考试所需的所有核心知识点
>
> 使用说明: 在复选框中打勾 `[x]` 表示已掌握该知识点

---

## 📊 学习进度总览

- **身份与访问管理 (IAM)**: ___/23
- **计算服务**: ___/35
- **存储服务**: ___/32
- **数据库服务**: ___/28
- **网络与内容分发**: ___/38
- **应用集成**: ___/25
- **安全、身份与合规**: ___/30
- **管理与监控**: ___/22
- **分析服务**: ___/12
- **容器服务**: ___/15
- **开发工具 (CI/CD)**: ___/12
- **成本管理与优化**: ___/10
- **架构设计最佳实践**: ___/20

**总计**: ___/302

---

## 🔐 1. 身份与访问管理 (IAM)

### IAM基础
- [ ] AWS账户根用户的特性和最佳实践
- [ ] IAM用户、组、角色的概念和区别
- [ ] IAM策略(Policy)的结构: Effect, Action, Resource, Condition
- [ ] 身份基础策略(Identity-based policies)
- [ ] 资源基础策略(Resource-based policies)
- [ ] 权限边界(Permissions boundaries)
- [ ] 服务控制策略(SCPs) - AWS Organizations

### IAM最佳实践
- [ ] 最小权限原则(Least privilege)
- [ ] 启用MFA(多因素认证)
- [ ] 使用角色而非长期凭证
- [ ] 定期轮换凭证
- [ ] 使用策略条件增强安全性

### 访问密钥与凭证
- [ ] 访问密钥的创建和管理
- [ ] 临时安全凭证(STS)
- [ ] AssumeRole操作
- [ ] 跨账户访问

### 高级IAM
- [ ] IAM Access Analyzer - 识别过度权限
- [ ] IAM策略评估逻辑(默认拒绝 → 显式拒绝 > 显式允许)
- [ ] 服务链接角色(Service-linked roles)
- [ ] 传递角色(PassRole)权限
- [ ] 身份联合(Federation) - SAML 2.0, OIDC
- [ ] AWS Cognito与IAM集成

---

## 💻 2. 计算服务

### Amazon EC2 基础
- [ ] EC2实例类型: 通用型、计算优化型、内存优化型、存储优化型、加速计算型
- [ ] 实例命名规则(例: m5.xlarge)
- [ ] AMI(Amazon Machine Image)的创建和使用
- [ ] 实例元数据服务(IMDS) - v1 vs v2
- [ ] 用户数据(User Data)脚本
- [ ] 实例生命周期: pending, running, stopping, stopped, terminated

### EC2 定价模型
- [ ] 按需实例(On-Demand)
- [ ] 预留实例(Reserved Instances) - 标准RI vs 可转换RI
- [ ] Savings Plans - Compute Savings Plans vs EC2 Instance Savings Plans
- [ ] Spot实例 - 出价策略、中断处理
- [ ] Spot Fleet
- [ ] 专用主机(Dedicated Hosts) vs 专用实例(Dedicated Instances)
- [ ] 容量预留(Capacity Reservations)

### EC2 网络与存储
- [ ] 弹性IP地址(EIP)
- [ ] 弹性网络接口(ENI)
- [ ] 增强联网(Enhanced Networking) - SR-IOV
- [ ] 置放群组(Placement Groups): Cluster, Spread, Partition
- [ ] EC2 Instance Connect
- [ ] EC2实例存储(Instance Store) vs EBS

### EC2 扩展与管理
- [ ] Auto Scaling组(ASG)基础
- [ ] 启动模板(Launch Templates) vs 启动配置(Launch Configurations)
- [ ] 扩展策略: 目标跟踪、简单扩展、步进扩展、预测扩展
- [ ] 健康检查: EC2 vs ELB
- [ ] 生命周期钩子(Lifecycle Hooks)
- [ ] 实例预热(Warm-up time)
- [ ] 冷却期(Cooldown period)

### AWS Lambda
- [ ] Lambda函数基础概念
- [ ] 支持的运行时(Python, Node.js, Java, .NET, Go, Ruby等)
- [ ] Lambda执行环境和冷启动
- [ ] Lambda超时限制(最长15分钟)
- [ ] Lambda内存配置(128MB - 10GB)
- [ ] Lambda环境变量
- [ ] Lambda Layers - 共享代码和依赖
- [ ] Lambda并发: 预留并发、预配置并发
- [ ] Lambda触发器: S3, DynamoDB, SQS, EventBridge, API Gateway等
- [ ] Lambda版本和别名
- [ ] Lambda容器镜像支持
- [ ] Lambda与VPC集成

---

## 💾 3. 存储服务

### Amazon S3 基础
- [ ] S3存储桶(Bucket)和对象(Object)
- [ ] S3全局命名空间
- [ ] S3对象键(Key)和版本ID
- [ ] S3对象大小限制(单个对象最大5TB)
- [ ] 多部分上传(Multipart Upload) - 对象>100MB推荐
- [ ] S3传输加速(Transfer Acceleration)

### S3 存储类别
- [ ] S3 Standard - 频繁访问
- [ ] S3 Intelligent-Tiering - 自动分层
- [ ] S3 Standard-IA - 不频繁访问
- [ ] S3 One Zone-IA - 单可用区不频繁访问
- [ ] S3 Glacier Instant Retrieval - 毫秒级检索
- [ ] S3 Glacier Flexible Retrieval - 分钟到小时检索
- [ ] S3 Glacier Deep Archive - 12小时检索
- [ ] S3 Express One Zone - 高性能(单可用区)

### S3 安全与访问控制
- [ ] S3存储桶策略(Bucket Policies)
- [ ] S3访问控制列表(ACLs)
- [ ] S3阻止公共访问(Block Public Access)
- [ ] S3访问点(Access Points)
- [ ] S3 Access Grants
- [ ] S3对象所有权
- [ ] 预签名URL(Pre-signed URLs)

### S3 加密
- [ ] 服务端加密 - SSE-S3 (AES-256)
- [ ] 服务端加密 - SSE-KMS
- [ ] 服务端加密 - SSE-C (客户提供密钥)
- [ ] 客户端加密
- [ ] 传输中加密(HTTPS/TLS)
- [ ] 默认加密配置

### S3 高级特性
- [ ] S3版本控制(Versioning)
- [ ] S3生命周期策略(Lifecycle Policies)
- [ ] S3复制: 跨区域复制(CRR) vs 同区域复制(SRR)
- [ ] S3事件通知(Event Notifications) - SNS, SQS, Lambda
- [ ] S3 Object Lock - 合规模式 vs 治理模式
- [ ] S3 Object Lambda - 处理检索数据
- [ ] S3 Inventory - 对象清单
- [ ] S3 Storage Lens - 组织级可见性
- [ ] S3 Select和Glacier Select - 查询对象内容
- [ ] S3静态网站托管
- [ ] S3 Requester Pays

### Amazon EBS
- [ ] EBS卷类型: gp3, gp2, io2, io1, st1, sc1
- [ ] EBS卷性能特性: IOPS vs 吞吐量
- [ ] EBS快照(Snapshots)
- [ ] EBS快照生命周期管理
- [ ] EBS加密
- [ ] EBS Multi-Attach (io2系列)
- [ ] EBS卷大小调整和类型转换
- [ ] EBS优化实例
- [ ] EBS Snapshots Archive

### Amazon EFS
- [ ] EFS文件系统基础(NFS v4.1)
- [ ] EFS性能模式: 通用 vs 最大I/O
- [ ] EFS吞吐模式: 突发 vs 预置 vs 弹性
- [ ] EFS存储类别: Standard vs One Zone
- [ ] EFS生命周期管理
- [ ] EFS加密(静态和传输中)
- [ ] EFS访问点(Access Points)
- [ ] EFS Replication - 跨区域复制

### 其他存储服务
- [ ] AWS Storage Gateway - 文件网关、卷网关、磁带网关
- [ ] AWS FSx for Windows File Server
- [ ] AWS FSx for Lustre
- [ ] AWS FSx for NetApp ONTAP
- [ ] AWS FSx for OpenZFS
- [ ] AWS Backup - 集中式备份管理

---

## 🗄️ 4. 数据库服务

### Amazon RDS
- [ ] RDS支持的数据库引擎: MySQL, PostgreSQL, MariaDB, Oracle, SQL Server
- [ ] RDS实例类型和大小选择
- [ ] Multi-AZ部署 - 同步复制(高可用)
- [ ] 读副本(Read Replicas) - 异步复制(扩展读)
- [ ] 跨区域读副本
- [ ] RDS自动备份 - 保留期1-35天
- [ ] RDS手动快照
- [ ] RDS备份窗口和维护窗口
- [ ] RDS加密: 静态加密(KMS) vs 传输加密(SSL/TLS)
- [ ] RDS性能洞察(Performance Insights)
- [ ] RDS Enhanced Monitoring
- [ ] RDS事件通知
- [ ] RDS代理(RDS Proxy) - 连接池

### Amazon Aurora
- [ ] Aurora与MySQL/PostgreSQL兼容性
- [ ] Aurora集群架构: 1个主实例 + 最多15个副本
- [ ] Aurora存储自动扩展(10GB - 128TB)
- [ ] Aurora全局数据库(Global Database) - 跨区域复制
- [ ] Aurora Serverless v1 vs v2
- [ ] Aurora Multi-Master(仅MySQL)
- [ ] Aurora副本自动故障转移
- [ ] Aurora Backtrack - 快速回退
- [ ] Aurora克隆 - 快速创建副本
- [ ] Aurora机器学习集成
- [ ] Aurora性能优势: 5倍MySQL, 3倍PostgreSQL

### Amazon DynamoDB
- [ ] DynamoDB NoSQL数据模型
- [ ] 分区键(Partition Key) vs 复合主键(Partition Key + Sort Key)
- [ ] DynamoDB项(Item)和属性(Attribute)
- [ ] 全局二级索引(GSI) vs 本地二级索引(LSI)
- [ ] DynamoDB容量模式: 按需 vs 预置
- [ ] DynamoDB读一致性: 最终一致性 vs 强一致性
- [ ] DynamoDB Streams - 变更数据捕获
- [ ] DynamoDB Accelerator (DAX) - 内存缓存
- [ ] DynamoDB全局表(Global Tables) - 多区域主动-主动
- [ ] DynamoDB事务
- [ ] DynamoDB TTL(生存时间)
- [ ] DynamoDB备份: 按需备份 vs 时间点恢复(PITR)
- [ ] DynamoDB加密

### Amazon Redshift
- [ ] Redshift数据仓库概念
- [ ] Redshift集群架构: Leader Node + Compute Nodes
- [ ] 列式存储(Columnar Storage)
- [ ] 大规模并行处理(MPP)
- [ ] Redshift Spectrum - 查询S3数据
- [ ] Redshift Serverless
- [ ] Redshift增强VPC路由
- [ ] Redshift快照和恢复
- [ ] Redshift并发扩展(Concurrency Scaling)

### 其他数据库服务
- [ ] Amazon ElastiCache - Redis vs Memcached
- [ ] ElastiCache集群模式 vs 非集群模式
- [ ] ElastiCache缓存策略: Lazy Loading vs Write-Through
- [ ] Amazon DocumentDB - MongoDB兼容
- [ ] Amazon Neptune - 图数据库
- [ ] Amazon QLDB - 账本数据库
- [ ] Amazon Timestream - 时序数据库
- [ ] Amazon Keyspaces - Cassandra兼容

---

## 🌐 5. 网络与内容分发

### Amazon VPC 基础
- [ ] VPC概念和CIDR块
- [ ] 子网(Subnets): 公有子网 vs 私有子网
- [ ] 路由表(Route Tables)
- [ ] 互联网网关(Internet Gateway)
- [ ] NAT网关(NAT Gateway) vs NAT实例
- [ ] 仅出口互联网网关(Egress-Only Internet Gateway) - IPv6
- [ ] VPC对等连接(VPC Peering)
- [ ] VPC终端节点(VPC Endpoints): 网关型 vs 接口型
- [ ] PrivateLink

### VPC 安全
- [ ] 安全组(Security Groups) - 有状态、实例级
- [ ] 网络ACL(NACLs) - 无状态、子网级
- [ ] 安全组 vs NACL对比
- [ ] VPC Flow Logs - 流量日志
- [ ] 网络访问分析器(Network Access Analyzer)

### VPC 高级特性
- [ ] VPC共享(VPC Sharing) - RAM
- [ ] AWS Transit Gateway - 中心辐射型拓扑
- [ ] Transit Gateway路由表
- [ ] Transit Gateway跨区域对等
- [ ] VPN连接: Site-to-Site VPN
- [ ] 客户网关(Customer Gateway)
- [ ] 虚拟私有网关(Virtual Private Gateway)
- [ ] AWS VPN CloudHub
- [ ] AWS Client VPN

### AWS Direct Connect
- [ ] Direct Connect概念和优势
- [ ] 专用连接(Dedicated Connection) vs 托管连接(Hosted Connection)
- [ ] 虚拟接口(VIF): 私有VIF vs 公有VIF vs 传输VIF
- [ ] Direct Connect网关
- [ ] Direct Connect + VPN(加密)
- [ ] Direct Connect链路聚合组(LAG)
- [ ] Direct Connect弹性(Resiliency)

### Elastic Load Balancing (ELB)
- [ ] Application Load Balancer (ALB) - Layer 7 (HTTP/HTTPS)
- [ ] ALB目标组(Target Groups)
- [ ] ALB路由规则: 基于路径、基于主机、基于HTTP头
- [ ] ALB固定响应和重定向
- [ ] ALB Lambda目标
- [ ] Network Load Balancer (NLB) - Layer 4 (TCP/UDP)
- [ ] NLB静态IP和弹性IP
- [ ] NLB跨区域负载均衡
- [ ] Gateway Load Balancer (GLB) - 第三方虚拟设备
- [ ] Classic Load Balancer (CLB) - 已过时
- [ ] ELB健康检查
- [ ] ELB访问日志
- [ ] ELB连接耗尽(Connection Draining/Deregistration Delay)
- [ ] ELB跨区域负载均衡
- [ ] ELB粘性会话(Sticky Sessions)

### Amazon Route 53
- [ ] Route 53托管区域: 公有 vs 私有
- [ ] DNS记录类型: A, AAAA, CNAME, MX, NS, PTR, SOA, SPF, SRV, TXT
- [ ] Alias记录 vs CNAME记录
- [ ] Route 53路由策略:
  - [ ] 简单路由(Simple)
  - [ ] 加权路由(Weighted)
  - [ ] 延迟路由(Latency)
  - [ ] 故障转移路由(Failover)
  - [ ] 地理位置路由(Geolocation)
  - [ ] 地理邻近路由(Geoproximity)
  - [ ] 多值应答路由(Multivalue Answer)
- [ ] Route 53健康检查
- [ ] Route 53流量策略(Traffic Flow)
- [ ] Route 53 Resolver - VPC内DNS解析
- [ ] Route 53 DNSSEC

### Amazon CloudFront
- [ ] CloudFront CDN概念
- [ ] CloudFront分配(Distribution): Web vs RTMP
- [ ] 源(Origin): S3, ALB, EC2, 自定义源
- [ ] CloudFront缓存行为和TTL
- [ ] CloudFront签名URL和签名Cookie
- [ ] CloudFront地理限制(Geo Restriction)
- [ ] CloudFront与AWS Shield和WAF集成
- [ ] CloudFront Lambda@Edge和CloudFront Functions
- [ ] CloudFront Origin Failover
- [ ] CloudFront字段级加密

### 其他网络服务
- [ ] AWS Global Accelerator - 全局网络加速
- [ ] AWS App Mesh - 服务网格
- [ ] AWS Cloud Map - 服务发现

---

## 🔗 6. 应用集成

### Amazon SQS
- [ ] SQS队列类型: 标准队列 vs FIFO队列
- [ ] SQS消息保留期(默认4天,最长14天)
- [ ] SQS可见性超时(Visibility Timeout)
- [ ] SQS死信队列(DLQ)
- [ ] SQS长轮询 vs 短轮询
- [ ] SQS延迟队列(Delay Queue)
- [ ] SQS消息大小限制(最大256KB)
- [ ] SQS批量操作
- [ ] SQS FIFO去重和消息组

### Amazon SNS
- [ ] SNS发布/订阅(Pub/Sub)模型
- [ ] SNS主题类型: 标准主题 vs FIFO主题
- [ ] SNS订阅协议: HTTP/S, Email, SMS, SQS, Lambda, Kinesis Firehose
- [ ] SNS消息过滤策略
- [ ] SNS消息属性
- [ ] SNS + SQS Fanout模式
- [ ] SNS消息加密(SSE)
- [ ] SNS访问策略

### Amazon EventBridge
- [ ] EventBridge事件总线: 默认、自定义、合作伙伴
- [ ] EventBridge事件规则(Rules)
- [ ] EventBridge事件模式匹配
- [ ] EventBridge目标: Lambda, SQS, SNS, Step Functions, Kinesis等
- [ ] EventBridge Schema Registry
- [ ] EventBridge存档和重放
- [ ] EventBridge API目标(API Destinations)
- [ ] EventBridge Pipes

### AWS Step Functions
- [ ] Step Functions状态机概念
- [ ] 状态机类型: Standard vs Express
- [ ] 状态类型: Task, Choice, Parallel, Wait, Pass, Succeed, Fail, Map
- [ ] Step Functions集成: Lambda, ECS, SNS, SQS, DynamoDB等
- [ ] Step Functions错误处理和重试
- [ ] Step Functions服务集成模式: Request Response, Run a Job, Wait for Callback
- [ ] Step Functions分布式Map

### Amazon API Gateway
- [ ] API Gateway API类型: REST API, HTTP API, WebSocket API
- [ ] API Gateway集成类型: Lambda, HTTP, AWS服务, Mock, VPC Link
- [ ] API Gateway授权: IAM, Cognito用户池, Lambda授权器
- [ ] API Gateway阶段(Stages)
- [ ] API Gateway缓存
- [ ] API Gateway限流和使用计划(Usage Plans)
- [ ] API Gateway API密钥
- [ ] API Gateway CORS配置
- [ ] API Gateway私有API(Private API)

### 其他集成服务
- [ ] Amazon AppSync - GraphQL API
- [ ] Amazon MQ - 托管消息代理(ActiveMQ, RabbitMQ)

---

## 🔒 7. 安全、身份与合规

### AWS Organizations
- [ ] Organizations组织单元(OUs)
- [ ] 服务控制策略(SCPs)
- [ ] 整合账单(Consolidated Billing)
- [ ] 跨账户访问

### AWS KMS
- [ ] KMS客户主密钥(CMK): AWS托管 vs 客户托管
- [ ] 对称密钥 vs 非对称密钥
- [ ] KMS密钥策略
- [ ] KMS授权(Grants)
- [ ] KMS密钥轮换
- [ ] KMS信封加密(Envelope Encryption)
- [ ] KMS多区域密钥
- [ ] KMS自定义密钥存储(CloudHSM)

### AWS Secrets Manager
- [ ] Secrets Manager存储和轮换密钥
- [ ] 与RDS自动集成
- [ ] Secrets Manager vs Systems Manager Parameter Store

### AWS Certificate Manager (ACM)
- [ ] ACM公有证书 vs 私有证书
- [ ] ACM证书自动续订
- [ ] ACM与CloudFront、ALB、API Gateway集成

### AWS WAF & Shield
- [ ] AWS WAF Web应用防火墙
- [ ] WAF规则组: 托管规则 vs 自定义规则
- [ ] WAF条件: IP集、字符串匹配、SQL注入、XSS
- [ ] AWS Shield Standard vs Shield Advanced
- [ ] DDoS防护

### Amazon GuardDuty
- [ ] GuardDuty威胁检测
- [ ] GuardDuty数据源: CloudTrail, VPC Flow Logs, DNS日志
- [ ] GuardDuty EKS Protection
- [ ] GuardDuty RDS Protection
- [ ] GuardDuty Malware Protection

### Amazon Inspector
- [ ] Inspector漏洞扫描: EC2, ECR, Lambda
- [ ] Inspector持续扫描
- [ ] Inspector风险评分

### Amazon Macie
- [ ] Macie敏感数据发现(PII)
- [ ] Macie S3存储桶清单
- [ ] Macie敏感数据类型

### AWS Security Hub
- [ ] Security Hub中央安全态势管理
- [ ] 合规标准: CIS, PCI DSS, AWS基础安全最佳实践
- [ ] Security Hub与GuardDuty、Inspector、Macie集成
- [ ] Security Hub自动化响应

### AWS Config
- [ ] Config配置历史记录
- [ ] Config规则: AWS托管 vs 自定义
- [ ] Config合规性检查
- [ ] Config补救操作(Remediation)

### 其他安全服务
- [ ] Amazon Detective - 安全调查
- [ ] AWS Audit Manager - 审计管理
- [ ] AWS Artifact - 合规性报告
- [ ] AWS Firewall Manager - 集中防火墙管理
- [ ] AWS Network Firewall

---

## 📊 8. 管理与监控

### Amazon CloudWatch
- [ ] CloudWatch指标(Metrics): 标准 vs 自定义
- [ ] CloudWatch命名空间、维度
- [ ] CloudWatch统计信息和周期
- [ ] CloudWatch Logs - 日志组、日志流
- [ ] CloudWatch Logs Insights - 日志查询
- [ ] CloudWatch告警(Alarms)
- [ ] 告警状态: OK, ALARM, INSUFFICIENT_DATA
- [ ] CloudWatch复合告警(Composite Alarms)
- [ ] CloudWatch Dashboards
- [ ] CloudWatch Events → Amazon EventBridge
- [ ] CloudWatch Synthetics - 金丝雀监控
- [ ] CloudWatch ServiceLens
- [ ] CloudWatch Contributor Insights
- [ ] CloudWatch Application Insights

### AWS CloudTrail
- [ ] CloudTrail API审计日志
- [ ] CloudTrail事件类型: 管理事件 vs 数据事件 vs 洞察事件
- [ ] CloudTrail日志文件完整性验证
- [ ] CloudTrail Lake - 事件数据存储和查询
- [ ] CloudTrail Insights - 异常检测
- [ ] CloudTrail与CloudWatch Logs集成

### AWS Systems Manager
- [ ] Systems Manager Session Manager - 无需SSH/RDP
- [ ] Systems Manager Run Command - 远程执行命令
- [ ] Systems Manager Patch Manager - 补丁管理
- [ ] Systems Manager State Manager - 维护实例状态
- [ ] Systems Manager Parameter Store - 配置和密钥存储
- [ ] Systems Manager Automation - 自动化运维任务
- [ ] Systems Manager Inventory - 资源清单
- [ ] Systems Manager Maintenance Windows
- [ ] Systems Manager OpsCenter

### AWS Trusted Advisor
- [ ] Trusted Advisor检查类别: 成本优化、性能、安全、容错、服务限制
- [ ] 基本支持 vs 商业/企业支持检查

### 其他管理服务
- [ ] AWS Service Catalog - 服务目录
- [ ] AWS Control Tower - 多账户治理
- [ ] AWS License Manager - 许可证管理
- [ ] AWS Managed Grafana - 可观测性仪表板
- [ ] AWS Managed Prometheus - 监控和告警

---

## 📈 9. 分析服务

### Amazon Kinesis
- [ ] Kinesis Data Streams - 实时数据流
- [ ] Kinesis分片(Shards)和容量
- [ ] Kinesis数据保留(1-365天)
- [ ] Kinesis Data Firehose - 数据传输
- [ ] Firehose目标: S3, Redshift, OpenSearch, Splunk, HTTP
- [ ] Firehose数据转换(Lambda)
- [ ] Kinesis Data Analytics - 流数据分析(SQL, Apache Flink)
- [ ] Kinesis Video Streams

### Amazon Athena
- [ ] Athena Serverless SQL查询
- [ ] Athena查询S3数据
- [ ] Athena与Glue Data Catalog集成
- [ ] Athena分区优化

### AWS Glue
- [ ] Glue ETL服务
- [ ] Glue Data Catalog
- [ ] Glue Crawler - 自动发现Schema
- [ ] Glue Job - ETL作业

### 其他分析服务
- [ ] Amazon EMR - 大数据处理(Hadoop, Spark)
- [ ] Amazon OpenSearch Service - 搜索和分析
- [ ] Amazon QuickSight - 商业智能(BI)
- [ ] AWS Data Exchange - 数据共享
- [ ] AWS Lake Formation - 数据湖管理

---

## 🐳 10. 容器服务

### Amazon ECS
- [ ] ECS任务定义(Task Definition)
- [ ] ECS服务(Service)
- [ ] ECS启动类型: EC2 vs Fargate
- [ ] ECS集群
- [ ] ECS任务放置策略
- [ ] ECS服务自动扩展
- [ ] ECS与ALB/NLB集成
- [ ] ECS服务发现(Cloud Map)
- [ ] ECS Exec - 容器调试
- [ ] ECS Anywhere

### Amazon EKS
- [ ] EKS Kubernetes控制平面
- [ ] EKS节点组: 托管节点组 vs 自管理节点组
- [ ] EKS Fargate
- [ ] EKS Pod Identity
- [ ] EKS与ALB Ingress Controller
- [ ] EKS与EBS CSI Driver
- [ ] EKS Anywhere

### Amazon ECR
- [ ] ECR私有镜像仓库
- [ ] ECR镜像扫描: 基础扫描 vs 增强扫描
- [ ] ECR生命周期策略
- [ ] ECR跨区域和跨账户复制
- [ ] ECR公共仓库(Public Gallery)

---

## 🛠️ 11. 开发工具 (CI/CD)

### AWS CodeCommit
- [ ] CodeCommit私有Git仓库
- [ ] CodeCommit分支和PR工作流

### AWS CodeBuild
- [ ] CodeBuild构建项目
- [ ] buildspec.yml配置文件
- [ ] CodeBuild构建环境(Docker镜像)
- [ ] CodeBuild与VPC集成

### AWS CodeDeploy
- [ ] CodeDeploy部署类型: In-place vs Blue/Green
- [ ] CodeDeploy部署目标: EC2, Lambda, ECS
- [ ] appspec.yml配置文件
- [ ] CodeDeploy部署配置: AllAtOnce, HalfAtATime, OneAtATime
- [ ] CodeDeploy自动回滚

### AWS CodePipeline
- [ ] CodePipeline持续交付
- [ ] Pipeline阶段: Source, Build, Test, Deploy
- [ ] CodePipeline与CodeCommit、CodeBuild、CodeDeploy集成
- [ ] CodePipeline手动审批

### 其他开发工具
- [ ] AWS CodeArtifact - 软件包管理
- [ ] AWS Cloud9 - 云IDE
- [ ] AWS X-Ray - 分布式追踪
- [ ] AWS CodeGuru - 代码审查和性能分析

---

## 💰 12. 成本管理与优化

### 成本管理工具
- [ ] AWS Cost Explorer - 成本可视化和分析
- [ ] AWS Budgets - 预算和告警
- [ ] AWS Cost and Usage Report (CUR)
- [ ] AWS Cost Anomaly Detection - 异常检测

### 定价模型
- [ ] EC2定价模型对比(按需、预留、Savings Plans、Spot)
- [ ] S3存储类别定价对比
- [ ] 数据传输成本优化

### 成本优化策略
- [ ] 右大小(Right-sizing)资源
- [ ] 使用Auto Scaling
- [ ] 删除未使用资源
- [ ] 使用AWS Compute Optimizer建议
- [ ] 标签和成本分配

---

## 🏗️ 13. 架构设计最佳实践

### AWS Well-Architected Framework
- [ ] 运营卓越支柱(Operational Excellence)
- [ ] 安全性支柱(Security)
- [ ] 可靠性支柱(Reliability)
- [ ] 性能效率支柱(Performance Efficiency)
- [ ] 成本优化支柱(Cost Optimization)
- [ ] 可持续性支柱(Sustainability)

### 高可用性设计
- [ ] 多可用区(Multi-AZ)架构
- [ ] 跨区域(Multi-Region)架构
- [ ] 故障转移和灾难恢复策略: Backup & Restore, Pilot Light, Warm Standby, Multi-Site
- [ ] 弹性设计模式

### 可扩展性设计
- [ ] 水平扩展 vs 垂直扩展
- [ ] 无状态应用设计
- [ ] 松耦合架构
- [ ] 缓存策略

### 安全最佳实践
- [ ] 深度防御(Defense in Depth)
- [ ] 最小权限原则
- [ ] 数据加密(静态和传输中)
- [ ] 日志和监控
- [ ] 安全分层

### 性能优化
- [ ] 选择合适的计算资源
- [ ] 使用CDN(CloudFront)
- [ ] 数据库优化: 索引、缓存、读副本
- [ ] 异步处理和队列

### 无服务器架构
- [ ] Lambda + API Gateway + DynamoDB模式
- [ ] S3静态网站 + CloudFront + Lambda@Edge
- [ ] 事件驱动架构

---

## 📝 学习建议

### 重点关注领域(按考试权重)
1. **高可用和弹性架构设计** (~30%)
2. **安全架构设计** (~26%)
3. **高性能架构设计** (~24%)
4. **成本优化架构设计** (~20%)

### 高频考点
- ✅ S3存储类别选择
- ✅ EC2定价模型选择
- ✅ RDS vs DynamoDB使用场景
- ✅ ALB vs NLB选择
- ✅ SQS vs SNS vs EventBridge
- ✅ 安全组 vs NACL
- ✅ Multi-AZ vs 跨区域部署
- ✅ IAM策略评估逻辑
- ✅ VPC架构设计
- ✅ 灾难恢复策略

### 学习方法
1. **理解概念** - 不要死记硬背参数
2. **场景应用** - 理解每个服务的使用场景
3. **动手实践** - 在AWS控制台实际操作
4. **做题巩固** - 通过练习题检验知识点
5. **错题总结** - 整理错题和薄弱环节

---

**祝你考试顺利! 🎉**

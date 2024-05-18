### Contents Description

Software quality assurance (SQA or simply QA) includes testing and various other activities aimed at ensuring that appropriate functionalities have been implemented correctly and efficiently in the software systems or software-related products or services to satisfy the requirements, needs and wants, and expectations of their target customers and users.

One important feature of this course is the user-centered perspective of software quality, testing, and QA. User requirements for new systems and usage models of existing systems or alternative systems will be the starting point and focus of our course. Quality metrics meaningful to the users will be used throughout the QA and SQE (Software Quality Engineering) process.

Another important feature of this course is the focus on the "prioritized" (or "risk-based") approach to testing and quality assurance. For any realistic system today, exhaustive testing and similar quality assurance approaches would be infeasible because of the increasing size and complexity. We will focus on the "kay" areas/goals/components/etc., related to importance/criticality (externally defined priority), likely defects (defect-based), usage frequencies (usage-based), etc., for our testing and QA effort.

We will devote slightly more than half of the class time to topics related to software testing, or executing the software in order to observe its behavior to ensure that it conforms to our expectations or to identify behavior deviations and possible underlying problems for correction. We will emphasis formal/systematic testing techniques and their applications, including:

- black-box or functional testing, with a focus on covering (or thoroughly testing) external functions or services required or expected by target customers and users;
- clear/transparent/white-box or structural testing; with a focus on covering (or verifying/testing) implementation details, including internal components and structures;
- usage-based statistical testing (UBST), with a focus on adequately testing operations or services important to and commonly used by target customers and users to ensure overall product or system reliability (a quality view most meaningful to customers and users) after product delivery or system deployment.

These testing techniques are organized by their underlying models:

- Testing techniques based on "flat" structures, such as lists, (top-down) partitions and (bottom-up) equivalent classes, include t1) basic partition testing (PT), t2) input domain boundary testing (BT), and t3) Musa's operational profiles (Musa OP) or usage model for UBST.
- Testing techniques based on finite-state machines (FSM) and related variations include t4) basic FSM testing to, t5) control flow testing (CFT), t6) data dependency analysis and data flow testing (DFT), and t7) Markov operational profiles (Markov OP) for UBST.
- Notice that t3 and t7 above are usage-based, while the others can be either BBT or WBT in perspective, resulting in a total number of 12 variations of formal/systematic testing techniques.
  (Note: These testing techniques will be the candidates to be selected for implementation in your course project. -- More details later.)

These models will help us prepare, perform, and perfect (manage/improve) testing to achieve functional or structural coverage or to mimic realistic usage scenarios in a systematic way to ensure overall product/system quality and reliability.

Specific testing techniques to be covered: Besides the formal/systematic ones mentioned above (t1-t7: PT, BT, Musa-OP/UBST, FSM, CFT, DFT, Markov-OP/UBST), we will also briefly cover various forms of informal or ad-hoc testing, checklists, fault injection and mutation testing. Specialized testing techniques for specific purposes and/or applicable to different application domains, such as usability testing, Web testing, Cloud (and API) testing, embedded system testing, performance and stress testing, etc. will also be briefly covered.

Test activities, management, automation, and related issues, such as team organization, testing process, people's roles and responsibilities, user involvement (user-centered testing/QA), test automation tools, test integration, etc., will be briefly discussed. Applicability and effectiveness of specific testing techniques in different sub-phases and for different purposes will also be briefly discussed.

The rest of the class time, beyond various testing-related topics mentioned above, will be devoted to the following topics:

- General concepts about quality, quality assurance (QA), and software quality engineering (SQE). Concepts related to quality will be covered, including reliability, safety, security, usability, dependability, maintainability, availability, etc., primarily from a user's perspective. QA activities and SQE process will also be discussed, in the context of overall software development and maintenance processes, with customer involvement.
- Other QA alternatives beyond testing, including, activities and related techniques for defect prevention and process improvement, inspection/review/walkthrough, formal verification (and its prerequisite, formal specification, briefly), fault tolerance and safety assurance. A good understanding of each alternative's relative strengths and weaknesses will help us construct and carry out a comprehensive QA strategy that more often than not will include and integrate several such alternatives.
- Quality assessment and improvement, including, overall strategy for quantifiable quality improvement, measurement and feedback mechanisms, quality models and measurements, defect classification and analysis, risk identification and analysis, and software reliability engineering. These activities will help us monitor, assess, improve the overall SQE process to achieve our quality and reliability goals effectively and efficiently.

> 软件质量保证（SQA或简称QA）包括测试和其他多种活动，旨在确保在软件系统或与软件相关的产品或服务中正确且高效地实现了适当的功能，以满足目标客户和用户的要求、需求、期望。
>
> 本课程的一个重要特点是软件质量、测试和QA的用户中心视角。新系统的用户需求和现有系统或替代系统的使用模式将是我们课程的起点和焦点。我们将在QA和SQE（软件质量工程）过程中使用对用户有意义的质量指标。
>
> 另一个重要特点是重点关注测试和质量保证的“优先级”（或“基于风险”的）方法。对于今天的任何现实系统，由于大小和复杂性的增加，穷尽测试和类似的质量保证方法是不可行的。我们将关注测试和QA工作的“关键”领域/目标/组件等，这些关键点与重要性/关键性（外部定义的优先级）、可能的缺陷（基于缺陷）、使用频率（基于使用）等相关。
>
> 我们将把略多于一半的课程时间用于与软件测试相关的主题，即执行软件以观察其行为，确保它符合我们的期望或识别行为偏差和可能的底层问题以进行纠正。我们将强调正式/系统化的测试技术及其应用，包括：
>
> - 黑盒或功能测试，重点是覆盖（或彻底测试）目标客户和用户所要求或期望的外部功能或服务；
> - 明确/透明/白盒或结构测试；重点是覆盖（或验证/测试）实现细节，包括内部组件和结构；
> - 基于使用的统计测试（UBST），重点是充分测试对目标客户和用户重要且常用的操作或服务，以确保产品交付或系统部署后的整体产品或系统可靠性（对客户和用户最有意义的质量视角）。
>
> 这些测试技术是基于它们的底层模型组织的：
>
> - 基于“平面”结构的测试技术，如列表、（自上而下的）分区和（自下而上的）等效类，包括t1)基本分区测试（PT），t2)输入域边界测试（BT），和t3)Musa的操作配置文件（Musa OP）或UBST的使用模型。
> - 基于有限状态机（FSM）及其相关变体的测试技术包括t4)基本FSM测试，t5)控制流测试（CFT），t6)数据依赖性分析和数据流测试（DFT），以及t7)马尔可夫操作配置文件（Markov OP）用于UBST。
> - 注意，t3和t7以上是基于使用的，而其他的可以是BBT或WBT的视角，结果是共有12种形式的正式/系统化测试技术。 （注意：这些测试技术将是选定用于课程项目实施的候选技术。--稍后将提供更多细节。）
>
> 这些模型将帮助我们准备、执行和完善（管理/改进）测试，以实现功能或结构覆盖，或模拟现实使用场景的系统方法，以确保整体产品/系统质量和可靠性。
>
> 特定要覆盖的测试技术：除了上述提到的正式/系统化技术（t1-t7: PT, BT, Musa-OP/UBST, FSM, CFT, DFT, Markov-OP/UBST），我们还将简要介绍各种非正式或临时测试、清单、故障注入和变异测试。针对特定目的和/或适用于不同应用领域的专门测试技术，如可用性测试、Web测试、云（和API）测试、嵌入式系统测试、性能和压力测试等，也将简要介绍。
>
> 测试活动、管理、自动化和相关问题，如团队组织、测试过程、人员角色和责任、用户参与（以用户为中心的测试/QA）、测试自动化工具、测试集成等，将简要讨论。特定测试技术在不同子阶段和不同目的的适用性和有效性也将简要讨论。
>
> 除了上述提到的各种测试相关主题之外，课程剩余时间将用于以下主题：
>
> - 关于质量、质量保证（QA）和软件质量工程（SQE）的一般概念。将讨论与质量相关的概念，包括可靠性、安全性、安全性、可用性、可依赖性、可维护性、可用性等，主要从用户的视角出发。QA活动和SQE过程也将讨论，作为整个软件开发和维护过程的一部分，涉及客户参与。
> - 测试之外的其他QA替代方案，包括缺陷预防和过程改进活动及相关技术、检查/审查/走查、正式验证（及其前提条件，简要介绍正式规范）、容错和安全保障。对每种替代方案的相对优势和劣势的良好理解将帮助我们构建和执行一个综合的QA策略，这一策略通常会包括并整合几种这样的替代方案。
> - 质量评估和改进，包括可量化质量改进的总体策略、测量和反馈机制、质量模型和测量、缺陷分类和分析、风险识别和分析，以及软件可靠性工程。这些活动将帮助我们监控、评估、改进整个SQE过程，以有效、高效地实现我们的质量和可靠性目标。
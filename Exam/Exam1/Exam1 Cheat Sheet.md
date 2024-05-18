# Exam1 Cheat Sheet 

### Software Quality Assurance (SQA) Cheat Sheet

#### I. Quality Attributes & Techniques

- **Quality Attributes:**

  - Reliability: The ability of software to perform under specified conditions for a specified period.
  - Safety: The software's ability to operate without causing unacceptable risk of harm or loss.
  - Capability/Functionality: The degree to which software fulfills its specified requirements.
  - Maintainability: Ease with which software can be modified to correct faults, improve performance, or adapt to a changed environment.
  - Usability: The ease with which users can learn and use the software.
  - Security: The ability of software to protect against unauthorized access or modifications.
  - Portability: The ease with which software can be transferred from one environment to another.

  > **质量属性:**
  >
  > - 可靠性：软件在指定条件下为指定期间执行的能力。
  > - 安全性：软件操作不会引起不可接受的风险或损失的能力。
  > - 功能性/能力：软件满足其指定要求的程度。
  > - 可维护性：软件为更正错误、提高性能或适应变化的环境而被修改的容易程度。
  > - 可用性：用户学习和使用软件的容易程度。
  > - 安全性：软件保护防止未经授权的访问或修改的能力。
  > - 可移植性：软件从一个环境转移到另一个环境的容易程度。

- **Quality Attributes Not Discussed:**

  - Cost/Affordability: While important, not typically classified as a quality attribute in software engineering.

  > **未讨论的质量属性:**
  >
  > - 成本/负担能力：虽然重要，但在软件工程中通常不被分类为质量属性。

#### II. QA Techniques Classification

- **Defect Prevention (Process Improvement):** Techniques aimed at preventing defects by enhancing development processes.
- **Defect Removal (Inspection, Testing):** Techniques focused on identifying and removing defects from software artifacts.
- **Defect Containment (Safety Assurance, Fault Tolerance):** Techniques designed to ensure software can operate safely even when faults occur.

> #### QA 技术分类
>
> - **缺陷预防（过程改进）:** 通过增强开发过程来预防缺陷的技术。
> - **缺陷移除（审查、测试）:** 专注于从软件工件中识别和移除缺陷的技术。
> - **缺陷包容（安全保证、容错）:** 设计以确保软件即使在出现故障时也能安全运行的技术。



#### III. Software Quality Engineering (SQE) Process

- Includes:
  - Quality Planning
  - Quality Assurance Strategy Formation
  - Quality Measurement and Model Determination
  - Quality Assurance Activity Execution
  - Quality Measurement and Analysis
  - Feedback and Adjustment

> #### 软件质量工程 (SQE) 过程
>
> - 包括:
>   - 质量规划
>   - 质量保证策略形成
>   - 质量测量和模型确定
>   - 质量保证活动执行
>   - 质量测量和分析
>   - 反馈和调整



#### IV. Testing Techniques

- **Formal/Systematic Testing Techniques:**
  - Typically, more than one technique is needed for comprehensive testing of a software product/system.
- **Types of Testing Based on Coverage:**
  - Black Box Testing (BBT) and White Box Testing (WBT) are both coverage-based testing methods.
  - BBT focuses on external/user’s perspective without considering internal workings.
  - WBT focuses on internal/developer’s perspective, considering the software's structure.

> ####  测试技术
>
> - **正式/系统测试技术:**
>   - 通常，需要多种技术来全面测试软件产品/系统。
> - **基于覆盖的测试类型:**
>   - 黑盒测试 (BBT) 和白盒测试 (WBT) 都是基于覆盖的测试方法。
>   - BBT 关注外部/用户的视角，不考虑内部工作。
>   - WBT 关注内部/开发者的视角，考虑软件的结构。

#### V. Musa-OP Construction for UBST

- Usage Scenarios for Testing:
  - Successful login on first attempt (70%)
  - Incorrect password corrected on second attempt (20%)
  - Attempt to login with a username that doesn't exist (10%)

> #### 使用Musa-OP 构建UBST
>
> - 测试的使用场景:
>   - 第一次尝试成功登录（70%）
>   - 第二次尝试中更正错误密码（20%）
>   - 尝试使用不存在的用户名登录（10%）

#### VI. Common Misconceptions

- Inspection vs. Testing Costs:
  - The assumption that inspection personnel costs are always 4 times that of testing is an oversimplification. Effectiveness in finding and fixing defects early can lead to overall cost savings.

> - 审查与测试成本:
>   - 假设审查人员成本总是测试的4倍是一种过于简化的观点。早期有效地发现和修复缺陷可以带来总体成本节约。



#### VII. Practical Testing Insights

- **Detecting Missing Requirements:**
  - Black Box Testing (BBT) is most effective in detecting problems with missing requirements by focusing on the external behavior of the software system.
- **Differences Between SQE and Testing:**
  - SQE is a broader process encompassing all aspects of software quality, including planning, assurance, measurement, and improvement. Testing is a component of SQE focused on identifying defects through execution.

> - **检测缺失的需求:**
>   - 黑盒测试 (BBT) 通过关注软件系统的外部行为，最有效地检测缺失需求的问题。
> - **SQE与测试的差异:**
>   - SQE是一个更广泛的过程，包括所有软件质量方面的规划、保证、测量和改进。测试是SQE的一个组成部分，专注于通过执行来识别缺陷。





##==2.7 Defining Quality in SQE==

* Quality: views and attributes

  <img src="./Exam1 Cheat Sheet/Screenshot 2024-02-17 at 01.17.43.png" alt="Screenshot 2024-02-17 at 01.17.43" style="zoom:50%;" />

* SQE focus: correctness-related.
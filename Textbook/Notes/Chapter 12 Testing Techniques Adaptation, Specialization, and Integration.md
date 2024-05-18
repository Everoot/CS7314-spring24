# Chapter 12 Testing Techniques: Adaptation, Specialization, and Integration

For large-scale testing for today’s large and complexity software systems, many tasks are carried out to fulfill multiple goals and objectives. Different testing techniques might be used and integrated, and many resources are also involved. In this chapter, we examine these issues in detail, including, 

* Individual testing sub-phases and appropriate techniques for them are discussed in Section 12.1. 

* Other specialized tasks and specialized testing techniques are described in Section 12.2. 
* Integration of different testing techniques covered in the previous chapters to fulfill some specific purposes in practical applications are described in Section 12.3, and illustrated through a strategy for web testing that integrates both usage-based and coverage-based testing at different levels in Section 12.4.

> 在今天的大型和复杂软件系统的大规模测试中，进行了许多任务以实现多个目标和目的。可能会使用和整合不同的测试技术，而且涉及许多资源。在本章中，我们将详细探讨这些问题，包括：
>
> - 第12.1节讨论了各个测试子阶段及其适用的技术。
> - 第12.2节描述了其他专业任务和专业测试技术。
> - 第12.3节描述了前几章覆盖的不同测试技术的整合，以在实际应用中实现一些特定目的，并通过第12.4节中的一个策略示例来说明，该策略集成了在不同层次上基于使用的和基于覆盖的测试的网页测试。

## 12.1 TESTING SUB-PHASES AND APPLICABLE TESTING TECHNIQUES

For large-scale testing, typically multiple testing techniques are used to test multiple objects. The test activities spread out over time, lasting over months or more than a year. The overall testing is commonly divided further into various sub-phases to allow testing to be carried out in a smaller, more manageable scale. In this section, we examine the problems and focuses of these sub-phases and suitable testing techniques for them.

> 在大规模测试中，通常会使用多种测试技术来测试多个对象。测试活动会贯穿数月甚至超过一年的时间。整体测试通常进一步细分为各种子阶段，以便在更小、更易管理的规模上进行测试。在本节中，我们将探讨这些子阶段的问题和焦点，以及适合它们的测试技术。

<img src="./Chapter 12 Testing Techniques Adaptation, Specialization, and Integration/Screenshot 2024-04-01 at 10.40.23.png" alt="Screenshot 2024-04-01 at 10.40.23" style="zoom:50%;" />

Testing sub-phases Figure 12.1 illustrates the testing sub-phases through the use of V-model, a variation of the commonly used waterfall process with an emphasis on verification and validation activities. 
It shows an annotated V-model with additional information about the specific testing subphases. All the sub-phases not included in the original V-model are shown in dashed boxes, with their relationship to the other sub-phases also illustrated. Specific information about these sub-phases is described below: 

* When problems are reported by customers during operational use, diagnosis testing can be used to recreate and diagnose the problems. Diagnosis testing can also be used for other sub-phases of testing for the same purpose as well, as illustrated by the downward arrow in Figure 12.1. 
* Controlled product release and operational use by limited customers lead to beta testing. Beta testing can be considered as an additional testing sub-phase closely linked to operational use. It often directly precedes operational use or is carried out at the very beginning of it, as depicted accordingly in Figure 12.1. 
* A special testing sub-phases, acceptance testing, is attached to the end of system testing, because it is typically performed right after system testing to determine if the product should be released. Sometimes, the late part of system testing is used as acceptance test instead of a dedicated acceptance testing sub-phases. Therefore, we also show possible overlap between the two in Figure 12.1. 
* As a direct division of the testing phase in the waterfall process, several specific subphases of testing, such as system testing, integration testing, and component testing have already been represented in the V-model originally. Therefore, no modification or annotation is necessary to represent these sub-phases in Figure 12.1.

* Similarly, unit testing is depicted as is, both as a sub-phase of overall testing and as a part of the coding-and-unit-testing phase. 
* A special case is regression testing, which typically spreads over the overall test activities for new product releases based on previous ones or other similar products. However, since a significant part of tlhe existing product is used, the focus of regression testing is typically on the integration testing sub-phase and thereafter, where old and new product components are integrated. On the other hand, the unit and component testing for the new components are similar to those for traditional new products. The existing components can typically forgo full-fledged unit and component testing, while only subjected to testing focused on interface and interaction problems with the new components, typically in the integration testing sub-phase and after. Therefore, we depict regression testing in Figure 12.1 as linked to integration testing, with an additional arrow pointing to later testing sub-phases.

> 
> 图12.1通过使用V模型来说明测试子阶段，V模型是常用瀑布流程的一种变体，强调了验证和确认活动。它展示了一个带有额外信息的注释V模型，关于特定测试子阶段的信息。所有未包括在原始V模型中的子阶段都显示在虚线框中，它们与其他子阶段的关系也得到了说明。关于这些子阶段的具体信息如下所述：
>
> - 当客户在操作使用期间报告问题时，可以使用诊断测试来重现和诊断问题。诊断测试也可用于测试的其他子阶段，以实现相同的目的，如图12.1中的向下箭头所示。
> - 有限客户的控制产品发布和操作使用导致了beta测试。Beta测试可以被视为一个与操作使用紧密相关的额外测试子阶段。它通常直接在操作使用之前或在其开始时进行，如图12.1所示。
> - 一个特殊的测试子阶段，验收测试，附加在系统测试的末尾，因为它通常在系统测试之后立即执行，以确定产品是否应该发布。有时，系统测试的后期部分被用作验收测试而不是一个专 dedicated的验收测试子阶段。因此，我们也在图12.1中显示了两者之间可能的重叠。
> - 作为瀑布流程中测试阶段的直接划分，几个特定的测试子阶段，如系统测试、集成测试和组件测试已经在原始的V模型中表示。因此，无需修改或注释就可以在图12.1中表示这些子阶段。
> - 同样，单元测试被视为整体测试的一个子阶段，也是编码和单元测试阶段的一部分。
> - 回归测试是一个特例，它通常贯穿于基于先前产品或其他类似产品的新产品发布的整个测试活动。然而，由于使用了相当一部分现有产品，回归测试的焦点通常在集成测试子阶段及其之后，旧产品和新产品组件被集成的地方。另一方面，新组件的单元和组件测试类似于传统新产品的测试。现有组件通常可以不进行完整的单元和组件测试，而只接受针对与新组件的接口和交互问题的测试，通常在集成测试子阶段及之后。因此，我们在图12.1中将回归测试与集成测试联系起来，并增加了一个指向后续测试子阶段的额外箭头。



**Unit testing for implementation details**

Unit testing tests a small software unit at a time, which is typically performed by the individual programmer who implemented the unit. Depending on the different programming languages used, this unit may correspond to a function, a procedure, or a subroutine for traditional structured programming languages such as C, PASCAL, or FORTRAN, or correspond to a method in object-oriented languages such as C++, Java, and Smalltalk. 

Unit testing typically focuses on the implementation details and uses white-box testing techniques, with various coverage criteria as the exit criteria. It typically focuses on the executable statements and related control and data elements. The commonly used testing techniques for unit testing include: 

* Ad hoc testing or informal debugging are often used to execute the unit in isolation, typically with the help of some debugging tools to relate specific execution state to the execution of specific statements. Complete statement coverage is a common goal for such testing. For units where interaction with other units is essential, a specific testing environment or testbed may need to be used to simulate this interaction without actually involving other units. 

* Input domain partitions based on input variables for the unit are often used to perform input domain partition testing and related boundary testing, as described in Chapter 8. 
* Various traditional structural testing techniques, such as control flow testing (CFT) and data flow testing (DFT) described in Chapter 11, are often used, with the models 'built based on analyzing the code through control flow analysis and data dependency analysis. 

Black-box testing could also be performed on the unit, while focusing on the inputoutput relations. However, it is used much less frequently than white-box coverage testing because of the implementation knowledg,e possessed by the programmers who test their own code.

> **单元测试的实现细节**
>
> 单元测试一次测试一个小的软件单元，通常由实现该单元的个别程序员执行。根据使用的不同编程语言，这个单元可能对应于传统结构化编程语言（如C、PASCAL或FORTRAN）中的一个函数、过程或子程序，或对应于面向对象语言（如C++、Java和Smalltalk）中的一个方法。
>
> 单元测试通常关注实现细节，并使用白盒测试技术，以各种覆盖标准作为退出标准。它通常关注可执行语句及相关的控制和数据元素。常用于单元测试的技术包括：
>
> - 临时测试或非正式调试经常用于独立执行单元，通常借助某些调试工具将特定执行状态与特定语句的执行关联起来。完全语句覆盖是这种测试的常见目标。对于与其他单元的交互至关重要的单元，可能需要使用特定的测试环境或测试床来模拟这种交互，而实际上不涉及其他单元。
> - 基于单元的输入变量进行输入域划分，常用于执行输入域划分测试和相关的边界测试，如第8章所述。
> - 各种传统的结构测试技术，如控制流测试（CFT）和数据流测试（DFT），如第11章所述，经常被使用，模型是基于通过控制流分析和数据依赖分析来分析代码构建的。
>
> 黑盒测试也可以在单元上执行，同时关注输入输出关系。然而，由于编程者测试自己的代码时拥有的实现知识，黑盒覆盖测试使用得不如白盒测试频繁。



**Component testing for implementation details and specific functions**

Component testing tests a software component at a time, typically by a small group of developers. A component generally includes a collection of smaller units that together accomplish something or form an object. For traditional software products, such as those developed using structured programming and high-level structured programming languages such as C, PASCAL, and FORTRAN, there isn’t a clear-cut distinction between units and components, except that components are general larger and each of them typically includes a few units. Consequently, component testing is almost identical to unit testing, except at a slightly larger scale. 

For some new programming models and software development paradigms, component testing and unit testing are more likely to be different. For example, for object-oriented (00) systems, a components is typically an object or a class, which include both the internally defined data objects as well as the pre-defined operations (or methods) on them.  Although the same white-box approach for unit testing can still be used for testing such components, it runs contrary to information hiding principle, one of the fundamental ideas in object-orientation. Black-box view is more in line with such objects as components.  Corresponding black-box testing techniques or usage-based testing techniques can be used, similar to those we describe with system testing below. In addition, some recent work has been focused on adapting traditional testing techniques to work for object-oriented systems (Binder, 2000; Kung et al., 1998), which attempts to adapt use cases and design pattern ideas in testing as well as in product development. 

The increasing use of software development based on COTS (commercial-off-the shelf) components and CBSE (component based software engineering, or CBSD componentbased software development) has also altered people’s perception of component testing. In such paradigms, components play a much more important role, which also increases the need for us to ensure and demonstrate the quality and reliability of individual components. Independent testing and certification of software components or reusable parts is key to the possible selection, use, and adoption of certain software components. Therefore, independent verification and validation (IV&V) by third-party participants described in Chapter 7 are often performed for such situations. As for the testing techniques used, the situation is similar to system testing we describe later in this section, where black-box and usage-based techniques dominate, but at a smaller scale.

> **组件测试的实现细节和特定功能**
>
> 组件测试一次测试一个软件组件，通常由一小组开发人员执行。组件通常包括一系列较小的单元，这些单元共同完成某项任务或形成一个对象。对于传统软件产品，例如那些使用结构化编程和高级结构化编程语言（如C、PASCAL和FORTRAN）开发的产品，并没有清晰的区分单元和组件，除了组件通常更大，每个组件通常包括几个单元。因此，组件测试几乎与单元测试相同，只是规模稍大。
>
> 对于一些新的编程模型和软件开发范式，组件测试和单元测试更可能有所不同。例如，对于面向对象（OO）系统，一个组件通常是一个对象或一个类，它包括内部定义的数据对象以及对它们预定义的操作（或方法）。虽然可以使用与单元测试相同的白盒方法来测试此类组件，但这与对象导向的基本理念之一——信息隐藏原则相悖。黑盒视角更符合将这些对象视为组件的观点。可以使用相应的黑盒测试技术或基于使用的测试技术，类似于我们在下面描述的系统测试中使用的技术。此外，一些最近的工作集中在将传统测试技术适应于面向对象系统（Binder, 2000; Kung et al., 1998），这尝试在测试以及产品开发中适应用例和设计模式的想法。
>
> 基于COTS（现成的商业软件组件）和CBSE（基于组件的软件工程，或CBSD基于组件的软件开发）的软件开发的日益使用，也改变了人们对组件测试的看法。在这些范式中，组件扮演了更重要的角色，这也增加了我们确保和展示单个组件的质量和可靠性的需求。软件组件或可重用部件的独立测试和认证是可能选择、使用和采用某些软件组件的关键。因此，第三方参与者所执行的独立验证和确认（IV&V），如第7章所述，常常用于此类情况。就使用的测试技术而言，情况与我们在本节后面描述的系统测试类似，其中黑盒和基于使用的技术占主导地位，但规模较小。



**Integration testing for interface and interactions**

Integration testing deals with the integration of different product components to work together, with the focus on interface and interaction problems among these components.  Therefore, in integration testing, each component is treated as an atomic unit or as a blackbox, while the interconnections among them are examined and modeled to test component interfaces and interactions. Most of the integration testing uses white-box testing techniques. However, the individual units are no longer individual statements or programming unit, but individual components instead. Again, coverage is typically used as the exit criterion for such testing. From integration testing onward, testing is typically performed by dedicated professional testers.

The execution control in such integration situations typically passes from one component to another and back-and-forth, which can be modeled by a finite-state machine (FSM). Therefore, FSM-based testing described in Chapter 10. is often used to cover the different states and transitions to ensure correct handling of interfaces, interactions, and execution control.

Sometimes, we may choose to adopt a completely black-box view for integration testing, and treat the whole collection of the components to be integrated as a black-box and test it accordingly. This view is similar to the system testing view below, and the testing techniques also correspond to those used in system testing. In fact, in many organizations, integration testing is considered as part of system testing instead of a separate testing sub-phase. We make the distinction in this book, using integration testing to indicate the part of testing that focuses on the interface and interactions among different product components, and using system testing to indicate the part of testing that focuses on the overall system operations.

> **集成测试：针对接口和交互的测试**
>
> 集成测试处理的是不同产品组件的整合，使其能够一起工作，重点在于这些组件之间的接口和交互问题。因此，在集成测试中，每个组件被视为一个原子单元或黑盒，同时检查并建模它们之间的连接以测试组件接口和交互。大多数集成测试使用白盒测试技术。然而，个别单元不再是个别声明或编程单元，而是个别组件。同样，覆盖率通常用作此类测试的退出标准。从集成测试开始，测试通常由专业测试人员执行。
>
> 在此类集成情况下的执行控制通常从一个组件传递到另一个组件，来回转换，这可以通过有限状态机（FSM）来建模。因此，如第10章所描述的基于FSM的测试经常用于覆盖不同的状态和转换，以确保正确处理接口、交互和执行控制。
>
> 有时，我们可能选择采取完全黑盒视角进行集成测试，并将要集成的所有组件的集合视为一个黑盒相应地进行测试。这种视角类似于下面的系统测试视角，测试技术也对应于系统测试中使用的技术。实际上，在许多组织中，集成测试被视为系统测试的一部分，而不是一个独立的测试子阶段。在本书中，我们进行了区分，使用集成测试来指代专注于不同产品组件之间的接口和交互的测试部分，并使用系统测试来指代专注于整个系统操作的测试部分。



**System testing for overall system operations**

System testing tests the overall system operations as a whole, typically from a customer’s perspective. The primary concern is how the software system works as a whole under the operational environment of actual customers. Therefore, in system testing, the whole system is treated as a black-box, where external functions are tested. In addition, because of the customer’s perspective adopted for this testing sub-phase, usage-based statistical testing techniques are often used. 

Because of this concern and perspective, the entities to be tested stay at fairly high levels of abstraction. For example, high-level functions or components may be tested, typically those directly visible to the customers, but not implementation details or those elements far removed from customers. As for the team who performs the testing, knowledge about overall product functions, application domain and market segment, and customer expectations and their usage of the system is more important than product implementation details. The commonly used techniques include: 

* High-level functional checklists are often used to ensure that all the major functions expected by the customers are present and perform satisfactorily. We can either try to achieve complete coverage of all major functions, therefore resulting in coveragebased testing, or to achieve reliability goals by emphasizing functions important to and frequently used by customers, resulting in usage-based statistical testing. With the latter technique variation, Musa’s operational profile (OP) can be used. Both these coverage-based and usage-based system testing techniques were covered in Chapter 8. 
* Finite-state machines (FSMs) for the above system functions may be constructed for more systematic testing than merely using the checklists above. Each state here represents a major function expected by and visible to target customers. These testing models and techniques are black-box ones, because they are based on external functions instead of internal implementations. Various coverage criteria can be used as stopping criteria. 
* Similar to the way Musa OP enhances checklist to perform usage-based testing for direct reliability assurance. Markov OPs enhanced from FSMs can be used for usagebased statistical testing, as described in Chapter 10.

For embedded software systems or for heterogeneous systems with important software components, such as software controlled medical equipment and modern telecommunication networks, the term “system” typically means the complete system with the software part as a component or a sub-system. In such systems, system testing takes on additional meaning as well, which we refer to as super-system testing. Both integration testing and system testing described above can be applied to such super-system testing, to check for interface, interaction, and interoperability problems among different sub-systems, as well as to check for the overall super-system operations as a whole.

> **系统测试：针对整体系统操作**
>
> 系统测试测试整个系统的运作，通常从客户的角度出发。主要关注是软件系统作为一个整体在实际客户的操作环境下如何工作。因此，在系统测试中，整个系统被视为一个黑盒，其中测试外部功能。此外，由于采用了客户的视角，经常使用基于使用的统计测试技术。
>
> 因为这种关注和视角，被测试的实体保持在相当高的抽象级别。例如，可能测试高级功能或组件，通常是那些客户直接可见的，而不是实现细节或那些与客户相距甚远的元素。至于执行测试的团队，对整个产品功能、应用领域和市场细分的了解，以及客户的期望和他们使用系统的方式比产品实现细节更重要。常用的技术包括：
>
> - 高级功能检查表经常被用来确保所有客户期望的主要功能都存在并且表现令人满意。我们可以试图实现所有主要功能的完全覆盖，因此导致基于覆盖的测试，或通过强调对客户重要且经常使用的功能来实现可靠性目标，从而导致基于使用的统计测试。对于后一种技术变体，可以使用Musa的操作配置文件（OP）。这些基于覆盖和基于使用的系统测试技术都在第8章中介绍过。
> - 可以为上述系统功能构建有限状态机（FSMs），以实现比仅使用上述检查表更系统化的测试。这里的每个状态代表客户期望并对目标客户可见的主要功能。这些测试模型和技术是黑盒的，因为它们基于外部功能而不是内部实现。可以使用各种覆盖标准作为停止标准。
> - 类似于Musa OP增强检查表以执行基于使用的测试以直接保证可靠性的方式。从FSMs增强的Markov OPs可以用于基于使用的统计测试，如第10章所述。
>
> 对于嵌入式软件系统或具有重要软件组件的异构系统，如软件控制的医疗设备和现代通信网络，“系统”通常意味着带有软件部分作为一个组件或子系统的完整系统。在这些系统中，系统测试也具有额外的意义，我们将其称为超级系统测试。上述的集成测试和系统测试都可以应用于这种超级系统测试，以检查不同子系统之间的接口、交互和互操作性问题，以及检查整个超级系统的整体操作。



**Acceptance testing and product release**

In most organized development in mature software organizations, some form of acceptance testing is usually performed as the final sub-phase of testing to determine if the product should be released. Related questions also include: 

* What is the expectations of product reliability in customer settings if the product is released now?  
* What is the appropriate level of post-release product support?

Sometimes, acceptance testing can be a part of system testing, typically the last part that answers the product release questions. However, we distinguish it from regular system testing by the different focuses as well as the differences in defect fixing possibilities: In regular system testing, all major problems observed will be fixed before product release; while in acceptance testing, we assume that the problems will not be fixed because of imminent product release. The discovered problems in acceptance testing will be dealt with during post-release product support. In practical applications, critical problems observed in acceptance testing could cause costly delays to pre-planned and often pre-announced product release. The cost of delay needs to be weighed against the cost of delivering a product with major flaws, in order to arrive at a product release decision. 

In terms of testing techniques, the ones usable for system testing are all potentially usable for acceptance testing. But with the focus on product release decisions and expected post-release product support, usage-based statistical testing techniques are typically favored over traditional black-box testing because of their direct linkage to reliability. Repeated random sampling without defect fixing (in statistical terms, without replacement) supported by either Musa or Markov OPs mentioned above is often used for acceptance testing.

> 在成熟的软件组织中的大多数有组织的开发中，通常会执行某种形式的验收测试作为测试的最终子阶段，以确定产品是否应该发布。相关问题还包括：
>
> - 如果现在发布产品，客户环境中的产品可靠性预期是什么？
> - 适当的发布后产品支持水平是什么？
>
> 有时，验收测试可以是系统测试的一部分，通常是回答产品发布问题的最后一部分。然而，我们将其与常规系统测试区分开来，因为焦点不同以及缺陷修复的可能性不同：在常规系统测试中，观察到的所有主要问题将在产品发布前修复；而在验收测试中，我们假设由于产品即将发布，问题将不会被修复。验收测试中发现的问题将在发布后的产品支持期间处理。在实际应用中，验收测试中观察到的关键问题可能会导致预计划且经常预先宣布的产品发布的昂贵延迟。延迟的成本需要与交付带有主要缺陷的产品的成本相权衡，以做出产品发布决策。
>
> 就测试技术而言，适用于系统测试的技术都可能适用于验收测试。但是，由于关注于产品发布决策和预期的发布后产品支持，基于使用的统计测试技术通常比传统的黑盒测试受到更多青睐，因为它们与可靠性直接相关。经常使用上述提到的Musa或Markov操作配置文件（OPs）支持的重复随机抽样而不修复缺陷（在统计学术语中，不替换）用于验收测试。



**Beta testing and testing based on operational problems**

Although usage-based statistical testing can be used to ensure product reliability from the user’s perspective, there are various limitation to the accuracy and practicality of these techniques. For example, the collection of information about actual usage scenarios, sequences, and patterns is often hindered or completely blocked by proprietary nature of such information, because much of it may be business sensitive. In addition, the diversity of customers and related population pool also present major obstacles in constructing OPs that are accurate for everyone involved. 

An alternative to bring information “in” for usage-based testing is to ship the software product “out” in controlled release so that likely problems to be experienced by the general user population can be exposed and corrected before general product release. This model is commonly referred to as beta testing. The benefit is obvious and significant, especially for product with wide release and large user pool, and when usage-based statistical testing is inadequate. However, the cost of running such a testing program is also significant, including:

* Direct cost and limitations of running beta tests: A large enough and representative set of customers and users have to be identified; and the relationship with them often needs to be nurtured over a long pleriod of time to gain their trust and cooperation. Sometimes, other criteria instead of representativeness can be used for selection of beta test customers, such as selecting customers who reported most field defects to effectively reduce such chances for similar problems after product release. 
* Indirect cost in product delays could be significant, because beta test not only takes time to run, it also takes time and effort to prepare. In addition, enough time should be allowed for customers and users to get familiar with the product and start to use its full set of functionalities. 

Therefore, whether to run a beta test, and what kind of beta test to run, its scope and length, etc., all need to be decided with all the factors considered. The general trend for increasing numbers of software products is to run some beta tests. In fact, direct involvement of the massive numbers of users who use the products and report problems, much similar to beta testing, but at a larger scale, has been credited as an important reason for high quality of various open source and Internet-based products (Raymond, 1999; Vixie, 1999).

> 尽管可以使用基于使用的统计测试从用户的角度确保产品可靠性，但这些技术的准确性和实用性有各种限制。例如，关于实际使用场景、序列和模式的信息收集通常因这些信息的专有性而受阻或完全被阻止，因为其中很多可能是商业敏感信息。此外，客户的多样性及相关人口池也在构建对所有相关人员都准确的操作配置文件（OPs）方面构成了主要障碍。
>
> 将信息“引入”基于使用的测试的另一种方法是以控制发布的形式将软件产品“发布出去”，以便可以暴露并纠正普通用户群体可能经历的问题，然后再进行一般产品发布。这种模式通常被称为beta测试。尤其是对于广泛发布和拥有大量用户群体的产品，当基于使用的统计测试不足时，这种方法的好处是显而易见且重要的。然而，运行此类测试计划的成本也是显著的，包括：
>
> - 运行beta测试的直接成本和限制：必须识别足够大且有代表性的客户和用户群体；与他们的关系通常需要长时间培养，以获得他们的信任和合作。有时，除了代表性之外的其他标准可以用于选择beta测试客户，例如选择报告最多现场缺陷的客户，以有效减少产品发布后类似问题的可能性。
> - 产品延迟的间接成本可能很大，因为beta测试不仅需要时间来运行，还需要时间和精力来准备。此外，应该允许足够的时间让客户和用户熟悉产品并开始使用其全部功能集。
>
> 因此，是否进行beta测试，以及进行何种beta测试、其范围和长度等，都需要考虑所有因素后决定。对于越来越多的软件产品来说，进行某种形式的beta测试是一种普遍趋势。事实上，大量用户直接参与使用产品并报告问题，这与beta测试非常相似，但规模更大，被认为是各种开源和基于互联网产品高质量的一个重要原因（Raymond, 1999; Vixie, 1999).



**Summary and comparison of  testing sub-phases** 

Table 12.1 summarizes the different testing sub-phases in roughly the chronological order with respect to several important characteristics: 

<img src="./Chapter 12 Testing Techniques Adaptation, Specialization, and Integration/Screenshot 2024-04-01 at 10.46.17.png" alt="Screenshot 2024-04-01 at 10.46.17" style="zoom:50%;" />

* Perspective: black-box (functional) vs. white-box (structural). 
* Stopping criteria: coverage-based vs. usage based. 
  Who is performing the test, including programmers, tester, customers, and independent third party (labeled “3p” in Table 12.1). 
* Major types of specific testing techniques used, including, informal debugging (db), functional and structural checklists (f-list and s-list), boundary test (BT), finite-state machine based testing (FSM), control flow testing (CFT), data flow testing (DFT), Musa operation profiles (Musa), and Markov operational profiles (Markov). Notice that main objectives are not directly stated but implied in the above characterization: Black-box testing focuses on external functions provided, while white-box testing

Notice that main objectives are not directly stated but implied in the above characterization: Black-box testing focuses on external functions provided, while white-box testing focuses on internal implementations of different levels of detail; and coverage-based testing focuses on detecting problems for fixing, while usage-based testing focuses on reliability from a user’s perspective. 

Component testing is divided into two types, with type I (component-I) as loosely grouped components, and type I (component-I) as tightly packed components which form the basis of objects and reusable and resalable components in object-oriented (00), component-based software engineering (CBSE), and commercial-off-the-shelf (COTS) component market.

> 表12.1大致按照时间顺序总结了不同的测试子阶段，并针对几个重要特性进行了比较：
>
> - 视角：黑盒（功能性）与白盒（结构性）。
> - 停止标准：基于覆盖与基于使用。
> - 执行测试的人员，包括程序员、测试员、客户和独立第三方（在表12.1中标记为“3p”）。
> - 使用的主要特定测试技术类型，包括非正式调试（db）、功能和结构检查表（f-list和s-list）、边界测试（BT）、基于有限状态机的测试（FSM）、控制流测试（CFT）、数据流测试（DFT）、Musa操作配置文件（Musa）和Markov操作配置文件（Markov）。请注意，主要目标并未直接说明，而是在上述特征中隐含：黑盒测试关注提供的外部功能，而白盒测试关注不同细节级别的内部实现；基于覆盖的测试关注于发现问题以进行修复，而基于使用的测试关注于从用户角度的可靠性。
>
> 组件测试被分为两种类型，类型I（component-I）为松散分组的组件，类型II（component-II）为紧密打包的组件，这些组件构成了面向对象（OO）、基于组件的软件工程（CBSE）和现成商业组件（COTS）市场中的对象和可重用及可再销售的组件的基础。

## 12.2 SPECIALIZED TEST TASKS AND TECHNIQUES

In the above description of testing sub-phases, the tasks can be ordered in roughly chronological order. However, some specialized tasks related to testing would cut through many of these sub-phases, such as defect diagnosis testing and regression testing mentioned above. There are also other specialized testing techniques that can be applied to different objects beyond programs, designed to fulfill different goals, or other techniques that can be used as substitute to testing. We next cover these specialized testing and analysis tasks and related techniques.

> 在上述测试子阶段的描述中，任务可以大致按时间顺序排列。然而，一些与测试相关的专门任务会穿越许多这些子阶段，例如上述的缺陷诊断测试和回归测试。还有其他专门的测试技术可以应用于程序之外的不同对象，旨在实现不同的目标，或其他可以用作测试替代的技术。接下来，我们将介绍这些专门的测试和分析任务及相关技术。

**Defect diagnosis testing**

When problems are reported by customers during normal operations or during beta testing, diagnosis testing is often used to help with the problem diagnosis by recreating the problem, observing program behavior associated with these problems, collecting relevant information, narrowing down the possibilities, and finally diagnosing the problems by analyzing all the information collected. Diagnosis testing can often help us find the exact location of the underlying faults in the program so that they can be fixed. In performing diagnosis testing, a series of test runs may be executed in succession to progressively narrow down the possible areas of problems. Therefore, highly correlated test runs based on similar scenarios are carried out, which is different from the normal testing or usage situations where a wider variety of usage scenarios are used. 

Diagnosis testing can also be used to diagnose problems discovered during testing, as illustrated by the downward arrow in Figure 12.1. However, they may be used less extensively than the diagnosis testing for in-field problems reported by the customers. The key difference between the two situations is information availability: For in-house testing, all the test cases and the related test run details can be provided by the testers for code owners to diagnose the problems. However, actual customers are typically less willing to share detailed usage scenarios and detailed information when problems were encountered. 
Therefore, the code owners rely more on diagnosis testing to obtain more information for analyzing the in-field problems. The use of diagnosis testing in third-party testing in the IV&V (independent verification and validation) environment resembles in-field problem diagnosis. 

In general, the more information that we can collect from specific testing or operational usage, the less our reliance on diagnosis testing. In addition, diagnosis testing can also be used to deal with other problems found through other means as well, such as through inspection and other QA activities. Therefore, diagnosis testing is an important specialized testing activity that cut through many related testing, usage, and QA activities.

> **缺陷诊断测试**
>
> 当客户在正常操作期间或在beta测试期间报告问题时，通常使用诊断测试来帮助通过重现问题、观察与这些问题相关的程序行为、收集相关信息、缩小可能性范围，最后通过分析所有收集的信息来诊断问题。诊断测试通常可以帮助我们找到程序中潜在故障的确切位置，以便修复。在执行诊断测试时，可能会连续执行一系列测试运行，以逐步缩小问题可能出现的范围。因此，执行基于类似场景的高度相关的测试运行，这与正常测试或使用情况不同，在那里使用了更广泛的使用场景。
>
> 如图12.1中的向下箭头所示，诊断测试也可用于诊断测试过程中发现的问题。然而，与客户报告的现场问题的诊断测试相比，它们可能不会被广泛使用。两种情况之间的关键区别是信息的可用性：对于内部测试，所有测试用例和相关的测试运行细节都可以由测试人员提供给代码所有者以诊断问题。然而，实际客户在遇到问题时通常不太愿意分享详细的使用场景和详细信息。 因此，代码所有者更依赖于诊断测试来获取更多信息以分析现场问题。在第三方测试中使用诊断测试，在IV&V（独立验证和确认）环境中类似于现场问题诊断。
>
> 通常，我们能从特定测试或操作使用中收集的信息越多，我们对诊断测试的依赖就越小。此外，诊断测试也可以用来处理通过其他手段发现的其他问题，如通过检查和其他QA活动。



**Defect-based testing** 

Besides testing based on specification, implementation, and usage of the programs and other artifacts, testing can be based on the disclovered defects or potential defects. The simplest form of such defect-based testing is the ad hoc testing based on guesses where potential faults might be located (not yet discovered, unlike in defect diagnosis testing) based on subjective feelings or some objective evidence, so that related functions or components can be tested accordingly. Systematic application of defect-based testing results in several strategies, including the following: 

* Defect risk based testing: If the guesswork on where defects are likely can be replaced by estimates supported by quantifiable evidence, the above ad hoc defect based testing can then be more effectively used to focus on the identified high-risk areas, or those areas more likely to contain more defects. 
* ==Defect injection and testing:== This technique is also call fault seeding and testing (Mills, 1972). The idea is to inject known faults into the software system, and then use testing to catch both injectedseeded faults and original faults to ensure that certain types of defects are detected and removed, much like what immunization do to keep people healthy. 
* ==Mutation testing:== The basic idea of mutation testing is similar to fault injectiodseeding above, but somewhat more systematic in creating slightly changed programs from the original ones. Such slightly changed programs, or mutants, are then subjected to testing by running a test suite to see if the mutants can be detected and “killed”. This technique could be used effectively to detect various syntactic variations and related faults, as well as used to evaluate the “strength” or “kill rate” of existing test suites. 

Due to the size limit of this book, we will omit detailed discussions of these more specialized testing techniques (Mills, 1972; Hamlet, 1977; Howden, 1982; Voas, 1998). Risk-based testing is covered in connection with the general topic of risk identification and risk-based QA activities in Chapter 21.

> **基于缺陷的测试**
>
> 除了基于程序及其他工件的规范、实现和使用的测试之外，测试也可以基于发现的缺陷或潜在缺陷进行。这种基于缺陷的测试的最简单形式是基于猜测的临时测试，猜测潜在的错误可能位于何处（与缺陷诊断测试中已发现的不同）基于主观感觉或一些客观证据，以便相应地测试相关的功能或组件。系统地应用基于缺陷的测试会产生几种策略，包括以下几种：
>
> - 基于缺陷风险的测试：如果关于缺陷可能存在的地方的猜测可以被可量化证据支持的估计所替代，上述基于偶然的缺陷测试可以更有效地用于关注被识别的高风险区域，或那些更有可能包含更多缺陷的区域。
> - 缺陷注入和测试：这种技术也被称为错误植入和测试（Mills, 1972）。其思想是向软件系统注入已知的错误，然后使用测试来捕捉注入的种子错误和原始错误，以确保检测并移除某些类型的缺陷，这与免疫接种保持人们健康的作用类似。
> - 变异测试：变异测试的基本思想类似于上述的错误注入/植入，但在从原始程序创建略有变化的程序时更为系统化。这些略有变化的程序，或称为变异体，然后通过运行测试套件进行测试，看看这些变异体是否可以被检测并“杀死”。这种技术可以有效地用于检测各种句法变化和相关的错误，以及用于评估现有测试套件的“强度”或“杀伤率”。
>
> 由于本书的篇幅限制，我们将省略这些更专门的测试技术的详细讨论（Mills, 1972; Hamlet, 1977; Howden, 1982; Voas, 1998）。基于风险的测试与第21章的风险识别和基于风险的QA活动的一般主题相关。



**Software maintenance, product updates, and regression testing** 

For software maintenance and post-release product support, problems reported by customers need to be analyzed to fix the underlying defects. In doing so, diagnosis testing is typically used to recreate the problem scenario and to diagnose the problem. 

Besides the above corrective software maintenance activities, software maintenance often includes adaptive and perfective activities to adapt the product to different operational environment, or to improve the product in various ways, as a pro-active move. Various product updates through new releases can be considered as an extension to such maintenance activities. The products with a long history and numerous previous releases are commonly referred to as legacy products. For these maintenance activities and for legacy products, a special form of testing called regression testing is typically used to make sure that previously supported software functions are not negatively affected by the updates. 

Unlike problem diagnosis testing and defect-based testing, regression testing is more closely associated with specific testing phases for legacy products and for major software maintenance activities. For major new product releases, we usually go through a full cycle of testing, with the focus of regression testing typically on the integration testing subphases where old and new product components are integrated. For smaller product updates and software maintenance activities, regression testing may constitute the main part of the testing. The testing techniques for regression testing are typically more specialized (Rothermel and Harrold, 1996; Rosenblum and Weyuker, 1997), including the following components: 

* An analysis of differences between the previous version of the product and the current version based on some formal or informal models to select from existing test cases, and to determine what new test cases are needed. 

* The new test cases focus on two areas: 
  * the newly developed or updated part, which is fundamentally the same as testing 
  * the interactions involving both old and new parts, which is similar to integration of new systems but on a smaller scale, testing, but with a focus on specific kind of interfaces and interactions.

> 对于软件维护和发布后的产品支持，客户报告的问题需要被分析以修复底层缺陷。在这个过程中，通常使用诊断测试来重现问题场景并诊断问题。
>
> 除了上述纠正性软件维护活动外，软件维护通常还包括适应性和完善性活动，以适应不同的操作环境，或以积极的方式以各种方式改进产品。通过新版本的各种产品更新可以被视为此类维护活动的延伸。拥有悠久历史和众多以前版本的产品通常被称为遗留产品。对于这些维护活动和遗留产品，通常使用一种特殊形式的测试称为回归测试，以确保以前支持的软件功能不会因更新而受到负面影响。
>
> 与问题诊断测试和基于缺陷的测试不同，回归测试更紧密地与遗留产品的特定测试阶段和主要软件维护活动相关联。对于主要的新产品发布，我们通常会经历一个完整的测试周期，回归测试的焦点通常在集成测试子阶段，其中旧产品和新产品组件被集成。对于较小的产品更新和软件维护活动，回归测试可能构成测试的主要部分。回归测试的测试技术通常更为专门化（Rothermel和Harrold, 1996; Rosenblum和Weyuker, 1997），包括以下组成部分：
>
> - 基于某些正式或非正式模型分析产品的前一版本与当前版本之间的差异，以从现有测试用例中选择，并确定需要哪些新的测试用例。
> - 新的测试用例关注两个领域：
>   - 新开发或更新的部分，这本质上与测试相同
>   - 涉及旧部分和新部分的交互，这类似于新系统的集成，但规模较小，测试，但关注特定类型的接口和交互。



**Testing beyond programs** 

The primary object of testing is program code produced in the software development process. 
However, this process also produces various other artifacts, such as product specifications, high-level (architectural), module-level, and detailed design documents, user manual, etc.  If some of these artifacts can be implemented through some mockups or software prototypes, then the basic testing ideas and related techniques can be applied to test the general feasibility and performance of these prototypes, and testing results can be used to improve the prototypes for inclusion in the final products or for the construction of their successors. 

As execution-based techniques for QA, testing can also be applied to various softwareintensive systems instead of pure software systems we dealt with so far. Such softwareintensive systems include embedded software used to monitor or control physical or hardware systems, equipments, or processes, as well as other general heterogeneous systems. Examples of embedded systems include software controlled medical equipments and passive restraint systems in automobiles. Examples of general heterogeneous systems include telecommunication networks and distributed computing facilities over wide geographical areas, where software, hardware, and networks interact with one another. For such systems, it is sometimes hard to distinguish when software testing ends and overall system testing starts. Functional testing and usage-based statistical testing are typically more suitable for testing these system interactions than structural testing and coverage-based testing. 

The Internet and the world wide web (WWW or simply the web) are some specific example of general heterogeneous systems. With the prevalence of them and people’s reliance on them for their informal needs in daily life and work, testing and QA for these systems are also gaining importance. Various techniques for software testing can be adapted to test web-based applications, as we described in Chapter 10. The integration of different testing techniques for web testing is described in Section 12.4.

> 测试的主要对象是软件开发过程中产生的程序代码。然而，这个过程也产生了各种其他工件，如产品规范、高层（架构）设计文档、模块级设计文档、详细设计文档、用户手册等。如果其中一些工件可以通过一些模型或软件原型实现，则可以应用基本测试思想和相关技术来测试这些原型的一般可行性和性能，并且测试结果可以用来改进原型，以便包含在最终产品中或用于构建它们的后继产品。
>
> 作为QA的基于执行的技术，测试也可以应用于各种软件密集型系统，而不仅仅是到目前为止我们处理的纯软件系统。这类软件密集型系统包括用于监控或控制物理或硬件系统、设备或过程的嵌入式软件，以及其他一般的异构系统。嵌入式系统的例子包括软件控制的医疗设备和汽车中的被动约束系统。一般异构系统的例子包括跨广泛地理区域的电信网络和分布式计算设施，其中软件、硬件和网络相互作用。对于这些系统，有时很难区分软件测试结束和整体系统测试开始的时刻。功能测试和基于使用的统计测试通常比结构测试和基于覆盖的测试更适合测试这些系统交互。
>
> 互联网和万维网（WWW或简称Web）是一般异构系统的一些特定例子。随着它们的普及和人们在日常生活和工作中对它们的非正式需求的依赖，对这些系统的测试和QA也日益重要。可以调整各种软件测试技术来测试基于Web的应用程序，正如我们在第10章中描述的。不同测试技术对于Web测试的整合在12.4节中描述。



**Testing to achieve other goals/objectives** 

As described in Chapter 2, the primary focus of this book is the correctness aspect of quality, which can be characterized by various reliability measures or defect-related entities.

Therefore, all the testing related topics we discussed so far had this focus in the background, that is, to achieve high-reliability or low-defect goals. However, as we have also noticed in Chapter 2, there are various other aspects of quality and related attributes and sub-attributes, which can be addressed by other types of testing, including: 

* Performance testing, which focuses on the performance of the software system in realistic operational environments. Many such systems are real-time systems, where timely completion of computational tasks and overall workload handling are of critical importance. 
* Stress testing, which is a special form of performance testing, where software system performance under stress is tested. This type of testing is also closely related to capacity testing, where the maximal system capacity is assessed. 
* Usabiliv testing, which assesses the overall usability of software systems, particularly for those systems where user interfaces play an important role, such as web browsers, GUI (graphical user interface) products, etc. For such software products and systems, usability may be more important than reliability. 

In addition, there are other types of testing, although less formalized than the above to test the other quality aspects, such as testing the installation, maintainability, different environmental configurations, portability, interoperability, security, fault tolerance, recoverability, adaptability, etc. Again, we will omit detailed discussions about these specialized testing due to our book size limit.

> 正如第2章所述，本书的主要焦点是质量的正确性方面，这可以通过各种可靠性度量或与缺陷相关的实体来表征。
>
> 因此，我们到目前为止讨论的所有与测试相关的主题都是在这一背景下，即实现高可靠性或低缺陷目标。然而，正如我们在第2章中也注意到的，质量有各种其他方面及相关属性和子属性，这些可以通过其他类型的测试来解决，包括：
>
> - 性能测试，关注软件系统在实际操作环境中的性能。许多这样的系统是实时系统，及时完成计算任务和整体工作量处理至关重要。
> - 压力测试，这是性能测试的一种特殊形式，测试软件系统在压力下的性能。这种类型的测试也与容量测试密切相关，评估系统的最大容量。
> - 可用性测试，评估软件系统的整体可用性，特别是对于那些用户界面起重要作用的系统，如网页浏览器、GUI（图形用户界面）产品等。对于这些软件产品和系统，可用性可能比可靠性更重要。
>
> 此外，还有其他类型的测试，虽然不如上述测试那样正式化，但用于测试其他质量方面，如安装、可维护性、不同的环境配置、可移植性、互操作性、安全性、容错性、恢复能力、适应性等。同样，由于本书篇幅限制，我们将省略这些专门测试的详细讨论。



**Dynamic analyses and other related techniques for QA** 

Various analyses for problem diagnosis, fault locating, and other purposes associated with testing is the most commonly used dynamic analyses for defect detection and removal (Wallace et al., 1996). In addition, other dynamic, execution-based techniques, including simulation and prototyping, can help us detect and remove various defects early in the software development process, before large-scale testing becomes a viable alternative. On the other hand, in-field measurement and related analyses, such as timing and performance monitoring and analysis for real-time systems, and accident reconstruction using software event trees for safety-critical systems, can also help us locate and remove related defects. 
The basic ideas of these dynamic analyses and related techniques for QA are summarized below: 

* Simulation is an important techniques early in the development process before fully operational systems become available, which can push the verification of some highlevel design ideas or system architectural features to much earlier stages before expensive implementation and rework are involved. The expected behavior of part or even the whole system can be simulated through some simulation programs or hardware simulators, which capture the essential input/out and timing information. This could be a viable alternative when actual testing becomes exceedingly expensive. 
  The most famous example is probably the extensive and exclusive use of computer simulation instead of wind-tunnel testing for Boeing 777, a product with extensive software components, throughout its entire design and development process. 
* Prototyping is similar to simulation in basic ideas, where software prototypes, or simplified systems with some key features implemented, are built to test some highlevel ideas in architecture, design, or operation environment. These prototypes could be thrown away later (throw-away prototypes) or revised to be included as part of the delivered system. 
* Timing and sequencing analyses of operational systems can be similar to the analyses performed during problem diagnosis after failures are observed in testing. However, these analyses may be more limited by the amount of information available and different operational environments the system is subjected to. Therefore, various heuristics are used to approximate the causal relations and environmental impacts. 
* Event-tree analysis is extensively used in accident reconstruction for safety critical systems, which is covered in Chapter 16 in connection to failure containment strategies commonly used for such systems

> 用于问题诊断、故障定位以及与测试相关的其他目的的各种分析是最常用的动态分析，用于缺陷检测和移除（Wallace等，1996）。此外，其他基于执行的动态技术，包括仿真和原型设计，可以帮助我们在软件开发过程的早期阶段发现并移除各种缺陷，这是在大规模测试成为可行选择之前。另一方面，现场测量和相关分析，如实时系统的时间和性能监控与分析，以及使用软件事件树进行安全关键系统的事故重建，也可以帮助我们定位并移除相关缺陷。 这些动态分析及相关QA技术的基本思想如下总结：
>
> - 仿真是开发过程早期的一项重要技术，在完全操作的系统可用之前，可以将一些高层设计理念或系统架构特征的验证推向更早的阶段，而不涉及昂贵的实现和返工。可以通过一些仿真程序或硬件仿真器模拟部分甚至整个系统的预期行为，这些仿真器捕获了基本的输入/输出和定时信息。当实际测试变得极其昂贵时，这可以是一个可行的替代方案。 最著名的例子可能是波音777在其整个设计和开发过程中广泛而独家使用计算机仿真代替风洞测试，波音777是一个包含广泛软件组件的产品。
> - 原型设计在基本思想上类似于仿真，其中构建软件原型，或者实现了一些关键特征的简化系统，以测试架构、设计或操作环境中的一些高层思想。这些原型后来可能会被丢弃（一次性原型），或修改后作为交付系统的一部分。
> - 操作系统的定时和序列分析可能与在测试中观察到失败后进行问题诊断时执行的分析类似。然而，这些分析可能更受可用信息量和系统所受不同操作环境的限制。因此，使用各种启发式方法来近似因果关系和环境影响。
> - 事件树分析在安全关键系统的事故重建中被广泛使用，与第16章中介绍的针对此类系统常用的故障隔离策略有关。

## 12.3 TEST INTEGRATION

Many testing techniques and activities can be applied to test large software systems and to ensure their reliability and quality in general. On the other hand, each technique and related activities are only more effective than others for specific purposes under specific environment or product development phases. A collection of techniques and activities instead of a single one is called for because of the many different aspects of software systems that need to be tested for and many different problems we need to guard against for such large systems. The main advantages of such integrations include: 

* Benefit enhancement: By taking advantage of the different techniques, the integrated strategies can be used to perform not only the original tasks the individual techniques were designed for, but also provide an “all-around” QA that may go above and beyond customer expectations to delight customers. The combination may yield some unforeseen insights into problem areas or quality aspects so that the combined total benefit may well be more that the sum of its individual elements. 
* ZncreasedJlexibiZity: Such integrated strategies also offers more flexibility in overall QA and in deriving results that can be extrapolated to different situations and for different types of products and market segments. For example, if we are shifting from new product development to product support and update, much of the suite of testing techniques can still be used but with more of a focus on integrating updated parts with the existing parts. 
* Cost reduction: By consolidating the models and techniques, substantial savings could be realized because such integrated strategies eliminate much of the redundant work associated with different techniques and activities. For example, many of the information sources can be shared, some models can be reused, even testing results by different techniques can serve as oracles to cross-check each other, etc.

> 许多测试技术和活动可以应用于测试大型软件系统，并确保它们的可靠性和质量。另一方面，每种技术及相关活动在特定环境或产品开发阶段对特定目的而言可能比其他技术更有效。由于需要针对软件系统的许多不同方面进行测试，并且需要防范这些大型系统可能出现的许多不同问题，因此需要一系列技术和活动，而不是单一的技术或活动。这种整合的主要优点包括：
>
> - 效益增强：通过利用不同的技术，整合策略不仅可以用来执行个别技术设计的原始任务，还可以提供可能超越客户期望的“全方位”QA，以取悦客户。组合可能会产生一些对问题领域或质量方面的意想不到的洞察，因此组合的总体益处可能远大于其个别元素的总和。
> - 增加的灵活性：这种整合策略也提供了更大的整体QA灵活性，并能得出可以外推到不同情况和不同类型的产品及市场细分的结果。例如，如果我们从新产品开发转向产品支持和更新，许多测试技术套件仍然可以使用，但更多地集中于将更新的部分与现有部分整合。
> - 成本降低：通过整合模型和技术，可以实现实质性的节省，因为这种整合策略消除了与不同技术和活动相关的许多重复工作。例如，许多信息源可以共享，一些模型可以重用，甚至不同技术的测试结果可以作为交叉检查彼此的标准等。

## 12.4 CASE STUDY: HIERARCHICAL WEB TESTING

The realization of many of the advantages of test integration can be best illustrated in the following integrated strategy for web testing. Continuing our case study of web testing described in Chapter 10, we next examine the different testing techniques that are applicable to web testing and the possible integration of them to effectively assure quality from the perspective of web users.

> 实现测试整合的许多优点可以在以下针对Web测试的综合策略中得到最佳示例。继续我们在第10章中描述的Web测试案例研究，接下来我们将检查适用于Web测试的不同测试技术以及可能的整合，以有效地从Web用户的角度确保质量。



**Techniques applicable to web testing** 

Most existing work on web testing focus on functionality testing to test web components to ensure that the web site performs its intended functions as expected. This type of testing usually involves analyzing given web components, and checking their conformance to relevant standards and external specifications (Bowers, 1996). Specific types of functionality testing include: 

* HTML syntax checking: HTML validators, such as Weblint (www . weblint. org) and W3C Validator (validator. w3. org), can parse HTML files and check their conformance to relevant language specifications and document standards. Most of such validators and similar tools can also perform spelling checking on these files. 
  This testing technique corresponds to automated testing based on checklists we discussed in Chapter 8 or automated syntax testing (Beizer, 1990). 
* Link checking can be performed to check the entire site for broken links, with the help of tools like Net Mechanic (www.netmechanic. com). This is similar to link coverage testing we discussed above for FSM-based testing, but without formally constructing a FSM. 
* Form testing checks input types and variable names in various forms, with the help of tools such as Doctor HTML (www2. imagiware . com/RxHTML). This can be considered as rudimentary input domain testing covered in Chapter 8. 
* Verification of end-to-endtransactions, which is similar to testing complete execution paths in control flow testing covered in Chapter 11. 
*  Java component testing: Java applets, which work on the clients side, or other Java applications, which work on the server side, need to be tested, similar to traditional software testing we covered in the previous chapters.

Besides these forms of functionality testing, various other forms of testing and related testing techniques have been used for web testing and evaluation:

* Load testing is a subset of stress (or performance) testing. It verifies that a web site can handle a large number of concurrent users while maintaining acceptable response time. 
* Usability testing focuses on the ease-of-use issues of different web designs, overall layout, and navigations. A lot of work has been done on web usability testing. However, such work relies heavily on subjective preferences of selected users. The focus is not on the reliability (the correct delivery of required information or documents), but rather on the appearance and usability. Therefore, it is not included as a part of this case study. 
* Browser rendering problems may affects the delivery as well as presentation of web contents. For example, HTML files that look good on one browser may look bad on another. We need to make sure that the web site functions appropriately with all these different browser versions. However, the browser checking is done manually to assess the “look & feel” of the GUI etc., similar to usability testing discussed above. Other basic tests to detect browser rendering problems can be done to test for functionality and download time using different browsers.

Besides the above coverage-based testing for individual web components and some other limited aspect, other techniques have been used to test the overall usage scenarios and navigation patterns and evaluate web reliability (Tian and Lin, 1998; Tian and Nguyen, 1999; Kallepalli and Tian, 2001; Tian et al., 2004). In particular, selective functional testing based-on FSM and unified Markov models (UMMs) was performed for frequently used web contents and navigation patterns was supported automated information extraction from existing web logs. This approach was described in our case studies of web testing in Chapter 10. 

On the other hand, loosely related collections of web pages can be more appropriately represented and tested by using some simpler usage models based on a flat list of operations and associated probabilities, such as Musa’s operational profiles (OPs) we described in Chapter 8. The introduction of statistical testing strategies based on such OPs or UMMs is not to replace traditional testing techniques, but to use them selectively on important or frequently used functions or components, as in the following integrated strategy.

> 实现测试整合的许多优点可以在以下针对Web测试的综合策略中得到最佳示例。继续我们在第10章中描述的Web测试案例研究，接下来我们将检查适用于Web测试的不同测试技术以及可能的整合，以有效地从Web用户的角度确保质量。
>
> **适用于Web测试的技术**
>
> 大多数现有的关于Web测试的工作都集中在功能测试上，以测试Web组件确保网站按预期执行其既定功能。这种类型的测试通常涉及分析给定的Web组件，并检查它们是否符合相关标准和外部规范（Bowers, 1996）。功能测试的特定类型包括：
>
> - HTML语法检查：HTML验证器，如Weblint（www.weblint.org）和W3C Validator（validator.w3.org），可以解析HTML文件并检查它们是否符合相关语言规范和文档标准。大多数此类验证器和类似工具也可以对这些文件进行拼写检查。 这种测试技术对应于我们在第8章讨论的基于检查表的自动化测试或自动化语法测试（Beizer, 1990）。
> - 链接检查可以使用像Net Mechanic（www.netmechanic.com）这样的工具检查整个站点的断开链接。这类似于我们上面讨论的基于FSM的链接覆盖测试，但无需正式构建FSM。
> - 表单测试检查各种表单中的输入类型和变量名，使用工具如Doctor HTML（www2.imagiware.com/RxHTML）。这可以被视为第8章覆盖的基本输入域测试。
> - 端到端交易验证，类似于第11章覆盖的控制流测试中测试完整执行路径。
> - Java组件测试：在客户端工作的Java applets或在服务器端工作的其他Java应用需要被测试，类似于前几章覆盖的传统软件测试。
>
> 除了这些形式的功能测试外，还有各种其他形式的测试和相关测试技术被用于Web测试和评估：
>
> - 负载测试是压力（或性能）测试的子集。它验证一个网站是否能够在保持可接受响应时间的同时处理大量并发用户。
> - 可用性测试关注不同Web设计的易用性问题、整体布局和导航。已经完成了大量关于Web可用性测试的工作。然而，这些工作严重依赖于选定用户的主观偏好。焦点不在于可靠性（正确交付所需信息或文档），而是在于外观和可用性。因此，它不作为本案例研究的一部分包含在内。
> - 浏览器渲染问题可能影响Web内容的交付以及呈现。例如，在一个浏览器上看起来好的HTML文件在另一个浏览器上可能看起来很糟糕。我们需要确保网站能够与所有这些不同版本的浏览器兼容。然而，浏览器检查是手动完成的，以评估GUI等的“外观和感觉”，类似于上面讨论的可用性测试。可以进行其他基本测试来检测浏览器渲染问题，以测试使用不同浏览器的功能和下载时间。
>
> 除了上述针对个别Web组件的基于覆盖的测试和一些其他有限的方面外，还使用了其他技术来测试整体使用场景和导航模式，并评估Web可靠性（Tian和Lin, 1998; Tian和Nguyen, 1999; Kallepalli和Tian, 2001; Tian等，2004）。特别是，基于FSM和统一马尔科夫模型（UMMs）的选择性功能测试针对频繁使用的Web内容和导航模式进行了支持，通过从现有Web日志中自动提取信息。这种方法在第10章的Web测试案例研究中进行了描述。
>
> 另一方面，松散相关的Web页面集合可以通过使用一些基于平面操作列表及相关概率的简化使用模型来更恰当地表示和测试，如我们在第8章中描述的Musa的操作配置文件（OPs）。基于此类OPs或UMMs的统计测试策略的引入不是为了取代传统测试技术，而是选择性地用于重要或频繁使用的功能或组件，如下面的综合策略所示。



**An integrated hierarchical strategy for web testing** 

We next describe an integrated strategy that integrates existing testing techniques and reliability analyses in a hierarchical framework (Tian et al., 2003). This strategy combines various usage models for statistical testing to perform high-level testing and to guide selective testing of critical and frequently used subparts or components using traditional coverage-based structural testing. There are three-tiers to this strategy, as follows: 

1. Development of the high-level operational profile (OP), which enumerates major functions to be supported by web-based applications and their usage frequencies by target customers. This list-like flat OP will be augmented with additional information and supported by lower-level models based on unified Markov models (UMMs). The additional information includes grouping of related functions and mapping of major external functions to primary web sources or components. 

2. For each of the high-level function groups, a UMM can be constructed to thoroughly test related operations and components. UMMs capture desired behavior, usage, and criticality information for web-based applications, and can be used to generate test cases to exhaustively cover high-level operations and selectively cover important low-level implementations. The testing results can be analyzed to identify system bottlenecks for focused remedial actions, and to assess and improve system performance and reliability. 
3. Critical parts identified by UMMs can be thoroughly tested using lower-level models based on traditional testing techniques. Other QA alternatives, such as inspection, static and dynamic analyses, formal verification, preventive actions, etc., can also be used to satisfy user needs and expectations for these particular areas. 
  Reliability analysis and risk identification form an integral part of this strategy to help assure and improve the overall reliability for web-based applications. The use of this integrated testing strategy also yield data for use to perform various reliability analyses for several purposes, including: 1) providing an objective assessment of current web reliability from the user’s perspective,2) predicting future reliability (reliability growth) if we continue with testing using our integrated strategy 3) identifying problematic areas or software components for focused reliability improvement. Some examples of such reliability analysis and improvement activities can be found in Chapter 22.

> 我们接下来描述一个集成策略，它在一个分层框架中整合了现有的测试技术和可靠性分析（Tian等人，2003）。这一策略结合了各种用于统计测试的使用模型，以执行高级测试，并指导使用传统的基于覆盖的结构测试来选择性测试关键且频繁使用的子部分或组件。这一策略有三个层次：
>
> 1. 开发高级操作配置文件（OP），列出Web基应用要支持的主要功能及其目标客户的使用频率。这种列表式的平面OP将通过基于统一马尔科夫模型（UMMs）的低级模型得到增强和支持。额外信息包括相关功能的分组和将主要外部功能映射到主要Web源或组件。
> 2. 对于每个高级功能组，可以构建一个UMM来彻底测试相关操作和组件。UMMs捕获Web基应用所需的行为、使用和关键性信息，并可用于生成测试用例，以彻底覆盖高级操作并选择性覆盖重要的低级实现。测试结果可以分析，以识别系统瓶颈，采取针对性的补救措施，并评估和改进系统性能和可靠性。
> 3. 由UMMs识别的关键部分可以使用基于传统测试技术的低级模型进行彻底测试。其他QA替代方案，如检查、静态和动态分析、形式验证、预防措施等，也可以用来满足用户对这些特定领域的需求和期望。 可靠性分析和风险识别是这一策略不可分割的一部分，有助于确保和提高Web基应用的整体可靠性。使用这种集成测试策略还可产生数据，用于执行各种可靠性分析，包括：1) 从用户的角度提供当前Web可靠性的客观评估，2) 如果我们继续使用我们的集成策略进行测试，预测未来的可靠性（可靠性增长），3) 识别问题领域或软件组件，以集中改进可靠性。一些这种可靠性分析和改进活动的例子可以在第22章中找到。

**Implementation of the integrated strategy** 

The following reports can be easily produced from analyzing the web access logs kept at the web servers: 

* Top access report (TAR) that lists frequently accessed (individual) services or web pages together with their access counts. 
* Call pair report (CPR) which lists call pairs (transition from one individual service to another) and the associated frequency. 

TAR is important because many of the individual services can be viewed as stand-alone ones in web-based applications, and a complete session can often be broken down into these individual pieces. This report, when normalized by the total access count or session count, resembles the flat OP (Musa, 1998) we covered in Chapter 8. Each service unit in a TAR may correspond to multiple pages grouped together instead of a single page. Such results provide useful information to give us an overall picture of the usage frequencies for individual web service units, but not navigation patterns and associated occurrence frequencies. 

CPR connects individual services and provides the basic state transitions and transition probabilities for our UMMs. We can traverse through CPR for strong connections among TAR entries, which may also include additional connected individual services not represented in TAR because of their lower access frequencies or because they represent lower-level service units. A UMM can be constructed for each of these connected groups. In this way, we can construct our UMMs from TAR and CPR. 

Notice that multiple OPs, particularly multiple UMMs in addition to TAR, our top-level OP, usually result for a single set of web-based applications using the above approach. This implementation of our integrated strategy in a hierarchical form is discussed below: 

* At the top level, TAR can be used directly as our flat OP for statistical usage-based testing. 
* Entries in TAR can be grouped according to their connections via CPR, and a UMM can be constructed for each of these groups, forming our middle-level usage models, or our individual UMMs. 
* The hierarchical nature of our UMMs will allow us to have lower-level UMMs as well as other lower-level testing models to thoroughly test selected functional areas or web components. 

This hierarchical implementation of our integrated strategy is graphically depicted in Figure 12.2. We focus on testing frequently used individual functions or services at the top level, testing common navigation patterns and usage sequences at the middle level, and covering selected areas at the bottom level. Specific low-level UMMs or other coverage-based testing models can be built to thoroughly test the related features or critical components in the higher-level flat OPs or UMMs. Coverage, criticality, and other information can also be easily used to generate test cases using lower-level models under our OPs.

> **集成策略的实施**
>
> 以下报告可以很容易地从分析Web服务器保留的Web访问日志中生成：
>
> - 高访问报告（TAR），列出频繁访问的（个别）服务或网页及其访问次数。
> - 调用对报告（CPR），列出调用对（从一个个别服务转移到另一个服务）及相关频率。
>
> TAR很重要，因为许多个别服务可以被视为Web基应用中的独立服务，且完整的会话通常可以分解为这些个别部分。这份报告，当通过总访问次数或会话计数标准化时，类似于我们在第8章中覆盖的平面OP（Musa, 1998）。TAR中的每个服务单元可能对应于多个页面的组合，而不是单个页面。这样的结果提供了有用的信息，给我们一个关于个别Web服务单元的使用频率的总体画面，但不涵盖导航模式和相关出现频率。
>
> CPR连接个别服务，并为我们的UMMs提供基本状态转换和转换概率。我们可以通过CPR来遍历TAR条目之间的强连接，这也可能包括在TAR中未表示的附加连接的个别服务，因为它们的访问频率较低或因为它们代表较低级别的服务单元。可以为这些连接的组构建UMM。通过这种方式，我们可以从TAR和CPR构建我们的UMMs。
>
> 请注意，使用上述方法对单个Web基应用进行测试通常会产生多个OPs，特别是除了TAR（我们的顶级OP）之外的多个UMMs。我们以分层形式实施集成策略的讨论如下：
>
> - 在顶层，TAR可以直接用作我们的平面OP进行基于统计使用的测试。
> - TAR中的条目可以根据它们通过CPR的连接进行分组，为这些组构建UMM，形成我们的中级使用模型，或我们的个别UMMs。
> - 我们UMMs的分层性质将允许我们有低级UMMs以及其他低级测试模型来彻底测试选定的功能区域或Web组件。
>
> 这种集成策略的分层实施在图12.2中以图形方式描绘。我们专注于在顶层测试频繁使用的个别功能或服务，在中级测试常见的导航模式和使用序列，并在底层覆盖选定区域。可以构建特定的低级UMMs或其他基于覆盖的测试模型来彻底测试高级平面OPs或UMMs中的相关特性或关键组件。覆盖率、关键性和其他信息也可以很容易地使用低级模型在我们的OPs下生成测试用例。



## 12.5 CONCLUDING REMARKS

When testing can be divided and performed in several sub-phases, each one can focus on some specific aspects and try to achieve some specific objectives. Various testing techniques covered in the previous four chapters can be adapted and used in these testing sub-phases. The major testing sub-phases covered in this chapter and applicable testing techniques are summarized in Table 12.1. 

<img src="./Chapter 12 Testing Techniques Adaptation, Specialization, and Integration/Screenshot 2024-04-01 at 11.00.10.png" alt="Screenshot 2024-04-01 at 11.00.10" style="zoom:50%;" />



In addition to these sub-phases, various specialized tasks and related testing techniques were also described in this chapter, including:

* problem diagnosis testing, 
* defect-based testing, such as defect injection and mutation testing, 
* regression testing for product maintenance, updates, and for legacy products, 
* testing to achieve other objectives, such specialized testing for usability, stress, performance, etc. 
* other execution and dynamic alternatives to testing, such as simulation, prototyping, and dynamic analysis techniques. 

Another important issue addressed in this chapter is the possible integration of multiple testing techniques and related activities in a concerted effort to test large software systems and ensure their quality from different perspectives or to guard against different problems. Substantial amount of savings can also be achieved through such integrated strategies due to sharing of many common information sources, models, and other artifacts and results. We demonstrated such testing integration ideas in a case study of hierarchical testing of web-based applications: 

* The user focus of web-based applications are supported in this integrated strategy by testing functions, usage scenarios, and navigation patterns important to and frequently used by end users under our top-tier usage model based on the list-like Musa’s operational profiles described in Chapter 8 as well as our middle-tier usage models based on Unified Markov Models (UMMs) described in Chapter 10. 
* On the other hand, internal components and structures for web-based applications can also be thoroughly exercised by using our bottom-tier models based on traditional coverage-based testing, under the guidance of the upper-level usage models. 

In general, a collection of appropriate testing techniques can be selected and adapted to help us perform testing for different purposes and under different project environments. The integration of them would also enable us to achieve our testing goals more effectively and efficiently.

> 当测试可以被分解并在几个子阶段内执行时，每个子阶段都可以专注于某些特定方面并尝试实现一些特定目标。前四章中覆盖的各种测试技术可以被适应并用于这些测试子阶段。本章中覆盖的主要测试子阶段和适用的测试技术在表12.1中总结。
>
> 除了这些子阶段外，本章还描述了各种专门任务和相关测试技术，包括：
>
> - 问题诊断测试，
> - 基于缺陷的测试，如缺陷注入和变异测试，
> - 针对产品维护、更新和遗留产品的回归测试，
> - 实现其他目标的测试，如针对可用性、压力、性能等的专门测试，
> - 其他执行和动态测试替代方案，如仿真、原型设计和动态分析技术。
>
> 本章还讨论了另一个重要问题，即可能将多种测试技术和相关活动整合在一起，共同努力测试大型软件系统并从不同的角度确保其质量或防范不同的问题。通过这种集成策略也可以实现大量的节省，因为许多共同的信息源、模型和其他工件及结果可以共享。我们在基于Web的应用程序的分层测试案例研究中展示了这种测试整合思想：
>
> - 基于Web的应用程序的用户焦点在这一集成策略中得到支持，通过测试对最终用户重要且频繁使用的功能、使用场景和导航模式，在我们的顶级使用模型中基于类似列表的Musa操作配置文件（第8章描述）以及我们的中级使用模型基于统一马尔科夫模型（UMMs）（第10章描述）。
> - 另一方面，基于Web的应用程序的内部组件和结构也可以通过使用我们基于传统基于覆盖的测试的底层模型在上层使用模型的指导下得到彻底的测试。
>
> 总的来说，可以选择并适应一系列合适的测试技术，帮助我们出于不同的目的和在不同的项目环境下进行测试。它们的整合也将使我们能够更有效、更高效地实现我们的测试目标。
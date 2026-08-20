# Research System Model v0

### 1. 系统定位

这个 Repository 是一个持续使用中的研究系统（Research System）。

它用于保存研究探索过程中形成的问题、理解、依据与关系，使这些内容能够在之后被重新找到、重新连接、重新解释，并与产品案例（Product Case）建立可追溯的联系。



研究长期来自一个问题：人在不断变化的理解中，怎样让过去的经验和材料仍然能够被重新看见、重新解释、重新建立关系，并最终参与新的判断和创造？系统在这个过程中应该帮助什么，又不应该替人决定什么？



围绕这个长期问题，当前形成了若干研究问题空间，包括：

- 为重新理解而设计；
- Block；
- DES；
- 创造 / 新理解；
- AI；
- Agent。

这些问题空间来自同一条长期研究脉络，但这并不意味着：

- 它们已经构成一个统一理论；
- 它们已经形成确定的系统架构；
- 它们彼此之间的关系已经全部成立；
- 它们处于相同的研究成熟度。

Research System 本身不按这些主题对研究历史进行固定分类。研究主题可以变化，旧材料也可能在未来进入新的问题空间。

当前具体在关注什么、每条研究线进行到什么阶段，以及哪些关系仍然只是候选或推断，由 `current-focus.md` 记录。



这个 Repository 保存的是探索本身，例如：

- 问题如何被提出；
- 对象如何被区分；
- 理解如何发生变化；
- 新关系如何形成；
- 旧判断如何被重新解释或修正；
- 研究假设如何进入实践并接受检验。

### 2. 系统的基本原则

#### 2.1 保存探索，而不是覆盖历史

它可以记录当时的问题、观察、解释、区分、假设、判断或探索方向。



后来的新理解不能直接覆盖旧 Research Node。如果后来重新理解一条旧 Research Node，应当：

1. 保留旧 Research Node；
2. 创建新的 Research Node；
3. 在新的 Research Node 中保存后来形成的理解；
4. 如果形成了明确的新关系，在新的 Research Node 中记录这条 Relation。



因此： 旧 Research Node 保存“当时怎样理解”，新 Research Node 保存“后来怎样重新理解”。系统不能通过修改历史记录，让后来的认识看起来像当时就已经存在。

#### 2.2 研究主题可以变化，信息对象的身份应保持稳定

一个 Research Node 今天可能主要与 DES 有关，几年后也可能重新进入 Block、AI 或其他问题空间。因此：Research Node 不依赖固定主题分类获得身份。

因此：Research Node 不依赖固定主题分类获得身份。

同样的，一个对象的身份也不应依赖它当前所在的文件路径。文件可以移动，目录结构可以调整，但对象的稳定身份不应因此改变。

#### 2.3 数据结构与阅读方式分离

Research System 中需要区分：
- Domain Model：系统中有哪些信息对象
- Data Representation：这些对象怎样被持久化
- Directory Structure：这些数据怎样被放进 Repository
- View / Presentation：人或程序怎样阅读、组合和呈现这些内容。

因此：Domain Model ≠ Data Representation ≠ Directory Structure ≠ View。



目录结构只承担相对稳定的物理存储边界。

对象身份、时间、显式关系等信息由对象数据和 metadata 保存。

Timeline、Relation Graph 或其他阅读方式，可以在这些底层数据之上生成，而不需要直接编码进目录结构。

### 3. Research System 是什么

Research System 不作为普通信息对象存在。

它是整个 Repository 的 Meta Layer，用来定义：
- 核心信息对象；
- 对象进入系统的规则；
- 历史保存规则；
- Relation 规则；
- Focus 规则；
- 数据表示原则；
- 当前仍未解决的问题。

当前这些规则由 `system/model.md`进行记录。`v0` 阶段以可读的 Markdown 为主。



这个 Repository 同时具有两个角色：

- 第一，它是实际承载研究活动的运行环境。

- 第二，它本身也是一次正在进行的信息架构实验：如果研究理解会长期变化，一个系统应该怎样保存对象、关系、来源和历史，使未来能够恢复这些变化发生时的条件，并重新解释它们？

### 4. Research Node

#### 4.1 定义

Research Node 是研究探索过程中形成的、以后可以被重新找到、引用、连接和重新解释的历史研究单元。

它可能记录：
- 一个问题；
- 一个观察；
- 一个解释；
- 一个区分；
- 一个假设；
- 一个新的关系判断；
- 对旧理解的修正；
- 一个值得继续追踪的探索方向；
- 其他需要作为研究历史被保存的内容。

Research Node 不是某种固定文档类型。它的共同点是：它们都是研究过程中可以被重新找到、引用、连接和重新解释的节点，记录的是一次值得保留的认识活动。

#### 4.2 历史原则

Research Node 一旦成为历史研究记录，后来的理解不直接修改其原有认识内容。

新的解释、反驳、连接、区分或修正，应形成新的 Research Node。

#### 4.3 `v0` 数据表示

当前一个 Research Node 用一个 Markdown 文件表示：

- Markdown 正文保存主要的人类可读研究语境。

- YAML Frontmatter 保存需要被程序稳定解析的结构化信息。例如：

  ```yaml
  id: RN-XXXX
  created: YYYY-MM-DD
  relations: []
  ```

当前不提前固定“完整 metadata schema、完整 Node taxonomy、所有可能的 lifecycle 状态、所有 admission rules......”，这些在真实 Research Nodes 进入系统以后再确定。

### 5. Source

#### 5.1 定义

Source 是因为 Research Node 的溯源、依据或原始语境需要而进入系统的研究依据对象。

Source 不因为“以后可能有用”而独立进入系统。进入路径是：Research Node → 产生溯源 / 依据 / 原始语境需求 → Source 进入系统。

因此：不存在独立的“先收藏 Source，再等以后研究”。

#### 5.2 Source 与 Research Node 的边界

Source 主要回答：当时所依据的材料究竟是什么？
Research Node 主要回答：为什么这份材料在当时重要？我如何理解和使用它？



因此：

- 原材料身份、来源、版本、获取状态等保存在 Source；

- 研究者自己的解释、引用理由、关系判断和后续推论保存在 Research Node。

这是为了避免把“原作者主张、原始材料、当前观察、当前解释、后续推论”误当作同一种信息。

#### 5.3 Source 需要支持的能力

`v0` 中，Source 至少应支持：

- Identity：这是什么 Source？
- Provenance：它来自哪里？
- Historical Integrity：当时实际依据的是哪个版本或状态？
- Context Preservation：未来能否恢复足够的原始材料语境？

URL、本地路径、文件名都只是定位或表示方式，不等于 Source 身份本身。

#### 5.4 Source Record 与 Source Artifact

一个 Source 有一个 Source Record，并可以有 0..n 个 Source Artifacts。



Source Record 保存：

- 稳定身份；
- 标题；
- provenance；
- retrieved time；
- version（如适用）；
- artifact references。



Source Artifact 是为了保存、恢复或处理该 Source 而持久化下来的具体 representation，例如：PDF、网页 snapshot、screenshot、extracted Markdown......其他持久化表示。



`v0` 中，一个 Source 可以表示为：

```shell
sources/
└── SRC-XXXX/
    ├── index.md
    └── artifacts/
```



是否保存本地 Artifact，不由文件类型决定，而由以下因素共同决定：

- 未来是否能够可靠恢复当时依据的材料；
- Source 是否容易失效或变化；
- 存储成本；
- 版权；
- 隐私；
- 实际研究需要。

### 6. Product Case

#### 6.1 定义

Product Case 可能是：一个产品、一个研究工具、一个原型、一个实验、一个视频创作、一个持续发展的实现......以及其他能够承载研究实践结果的 Case。

当前 Product Cases 包括：
- DES
- Block 在 Agent 中的机制

未来可能新增、合并、重新定义或停止。

#### 6.2 不同 Product Case 可以具有明显不同的研究成熟度

Product Case 不要求一开始就已经存在稳定结论。一个 Product Case 可以仍处于问题形成阶段，也可以已经进入 prototype、实验、实现或持续迭代阶段。

因此，不同 Product Case 可以具有明显不同的研究成熟度。

#### 6.3 Product Case 是异构容器

不同 Product Case 的内部结构不需要一致。一个 Case 可能主要包含研究工具、实验数据和 badcase；另一个 Case 可能包含问题拆解、原型、代码、设计文档或压力测试。因此，Product Case 不使用统一的内部目录模板。

#### 6.4 历史行为

Product Case 是 mutable object。文件可以持续修改。

Git 保存 Repository 中文件层面的变化轨迹。Research Node 保存推动、解释、质疑或修正这些变化的研究语境。

因此：

- Git 主要回答：“Repository 中什么发生了变化？”
- Research Node 主要回答：“为什么形成了这样的研究判断或实践变化？”

#### 6.5 v0 数据表示

一个 Product Case 用一个目录表示。

目录中至少有一个` index.md` 作为：

- Case Record；
- 阅读入口；
- 稳定身份入口。

其他文件和子目录根据这个 Case 的真实需要逐步增加。

Product Case 的稳定身份原则与其他系统对象一致：身份不应只依赖当前目录路径。

### 7. Relation

#### 7.1 Relation 不作为独立信息对象

`v0` 中，Relation 是重要的系统结构，但不独立对象化。也就是说，目前不建立 `REL-XXXX` 这样的独立 Relation 对象。

因为独立对象会进一步引入比如：独立ID、生命周期......这会增加复杂度。

#### 7.2 研究性 Relation

新的研究性关系不会脱离 Research Node 独立产生。当明确形成一个新的对象关系判断时，这本身就是新的研究理解。

因此需要：
- 创建新的 Research Node；

- 在正文中说明这条关系为什么成立；

- 在 metadata 中结构化声明这条明确形成的 Relation。例如：

  ```yaml
  relations:
  	- target: RN-XXXX	
  ```



Research Node 正文中保存：

- 为什么建立这条关系；
- 当时的解释语境；
- 这条关系意味着什么。

metadata 保存：哪个对象与哪个对象之间已经明确建立了什么关系。

#### 7.3 Structural Relation

并不是所有结构关系都需要产生新的 Research Node。

例如：

- Research Node 引用 Source；
- Source Artifact 属于某个 Source；
- 某个文件属于 Product Case。

这些不是新的研究判断。

### 8. Focus

#### 8.1 定义

Focus 表示当前问题空间。

它回答：现在正在关注哪些对象和问题？

Focus 由人工进行维护。

系统不能仅根据“最近修改、Commit 数量、文件活动、Relation 数量、其他行为信号......”自动推断 Focus。

#### 8.2 `v0` 范围

`v0` 中只保存 Current Focus。用 `current-focus.md` 记录当前关注中心。

### 9. 时间与历史

Research System 需要追踪：

- 对象何时进入研究历史；
- 新的研究关系何时形成；
- 后来的 Research Node 如何重新解释旧 Node；
- Research Node 如何进入、影响、解释、质疑或修正 Product Case；
- Source 在什么研究条件下被引用；
- 系统中的研究理解如何随时间发生变化。



新的研究性 Relation 如果是在后来形成的，应通过“新 Research Node + 新 Relation declaration”进入系统。不通过回头修改旧 Research Node 来伪装成“当时已经存在”。

系统要尽量保留：“当时怎样理解”与“后来怎样重新理解”之间的区别。

Research System 可以因此被理解为一个具有时间维度的 persistent research network。这里的“时间”不是为了建立一个宏大的研究演化模型，而只是为了保证：历史不被倒写、新理解能够被追加、关系形成具有时间位置、后来的重新解释可以被追溯。

Timeline 本身可以是未来生成的 View。

### 10. Repository v0 物理结构

当前 Repository 的最小结构为：

```shell
/
├── README.md
├── current-focus.md
│
├── system/
│   └── model.md
│
├── research/
│   ├── nodes/
│   └── sources/
│
└── product-cases/
    ├── des/
    │   └── index.md
    │
    └── block-agent/
        └── index.md
```

其中：

- `README.md`：Repository 总入口；
- `current-focus.md`：当前问题空间；
- `system/model.md`：Research System 当前规则；
- `research/nodes/`：Research Nodes；
- `research/sources/`：Sources；
- `product-cases/`：持续变化的 Product Cases。

这个目录结构只提供稳定的物理存储边界。它不直接编码完整的关系网络、研究主题、时间演化或未来阅读方式。

## 11. `v0` 的推进方式

v0 的目标是让系统可以开始真实使用，而不是完成全部理论设计。

当前先建立足够工作的最小模型，然后再在实践中迭代。


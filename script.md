# ForgeMind · VentureWest 5-Minute Pitch Script

Slides: https://wuhubing.github.io/forgemind-pitch/
Format: 5-minute pitch, one presenter. 7 main slides plus 1 backup slide (A1).
Length: about 576 English words. At 130 words per minute that is about **4:25**, leaving roughly 35 seconds of buffer.

> Present in English. The Chinese under each slide is a translation to help you understand and memorize the script; it isn't meant to be read aloud.

---

## 1 · Cover (~25 s)

**EN**
Hi, I'm [name], here with Jiayu and Harris. We're ForgeMind, three MIT MEng students in Data Science for Engineering Systems. AI already lets anyone vibe-code a website. We want to bring that shift to hardware. But in hardware, a design that only *looks* right is worthless. So we built an AI agent that designs machines and verifies they actually work before delivery.

**中文**
大家好，我是 [名字]，和 Jiayu、Harris 一起。我们是 ForgeMind，三个人都是 MIT 工程系统数据科学方向的 MEng 学生。今天的 AI 已经让任何人都能靠"氛围编程"做出一个网站，我们想把这种变化带到硬件领域。但在硬件里，一个只是"看起来对"的设计毫无价值。所以我们做了一个能设计机器，并在交付前验证它真的能工作的 AI 智能体。

---

## 2 · The Problem (~45 s)

**EN**
Text-to-CAD tools today generate geometry. It looks plausible, but machines fail in ways a render can't show: parts interfere, joints lock, a gearbox has the right ratio but tips over. A real example from our own system: we asked a quadruped robot to stand still. The pose metric reported a 2.1-degree tilt, so it returned **PASS**. When our vision model watched the simulation frames, the robot had tipped onto its side. The numbers were wrong and the video wasn't. Our conclusion: **the evaluator has to watch the machine actually work.**

**中文**
今天的"文字生成 CAD"工具生成的是几何形状。它们看起来合理，但机器会以渲染图看不出来的方式失败：零件互相干涉，关节卡死，减速箱传动比是对的，整台机器却翻倒了。举一个我们自己系统里的真实例子：我们让一只四足机器人保持站立。姿态指标显示倾斜 2.1 度，所以判定**通过**。可是当我们的视觉模型去看仿真画面时，机器人已经侧翻倒地了。数字是错的，视频没有骗人。我们的结论是：**评估器必须亲眼看着机器真正动起来。**

---

## 3 · Product (~40 s)

**EN**
That's what ForgeMind does. You type a goal, for example "design a 4-to-1 planetary reducer." The system writes a parametric CAD script and builds the parts and joints. You get an orbitable 3D model, a physics video with metrics, and, if it fails, the cause and how to fix it. It all happens in one browser workspace and runs locally on a laptop CPU, with no GPU, no Docker and no database. That matters for adoption: an engineer can try it in minutes.

**中文**
这正是 ForgeMind 做的事。你输入一个目标，比如"设计一个 4 比 1 的行星减速器"。系统会写出参数化的 CAD 脚本，搭好零件和关节。你会得到一个可以旋转查看的 3D 模型、一段带指标的物理仿真视频；如果失败了，还会告诉你失败原因和修改方法。这一切都在一个浏览器工作台里完成，在笔记本的 CPU 上本地运行，不需要 GPU、Docker 或数据库。这一点对推广很关键：工程师几分钟就能上手试用。

---

## 4 · How It Works + Proof (~50 s)

**EN**
Under the hood is a closed loop. **Design**: the model writes one CAD script. **Build**: parts, joints and meshes. **Check**: interference, support and collision. **Judge**: a vision model inspects six views for structural faults. **Simulate**: we drive the input and measure the output. **Refine**: every failure becomes concrete repair evidence for the next design. Under strict review this loop has already produced two working mechanisms: a four-planet reducer that measures 4.0 to 1 with every planet orbiting and spinning, and a slider-crank with a 24-millimeter stroke and stable forward and return motion.

**中文**
它的核心是一个闭环。**设计**：模型写出一个 CAD 脚本。**搭建**：生成零件、关节和网格。**检查**：检测干涉、支撑和碰撞。**评审**：视觉模型从六个视角检查结构缺陷。**仿真**：我们驱动输入端，测量输出端。**修正**：每一次失败都会变成具体的修复依据，交给下一轮设计。在严格评审下，这个闭环已经做出了两个能工作的机构：一个四行星轮减速器，实测传动比 4.0 比 1，四个行星轮都在公转和自转；还有一个曲柄滑块机构，行程 24 毫米，往返运动都很稳定。

---

## 5 · Why We Win (~45 s)

**EN**
Why is this defensible? Text-to-CAD tools stop at geometry; we test behavior. Three things. First, **executable dependencies**: critical dimensions share parameters and formulas instead of hard-coded coordinates. In a one-task pilot on a three-planet reducer, that was 100 out of 100 versus 25 out of 100. It's a small sample and we're scaling it up. Second, a **task-level evaluator** that tests what the machine does, not how it looks. Third, a **failure-data flywheel**: every failure gives us collision points, trajectories, video and the fix that worked. That's data geometry-only tools never collect.

**中文**
为什么这能形成壁垒？文字生成 CAD 的工具停留在几何层面，而我们测试的是行为。体现在三点。第一，**可执行的尺寸依赖**：关键尺寸共用参数和公式，而不是写死的坐标。在一个三行星轮减速器的单任务试验中，这样做的结果是 100 分之 100，对比之下另一种做法只有 100 分之 25。样本还小，我们正在扩大规模。第二，**任务级评估器**：测试的是机器做了什么，而不是它看起来怎么样。第三，**失败数据飞轮**：每一次失败都会给我们留下碰撞点、运动轨迹、视频，以及最终奏效的修复方法。这些是只做几何的工具永远收集不到的数据。

---

## 6 · Go to Market (~40 s)

**EN**
Our first customers are teams that iterate on mechanisms often. Robotics and embodied-AI teams that need fixtures, transmissions and experimental mechanisms. University labs that need reproducible experiment assets. And small hardware teams that want to kill infeasible concepts before anyone spends days on detailed CAD. The business model is seats plus simulation usage, campus licenses, and paid pilots that convert into enterprise subscriptions. Our first milestone is **three to five design partners**, and we'll measure engineering hours saved and the share of designs that are usable.

**中文**
我们的首批客户，是需要频繁迭代机构设计的团队：需要夹具、传动结构和实验机构的机器人和具身智能团队；需要可复现实验资产的高校实验室；以及希望在有人花好几天做详细 CAD 之前，就先排除不可行方案的小型硬件团队。商业模式包括按席位加仿真用量收费、校园授权，以及先做付费试点、再转成企业订阅。我们的第一个里程碑是**三到五个设计合作伙伴**，衡量标准是节省的工程工时和可用设计的比例。

---

## 7 · Team + Next Steps (~30 s)

**EN**
We're three MIT MEng engineers with experience at Microsoft, Apple, JD.com, Ericsson and iFLYTEK, and this started as a second-place project at Microsoft's Global Intern Hackathon. Today the core loop works end to end and runs locally. In the next three to six months we'll add more mechanism types and manufacturing constraints. In six to twelve months we'll run pilots with design partners. ForgeMind: mechanical designs, verified before delivery. Thank you.

**中文**
我们是三位 MIT MEng 工程师，曾在微软、苹果、京东、爱立信和科大讯飞工作过。这个项目最初来自微软全球实习生黑客松，拿了第二名。目前核心闭环已经端到端跑通，可以在本地运行。接下来三到六个月，我们会扩充机构类型，并加入制造约束。六到十二个月内，我们会和设计合作伙伴一起做试点。ForgeMind：机械设计，交付前已验证。谢谢大家。

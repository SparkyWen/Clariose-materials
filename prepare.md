# 5-minute pitch covering problem, solution, demo, and what you’ve built, followed by a short Q&A.

## 1. 不需要讲完整技术论文

```
Why this problem matters
→ Why your solution is different
→ Show a live demo
→ Prove you actually built it
→ Defend safety, feasibility, and next steps
```

**5-minute English pitch script**

**8–10 slide pitch deck**

**2-minute demo flow**

**Q&A answer bank**

**Live demo backup plan**

**Final checklist**



## Hour 1 — 定故事线，不再加功能（重点， 只有定好了故事线明天才能做PPT）

### 目标

把你的项目从“很多技术”压缩成一个清晰故事。

### 你要完成

写出 4 句话：

```
Problem:
Patients leave doctor visits confused, forgetful, and unable to safely act on medical instructions.

Solution:
Clariose captures the visit in real time and turns it into verified, confirmed, caregiver-ready next steps.

Technology:
It combines OpenAI Realtime, a task-centric Codex multi-agent team, memory recall, multilingual voice support, and visual summaries.

Safety:
It does not diagnose, prescribe, or auto-trigger reminders; every action stays as a draft until the user confirms.
```

### 不要做

不要继续重构代码。
 不要增加新页面。
 不要解释所有模块。
 不要讲 11 roles、4 layers、AutoDream 太深。



## Hour 2 — 做 8–10 页 deck

建议你只做 **9 页**，不要超过 10 页。

| Slide | Title                      | 目标                           |
| ----- | -------------------------- | ------------------------------ |
| 1     | **Clariose**               | 一句话说明产品                 |
| 2     | **The Problem**            | 医患沟通 gap                   |
| 3     | **Why It Matters**         | 医嘱、药物、语言、照护人       |
| 4     | **The Solution**           | Clariose 总流程                |
| 5     | **Live Demo**              | 展示你要 demo 的步骤           |
| 6     | **The Agent Team**         | 8-agent care team              |
| 7     | **Memory Recall**          | 用户上传病历 + 知识库召回      |
| 8     | **Safety by Design**       | draft-only、confirmation-first |
| 9     | **What We Built & Vision** | 技术完成度 + 下一步            |

### 每页规则

每页只放：

```
1 headline
1 short sentence
3 bullets maximum
1 strong visual
```



## Hour 3 — 打磨 live demo

你的 demo 不要试图展示全部功能。展示一条完整链路：

```
Start Visit
→ realtime transcript appears
→ pause / complete segment
→ agent team processes transcript
→ transcript verification detects missing medication name / dose
→ clarification questions appear
→ medication schedule draft appears
→ caregiver draft appears
→ final summary / visual summary
```

### 推荐 demo 语音脚本

你可以用英文说：

```
I have had a fever and a cough for three days. I am allergic to penicillin.

Please take this medicine once a day after meals for three days.

If the fever does not improve after three days, please come back on Friday for a follow-up.

Please do a blood test tomorrow morning and bring the report to your next visit.
```

### 你要展示的结果

| 功能                    | 你要说的话                                                   |
| ----------------------- | ------------------------------------------------------------ |
| Realtime transcript     | “The conversation is captured live.”                         |
| Transcript verification | “The system detects missing or ambiguous information.”       |
| Clarification questions | “It turns uncertainty into questions the patient can ask.”   |
| Schedule draft          | “It drafts medication and follow-up tasks, but does not activate them.” |
| Caregiver summary       | “It prepares a caregiver update, but never sends automatically.” |
| Memory recall           | “If records are uploaded, relevant history can be retrieved.” |

------

## Hour 4 — 准备 Q&A

你需要准备 10 个高概率问题。下面我先给你核心答案。

------

### Q1. Is this an AI doctor?

**Answer:**

No. Clariose is not an AI doctor. It does not diagnose, prescribe, or change treatment. It is a communication and memory layer. It captures the visit, detects unclear information, drafts next steps, and requires human confirmation before any action.

------

### Q2. What makes this different from a transcription app?

**Answer:**

A transcription app gives raw text. Clariose turns the visit into safe, structured actions. It verifies transcript ambiguity, extracts medical instructions, generates doctor questions, drafts medication and follow-up tasks, prepares caregiver summaries, and links outputs back to the transcript and memory.

------

### Q3. What makes this different from a chatbot?

**Answer:**

A chatbot answers questions. Clariose is a task-centric care workflow. It uses a persistent multi-agent team where each agent has a specific role: transcript verification, extraction, scheduling, caregiver update, memory recall, and safety guardrails.

------

### Q4. How do you prevent unsafe medication reminders?

**Answer:**

Every reminder starts as a draft. If medication name, dose, frequency, timing, or duration is missing, the system marks it as “Needs Confirmation.” Nothing becomes active until the user confirms it.

------

### Q5. What if the transcript is wrong?

**Answer:**

That is exactly why we have a Transcript Verification Agent. It does not assume the transcript is perfect. It flags ambiguous medication names, missing dose, unclear timing, or speaker uncertainty, then passes those into questions for the doctor or pharmacist.

------

### Q6. How does memory recall work?

**Answer:**

Users can upload medical records, notes, discharge summaries, medication lists, or previous visit documents. Clariose indexes them into a personal knowledge base and retrieves relevant context during the visit, such as allergies, past medications, or previous diagnoses.

------

### Q7. How do you handle non-native English speakers?

**Answer:**

Users can choose their preferred display language. Clariose can show the final summary in that language. If the patient wants to ask a question but cannot express it in English, the system can translate the question into natural English and read it aloud using text-to-speech.

------

### Q8. What did you actually build?

**Answer:**

We built a live web application with a Nuxt frontend and NestJS backend. The browser connects to OpenAI Realtime through WebRTC. Transcript events are sent to the backend, processed by a Codex-powered multi-agent care team, and returned as clarification questions, medication drafts, caregiver summaries, safety notes, and visual summaries.

Your README supports this: the backend includes NestJS, Prisma, PostgreSQL, Redis, OpenAI Realtime, and a Codex harness; the frontend uses Nuxt 3, Vue 3, Tailwind, Three.js, and WebRTC.

------

### Q9. What happens if the OpenAI key is missing or demo fails?

**Answer:**

The system has a deterministic demo fallback for agents, so the UX can still run without an OpenAI key. Realtime transcription requires the key, but the multi-agent flow can still be demonstrated with fixtures.

This is also stated in your README: if `OPENAI_API_KEY` is missing, every agent returns deterministic fixtures, while realtime transcription itself requires a key and returns 503 otherwise.

------

### Q10. What is your next step?

**Answer:**

The next step is to move from hackathon MVP to production readiness: persistent storage for visit state, stronger authentication and ownership checks, improved caregiver workflows, more robust memory retrieval, and clinical safety evaluation with controlled users.

------

## Hour 5 — 彩排 + 备份

最后 1 小时只做三件事：

1. 录屏一次完整 demo。
2. 练 5 分钟 pitch 到不超时。
3. 准备 fallback screenshots / video。

### 必须准备 backup

| Backup               | 用途                                               |
| -------------------- | -------------------------------------------------- |
| 录屏 demo            | 现场网络/麦克风失败                                |
| 关键 UI 截图         | Realtime transcript、agent result、caregiver draft |
| 一段 mock transcript | Realtime 失败时直接 replay                         |
| 本地 fixture demo    | OpenAI API 不稳定时备用                            |
| PDF deck             | 投屏失败时可直接打开                               |

------

# 2. 5 分钟 Pitch 时间分配

## 推荐节奏

| 时间      | 内容                       |
| --------- | -------------------------- |
| 0:00–0:30 | Opening / problem          |
| 0:30–1:10 | Why this matters           |
| 1:10–1:50 | Solution                   |
| 1:50–3:20 | Demo                       |
| 3:20–4:20 | What we built              |
| 4:20–4:50 | Safety and differentiation |
| 4:50–5:00 | Closing                    |

# 3. 5 分钟英文讲稿初稿

你可以先用这版练习。

------

## **Opening**

Hi everyone, I’m David, and this is **Clariose**.

Clariose is a real-time AI communication bridge for doctor-patient conversations. It helps patients turn a medical visit into clear, verified, and confirmed next steps.

The problem is simple: patients often leave a doctor visit unsure about what the doctor said, what medication to take, what to ask again, or what to tell their family.

------

## **Problem**

A doctor visit is stressful. Patients may be sick, nervous, elderly, or not fluent in English. Important instructions are spoken quickly, and once the visit is over, the patient has to remember everything.

But memory is fragile. Medication details, follow-up plans, test instructions, and warning signs can easily be missed.

The real gap is not only medical knowledge. It is the handoff from clinical conversation to patient execution.

------

## **Solution**

Clariose closes that gap.

During the visit, the browser connects to OpenAI Realtime and captures the conversation as live transcript turns.

When the patient pauses or ends a segment, Clariose sends the transcript to a persistent multi-agent care team.

Each agent has a focused role: one verifies transcript quality, one extracts medical instructions, one generates clarification questions, one drafts medication and follow-up tasks, one prepares caregiver updates, and one applies safety guardrails.

The system is not an AI doctor. It does not diagnose, prescribe, or change treatment. It helps the patient understand, confirm, and act safely.

------

## **Demo**

Let me show a quick example.

Imagine the doctor says:

“Please take this medicine once a day after meals for three days.”

Clariose captures the transcript in real time.

Then the agent team processes it. The transcript verification agent notices that the medication name and dose are missing. The clarification agent generates a question: “Could you confirm the exact medication name and dose?”

The schedule agent creates a reminder draft, but it stays pending. It is not activated automatically.

Then the caregiver agent prepares a family-friendly update, also as a draft.

This is the key design: every action requires user confirmation.

------

## **What We Built**

Technically, Clariose is a full-stack web application.

The frontend is built with Nuxt 3, Vue, Tailwind, and WebRTC.

The backend is built with NestJS, Prisma, PostgreSQL, Redis, and a Codex-powered multi-agent harness.

The browser uses an ephemeral Realtime client secret, so the long-lived OpenAI API key never leaves the server.

We also built Recall Codex, a memory system that lets users upload notes and prior medical records, so relevant history can be retrieved during future visits.

------

## **Safety**

Safety is central.

Clariose does not auto-fire reminders. It does not auto-send caregiver messages. It does not hide uncertainty.

If something is missing or ambiguous, the system turns it into a question for the doctor or pharmacist.

The final result is not just a transcript. It is a safe, confirmed care plan.

------

## **Closing**

Clariose helps every patient leave a doctor visit with a verified memory, a clear action plan, and a caregiver-ready summary.

It is not replacing doctors. It is helping patients carry medical information safely from the consultation into real life.

Thank you.



## 0. 你项目现在的可讲核心

根据你的 README，你现在的项目已经不是一个简单 demo，而是一个完整的 **doctor-patient communication bridge**：浏览器通过 WebRTC 连接 OpenAI `gpt-realtime`，把实时咨询转写传回后端，再交给 **8-agent persistent care team** 生成 medication plans、clarification questions、caregiver digests 和 reminder drafts，并且 reminder 只有在用户明确接受后才会从 `DRAFT` 进入 `SCHEDULED`。README 也明确写了系统已包含 **Recall Codex**，可以把用户 notes 和 prior chat rollouts 变成可引用的知识面，并支持后台 daily two-phase consolidation。

这意味着你的 pitch 核心应该是：

> **Clariose helps patients turn medical conversations into verified, multilingual, caregiver-ready action plans — without pretending to be an AI doctor.**

你要反复强调：

```
Not diagnosis.
Not prescription.
Not automatic medical action.
It is a communication, memory, and confirmation layer.
```



# 4. 你 deck 的核心页面内容

## Slide 1 — Clariose

**Real-time AI memory for safer doctor visits**

- Live transcript
- Multi-agent care team
- Confirmed next steps

------

## Slide 2 — Problem

**Patients leave visits with uncertainty.**

- What did the doctor say?
- What should I do next?
- What should I ask again?
- What should I tell my family?

------

## Slide 3 — Why It Matters

**The care gap starts after the conversation.**

- Medication details can be missed
- Follow-up tasks can be forgotten
- Caregivers are often out of the loop
- Non-native speakers struggle to ask clearly

------

## Slide 4 — Solution

**Clariose turns conversations into safe next steps.**

```
Realtime transcript
→ Agent team
→ Questions to ask
→ Task drafts
→ Caregiver summary
→ User confirmation
```

------

## Slide 5 — Demo

**One doctor sentence becomes a safe workflow.**

Doctor says:

```
“Take this medicine once a day after meals for three days.”
```

Clariose outputs:

- Medication name missing
- Dose missing
- Ask doctor question
- Reminder draft
- Caregiver update draft

------

## Slide 6 — Multi-Agent Team

**8 product agents, one care workflow**

- Transcript Verification
- Medical Extraction
- Clarification
- Schedule Drafting
- Caregiver Update
- Safety Guardrail

------

## Slide 7 — Memory Recall

**Patient-owned knowledge base**

- Upload medical records
- Recall allergies, medications, history
- Connect today’s visit with past context

------

## Slide 8 — Safety by Design

**Assist, verify, confirm.**

- No diagnosis
- No prescription
- No automatic reminders
- No automatic sharing
- Every action is a draft first

------

## Slide 9 — What We Built

**A working full-stack system**

- OpenAI Realtime + WebRTC
- NestJS backend
- Nuxt frontend
- Codex-powered agent harness
- Persistent role memory and recall system

------

## Slide 10 — Vision

**From one visit to a trusted care memory system**

- Every visit remembered
- Every task confirmed
- Every caregiver informed
- Every patient more confident

------

# 5. Demo 操作顺序

你明天应该按这个顺序演：

1. 打开 `zai.gold`
2. 进入 Clariose / visit 页面
3. 创建 visit
4. 勾选 consent
5. 开始 realtime
6. 对麦克风说测试句
7. 展示 transcript
8. 展示 agent results
9. 展示 medication draft
10. 展示 clarification questions
11. 展示 caregiver summary
12. 展示 reminder 仍是 draft / pending
13. 结束 visit / final summary



# 6. 最容易被问的危险问题

## “Can this be used in real hospitals?”

你应该答：

> Not as a clinical decision tool yet. The current version is designed as a patient communication and memory assistant. It avoids diagnosis and treatment advice. The next step would be controlled user testing and safety evaluation.

------

## “What about privacy?”

答：

> The long-lived OpenAI key stays server-side. The browser only receives an ephemeral Realtime key. Raw audio is not stored by default. Visit outputs are confirmation-based, and caregiver sharing is draft-only.

------

## “What if the AI makes a mistake?”

答：

> The system is designed to surface uncertainty, not hide it. Missing medication name, missing dose, unclear timing, or transcript ambiguity become doctor questions. Nothing becomes active without user confirmation.

------

## “Why multi-agent?”

答：

> Because this is not one task. A medical visit requires transcript verification, instruction extraction, scheduling, caregiver communication, memory recall, and safety review. Separating roles makes the system more controllable and auditable.


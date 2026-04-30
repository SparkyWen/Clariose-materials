现在在这个路径下面有~/Zai/docs/openai_hackathon我准备的很多参考资料和源码， 例如~/Zai/docs/openai_hackathon/Qagent这个路径下就是我自己通过claude的SDK搭建的一套harness的多agents通信协作和召回系统，目前我认为技术上我已经完善的非常成熟， 我希望可以吸取经验并且复用。~/Zai/docs/openai_hackathon/docs/这个路径下分别我准备了CDXLearn， 即openai的SDK和codex的源码(~/Zai/docs/openai_hackathon/docs/CDXLearn/openai-codex-source)和我自己的为设计openai生态的harness系统的笔记非常重要 ~/Zai/docs/openai_hackathon/docs/CDXLearn/cdx_notes；和CCLearn，即claude的harness源码实现 ~/Zai/docs/openai_hackathon/docs/CCLearn/source/src和我的笔记 ~/Zai/docs/openai_hackathon/docs/CCLearn/notes/notes_integrated 这个路径笔记非常重要， 基本是我认为的全部claude 生态的harness的关键设计。



## 2-Minute Demo Video Script — **Clariose**

**[0:00–0:15 | Opening]**

Hi, this is **Clariose** — a real-time AI care communication assistant that helps patients turn doctor conversations into clear, safe, and actionable next steps.

Many patients leave a doctor visit unsure about what the doctor said, what medication to take, what to ask again, or what to tell their family. Clariose is designed to close that gap.

------

**[0:15–0:35 | Real-Time Capture]**

During the visit, Clariose listens in real time and captures the doctor-patient conversation as a live transcript.

The patient does not need to remember everything manually. Important instructions, medication details, follow-up plans, and unclear points are captured as the conversation happens.

------

**[0:35–1:05 | Multi-Agent Collaboration]**

After the conversation is paused or completed, Clariose activates a task-centric multi-agent team.

Each agent has a focused role: one verifies transcript quality, one extracts medical instructions, one checks missing medication details, one generates questions to ask the doctor, one drafts follow-up tasks, one prepares a caregiver update, and one applies safety guardrails.

The system does not diagnose or prescribe. It helps patients understand, confirm, and act safely.

------

**[1:05–1:25 | Multilingual Voice Support]**

Clariose also supports multilingual communication.

Patients can choose their preferred display language. If they want to ask a doctor a question but cannot express it confidently in English, Clariose can turn their question into natural English and read it aloud with text-to-speech.

This helps non-native English speakers communicate more clearly during medical visits.

------

**[1:25–1:45 | Image Summary]**

At the end of the visit, Clariose can generate a clean visual summary image.

Instead of showing long notes or hidden agent reasoning, the image highlights only the key information: what the doctor said, what needs confirmation, medication and follow-up drafts, questions to ask, safety notes, and caregiver updates.

It is designed to be understood instantly by patients and families.

------

**[1:45–2:00 | Closing]**

Clariose is not an AI doctor. It is a memory, communication, and safety layer for patients.

With real-time transcription, multi-agent collaboration, multilingual voice support, and visual summaries, Clariose helps every patient leave a visit with clearer understanding and safer next steps.


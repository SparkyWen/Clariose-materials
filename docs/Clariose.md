# **Clariose: Closing the Gap Between Doctor Conversations, Medical Records, and Patient Action**

Every doctor visit produces critical information, but patients often leave with fragmented understanding. They may not remember the full conversation, may not understand medical language, may miss medication details, or may fail to connect today’s advice with their previous medical history. This gap becomes even more serious when patients have multiple doctors, incomplete records, language barriers, or caregivers who were not present in the room.

The latest Australian patient experience data shows that communication and coordination remain real problems. In the 2024–25 financial year, only **66.5%** of patients said hospital emergency doctors and specialists “always listened carefully.” Among people aged 15–24, that number fell to **51.6%**, and only **49.6%** said emergency doctors and specialists always spent enough time with them. For people seeing three or more health professionals for the same condition, **28.8%** said no health professional helped coordinate their care, and **16.3%** reported issues caused by poor communication between health professionals.

The problem is not only what patients hear in the room. It is also what information the doctor can access, what the patient remembers, and what gets carried across visits. A 2025 Healthwatch England survey found that **23%** of adults had noticed inaccuracies or missing details in their medical records. Among those who noticed inaccuracies, **16%** reported incorrect medication history, **29%** said one or more diagnosed conditions were missing, and **29%** said important medical history was missing. The consequences were not minor: **12%** said they had been refused treatment because of inaccurate or missing information, **10%** said they had been given incorrect or inappropriate medication, and **9%** said they had received potentially unsafe care or treatment.

This is exactly where **Clariose** becomes valuable.

Clariose is not an AI doctor. It is a **real-time medical communication and memory layer** that helps patients capture, verify, recall, organize, and act on healthcare information safely.

The system starts with real-time transcription. During a doctor visit, Clariose listens through the Realtime API and captures the conversation as transcript turns. Instead of sending every short utterance into the agent team immediately, the product can support a more natural workflow: the realtime session keeps listening while the user continues the visit, and when the user pauses or ends a segment, the multi-agent team begins processing the accumulated transcript. This design is important because medical conversations are often long and contextual. A medication instruction mentioned at the end may depend on symptoms, allergies, test results, or past conditions mentioned earlier.

Clariose then adds something a normal transcription app cannot provide: **memory recall from patient-uploaded records**.

Users can upload their medical records, discharge summaries, lab reports, medication lists, referral letters, or previous visit notes into a personal knowledge base. Clariose indexes this information and retrieves the most relevant context during the current visit. This directly addresses the record-fragmentation problem shown in 2025 patient-record research: medical records may be incomplete, inaccurate, or spread across services, forcing patients to repeat their history or risk unsafe decisions. Clariose gives patients a patient-owned memory layer that can bring relevant history into the current conversation without relying only on what one clinical system happens to contain.

The system uses a task-centric multi-agent team. Each agent has its own isolated working memory, while the system also maintains shared memory and retrieval context. This prevents every agent from becoming a generic chatbot. Instead, each agent performs a focused job:

- A **Transcript Verification Agent** checks whether the transcript is clear or ambiguous.
- A **Medical Extractor Agent** extracts medication, dosage, timing, duration, tests, and follow-up instructions.
- A **Memory Recall Agent** retrieves relevant past records, allergies, medications, and conditions from the user’s knowledge base.
- A **Clarification Agent** turns missing or ambiguous information into questions the patient can ask the doctor.
- A **Schedule Agent** creates medication and follow-up task drafts.
- A **Caregiver Agent** prepares a caregiver-friendly update.
- A **Safety Guardrail Agent** prevents diagnosis, treatment advice, medication changes, or automatic actions.
- A **Recap Agent** consolidates all useful outputs into a clear final summary.

This architecture matters because the core healthcare problem is not simply “summarization.” The real problem is **safe actionability**. Patients do not only need a transcript. They need to know what to do next, what is missing, what must be confirmed, and what information should be shared with caregivers.

Medication is one of the highest-risk areas. The World Health Organization identifies unsafe medication practices and medication errors as a leading cause of avoidable harm, with global medication-error costs estimated at **US$42 billion per year**. WHO also reports that medication-related harm affects **1 in 30 patients**, and that more than a quarter of medication-related harm is severe or life-threatening.

Clariose responds to this risk with a confirmation-first design. If the doctor says, “Take this medicine once a day after meals for three days,” Clariose does not blindly create a reminder. It detects that the medication name and dose may be missing. It creates a draft only. It asks the patient to confirm the missing details with the doctor or pharmacist. No medication reminder becomes active until the user reviews and confirms it.

This is a safer approach than a generic voice note, a simple reminder app, or a chatbot. A generic recorder captures information but does not verify it. A reminder app requires the patient to manually understand and enter details. A chatbot may generate fluent but ungrounded answers. Clariose is grounded in three sources: the live transcript, uploaded medical records, and the user’s confirmed memory. Every important output can be traced back to the conversation or the knowledge base.

Language is another major gap. Many patients are not fluent in English, even if they can manage basic conversation. AHRQ notes that adverse events affect patients with limited English proficiency more frequently, are often caused by communication problems, and are more likely to result in serious harm than adverse events affecting English-speaking patients. Clariose addresses this by allowing users to choose their preferred display language from the start. The agent team can process the transcript and records, then present the final output in the patient’s chosen language. If the patient wants to ask the doctor a question but cannot express it confidently in English, Clariose can help convert the question from the patient’s native language into natural English and read it aloud through text-to-speech. This turns language support into an active care tool: the patient can ask clearer questions during the consultation, not just read a translation after the visit.

The final user experience is intentionally simple. Most users should not see the full multi-agent workflow by default. The agent process can be hidden inside a “team activity” or “agent reasoning” toggle. The main screen should show only what matters:

1. **Questions to ask the doctor**
2. **Medication details that need confirmation**
3. **Follow-up and test tasks**
4. **Safety notes**
5. **Caregiver summary draft**
6. **Relevant recalled medical history**
7. **Final visit summary**

Clariose can also generate a visual summary image after the visit. The Recap Agent collects the most important information from all agents and sends a structured prompt to an image-generation model. The output is a clean, one-page medical summary graphic that shows only the critical information: what the doctor said, what the patient must do next, what is unclear, what needs confirmation, and what can be shared with caregivers. The goal is instant comprehension, especially for elderly patients, stressed patients, non-native English speakers, and family members.

The broader safety need is significant. WHO reports that around **1 in 10 patients** is harmed in healthcare, and more than **50%** of this harm is preventable. In primary and ambulatory care, as many as **4 in 10 patients** may be harmed, and up to **80%** of this harm may be avoidable. These figures show that patient safety is not only a hospital issue. It is also a communication, memory, coordination, and follow-through issue.

Clariose targets that exact layer.

It does not replace clinicians. It does not diagnose. It does not prescribe. It does not override medical judgment. Instead, it helps the patient carry medical information safely from the consultation into real life.

The product transforms a doctor visit from a fragile conversation into a structured care workflow:

```
Live conversation
→ transcript
→ memory recall from uploaded records
→ doctor questions
→ medication and follow-up drafts
→ caregiver summary
→ visual recap
→ user confirmation
→ safe next steps
```

This is the core value of Clariose: it gives every patient a verified memory, a personal medical knowledge base, and a safe action plan after every visit.

In a healthcare system where communication gaps, incomplete records, medication errors, language barriers, and care coordination failures remain common, **Clariose provides a practical bridge between what doctors say and what patients can safely do.**
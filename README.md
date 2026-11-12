# LLM Skill: Research Instrument Auditor

**Assignment 4 · Creating a skill for an LLM · Monsoon Semester 2026**  
Author: Siddhi Rashi 25MA0012 · Digital Humanities and Social Sciences

**Abstract.** A skill is a Markdown file of instructions that tells a language model how to do one kind of job well, so that the person using it does not have to explain the job every time. My skill is called **Research Instrument Auditor**. It helps a student review a questionnaire or interview guide before collecting data. It checks whether questions are clear, neutral, answerable and connected to the research objective. It identifies design problems, explains why they matter, suggests revisions and prepares a pilot-testing checklist. The skill file is [`research_instrument_auditor_skill.md`](research_instrument_auditor_skill.md).

---

## Why this skill

Students often spend a lot of time choosing a research topic but give less attention to the instrument they will use to collect evidence. A questionnaire can look polished and still produce misleading data. A question may suggest an answer, combine two ideas, use vague words such as “often”, or offer response options that do not fit every respondent. Interview guides can have similar problems when prompts are judgemental, too broad or likely to lead the participant.

I wanted a skill that helps students catch these problems before they distribute a survey or begin interviews. It does more than correct grammar: it checks whether the questions actually measure what the research brief says they are supposed to measure.

## What the skill makes the model do

The skill takes the research brief and the student's draft instrument, then guides the model through seven moves:

| Move | What the model does |
|---|---|
| 1. Understand the study | Identifies the research aim, target respondents, data-collection mode and concepts to be measured. |
| 2. Inspect each question | Flags leading, loaded, vague, double-barrelled, assumptive or difficult-to-answer wording. |
| 3. Check measurement | Examines whether each question connects to the stated research concept and whether the response scale fits. |
| 4. Review response options | Finds missing, overlapping, unbalanced or non-exhaustive options, including cases where “not applicable” or “prefer not to say” may be needed. |
| 5. Review question order | Checks the flow, repetition, sensitive-question placement, skip logic and possible ordering effects. |
| 6. Check participant care | Highlights consent, privacy, unnecessary personal data and potentially distressing questions. |
| 7. Suggest improvements and pilot tests | Recommends revised wording, explains the changes and creates a practical pilot-testing checklist. |

## Choices I made, and why

- **It does not simply correct grammar.** A grammatically correct question can still be biased, confusing or unsuitable for the research objective. The skill reviews the research design implications of the wording.
- **It works from the student's research brief.** It does not invent research aims or assume what a question is meant to measure. If the objective is unclear, it asks the student to clarify it.
- **It preserves the student's intention.** Suggested revisions should improve clarity and neutrality without quietly changing the concept being measured.
- **It explains the reason for each important change.** The student can understand the problem and decide whether to accept the suggestion, rather than blindly copying a rewritten questionnaire.
- **It distinguishes severity.** High-, medium- and low-severity concerns help the student prioritise changes before data collection.
- **It respects qualitative research.** Interview prompts are not forced into survey-style scales. They are reviewed for openness, neutrality, sequencing and useful follow-up probes.
- **It does not claim validity or reliability.** A language model cannot establish either from wording alone. The skill identifies design risks and recommends piloting; it does not replace statistical testing, a supervisor or institutional ethics review.
- **It keeps the student responsible.** The skill offers a review, not a final approval. The student remains responsible for the instrument, sampling, consent process and interpretation.

## Structure of the file

The skill follows a practical layout:

1. A short header with `name` and `description`, explaining what the skill does and when it should be used.
2. Its purpose, intended users and situations where it is or is not appropriate.
3. A step-by-step audit process for understanding the study, reviewing questions, checking measurement and examining participant care.
4. A fixed output structure, including severity levels, question-by-question feedback, measurement alignment and survey-flow review.
5. Rules for neutral wording, preserving research intent, avoiding unsupported claims and treating qualitative and quantitative instruments appropriately.
6. A final pilot-testing checklist and a list of decisions that the student still needs to make.

A deliberately imperfect questionnaire and a copy-ready test prompt are included in [`sample_input.md`](sample_input.md).

## How to use it

- **In any chat model** (Claude, ChatGPT, or a model in LM Studio): paste the contents of `research_instrument_auditor_skill.md` at the start of the conversation, or put it in the system prompt. Then provide the research objective, target respondents, data-collection mode and draft questionnaire or interview guide.
- **As a skill in a tool that supports them:** create a folder named `research-instrument-auditor`, save the skill file inside it as `SKILL.md`, and add the folder in the tool's skill settings.
- Ask for a full audit or specify one section of the instrument. Review the suggestions, make your own decisions and pilot the revised instrument with a small group before full data collection.

## Links for the website

Replace `USERNAME` and `REPOSITORY` with the real names before submitting.

| File | URL |
|---|---|
| research_instrument_auditor_skill.md | [[https://github.com/siddhirashi/Project_4_LLM_Skill/blob/main/research_instrument_auditor_skill.md](https://github.com/siddhirashi/Project_4_LLM_Skill/blob/main/research_instrument_auditor_skill.md)] |
| sample_input.md | [[https://github.com/siddhirashi/Project_4_LLM_Skill/blob/main/sample_input.md](https://github.com/siddhirashi/Project_4_LLM_Skill/blob/main/sample_input.md)] |

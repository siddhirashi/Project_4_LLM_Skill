# LLM Skill: Synthetic Reading Guide

**Assignment 4 · Creating a skill for an LLM · Monsoon Semester 2026**
Author: Siddhi Rashi Pandey 25MA0012 · Digital Humanities and Social Sciences

**Abstract.** A skill is a Markdown file of instructions that tells a language model how to do one kind of job well, so that the person using it does not have to explain the job every time. My skill is called **Synthetic Reading Guide**. It helps a literature or cultural studies student get from "I have read part of a story" to a research problem, a justified choice of theory and a precise prompt for an LLM. The skill file is [`synthetic_reading_guide_skill.md`](synthetic_reading_guide_skill.md).

---

## Why this skill

While doing assignment 3 (the synthetic reading of "Sultana's Dream") I noticed that running the model was the easy part. The hard part was the middle: going from a few sampled lines to a research problem, choosing a theory I could defend, and writing a prompt that asks for the right thing. When I skipped that thinking, the extraction came back vague. So I wrote a skill for exactly that stretch of the method, steps 2 to 4 of the seven steps in the class handout.

## What the skill makes the model do

The skill walks the model through seven moves, always working from what the student pastes in:

| Move | What the model does |
|---|---|
| 1. Read only what is given | Works from the pasted lines and does not add plot points or quotations from memory |
| 2. Reflect the impression back | Says in two or three sentences what stands out, labels each point as "visible in the lines" or "my guess", then asks for the student's own first reaction |
| 3. Draft up to three research problems | Each one a single sentence, tied to the sample, in the form "How does the text [do something] through [device], and what does this show about [issue]?" |
| 4. Ask about positionality | Asks about language, region and discipline, gives one example of a blind spot, and does **not** answer for the student |
| 5. Suggest frameworks | One main and at most one supporting framework, each with the question it lets you ask and one thing it cannot see; a small table maps patterns to frameworks (Spivak, Said, Crenshaw, Harding, Mbembe, Ahmed, Williams, Buell, Genette) |
| 6. Write the extraction prompt | Builds it in eight labelled blocks: role, research question, lens, text, theme list, task, rules, output format |
| 7. Prepare for interpretation | Lists what to check by hand and reminds the student that counts support an argument but do not make it |

## Choices I made, and why

- **It does not write the essay or the interpretation.** Those are the student's work. The skill tells the model to decline politely and offer to help find a question instead.
- **It will not claim things about the text that are not in the pasted lines.** This is the most common way a model goes wrong with literature.
- **It separates what is visible from what is guessed.** The student can see which part of the answer rests on their own lines.
- **It limits itself.** At most two questions per reply, and under 600 words unless asked for more, so the reply stays usable.
- **The framework table is a starting map, not an authority.** The skill tells the student to read a primary source before citing any framework and not to invent page numbers or quotations.
- **It has a "when not to use" section.** If the student has not read anything yet, the skill sends them back to read a sample first, because the whole method depends on a real reader's first impression.
- **The prompt it builds carries the lessons from assignment 3.** It asks for word-for-word quotations of 25 words or fewer, allows an empty list, and tells the student to check quotations against the source by script. That check was needed in my own run, where 7 of 20 model quotations failed an exact-match test.

## Structure of the file

The skill follows the usual layout of a skill file:

1. A short header with `name` and `description`. The description says when the skill should be used, which is what lets a tool decide to load it.
2. Purpose, when to use it and when not to.
3. The process, step by step.
4. The output format (fixed headings in a fixed order).
5. Style rules (talk like a patient tutor, never present a guess as a finding).
6. One worked example, using the "Sultana's Dream" lines.

## How to use it

- **In any chat model** (Claude, ChatGPT, a model in LM Studio): paste the content of the skill file at the start of the conversation, or put it in the system prompt. Then paste your partial reading and ask what you can research.
- **As a skill in a tool that supports them:** create a folder named `synthetic-reading-guide`, save the file inside it as `SKILL.md`, and add the folder in the tool's skill settings.

## Links for the website

Replace `USERNAME` and `REPOSITORY` with the real names before submitting.

| File | URL |
|---|---|
| synthetic_reading_guide_skill.md | https://github.com/USERNAME/REPOSITORY/blob/main/synthetic_reading_guide_skill.md |

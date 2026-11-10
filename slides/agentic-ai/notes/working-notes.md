# Agentic AI Talk — Working Notes

Short presentation for the eSAIL instructional design team. Goal: a shared, accurate understanding of "agentic AI", not boilerplate.

We're working through this one chunk at a time.

| # | Chunk | Status |
|---|-------|--------|
| 1 | Definition and why it's not a tight definition (spectrum) | **In progress** |
| 2 | vs. narrow AI | Not started |
| 3 | vs. chatting with an assistant | Not started |
| 4 | Higher ed / ID examples | Not started |
| 5 | Cautions | Not started |
| 6 | Open decisions (talk length, audience starting point) | Not started |

---

## Visuals archive

- All inline visuals made so far (9) are backed up in `agentic-ai-visuals-archive.html`, labeled A–I in creation order.
- The final export will rebuild each one as a standalone SVG, renumbered in talk order.
- Still to make: use/configure/build, the dial depends on the goal, three places to save.

## Sources

1. **Anthropic, "Building effective agents"** (Dec 19, 2024; still the most-cited vocabulary).
   https://www.anthropic.com/research/building-effective-agents
   - Use it for the definitions, not the product details. Anthropic notes much of the tooling has changed since publication.
2. **EDUCAUSE Exchange, "4 Ways Agentic AI Will Reshape Higher Ed Work"** (Aug 20, 2026). Guests: Mark Daley (Chief AI Officer, Western University) and Szymon Machajewski (Director of Academic Systems, UIC).
   https://er.educause.edu/podcasts/educause-exchange/4-ways-agentic-ai-will-reshape-higher-ed-work

Vendor blogs with recycled market statistics were deliberately left out.

---

## Chunk 0 — Foundations (new, requested 2026-10-27; goes before the definition)

Purpose: give the team a shared base, since people are at different stages of use and knowledge.

**Narrative, from basic to specific:**
1. **AI** is the umbrella: systems that do tasks that normally need human judgment, such as recognizing speech, predicting outcomes, or writing text.
2. **Machine learning** is how most modern AI is made. The system learns patterns from examples (data) instead of following rules someone wrote.
   - Contrast: rules-based software, e.g. a checker that follows fixed if-then rules, was never trained.
3. **A model** is the trained result: learned patterns that turn an input into an output.
4. **Two kinds of models:**
   - *Specialized*: one function (captions, risk scores, OCR, text-to-speech). This is "narrow AI."
   - *General*, also called foundation models or LLMs (Opus, GPT, Gemini): many tasks, steered by instructions.
5. **Doors (interfaces):** desktop/web app, command line, or your own script calling the model through an API. The same model can sit behind each door.
6. **The system around the model** decides what it can do: tools, workspace, loop, who decides the next step. This is where "chat," "workflow," and "agent" live. → hand-off to chunk 1.

**Interface question (Gerry):** the interface is a door, not a category.
- Doors matter in practice because each one bundles different tools, permissions, and places to run:
  - An app gives you a sandbox plus connectors.
  - A command-line tool works on the files on your own computer.
  - A script gives you exactly what you code.
- An app can be used for chat or agentic work. A script can be a one-job tool, a workflow, or an agent.

**Doors matter for capability (Gerry):** "interface" is the technical term and "door" is the metaphor; use both once.

| Door | What it gives you |
|---|---|
| Chat app (web/desktop/mobile) | Sandbox, connectors, projects. The easiest start; the vendor runs it. |
| Assistant inside your tools | Works on the file you have open, e.g. Copilot in Word or Gemini in Docs. |
| Command line | Works on files on your computer and runs commands. For technical users. |
| Your script (API) | Exactly what you code. Can be a one-job tool, a workflow, or an agent. |

**Saved setups** ride on any door: instructions + files + skills.

**Custom GPTs and Gems (checked 2026-10-27):** both are being retired and folded into skills.
- **OpenAI:**
  - Personal accounts can no longer create GPTs; Business/Enterprise/Edu still can.
  - Enterprise retirement is scheduled for Dec 11, 2026.
  - Migration path: plugins. Instructions become a skill, connected apps become apps, and knowledge files become reference files.
- **Google:** reportedly phasing out Gems in favor of Gemini skills, with automatic migration starting Nov 17, 2026.
- Strong evergreen lesson: teach "saved setup = instructions + files + skills," not product names.
- A custom GPT/Gem was mostly chat with preset context. It became agentic only if it had actions/tools.

**Script vs. workflow (clarified):**
- A script is *how something is built*: code.
- A workflow is *who controls the path*: steps fixed in advance.
- A script can implement a one-job tool, a workflow, or an agent.
- A workflow can also be built without code, e.g. no-code flow builders.

**Workflow logic, refined (Gerry: "isn't a workflow a series of scripts?"):** both directions are true.
- A workflow has two parts:
  - **Steps**: each can be a script, a model call, a tool, or a person. → "A workflow is a series of scripts."
  - **A conductor** that runs them in a fixed order: a main script, a no-code flow, or a person with a checklist. → "A script contains a workflow."
- What makes it a workflow is not the scripts. It's that **the order is fixed in advance**. Swap the conductor for the model and it becomes an agent.
- Recipe analogy:
  - Workflow = a recipe followed exactly.
  - Steps = appliances and tasks.
  - Agent = a chef who tastes and decides what to do next.
- **Visual 0c: "Anatomy of a workflow."**
  - The conductor sits above four fixed steps, color-coded by type, using the alt-text pipeline as the example.
  - Tagline: "The workflow is the fixed order, not the scripts."

**Workflow vs. skill (Gerry's question: "is it the degree of autonomy?"):**
- They are different kinds of things. Autonomy is the *result* of that difference, not the definition.
  - A **workflow** is enforced. Code (or a flow builder) is the conductor and runs the steps in order no matter what.
  - A **skill** is guidance. It's written instructions (plus optional scripts/files) that the *model* reads. The model stays the conductor: it follows your preferred how but can adapt, loop back, add, or skip when the situation calls for it.
- Recipe analogy:
  - Workflow = a machine running the recipe.
  - Skill = your recipe card handed to the chef.
  - Open agent = a chef improvising.
- Live example: the co-develop-presentation skill said "chunk by chunk." When Gerry asked for a new chunk 0, Claude added it. A workflow would have kept the fixed chunk list.
- A skill can *contain* workflow pieces, e.g. a script the agent runs for one fixed sub-task.
- **Visual 0d: "Same steps, different conductor"** (approved concept: Gerry flagged it as powerful).
  - Three columns: workflow / guided agent (model + skill) / open agent.
  - The same three steps in each, with an autonomy arrow underneath.
  - Tagline: "A skill guides the agent. A workflow replaces it."

**Visual 0b: "Doors to the model."**
- A 2×2 grid of door cards with capabilities, plus a "saved setups ride on any door" band.
- Tagline: "Same model. The door decides what it can reach."

**Visual 0: "From AI to a model you can reach."**
- Nested layers: AI ⊃ machine learning ⊃ specialized vs. general models.
- Three doors point to the same general model.
- Tagline: "Doors, not categories."

## Chunk 1 — Definition

**Working definition (draft):**
Agentic AI is a system where the AI decides its own next step toward a goal. It acts on things outside the conversation, looks at the results, and adjusts, repeating until the goal is met or it needs a human.

**Three ingredients:**
- **Goal**: a desired outcome, not just a prompt.
- **Tools**: ways to act outside the chat (files, LMS, search, email).
- **Loop with feedback**: plan → act → observe → adjust.

Anthropic's description of the mechanics: agents are typically LLMs using tools based on environmental feedback, in a loop.

**It's not a tight definition. It's a spectrum.**
- Anthropic groups everything under "agentic systems" but splits it into two kinds:
  - **Workflows**: LLMs and tools follow predefined code paths. Steps are fixed in advance.
  - **Agents**: the LLM directs its own process and tool use.
- The placement test: **Who decides the next step: a human, a script written in advance, or the model?**
- Anthropic's practical advice is to use the simplest option that works. Sometimes that means not being agentic at all.

**Visual:** an infographic showing the definition, the three ingredients, and the spectrum. Gerry has approved the definition wording and the spectrum.

**Discussion note: "agentic" from agency, or from acting on someone's behalf?**
- Both senses of "agent" are in play, and each maps to a different part of the definition:
  - **Agent as representative** (a travel agent, an agent acting for a principal): it works toward a goal someone *assigned*. This is the *goal* ingredient.
  - **Agency as discretion** (the capacity to choose how to act): this is what the spectrum measures. More agentic means more discretion over the *how*.
- Key line: **the human sets the what; the agent gets discretion over the how.** The AI doesn't pick its own goals.
- The representative sense explains accountability. If someone acts on your behalf, you answer for them, which matches Daley's "if it's your agent, you're accountable."
- **Visual 2 (approved concept): "Agent vs. agency."** Two columns:
  - Agent (acts on someone's behalf) → the what (goal set by a human) → stays fixed along the spectrum.
  - Agency (discretion) → the how (steps, tools, recovery) → shifts from human to script to model.
  - Tagline: "The human sets the what. The agent gets discretion over the how."
- Optional hook for IDs: "learner agency" in our field means choice over the *what*. Agentic AI has agency over the *how*. The word is the same, but the scope is different.

---

## Chunk 2 — vs. narrow AI (in progress, 2026-10-27)

**Definition:** narrow AI is a system built or trained for one specific task in one domain. It has a fixed input and output, and it can't carry its skill outside that task.
- ID examples: auto-captioning (speech-to-text), similarity/plagiarism scores, early-alert risk models, OCR on scanned PDFs.

**Nuances:**
- "Narrow" describes scope, not quality. Narrow AI can be excellent, even superhuman, at its one task.
- Not every automation is AI. A rules-based accessibility checker follows fixed rules; it isn't trained.
- Narrow AI isn't on the agentic spectrum at all. It is a single step, so there is no "next step" for anyone to decide.
- It's often the right choice: cheaper and more predictable. Captioning should stay narrow.

**Three categories, in order:**
1. **Narrow AI:** one task, does a step.
2. **General AI you chat with:** many tasks, responds.
3. **Agentic AI:** many tasks, acts and chooses the steps.

Category 3 is a general model plus tools plus a loop. This sets up chunk 3.

**Visual 4b: "Narrow AI vs. agentic AI."**
- Left: a fixed pipeline. Audio → speech-to-text → captions.
- Right: Goal → plan/act/check loop → tools.
- A dashed line shows the captioning model becoming one of the agent's tools.
- Tagline: "Narrow AI does one step. Agentic AI chooses the steps."

**Clarification (Gerry's question): what is "the AI"? Two layers.**

1. **The model** is the trained engine. There are two kinds:
   - *Specialized*: trained for one job, such as speech-to-text. It cannot do anything else.
   - *General*: an LLM like Opus. It can do many jobs depending on instructions.
2. **The system** is how the model is used. *Narrow* and *agentic* describe the system's job, not the model.

**Narrowness can come from either layer:**
- *From the model*: a captioning model can only caption.
- *From the wrapper*: a script sends each image to a general model with one fixed instruction ("write alt text") and saves the result. That is a narrow use of a general model.
- Strictly, the term "narrow AI" means specialized models. For the talk, say "narrow tool" or "one-job tool" to cover both.

**Same model, both roles:** Opus can be the agent's brain *and* be called by a script for one fixed job.

**An agent's tools come in three kinds:**
- Plain tools with no AI (search, save files, render)
- Specialized narrow AI (text-to-speech, captions)
- General models in a fixed job (an alt-text script)

Tools can also be other agents (subagents).

**Research is not a narrow step.** Search, read, decide, search again is a loop, so the agent does it itself. That makes research agentic. A step can be agentic too.

**Visual 4c: "One agent, many kinds of tools"** (podcast example).
- Goal → Agent → three color-coded columns: plain tools / narrow AI / narrow use of a general model.
- Tagline: "Narrow or agentic describes the job, not the model."

**Vocabulary for the talk (agreed with Gerry):**

| Term | Meaning |
|---|---|
| Narrow AI | Reserved for *specialized models*, i.e. a model with one function (captioning, text-to-speech). |
| One-job tool | Anything that performs one fixed step: a specialized model, a general model in a fixed wrapper, or a plain tool. |
| Workflow | A script chains several steps in a fixed order. The model may run each step, but the *script* decides the next step. Anthropic's term: predefined code paths. Not narrow, because it has many steps. Not an agent, because the model doesn't choose the path. |
| Agent | The *model* decides the next step. |

- If the script asks the model what to do next and follows its answer, the system has crossed into agent territory.
- Gerry's alt-text pipeline is likely a *workflow*: multi-step, fixed path.
- The spectrum test still sorts everything: *who decides the next step?* Nobody (a single step) → one-job tool. The script → workflow. The model → agent.

**Concrete examples by category (for a slide or handout):**

| Category | Who decides the next step | ID / higher-ed examples |
|---|---|---|
| Plain tool (not AI) | Nobody; fixed rules | Rules-based accessibility checker, broken-link checker |
| Narrow AI (specialized model) | Nobody; one step | Auto-captions, text-to-speech narration, similarity score, early-alert risk score, OCR on scanned PDFs |
| One-job tool (general model, fixed job) | Nobody; one step | Script that writes alt text for one image; a "summarize this transcript" button |
| Workflow | The script | Transcript → split into 10–15 min segments → draft quiz questions per segment; alt-text pipeline (extract → describe → check → save) |
| Agent | The model | "Evergreen this course shell": explores pages, finds date-specific references, drafts fixes, asks for approval; "make module 3 accessible"; research and draft a talk |

**Earlier draft points:**

- Narrow AI is one trained function: input in, output out. Examples: speech-to-text captions, a similarity score, an early-alert risk model. It never decides what to do next.
- It's a part, not a rival: an agent can call a narrow tool as one of its steps.
- Contrast with rigid automation. Daley calls older process automation brittle, built on simple classifiers and rules. Agents can weigh messy context.

## Chunk 3 — vs. chatting with an assistant (in progress, 2026-10-27)

**Key insight (Gerry): in pure chat, the human is the agent.**
- You hold the goal, plan the steps, act in the world (paste, edit, send), check the result, and loop.
- The AI is a consultant you call once per turn, effectively a one-job tool each time.
- In conductor terms: in chat, *you* conduct.

**Unifying idea across all visuals: who conducts?**

| Mode | Who conducts |
|---|---|
| Chat | You |
| Workflow | A script |
| Guided agent | The model + a skill |
| Open agent | The model alone |

- This is the same as the spectrum test, "who decides the next step?" Consider adding a "You conduct (chat)" column to visual I.

**Visual J (approved concept, Gerry: "the perfect analogy"): "Someone always conducts the work."**
- Four columns, each with a simple line icon:
  - Chat (person): you conduct.
  - Workflow (checklist doc): a script conducts.
  - Guided agent (chip + recipe card): model + skill.
  - Open agent (chip + sparkle): the model conducts.
- An autonomy arrow runs underneath.
- Tagline: "Someone has to conduct: you, a script, or the model."

**Terminology:**
- "Orchestrator" is the industry term; Anthropic's pattern is called "orchestrator-workers."
- "Conductor" is the plain-language metaphor; it fits, since conductors lead orchestras.
- Use both once: "the conductor, or orchestrator."
- Gerry's phrasing: in a workflow, agency is turned into a list of steps that run scripts, some of which call AI with specific prompts. In agentic AI, the agent *is* the orchestrator.

**The gray zone grew with "Work"-style modes.** ChatGPT's Work mode, and Claude, where the former Cowork capabilities are now part of the app itself, give the AI a workspace and tools inside the chat app. So the AI can take over conducting for parts of a task, and the same app slides along the spectrum depending on what you let it do.

**Example table — "Fix the date references in this course":**
- Chat: the AI explains or lists; you copy, open Canvas, and edit page by page. Nothing changes until you act. Your effort goes into doing.
- Agentic: the agent opens the course, searches every page, drafts fixes, and pauses for approval before saving. The course itself changes. Your effort goes into checking.

**Takeaway:** going agentic moves effort from doing to checking. This sets up the cautions chunk.

**Earlier draft points:**

- This is the most conflated distinction. Chat products now have agent-like features such as web search, so "chatbots just talk" won't hold up.
- The cleaner line is **who closes the loop**:
  - In chat, you are the loop. You read, decide, and paste into Canvas.
  - In an agentic setup, the system takes the next step itself and changes things outside the conversation.
- Machajewski's framing: in 2022 you asked and the model told you what it knew. Now a request goes through many steps before results come back.
- Live example: the research step of building this talk was partly agentic. Claude chose searches and picked sources. It didn't act outside the chat, though, and the human still decided each next step.

## Chunk 4 — Higher ed / ID examples (draft, not yet discussed)

- **Evergreening audit**: an agent walks a cloned course shell, flags date-specific references, and drafts fixes for a designer to approve.
- **Accessibility remediation**: find images missing alt text, draft descriptions, queue them for review.
  - Discussion point: a fixed-step alt-text pipeline is a *workflow*, not an agent, and that's fine.
- **From EDUCAUSE**:
  - A researcher's agent that searches the literature each morning and delivers a summary.
  - Monitoring a discussion forum against rules the instructor sets.

## Chunk 5 — Cautions (in progress, 2026-10-27)

**Framing:** each caution grows as the conductor shifts from you toward the model. Every caution comes with a practical countermeasure.

| Risk | What it looks like | What to do |
|---|---|---|
| Accountability stays with you | The agent sends, edits, or publishes; you answer for it | Own the *what*; delegate only actions you'd defend |
| Errors compound, and agents grade themselves kindly | A wrong assumption at step 2 runs through every step after; the agent reports success | Checkpoints after early steps; check against the source, not the agent's summary |
| Rubber-stamping ("agency laundering") | After several good results, approvals become reflexive | Fewer, meaningful checkpoints; spot-check the details |
| Data goes where the agent goes | Connectors expose more than intended; hidden instructions in a page or file steer the agent | Approved tools only; least access; treat content the agent reads as untrusted |
| Skills fade, and saved time vanishes | You can no longer spot the agent's errors; freed time fills with more volume | Keep doing some of the work by hand; decide in advance where saved time goes |

**Visual K (Gerry's concept): "More AI control, more risk, unless you shape it."**
- A chart with "how much the AI conducts" on the x-axis (chat → workflow → guided agent → open agent) and risk on the y-axis.
- Risk is defined as *how far a mistake can travel before a person sees it*.
- Two curves:
  - Left open (vague goal, broad access) rises steeply.
  - With guardrails, it rises gently.
- The gap between the curves is labeled "your strategy."
- Levers: clear brief, skill, reference docs, checkpoints, least access.
- Footer: "Guardrails lower risk. They never remove it."
- Gerry's point: risk depends on strategy, i.e. how open the goal is, the quality of the brief/prompt, and whether a skill or documents are included. It does not depend on autonomy alone.

**Sources:**
- Daley (EDUCAUSE) on accountability, rubber-stamping, and skill atrophy.
- Anthropic on compounding errors and cost.
- InfoQ/Anthropic: agents overrate their own results, so use a separate evaluator.
- EDUCAUSE theme 4: saved time has to go somewhere.

Prompt injection (hidden instructions in content the agent reads) is general knowledge; it's worth one plain sentence in the talk.

**Earlier draft points:**

- **Accountability**: if it's your agent, you're accountable for what it does (Daley).
- **Rubber-stamp oversight**: after an agent is right several times, people approve without looking. "Human in the loop" becomes true on paper only.
- **Errors compound**, and costs are higher (Anthropic). A mistake early on carries through every later step.

## New chunk — How do you get it? (draft, raised by Gerry; placement TBD)

**Use, configure, or build?** There are three levels:
1. **Use**: turn on agent features in a product you already have, such as ChatGPT agent mode, the Claude app, or Copilot. No setup.
2. **Configure**: no-code. Connect apps, add instructions, schedule tasks. Example: M365 Agent Builder.
3. **Build**: code. SDKs/APIs, custom tools, your own hosting. Example: Copilot Studio at the pro end, agent SDKs.

Most instructional designers will work at levels 1–2.

**Do we need Python scripts?** Not at levels 1–2. The agent writes and runs its own throwaway code in its sandbox. You only write tools to connect a system that has no connector.
- Pattern: let the agent figure out a process once, then freeze it into a script. That moves the task *left* on the spectrum, from agent to workflow, which makes it cheaper and more predictable.

**Setting goals:** write it like a delegation brief:
- Outcome
- Materials/context
- What "done" looks like
- Boundaries (what it may touch)
- Checkpoints (when to stop and ask)

**Reporting and continuity:** agents don't remember between sessions. Continuity comes from:
- Written state (progress files, task lists)
- Schedules for recurring runs

Live example: this working-notes file is doing that job for our project.

**Where it lives:**
- The vendor's cloud sandbox (e.g., ChatGPT agent's virtual computer, Claude's cloud workspace)
- Your own computer (desktop app, coding agents)
- Your organization's cloud tenant (e.g., M365 / Copilot Studio, AWS/Azure)

Where it lives = where your data goes.

**Vendors converge on the same anatomy.** OpenAI's naming is a good example: "Agent mode" is reportedly now "Work" in ChatGPT. Claude's agent capabilities run in the same chat app without a separate mode. Every major product has the same parts:
- A model
- A workspace (a sandboxed computer)
- Tools and connectors
- Persistence (projects/files)
- Cloud or local execution

Teach the anatomy, not the brand names, because the names change every few months. This is the evergreening principle applied to the talk itself.

**Visual 3 (approved concept): "Same anatomy, different names."**
- Top: product names as plain chips (ChatGPT, Claude, Copilot, Gemini).
- Below: a container with the Model at the center, linked to Workspace, Tools and connectors, Persistence, and Where it runs.
- Tagline: "Names change every few months. The anatomy doesn't." Then the spectrum test.

The Chat-vs-Work toggle is a product design choice, not the definition. The test is still who decides the next step and whether it acts outside the chat.

**TAMU context to verify:**
- TAMU requires AI tools to be reviewed by IT Security (System Policy 29.01.05).
- Approved options include M365 Copilot Chat / Copilot and TAMU AI Chat (beta, multi-model).

## Concept — More agentic isn't automatically better (approved)

- Being agentic is a **setting you choose**, not a quality score.
- The right setting depends on:
  - **The person's goal.** Do they want the output, or also the understanding?
  - **How much control they want.** Fine-tuning as they go, or reviewing only at the end?
- Turning the dial right gives speed and less effort, but also less understanding and less control.
- Turning it left gives more control and learning, but costs more time and attention.
- The dial can move per step within one task.
- Suggested line: **"Choose the setting based on the goal, not on what's possible."**

- Gerry's framing for the talk: **collaboration mode is a deliberate choice of "shared agency,"** not a leftover habit from early models.
- Many people who started with early models still hand-hold step by step, so they may not realize how much they can now delegate.
- Planning vs. plan mode:
  - Models now plan internally on their own.
  - A "plan mode" is a *permission* checkpoint: no actions until you approve the plan. It varies by product.
  - If you want the checkpoint, ask for it in the brief.

## Possible case study — "This talk, built two ways" (raised by Gerry)

- **Option A: one-shot.** "Build me a presentation on agentic AI." Claude picks the outline, sources, examples, and visuals, checks its own work, and delivers. The how shifts right: more agentic.
- **Option B: co-developed (what we actually did).** Within each turn, Claude acted agentically: chose searches, picked sources, wrote files, drew visuals. Between turns, Gerry was the loop.
- **Middle setting:** a delegation brief with checkpoints, e.g., "draft the definition section, then stop for my review."
- Key lessons:
  - More agentic ≠ better. The right setting depends on the goal.
  - Gerry's goal included *understanding the material well enough to present confidently*. Delegating fully would have delivered slides but not that understanding. This ties to EDUCAUSE theme 3: expertise shifts from execution to judgment, and skills atrophy if you outsource everything.
  - Several core ideas came from the human side: the agent-vs-agency question, the "how do you get it" chunk, and the app-agnostic visual. A one-shot run would likely have produced the generic explainer we wanted to avoid.
- The dial can move per step, not just per tool.

## Podcast script (drafted 2026-10-26)

- Format: a Claude Doc titled "Making It Agentic — Podcast Script," with two voices, Jordan (ID) and Agent, about 12–14 minutes.
- Story arc:
  1. Cold open
  2. Definition and spectrum (V1)
  3. Agent vs. agency (V2)
  4. How to get it (V4, V3)
  5. "Could I have asked for the deck?" (V5)
  6. Skills / more agentic relationship (V6)
  7. Close
- New visuals still to make:
  - V4: Use / configure / build
  - V5: The dial depends on the goal
  - V6: Three places to save (skill, memory, notes)

## Chunk 6 — Open decisions

- Where to draw the line. Current lean: teach the spectrum plus the "who decides the next step?" test.
- The audience's starting point: have they used Claude Code, Cowork, or agent modes, or mostly chat?
- Talk length.
- Final format: Slides artifact.

---

## Updates — 2026-11-10 (repo session)

- **Talk length decided:** about 30–45 minutes, split into 3 shorter parts. Audience: the eSAIL team, mostly experienced instructional designers who are relative beginners with AI.
- **Proposed 3-part split** (not yet agreed):
  1. *What are we even talking about?* Chunk 0 foundations, chunk 1 definition and spectrum, chunk 2 narrow vs. agentic and vocabulary.
  2. *Who's conducting?* Workflow anatomy, workflow vs. skill vs. agent, chat vs. agentic, visual J as the anchor.
  3. *Using it well and safely.* How do you get it, higher-ed/ID examples, "more agentic isn't automatically better," cautions with visual K, the "built two ways" closer.
- **Final format changed:** instead of a Slides artifact, the deck will be a full-screen HTML deck in this repo at `slides/agentic-ai/`, matching `slides/accessible-media-overview/` (same slide structure, keyboard navigation, handout view).
- **Palette:** use the existing deck's maroon tones: `--maroon #500000`, `--maroon-dark #3c0000`, `--maroon-light #732f2f`, `--sand #d6d3c4`, `--white #ffffff`, `--focus #1a5fb4`.
- **Visuals:** the earlier session also made visual K (risk vs. control), so there are 11 archived visuals (A–I, J, K), not 9. `agentic-ai-visuals-archive.html` still needs to be added to the repo before they can be rebuilt as slides.
- **Re-check before the talk:** custom GPT retirement (Dec 11, 2026) and Gems migration (Nov 17, 2026).
- **Suggested delegation experiment** (from the earlier session), to compare with step-by-step work:
  > Make the three missing visuals for the podcast script (V4: use/configure/build, V5: the dial depends on the goal, V6: three places to save). Match the style of the first three. Give me your plan first; after I approve it, build all three without checking in, update the script's visual cues if anything changes, and give me a short summary of any choices you made.

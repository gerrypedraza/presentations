# Agentic AI talk: working notes

Reconstructed from the earlier working session with another agent (pasted into this session on 2026-11-10). This file holds the decisions, vocabulary, and chunk content agreed so far. The earlier session also produced its own notes file (`Agentic ai talk working notes.md`) and a visuals archive (`agentic-ai-visuals-archive.html`); neither has been added to this repo yet.

## Talk basics

- **Audience:** the ESAIL team. Mostly experienced instructional designers who are fairly new to AI, at different stages of use and knowledge.
- **Length:** about 30–45 minutes, split into 3 shorter parts.
- **Goal:** give everyone the same shared vocabulary first, then build up to agentic AI, how to use it, and how to use it safely.
- **Companion piece:** a podcast script with visual cues (V1–V6). V4–V6 still need to be made (see Visuals).

## Core idea of the whole talk

**Someone has to conduct.** Every mode of AI use comes down to one question: *who decides the next step?*

- "Conductor" is the plain-language word. "Orchestrator" is the technical word (Anthropic's guide names an "orchestrator-workers" pattern). Say both once, then use whichever lands.
- Teach the **question** ("who's conducting right now?"), not the label ("is this an agentic app?"). The same app can slide along the whole spectrum.

| Mode | Who conducts |
| --- | --- |
| Chat | You |
| Workflow | A script (steps fixed in advance) |
| Guided agent | The model, following a skill |
| Open agent | The model alone |

In pure chat, **the human is the agent**: you hold the goal, plan the steps, carry each result into the world, check it, and decide what's next. The AI is a consultant you call once per turn.

## Chunk 0: Foundations (new; added so everyone starts from the same base)

Narrative, one new idea per step:

1. **AI** is the umbrella term: systems doing tasks that normally need human judgment (recognizing speech, predicting outcomes, writing text).
2. **Machine learning** is how most modern AI is made: the system learns patterns from examples instead of following rules someone wrote. That's why a rules-based accessibility checker isn't really AI: nobody trained it.
3. A **model** is what training produces: learned patterns that turn an input into an output. When people say "the AI," they usually mean the model.
4. Two kinds of models:
   - **Specialized models** do one function (captions, risk scores). These are *narrow AI*.
   - **General models** (Opus, GPT, Gemini) do many tasks depending on their instructions.
5. **Doors:** you reach a model through an app, a command line, or your own script.
6. **The system around the model** (tools, workspace, loop) decides what it can actually do. This is where chat, workflow, and agent live. Hand-off to chunk 1.

### Doors (interfaces)

"Interface" is the technical word, "door" the metaphor. The door is not a category, but it shapes what's possible because each comes with different tools and permissions:

- **Desktop/web app:** sandbox and connectors.
- **Command-line tool:** usually works directly on files on your computer.
- **Your own script:** does exactly what you coded and nothing more.

The same model can sit behind any door. A desktop app can do chat or agentic work; a script can be a one-job tool, a workflow, or an agent.

### Saved setups (GPTs, Gems, skills)

A saved setup = instructions + files (+ skills). It rides on top of any door rather than being a door of its own.

- **Custom GPTs** are being retired in favor of plugins: instructions become a skill, connected apps become apps, knowledge files become reference files. Personal accounts can no longer create new GPTs; Enterprise retirement scheduled for **December 11, 2026**.
- **Gems** are reportedly being phased out in favor of Gemini skills, with automatic migration starting **November 17, 2026**.
- **Re-check both dates right before the talk.** They were current as of the earlier session.
- Colleagues who built GPTs or Gems aren't behind: they already built saved setups. Every vendor is moving that idea into skills.
- Strong evergreening example: "How to build a custom GPT" would be outdated within weeks; "a saved setup = instructions + files + skills" will last.
- On the spectrum, most GPTs/Gems were chat with preset context. They only became agentic if they had actions that did things outside the conversation.

Sources from the earlier session: OpenAI Help Center (custom GPT retirement and migration FAQ); Jotform, "What is a custom GPT? (2026)"; EdTech Innovation Hub, "OpenAI to retire custom GPTs in December"; NewsBytes, "Google phases out Gems, adds Gemini skills."

## Chunk 1: Working definition and spectrum

The spectrum test (visual 1): **who decides the next step?** Also covers "agent vs. agency" and "same anatomy, different names" (visuals listed below). Detailed text for this chunk lives in the earlier notes file.

## Chunk 2: Narrow AI vs. agentic AI

**Narrow AI** is a system built or trained for one specific task in one domain: fixed kind of input, fixed kind of output, and it can't carry that skill anywhere else (a captioning model can't summarize a lecture; a plagiarism detector can't grade an essay). The team already uses plenty: auto-captioning, similarity scores, early-alert risk models, OCR on scanned PDFs.

Key relationship: narrow AI isn't a rival to agentic AI; it's a possible **part** of it. An agent working toward "make module 3 accessible" might call the same captioning model as one step.

Nuances to say out loud:

- "Narrow" describes **scope, not quality**. Narrow AI can be excellent at its one job.
- Narrow AI isn't on the spectrum at all: it's a single step, so there's no next step to decide.
- It's **often the better choice**: cheaper and more predictable. Captioning should stay narrow (Anthropic: use the simplest thing that works).
- Not every automation is AI: a rules-based checker follows rules someone wrote.

### Two layers: the model and the job

- **Layer 1, the model:** specialized (one job) or general (many jobs).
- **Layer 2, the job:** how the model is used. "Narrow" and "agentic" describe this layer.
- Narrowness can come from the model (captioning) or from the job it's locked into (a script that only asks Opus for alt text).
- An agent's tools come in three kinds: plain tools (no AI: web search, saving files), narrow AI (specialized models like text-to-speech), and a general model in a one-job wrapper (an alt-text script).
- Research is not a narrow step: search, read, decide what's missing, search again. That's a loop, so the agent does it.

### Vocabulary (decided)

- **Narrow AI:** only for specialized models (one model, one function).
- **One-job tool:** anything that does one fixed step, whether a specialized model, a general model locked to one instruction, or a plain script.
- **Workflow:** models and tools orchestrated through predefined code paths (Anthropic's definition). The script decides what happens next.
- **Agent:** the model decides, choosing steps as it goes.

Clue for the workflow/agent line: if a script ever asks the model "what should I do next?" and follows the answer, it has crossed into agent territory. Doing one thing at a time isn't what makes something non-agentic (agents also do one thing at a time). What matters is **who chose that one thing**.

### Examples table (for chunk 2)

| Category | Who decides the next step | Examples from our world |
| --- | --- | --- |
| Plain tool (not AI) | Nobody, fixed rules | Rules-based accessibility checker, link checker |
| Narrow AI | Nobody, one step | Auto-captions, text-to-speech narration, similarity scores, early-alert risk scores, OCR |
| One-job tool | Nobody, one step | A script that writes alt text for one image; a "summarize this transcript" button |
| Workflow | The script | Transcript → split into segments → draft quiz questions per segment; an alt-text pipeline |
| Agent | The model | "Evergreen this course shell," "make module 3 accessible," research and draft a talk |

### Script vs. workflow

Both "a workflow is a series of scripts" and "a script can contain a workflow" are true, because a workflow has two parts:

- **The steps:** each can be a script, a model call, a plain tool, or a person.
- **The conductor:** runs the steps in order. Often a main script, but could be a no-code flow builder or a person with a checklist.

A script is *how something is built* (code); a workflow is *who controls the path* (fixed in advance). What makes it a workflow is that **the order is fixed in advance**. Swap the conductor for the model and it becomes an agent, even with identical steps.

Recipe analogy: a workflow is a recipe followed exactly; the steps are tasks and appliances (a blender is a one-job tool); an agent is a chef who tastes, decides it needs more acid, and changes the plan.

### Workflow vs. skill

Autonomy is the result, not the definition. They're different kinds of things:

- **A workflow is enforced.** The conductor is code or a flow builder; it runs the steps in order no matter what. If step 2 produces something odd, step 3 runs anyway.
- **A skill is guidance.** Written instructions (sometimes with scripts or files) that the model reads. The model is still the conductor and can loop back, add, or skip steps when needed.
- Recipe analogy: a workflow is a machine running the recipe; a skill is a recipe card handed to the chef; an open agent is a chef improvising with no card.
- A skill can contain workflow pieces (a script for one fixed sub-task); the agent still decides when to run it.
- On the spectrum, a skill sits inside agent territory, at the guided end.
- **Tagline: a skill guides the agent; a workflow replaces it.**
- Live example: the presentation skill says to work chunk by chunk; when chunk 0 was requested, it was added, because the card guides rather than locks.

## Chunk 3: Chat vs. agentic

Core line: **who closes the loop.**

- **Chat:** you are the loop. The AI answers; you read it, decide, and carry the result into the world (paste into Canvas, send the email, fix the file).
- **Agentic:** the system closes the loop, takes the next step, and changes things outside the conversation.

| "Fix the date references in this course" | Chat | Agentic |
| --- | --- | --- |
| What the AI does | Explains how to find them, or lists the ones in pasted text | Opens the course, searches every page, drafts each fix |
| Who takes the next step | You: copy, open Canvas, edit page by page | The agent, pausing for your approval before it saves |
| What changes in the world | Nothing, until you act | The course itself |
| Where your effort goes | Doing the work | Checking the work |

- **Gray zone:** chat apps now have web search, file creation, connectors, and work modes (ChatGPT's Work; Cowork, now built into Claude). Within one reply the AI may take a few steps on its own (a little agentic); between replies, you decide. The line was never really between apps.
- **Takeaway:** going agentic doesn't remove effort; it **moves it from doing to checking**. Sets up the cautions chunk.

## Chunk 4: How to get it

Content from the earlier notes file (doors, saved setups, delegation brief, "where it lives is where your data goes"). Not fully captured in the pasted conversation.

### Delegation brief and plan mode

- Planning now happens automatically: current models break complex tasks into steps on their own.
- **"Plan mode" is a permission checkpoint, not a thinking mode**: the agent may read and research but takes no actions until you approve. Whether it kicks in automatically depends on the product.
- Reliable move: ask for it in the brief. *"Give me your plan first. Don't change anything until I approve it."* That's the middle setting on the dial: the agent decides the how, you get one look before it acts.
- A good brief has an **outcome, materials, done criteria, and one checkpoint**.
- **Shared agency:** working step by step isn't something to grow out of; it's a deliberate setting. Many people who started with earlier models still hand-hold because it was once necessary. Worth saying to the team.

## Chunk 5: Cautions

Frame: cautions grow as the conductor shifts from you toward the model. In chat you catch problems because you do every step; with an agent, problems travel further before anyone sees them.

| Risk | What it looks like | What to do |
| --- | --- | --- |
| Accountability stays with you | The agent edits, sends, or publishes, and you answer for it | Delegate only actions you'd be willing to defend |
| Errors compound, and agents grade themselves kindly | A wrong assumption at step 2 carries through every later step, and the summary says "done" | Checkpoint after the early steps; check against the source, not the agent's report |
| Rubber-stamping | After a few good results, approving becomes a reflex | Fewer but real checkpoints; spot-check the details |
| Data goes where the agent goes | Connectors reach more than you meant; hidden instructions in a page or file steer the agent | Approved tools; minimum access needed |
| Skills fade, and saved time vanishes | You can't spot the agent's mistakes anymore; freed time fills with more volume | Keep doing some work by hand; decide ahead where saved time goes |

Sources:

- **Accountability:** Daley: if it's your agent, you are accountable for what it does. Full stop.
- **Compounding errors:** Anthropic notes agents bring higher costs and potential for compounding errors, and that agents often overrate their own results (hence a separate evaluator agent).
- **Rubber-stamping:** Daley: after an agent is right seven times, you start clicking approve without paying attention; the agent's attention never runs out and yours does. Human in the loop on paper, not in practice.
- **Data:** "where it lives is where your data goes," plus prompt injection via web pages, email, or documents.
- **Skills fading:** Daley: the more you outsource, the rustier your skills, though you still need them to oversee the agent. EDUCAUSE: time saved by AI has to go somewhere.
- For instructional designers: their expertise (alignment, accessibility, pedagogy) *is* the judgment the agent lacks. Protect it.

Open: five cautions may be one too many. Suggested cut: fold "skills fade" into the closing reflection.

### Risk vs. control graphic (visual K)

- Two curves instead of one arrow; the gap between them is labeled **"your strategy."**
- **Risk defined on the slide** as *how far a mistake can travel before a person sees it*. Explains why chat is low, open agents high, and why checkpoints work (they shorten the distance).
- **Levers** along the bottom: clear brief, skill, reference documents, checkpoints, least access.
- Footer: **"Guardrails lower risk. They never remove it."**

## Closer

"This talk, built two ways": the first time, built step by step in conversation (the guardrail curve); the skill made for the presentation process moves that same safety into future runs. Possible addition: compare how the step-by-step session felt with a delegated run (see Experiments).

## Current talk order

Foundations → definition and spectrum → narrow vs. agentic (with examples table) → chat vs. agentic → how to get it → cautions → closer.

### Proposed split into 3 parts (~10–15 min each; not yet agreed)

1. **What are we even talking about?** Chunk 0 foundations, chunk 1 definition and spectrum, chunk 2 narrow vs. agentic and vocabulary.
2. **Who's conducting?** Workflow anatomy, workflow vs. skill vs. agent, chat vs. agentic, the conductor graphic as the anchor.
3. **Using it well and safely.** How to get it (doors, saved setups, delegation brief), cautions and the risk graphic, closer.

## Visuals

The earlier session made these as inline chat widgets; their source is saved in `agentic-ai-visuals-archive.html`, which hasn't been added to this repo yet. They borrow colors and fonts from the chat theme, so at final export each needs rebuilding as a standalone SVG with built-in colors and fonts, numbered in talk order.

Made (11):

1. From AI to a model you can reach (foundations)
2. Doors to the model (saved setups shown as a band across doors)
3. Anatomy of a workflow (conductor + steps)
4. Same steps, different conductor (workflow / skill / agent columns)
5. Working definition and spectrum
6. Agent vs. agency
7. Same anatomy, different names
8. Narrow AI vs. agentic AI
9. One agent, many kinds of tools
10. **Visual J:** Who conducts? Four modes with hand-drawn line icons (person = chat, checklist = workflow, chip + recipe card = guided agent, chip + spark = open agent). Subtitle: "Conductor = orchestrator: whoever decides the next step." Likely the anchor slide. Icons could be swapped for a set (Font Awesome, Material, department set) at export.
11. **Visual K:** Risk grows with control, and strategy bends the curve.

Pending (for the podcast):

- V4: use / configure / build
- V5: the dial depends on the goal
- V6: three places to save

Possible: a side-by-side visual for chat vs. agentic ("fix the dates"), or keep it as a table.

## Experiments

Suggested first delegated task, to compare against step-by-step work (and maybe use in the talk):

> Make the three missing visuals for the podcast script (V4: use/configure/build, V5: the dial depends on the goal, V6: three places to save). Match the style of the first three. Give me your plan first; after I approve it, build all three without checking in, update the script's visual cues if anything changes, and give me a short summary of any choices you made.

## Open questions

- Does the three-category framing (narrow / general chat / agentic) match how the team thinks today, or do they lump "AI" into one bucket?
- Cut one of the five cautions?
- Should the podcast script get a matching foundations opener, or stay focused on the agent conversation?
- Lock the overall flow and the 3-part split.

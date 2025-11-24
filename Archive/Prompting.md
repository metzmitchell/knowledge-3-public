---
status: Active
priority: Normal
tags: ["task"]
---

# Prompting

Status: Archive
Tags: AI, Knowledge, Task

**Image 1**

Ad agent is the primary thing you’ll use

Cursor fuels this. Not often used, but core

MCP - pull all logs in browser

Background agent - can go in and do longer tasks

while I’m doing other things

**Meta Prompting**

Parachute - customer support

- Very long - Markdown
- Role → Task → high level plan → important notes
    
    → structure
    
- How to reason about the task
- XML helps a lot
- Example of a plan - describe scenarios & how to do
- How to structure the output - important because of working with other agents
- Think of where the flexibility is necessary - which prompt is situation specific vs versatile

**System vs Developer vs user prompts**

- System is high level
- Add specific things, context of working with Perplexity, etc.
- End user prompt - exact specific needs (build a thing / button)

**Prompt folding**

- One prompt can generate better versions of itself
- Based on previous outputs
- Fed it previous examples of failures
- “Help me make this prompt better”

---

**Image 2**

- Add examples into meta prompts
- You have to give LLMs an escape hatch:
    
    “If you don’t have enough info, don’t just make it up. Stop and ask me”
    
    Or give it the ability to have part of the response to be a complaint to you. Delay info. Run it in production
    

When you need faster responses, do meta prompting within bigger models, then bring the prompt into smaller models

As the prompt gets longer - note things in adv that you’re seeing - then share that with the meta prompt writer

Look through the thinking “reasoning traces”

**Evals are the best asset**

- What does a specific person want & in this position
- Understand this person the closest
- Mercilessly obsessed with this person’s role
- Understand

**“Forward Deployed Engineer”** - sit right next to your ICP at their desk + gain insights + convert old things into clean stuff

- Have a meeting with an enterprise client, stuff all the info into the prompts, then turn around the next day
- Once they close the deal, they go onsite
- Win the deal with the best demo, can differentiate in the demo stage

Each model has its own personality

Give LLMs a rubric that has to be specific to the model

A quickie: trading system of priorities

- How I’ll evaluate & score them
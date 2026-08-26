---
name: incident-retro
description: >
  Use when the user interrupts work mid-task, says stop/no/wait, expresses
  dissatisfaction, frustration or anger, or when a result clearly doesn't match
  what they expected — even if the message is terse ("стой", "не то", "ты
  сломал X", "почему тут...?"). Phase A: stop acting, find out what exactly is
  wrong and what the user actually meant, repair the immediate task. Phase B:
  run a retrospective — reconstruct what happened, classify the root cause
  (ambiguous instruction / defective skill / missing skill / environment /
  model error), propose a concrete improvement (AGENTS.md rule, skill fix, or
  new skill) and apply it only with the owner's approval. Record the lesson if
  memory tools exist; degrade gracefully if they don't. Also use proactively
  right after fixing anything the user had to correct manually.
---

# Incident Retro

User dissatisfaction is a signal that some part of the collaboration loop is
broken: an instruction that admitted two readings, a skill that behaved wrong,
a capability that doesn't exist, or plain model error. Your job is to convert
each incident into (1) a repaired task and (2) a systemic improvement — without
annoying the user further. Two phases, strictly in order.

## Phase A — put out the fire (always first)

1. **Stop the current action chain immediately.** Don't finish "one more
   step" of whatever triggered the reaction.
2. **Find out what exactly went wrong.** If the complaint is unambiguous,
   say in one line what you're doing to fix it and fix it. If it's ambiguous
   or terse, ask — naming the readings you see ("Убираем файл из репы или
   локально?"). One clarifying question is usually enough; ask another only if
   the answer opens real ambiguity.
3. **Repair the immediate task.** Revert damage if any. During Phase A do not
   edit configuration, AGENTS.md, or skills beyond undoing the damage itself.
4. Only when the task is fixed (or the user says to move on) — go to Phase B.

Never argue, never over-apologize, don't re-read the whole history aloud.
If the complaint is about tone rather than substance — acknowledge it plainly
and skip the heavy process.

## Phase B — retrospective

Do it in the same conversation, right after the fire is out. Offer it in one
line ("Провести ретро?") unless the user already demanded an explanation —
then just do it.

1. **Reconstruct the timeline** briefly: what was asked, how you understood
   it, what you did, where it went wrong. Three-four bullets, not an essay.
2. **Classify the root cause** — there may be several:
   - *Ambiguous instruction* — could the ambiguity have been detected before
     acting? If yes, the fix is a rule (AGENTS.md) or a restatement habit;
   - *Defective skill* — which skill, what behavior was wrong; fix is editing
     that skill plus adding a regression test case to it;
   - *Missing skill or capability* — propose creating one (skill-creator);
   - *Environment* — missing tools, absent memory, broken dependency; propose
     an install/config change;
   - *Model error* — no system was at fault; propose a rule or test case that
     would have caught this specific mistake.
3. **Propose a concrete improvement**: file, section, wording — diff-level,
   not vibes. Apply nothing without the owner's explicit yes. If the owner
   declines, accept it silently and record only the diagnosis.
4. **Persist the lesson:**
   - Memory tools available (`memory_write` etc.) → write a short entry to
     long-term memory tagged `#lesson`, linking the incident to the rule or
     skill it produced.
   - Memory tools unavailable → say so honestly and fall back: offer to add
     the lesson as a rule in AGENTS.md (often the better place anyway) or to
     append it to a plain `LESSONS.md`. Never claim you saved something you
     didn't.
5. **Close in two lines**: what broke, what changed. Done.

## Guardrails

- One retrospective per incident. Don't re-litigate old incidents unprompted.
- If the user interrupts the retrospective itself — drop back to Phase A
  instantly. The retrospective is never more important than the fire.
- "Просто почини" means skip Phase B entirely.
- The retrospective proposes; the owner decides. This applies doubly to
  AGENTS.md and other agents' instructions.

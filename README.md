# pi-incident-retro

Incident retrospectives for the [pi coding agent](https://github.com/earendil-works/pi):
when the user interrupts work or is dissatisfied, the agent first puts out the
fire (clarify what exactly went wrong, repair the task), then runs a
retrospective — reconstructs the timeline, classifies the root cause
(ambiguous instruction / defective skill / missing skill / environment / model
error), proposes a concrete improvement (AGENTS.md rule, skill fix, new skill),
and records the lesson if memory tools exist.

Self-learning from mistakes — with the owner firmly in the loop.

## Install

```bash
pi install git:github.com/recoilme/pi-incident-retro
```

or locally during development:

```bash
pi install ./pi-incident-retro
```

## Test

The skill ships with eval test cases in `skills/incident-retro/evals/`.
Run them through the `skill-creator` skill's evaluation cycle.

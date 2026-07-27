# Hi, I'm Mike.

I'm an author, hands-on builder, and AI Craft leader from New Zealand. I use
Codex and other AI tools to turn ambitious ideas into working projects, then
study what makes AI-assisted development useful, reliable, and easy to
understand.

I publish plain-English guides and small runnable examples for people who want
to direct serious builds without giving up control of the decisions that
matter. The work focuses on reliable agents, local AI assistants, human-reviewed
workflows, source boundaries, scoped authority, and verification evidence. Most
examples use synthetic data and make no model call.

## Start Here

- **Build one useful private workflow now.**
  [Preview the Reliable AI Work Starter](https://github.com/TheDarkniteFalls/reliable-ai-work-starter),
  then [create a private copy](https://github.com/new?template_owner=TheDarkniteFalls&template_name=reliable-ai-work-starter&visibility=private)
  for one recurring workflow with named sources, approval boundaries, durable
  state, and a reviewable handoff. Setup takes about 10 minutes and needs no
  app, model API, or public data.
- **Learn how to direct and review AI work.** Start with
  [Build with Codex: A Plain-English Handbook](https://github.com/TheDarkniteFalls/agent-operator-handbook)
  to turn an idea into a bounded project and review the result without needing
  to read all the code.
- **Find the right reliability pattern for your problem.** The
  [Toolkit Navigator](https://thedarknitefalls.github.io/local-assistant-reliability-lab/)
  recommends a public example by problem, experience, runtime, proof, and
  limitation. If you are reviewing AI-assisted code, begin with
  [EvidenceGate](https://github.com/TheDarkniteFalls/evidencegate).

These routes are designed for self-service. Each technical project names its
runtime, first check, proof boundary, and limitations before you need to clone
or install anything. Most use synthetic data, make no model call, and require
no account beyond GitHub.

## Selected Open-Source Work

- **Merged contribution:**
  [Skillware PR #263](https://github.com/ARPAHLS/skillware/pull/263) added
  documentation for OpenAI-compatible model hosts and merged after the
  maintainer's requested revisions.
- **Review contribution:** On
  [GitHub Docs PR #45193](https://github.com/github/docs/pull/45193#issuecomment-5002096918),
  I identified three bounded corrections to workflow-run status guidance; the
  author implemented all three before the pull request returned to maintainer
  review.

## Experimental Work Open for Review

- **EvalBraid Evaluation Provenance Profile v0** records the evidence and
  judgment boundaries of one evaluation attempt. It is experimental,
  author-tested on macOS, and awaiting independent review. Linux portability
  is untested and production use is not recommended.
  [Read the draft](https://github.com/TheDarkniteFalls/evidencegate/pull/11)
  or [reproduce the included fixtures](https://github.com/TheDarkniteFalls/evidencegate/issues/12).

## What I'm Building

- **Reviewable agent work.**
  [Context Boundary Examples](https://github.com/TheDarkniteFalls/context-boundary-examples)
  catches answers that outrun supplied evidence, while
  [Agent Action Authority Examples](https://github.com/TheDarkniteFalls/agent-action-authority-examples)
  tests whether an approval still matches the exact action being proposed.
- **Agent evidence and evaluation.** The
  [Agent Evidence Catalog](https://github.com/TheDarkniteFalls/agent-evidence-catalog)
  is a static, synthetic reference for comparing exact agent versions by
  authority, evidence, and known gaps. Real-agent profile intake is not open.
- **Local-first assistant reliability.** The
  [Local Model Reliability Example](https://github.com/TheDarkniteFalls/local-model-reliability-example)
  keeps structured model output behind deterministic validation, and the
  [Context Contract Compiler](https://github.com/TheDarkniteFalls/context-contract-compiler)
  protects required context, explains selection decisions, and rejects stale
  receipts after declared material changes.
- **Repeatable project confidence.**
  [Earned Confidence](https://github.com/TheDarkniteFalls/earned-confidence)
  treats unknown as a state, not zero, and preserves what was known when a
  decision was made. The
  [Green-Spine QA Pattern](https://github.com/TheDarkniteFalls/green-spine-qa-pattern)
  turns a representative journey into one memorable checkpoint, while the
  [Public Repo Safety Kit](https://github.com/TheDarkniteFalls/public-repo-safety-kit)
  helps keep private context out of public repositories.
- **Human-directed game development.** The
  [Game Project Instructions for Coding Agents](https://github.com/TheDarkniteFalls/codex-project-instructions-starter/tree/main/examples/game-project)
  protects assets and saves, defines approval gates and checks, and preserves
  the human playtest across Godot, Unity, Unreal, or a custom engine.

These projects favour small synthetic examples, explicit limitations, and
evidence a reviewer can inspect. A passing check is useful evidence, not a claim
that the work is automatically correct, safe, or ready to publish.

Use the Lab's [two-minute Toolkit Navigator](https://thedarknitefalls.github.io/local-assistant-reliability-lab/)
to get one recommendation, or scan the
[complete toolkit map](https://github.com/TheDarkniteFalls/local-assistant-reliability-lab/blob/main/TOOLKIT_MAP.md)
when you want every option and trust boundary at once.
Agents and tools can read the same catalog from the
[machine-readable toolkit index](https://github.com/TheDarkniteFalls/local-assistant-reliability-lab/blob/main/toolkit_index.json).

## Field Notes

I keep the broader lessons in
[Field Notes From Building With AI](FIELD_NOTES.md): what the surrounding
harness should own, why useful work and permitted work are different, how to
test boundaries before calling a model, and where human judgement still has to
decide the outcome.

## Writing

Away from the technical work, I write stories where fantasy, science fiction,
and the apocalypse collide. I'm the author of *The Mana Influx Series* and
*Soul Spark Reclaimer*. You can
[meet The Mana Influx Series on Amazon](https://www.amazon.com/The-Mana-Influx/dp/B0CNPWZ745).

## How I Work

- **Make capability accessible.** People should be able to direct ambitious
  projects in ordinary language and understand the important decisions.
- **Keep humans responsible.** Models can propose and produce; people retain
  authority over consequential actions and protected areas.
- **Leave something inspectable.** Useful AI-assisted work has clear limits,
  relevant checks, honest uncertainty, and a handoff another person can review.

I like making real things, learning from where they break, and sharing the
smallest useful version with other people.

# Field Notes From Building With AI

These are working conclusions from building local assistants, deterministic
simulations, creative tools, and public contribution workflows with Codex.
They are not universal laws or model benchmark claims. They are patterns that
have survived contact with real projects and have been generalized here without
private data, unpublished material, or project-specific source code.

## 1. The Harness Is The Product Boundary

Here, the harness means the application and rules surrounding the model. A
model can propose an answer or change, but the harness should choose the
sources; validate output shapes and identifiers; control permitted actions,
state changes, and storage; and produce the final record of what happened.

This is especially important with small local models. Better prompting helps,
but compact context and deterministic validation often improve reliability more
than another paragraph of instructions.

Public examples:

- [Local Model Reliability Example](https://github.com/TheDarkniteFalls/local-model-reliability-example)
- [Agent Action Authority Examples](https://github.com/TheDarkniteFalls/agent-action-authority-examples)
- [Context Boundary Examples](https://github.com/TheDarkniteFalls/context-boundary-examples)

## 2. Prove The Boundary Before Calling The Model

Many important AI-workflow properties do not need an AI call to test them:
whether citations name supplied sources, whether protected writes are rejected,
whether a stale approval fails, whether structured output parses, and whether a
known-bad fixture is caught.

No-model tests are cheap, repeatable, public-safe, and easier to debug. They do
not prove answer quality, but they keep answer quality from being confused with
broken plumbing or unsafe permissions.

Public example: [Green-Spine QA Pattern](https://github.com/TheDarkniteFalls/green-spine-qa-pattern)

## 3. Useful Work And Authority Are Different Axes

An agent that refuses everything is safe but not useful. An agent that finishes
everything by stretching approval is useful-looking but unsafe. A serious eval
has to test both at once: complete the benign work, pause for genuinely new
authority, reject prohibited actions, and leave an accurate record of what
happened.

Public proposal: [Agent Authority Eval design-fit discussion](https://github.com/UKGovernmentBEIS/inspect_evals/issues/1926)

## 4. One Named Workflow Gate Creates Shared Confidence

Testing individual boundaries is useful. A named workflow gate brings the
relevant checks together around one representative journey. Large projects may
have unit tests, build checks, browser checks, and scenario tests, but people
still need one compact command that answers a human question: does the
important path work from beginning to end?

The gate should cover the smallest representative journey, reject known-bad
cases, and state what it does not prove. A memorable name makes it easier for
humans and agents to use the same checkpoint.

Public example: [Green-Spine QA Pattern](https://github.com/TheDarkniteFalls/green-spine-qa-pattern)

## 5. Context Selection Is A Contract Before It Is A Search Problem

AI systems often choose the information they give a model by searching for
similar text. The closest match is not always the right one. It may belong to
another project, be out of date, have been replaced, lack a reliable source, or
be unavailable to the current task.

Before ranking information by relevance, the surrounding system should enforce
the task's rules: which projects and sources are allowed, what must be included,
what must be excluded, and how much context will fit. It should explain every
choice. If a required record is missing or cannot fit, stopping is more honest
than silently producing a plausible-looking partial answer.

Public implementation: [Context Contract Compiler](https://github.com/TheDarkniteFalls/context-contract-compiler)

## 6. Receipts Need To Bind Claims To The Reviewed Revision

A receipt is a saved record of what was reviewed, which version was checked,
and what the checks established. A list of passing checks is weak evidence if
the repository changed afterward. A useful receipt identifies the exact
revision, file scope, checks, bounded claims, unresolved risk, and human review
state. It should stop claiming a pass when the current version or reviewed
files no longer match.

Unless a receipt is digitally signed, it does not prove who created it. A
passing receipt is also not a publication decision. Those limitations belong
in the design rather than in fine print.

Public implementation: [EvidenceGate](https://github.com/TheDarkniteFalls/evidencegate)

## 7. Generated Systems Need Structural And Experiential QA

Unit tests can pass while a generated world, workflow, or long-running
simulation is still unusable. Generated systems also need checks for required
content, graph reachability, entry-to-goal routes, stale generated assets, and
one representative human journey.

Structural readiness and play quality are separate evidence classes. The first
can be automated heavily; the second still needs an honest human test.

Public implementation: [Generated-System QA Pattern](https://github.com/TheDarkniteFalls/generated-system-qa-pattern)

## 8. Sealed Evaluation Needs A Real Information Boundary

When only one valuable body of material exists, treat it like an exam. Separate
the material used for learning, trial runs, and the final unseen test before
anyone inspects that final set. Freeze the test inputs and generated answers
before revealing the expected answers; record digital fingerprints and sources;
capture the judgement made before reveal; and never reuse revealed material in
a future unseen test.

If sealed material leaks into the run, the result is contaminated rather than
merely inconvenient. The correct response is to withdraw the affected claim
that the test was genuinely unseen.

Public implementation: [Sealed Evaluation Pattern](https://github.com/TheDarkniteFalls/sealed-evaluation-pattern)

## 9. Compare Models By Workload, Not Raw Totals

Raw token use says little when models handled different task types, context
sizes, reasoning settings, or numbers of turns. A useful comparison normalizes
by workload and then separates infrastructure failure, schema failure,
source-boundary failure, answer quality, and human usefulness.

Public implementation: [Model Workload Telemetry](https://github.com/TheDarkniteFalls/model-workload-telemetry)

## 10. Public Work Should Start From A Yes-List

Cleaning a private workspace in place is a poor publication strategy. A safer
pattern is to create a fresh public candidate, copy only files with a clear
public purpose, replace real data with synthetic fixtures, and run a local
publication gate before any push.

The same care applies when contributing to someone else's project. An open,
unassigned issue is not automatically an invitation to start coding. Read the
repository's contribution and AI-assistance rules, respect work reserved for
new contributors, check for existing ownership or overlapping changes, and
look for evidence that a maintainer wants the work. Stepping back when the fit
is wrong is part of contributing responsibly.

Public example: [Public Repo Safety Kit](https://github.com/TheDarkniteFalls/public-repo-safety-kit)

## 11. Missing Evidence Must Stay Visible

If a test cannot produce a score because a checking tool refuses, times out, or
fails, the missing result is not evidence that the system was safe. It is also
not automatically evidence that the system was unsafe. It is missing evidence,
and reviewers need to see that uncertainty.

A report should answer three questions separately: did the test run, did it
produce a score, and how much usable evidence is available? It should also show
how many cases were attempted, why some were not scored, and how much those
missing cases could change the headline result.

Public research note: [Missing Evidence Is Not Safety](https://github.com/TheDarkniteFalls/evidencegate/blob/main/docs/missing-evidence-is-not-safety.md)

## 12. Unknown Is A State, Not Zero

Section 11 concerns honest reporting when tests produce incomplete evidence. A
related problem appears when a system makes decisions over time: missing
information is often turned into a number because numbers are easier to sort
and display. That can make an unknown result look like a measured bad result,
or make unrelated evidence appear to answer a question it never tested.

Keep unknown values explicit, keep evidence tied to the exact thing it
describes, and preserve what was known when a decision was made. New evidence
can support a new decision; it should not quietly rewrite the old record.

Public implementation: [Earned Confidence](https://github.com/TheDarkniteFalls/earned-confidence)

## 13. A Lost Response Is Not A Failed Action

When a tool that sends a message, makes a booking, places an order, or writes a
file times out, two different things may have happened: the action may have
failed, or it may have succeeded and only the response was lost. Retrying
blindly can duplicate the action.

Give each operation a stable identifier, bind it to the exact request, keep a
durable record, and read the resulting state before deciding what to do next.
Retry only when the evidence supports it. If the outcome cannot be established,
stop for review instead of guessing.

Public implementation: [Effect Recovery Example](https://github.com/TheDarkniteFalls/agent-action-authority-examples#did-the-tool-already-run)

## 14. Owning The Goal Does Not Mean Owning The Process

A capable agent can remain committed to the requested outcome while quietly
changing how it plans to get there. It may switch tools, add a script, spend
more retries, skip a review point, or continue into the next stage. Each change
can sound helpful while the combined process is no longer the one a person
approved.

The surrounding system should preserve the confirmed route, tools, effect
limits, retry budgets, review points, and stopping conditions. Ordinary detail
can vary inside an approved stage, but changing the process requires a fresh
human decision. Reaching an agreed stop is a successful outcome even when the
larger goal is not yet finished.

Public implementation: [Plan Fidelity Gate](https://github.com/TheDarkniteFalls/agent-action-authority-examples/blob/main/PLAN_FIDELITY_GATE.md)

## How These Notes Become Projects

A lesson belongs here after a validated project result, a completed or failed
contribution, or useful maintainer feedback gives it real evidence. The next
step is usually a small public-safe example, test, or research note that other
people can inspect without needing the private project that produced the
lesson.

Each public artifact should name its first check, what a pass establishes, and
what remains outside the proof. A passing check is evidence, not a claim of
complete correctness, safety, usefulness, or permission to publish.

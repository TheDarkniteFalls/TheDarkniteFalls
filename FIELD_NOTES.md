# Field Notes From Building With AI

These are working conclusions from building local assistants, deterministic
simulations, creative tools, and public contribution workflows with Codex.
They are not universal laws or model benchmark claims. They are patterns that
have survived contact with real projects and have been generalized here without
private data, unpublished material, or project-specific source code.

## 1. The Harness Is The Product Boundary

A model can propose an answer or change. The surrounding application should
own source selection, schema validation, allowed identifiers, action authority,
state transitions, persistence, and the final receipt.

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

Large projects accumulate unit tests, linters, build checks, browser checks,
and scenario tests. People still need one compact command that answers a human
question: does the important path work from beginning to end?

The gate should cover the smallest representative journey, reject known-bad
cases, and state what it does not prove. A memorable name makes it easier for
humans and agents to use the same checkpoint.

Public example: [Green-Spine QA Pattern](https://github.com/TheDarkniteFalls/green-spine-qa-pattern)

## 5. Metadata Must Prevent A Named Failure

More metadata is not automatically better retrieval. A field earns its place
when it prevents a concrete error such as wrong-project retrieval, stale
evidence, an ineligible source, or a false relationship claim.

The practical loop is: record the failure, add the smallest discriminating
field or rule, replay that failure bucket, and keep the change only when the
targeted and broad results both hold.

Public example: [SQLite Context Retrieval Example](https://github.com/TheDarkniteFalls/sqlite-context-retrieval-example)

## 6. Receipts Need To Bind Claims To The Reviewed Revision

A list of passing checks is weak evidence if the repository changed afterward.
A useful receipt identifies the exact revision, file scope, checks, bounded
claims, unresolved risk, and human review state. It should fail closed when the
head or scope no longer matches.

Unsigned receipts are not authenticated, and a passing receipt is not a
publication decision. Those limitations belong in the design rather than in
fine print.

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

When only one valuable corpus exists, evaluating against it carelessly consumes
the test set. A stronger protocol partitions learning, calibration, and sealed
material before inspection; freezes inputs and generated outputs before reveal;
records checksums and provenance; captures pre-reveal judgement; and retires
revealed material from future blind tests.

If sealed material leaks into the run, the result is contaminated rather than
merely inconvenient. The correct response is to invalidate the affected blind
claim.

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

Public example: [Public Repo Safety Kit](https://github.com/TheDarkniteFalls/public-repo-safety-kit)

## What I Built Next

The sealed-evaluation protocol became one manifest-style case, one checker, and
a small synthetic pass/fail corpus. The generated-system checker covers graph
integrity, required services, reachability, drift, and a representative
journey. The telemetry CLI compares only shared task IDs inside each workload
class and refuses to name a universal winner.

Each implementation uses the Python standard library, runs without a model or
network call, and states what its passing result does not prove.

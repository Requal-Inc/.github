# Requal

**Automated eval infrastructure for critical AI systems, from building golden datasets to gating releases.**

[requal.ai](https://requal.ai) · [Book a demo](https://requal.ai)

Will your AI system refund twice, leak data, invent facts, skip a check, or say it worked when it did not? A prompt edit, a model upgrade or a new tool can change what an AI system does. Requal tests each candidate release by what it actually did (the actions it took and the state it left behind, not its own account of them), applies your qualification policy, and turns your approvers' sign-off into a signed release authorisation that your deployment pipeline enforces.

Agents that take actions, such as refunds, credits, orders and account changes, are the first example. The target is every critical AI system.

## What's built

A working pre-launch prototype; the platform source is private. It runs end to end on one machine against scripted models. In the demo, a faulty support-agent release is caught, its fix is qualified and authorised, and the deployment gate admits the fix and blocks the faulty release.

| Part | What it does |
|---|---|
| Evaluation engine (`rq`) | Statistics, verdicts and sealed runs; `rq verify` re-checks a sealed run |
| Agent test environments | Resettable state, sandboxed tools behind a tool gateway, fault injection and assertions |
| Contracts and policy | Versioned contracts, a qualification-policy evaluator, and a published verifier that recomputes each verdict from the evidence |
| Runner (`rqr`) | Signs each result as an Ed25519 statement |
| Deployment gate | Admits the release that was qualified and authorised and blocks the rest; examples for GitHub, GitLab and generic CI |
| Control plane and web app | Where people review results and authorise a release |

The platform also has a chaos suite and recovery drills.

## What's next

- Hosted execution on Requal's cloud by default, with the runner (`rqr`), already built to run in a team's own cloud, as the enterprise option
- An agentic harness that turns a team's production data into a private benchmark (golden datasets)
- A library of test environments

## Founder

**[Nanda Kiran Velaga](https://github.com/Nanda-Kiran)**. At Ford's AI Advancement Center he built and deployed an LLM agent, then the evaluation and observability harness around it, which cut evaluation time by about 60%. That harness is where he first ran into the problem Requal works on. He built the Requal prototype (244 commits, Oct 1–4, 2026) by running AI coding agents as his engineering team. MS Applied Machine Learning, University of Maryland.

## Repositories

[requal-ai](https://github.com/Requal-Inc/requal-ai) holds Requal's static pages. The platform source is private.

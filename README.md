# SRE for AI-ML Systems · Free Live Sessions

Measure what users feel, alert only on real burns, and stop the bleeding first.

**Free · Live · 30 minutes · Mondays and Thursdays, 7:30 PM Central** · with Emmanuel N. ([Transformed 2 Succeed](https://transformed2succeed.com))

### [Register free on Zoom](https://us06web.zoom.us/meeting/register/fT235rLjQaihJYrWj2_vjw)

Register once and you're in for every session. Zoom emails you the join link and reminders. Bring your questions: every session ends with live Q&A.

## Watch the recordings

Missed a session or want to watch it again? Recordings are added here after each live session.

| Date | Recording |
|---|---|
| _Coming after the first session_ | |

## Download the slides

**[05_SRE_for_AI_ML_Systems_Free_Live_Session.pdf](slides/05_SRE_for_AI_ML_Systems_Free_Live_Session.pdf)** (PDF)

## What you'll learn

1. **Measure What Users Feel**: Define SLIs and SLOs, see why averages lie, and catch a model that is up but wrong.
2. **Spend the Error Budget**: Turn the SLO into a monthly budget and build alerts that page only on real burns.
3. **When It Breaks**: Run a game day: two incidents, two rollbacks and a blameless postmortem.

## Three things to remember

- **If users feel it, measure it**: Up, fast, right. Percentiles, not averages. A quality SLI for the model.
- **Alert on burn, not on blips**: Budget = (1 − SLO) × window. Two windows must agree. Page fast, ticket slow.
- **Stop the bleeding first**: Confirm, what changed, roll back, verify. Then a blameless postmortem.

## Try it yourself

Get the hands-on labs here: [sre-for-ai-ml](https://github.com/Here2ServeU/sre-for-ai-ml)

**Module 1 · Measure What Users Feel**: Ship a wrong model. Watch only one SLI notice.

```bash
python3 deploy.py v3
python3 load.py --requests 300 && python3 sli.py --last 300
```

**Module 2 · Spend the Error Budget**: A bad deploy in the last 40 minutes

```bash
python3 simulate.py bad-deploy && python3 budget.py
```

**Module 3 · When It Breaks**: Incident 2: everything looks fine…

```bash
bash .lab/incident.sh 2
python3 sli.py --last 300
python3 deploy.py --history
python3 deploy.py v1 && python3 load.py --requests 300
```

## All free live sessions

A different course every session. The rotation repeats every 4 weeks, so if you miss one, it comes back around.

| Week | Day | Course |
|---|---|---|
| Week 1 | Monday | [Linux for AI-ML Systems](https://github.com/Here2ServeU/live-linux-for-ai-ml) |
| Week 1 | Thursday | [Python for AI-ML](https://github.com/Here2ServeU/live-python-for-ai-ml) |
| Week 2 | Monday | [Zero to AI-ML Systems Engineering](https://github.com/Here2ServeU/live-zero-to-ai-ml) |
| Week 2 | Thursday | [DevOps for AI-ML Systems](https://github.com/Here2ServeU/live-devops-for-ai-ml) |
| Week 3 | Monday | **SRE for AI-ML Systems** (you are here) |
| Week 3 | Thursday | [GPU Optimization for AI-ML Systems](https://github.com/Here2ServeU/live-gpu-optimization-for-ai-ml) |
| Week 4 | Monday | [FinOps for AI-ML Systems](https://github.com/Here2ServeU/live-finops-for-ai-ml) |
| Week 4 | Thursday | [AI Agent Operations](https://github.com/Here2ServeU/live-ai-agent-operations) |

## Want the full course?

The membership gives you **all 8 courses, every module and every lab, for $49/month**, plus a live session every month where we build something together.

**[Join at transformed2succeed.com](https://transformed2succeed.com)**

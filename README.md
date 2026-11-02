# SRE for AI-ML Systems · Free Live Sessions

Measure what users feel, alert only on real burns, and stop the bleeding first.

Free, live, 30-minute sessions with **Dr. Emmanuel Naweji** ([Transformed 2 Succeed](https://transformed2succeed.com)).
This course is presented on **Week 3, Monday at 7:30 PM Central** of a 4-week rotation (8 courses, every Monday and Thursday).
This repo holds the slides, the recording of every live session, and the notes and links from each one.

## Session recordings

| Date | Recording | Notes |
|---|---|---|
| _First session coming soon_ | | |
<!-- sessions:end -->

## What the session covers

1. **Measure What Users Feel**: Define SLIs and SLOs, see why averages lie, and catch a model that is up but wrong.
2. **Spend the Error Budget**: Turn the SLO into a monthly budget and build alerts that page only on real burns.
3. **When It Breaks**: Run a game day: two incidents, two rollbacks and a blameless postmortem.

## Three things to remember

- **If users feel it, measure it**: Up, fast, right. Percentiles, not averages. A quality SLI for the model.
- **Alert on burn, not on blips**: Budget = (1 − SLO) × window. Two windows must agree. Page fast, ticket slow.
- **Stop the bleeding first**: Confirm, what changed, roll back, verify. Then a blameless postmortem.

## Try it yourself

Clone the course lab repo: [sre-for-ai-ml](https://github.com/Here2ServeU/sre-for-ai-ml)

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

## Slides

[`slides/05_SRE_for_AI_ML_Systems_Free_Live_Session.pptx`](slides/05_SRE_for_AI_ML_Systems_Free_Live_Session.pptx): the presenter deck, with full speaker notes.

## Free live session schedule (Mondays and Thursdays, 7:30 PM Central)

| Week | Day | Course |
|---|---|---|
| Week 1 | Monday | [Linux for AI-ML Systems](https://github.com/Here2ServeU/live-linux-for-ai-ml) |
| Week 1 | Thursday | [Python for AI-ML](https://github.com/Here2ServeU/live-python-for-ai-ml) |
| Week 2 | Monday | [Zero to AI-ML Systems Engineering](https://github.com/Here2ServeU/live-zero-to-ai-ml) |
| Week 2 | Thursday | [DevOps for AI-ML Systems](https://github.com/Here2ServeU/live-devops-for-ai-ml) |
| Week 3 | Monday | **SRE for AI-ML Systems** (this repo) |
| Week 3 | Thursday | [GPU Optimization for AI-ML Systems](https://github.com/Here2ServeU/live-gpu-optimization-for-ai-ml) |
| Week 4 | Monday | [FinOps for AI-ML Systems](https://github.com/Here2ServeU/live-finops-for-ai-ml) |
| Week 4 | Thursday | [AI Agent Operations](https://github.com/Here2ServeU/live-ai-agent-operations) |

## Want all of it?

The membership gives you **all 8 courses, every module and every lab, for $49/month**, plus a live session every month where we build something together.
Join at **https://transformed2succeed.com**.

---

### For the presenter: logging a session

After each live session, run:

```bash
bash scripts/new-session.sh 2026-11-03 "https://link-to-the-recording"
git add -A && git commit -m "Session 2026-11-03" && git push
```

This creates `sessions/2026-11-03.md` from the template (fill in the Q&A and links) and adds a row to the recordings table above.

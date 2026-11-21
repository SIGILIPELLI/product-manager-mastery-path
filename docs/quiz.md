---
title: "Final Quiz"
description: "Test what you have learned across all four levels of Product Manager Mastery Path with a 19-question final quiz."
---

# Final Quiz

19 questions drawn from all four levels of this course. You need **70% (14 out of 19)** to pass —
you can retake it as many times as you like. Your best result is saved in this browser.

<div id="mp-quiz-root"></div>

<script type="application/json" id="mp-quiz-data">
[
  {
    "question": "Control converts 200/4000 and the variant 250/4000. What are the absolute and relative lifts?\n```python\na=200/4000;b=250/4000\nprint(round((b-a)*100,2), round((b-a)/a*100,1))\n```\n",
    "options": [
      "1.25 1.25",
      "1.25 25.0",
      "0.25 5.0",
      "25.0 1.25"
    ],
    "correctIndex": 1,
    "explanation": "Percentage points vs percent. Verified by running it."
  },
  {
    "question": "RICE: Reach 5000, Impact 1, Confidence 50%, Effort 2. Score?\n```python\nprint(5000*1*0.5/2)\n```\n",
    "options": [
      "625.0",
      "5000.0",
      "1250.0",
      "2500.0"
    ],
    "correctIndex": 2,
    "explanation": "R×I×C÷E. Verified by running it."
  },
  {
    "question": "A funnel has 8000 visits, 960 signups and 192 paid. What is the signup→paid rate in percent?\n```python\nprint(192/960*100)\n```\n",
    "options": [
      "20.0",
      "12.0",
      "4.0",
      "2.4"
    ],
    "correctIndex": 0,
    "explanation": "Stage-to-stage. Verified by running it."
  },
  {
    "question": "Price $40, COGS $10, churn 4%/month. LTV (gross-margin based)?\n```python\nprint((40-10)/0.04)\n```\n",
    "options": [
      "25.0",
      "750.0",
      "30.0",
      "1000.0"
    ],
    "correctIndex": 1,
    "explanation": "Margin ÷ churn. Verified by running it."
  },
  {
    "question": "A test is stopped as soon as p < 0.05 after a week of peeking daily. What's the issue?",
    "options": [
      "Too short",
      "Too long",
      "Nothing",
      "Repeated peeking inflates false positives; fix sample size or use sequential methods"
    ],
    "correctIndex": 3,
    "explanation": "Pre-register."
  },
  {
    "question": "A 50/50 test shows 4000 vs 5000 users. What do you suspect?",
    "options": [
      "Good",
      "A sample ratio mismatch: the assignment or logging is broken",
      "Nothing",
      "Luck"
    ],
    "correctIndex": 1,
    "explanation": "Invalidate the result."
  },
  {
    "question": "A variant lifts conversion but reduces 30-day retention. What do you do?",
    "options": [
      "Treat retention as a guardrail and investigate before shipping",
      "Roll",
      "Ignore",
      "Ship"
    ],
    "correctIndex": 0,
    "explanation": "Don't optimize one metric blindly."
  },
  {
    "question": "A customer demands a feature. What is the first question?",
    "options": [
      "What problem are they trying to solve and how often does it occur?",
      "Who",
      "When",
      "How much"
    ],
    "correctIndex": 0,
    "explanation": "Discovery."
  },
  {
    "question": "Your roadmap dates slip. What helps trust most?",
    "options": [
      "Hide",
      "Telling stakeholders early with impact and options",
      "Wait",
      "Blame"
    ],
    "correctIndex": 1,
    "explanation": "Transparency."
  },
  {
    "question": "Which key result is best?",
    "options": [
      "Launch Y",
      "Ship X",
      "Increase week-4 retention from 22% to 30%",
      "Run 10 tests"
    ],
    "correctIndex": 2,
    "explanation": "Outcome with a number."
  },
  {
    "question": "A PRD lists a solution but no problem. What's missing?",
    "options": [
      "The user problem, evidence and success metrics",
      "Dates",
      "Mockups",
      "Costs"
    ],
    "correctIndex": 0,
    "explanation": "Problem first."
  },
  {
    "question": "What is the biggest risk of prioritizing only by RICE?",
    "options": [
      "Treating guessed inputs as precise and ignoring strategy",
      "None",
      "Cost",
      "Speed"
    ],
    "correctIndex": 0,
    "explanation": "Frameworks inform."
  },
  {
    "question": "Why define guardrail metrics?",
    "options": [
      "Style",
      "Speed",
      "Law",
      "So you don't harm important things while improving the target"
    ],
    "correctIndex": 3,
    "explanation": "Healthy experiments."
  },
  {
    "question": "When is a platform investment justified?",
    "options": [
      "Always",
      "Cleaner",
      "When it speeds up or de-risks many future customer outcomes",
      "Never"
    ],
    "correctIndex": 2,
    "explanation": "Business case."
  },
  {
    "question": "A B2B champion loves a feature that only they need. What do you do?",
    "options": [
      "Validate demand across accounts before building",
      "Build",
      "Refuse",
      "Delay"
    ],
    "correctIndex": 0,
    "explanation": "Avoid one-off."
  },
  {
    "question": "What does PLG require from the product?",
    "options": [
      "Demos",
      "Contracts",
      "Fast time-to-value and low-friction self-serve onboarding",
      "Sales"
    ],
    "correctIndex": 2,
    "explanation": "Product does the selling."
  },
  {
    "question": "What do you do when an ML feature is sometimes wrong?",
    "options": [
      "Design for graceful failure and user control, and monitor quality",
      "Hope",
      "Ignore",
      "Hide"
    ],
    "correctIndex": 0,
    "explanation": "Responsible AI."
  },
  {
    "question": "What is a good first step in a product crisis?",
    "options": [
      "Stabilize, communicate and assign clear roles",
      "Wait",
      "Investigate",
      "Blame"
    ],
    "correctIndex": 0,
    "explanation": "Triage."
  },
  {
    "question": "How should a PM treat engineering estimates?",
    "options": [
      "As inputs to trade-offs, not targets to negotiate down",
      "Double",
      "Ignore",
      "Cut"
    ],
    "correctIndex": 0,
    "explanation": "Respect."
  }
]
</script>

## Coding challenges

Try these on your own computer, then compare your output. Nothing you write is sent anywhere.

### An A/B test analyzer with sample ratio and guardrail checks

Implement z_test (pooled two-proportion test with absolute and relative lift), sample_size_per_arm and srm_ok (chi-square on the traffic split). decide() is provided: it rejects invalid tests, blocks guardrail regressions, then ships only significant wins. Run it on five scenarios.

**Starter code**

```python
import math

def z_test(conv_a, n_a, conv_b, n_b):
    # pooled two-proportion z-test; return (absolute lift in percentage points, relative lift %, z, two-sided p)
    # p = math.erfc(abs(z) / math.sqrt(2))
    return 0, 0, 0, 1

def sample_size_per_arm(base, mde_rel, z_alpha=1.96, z_beta=0.84):
    # n = (z_alpha + z_beta)^2 * (p1(1-p1) + p2(1-p2)) / (p2 - p1)^2 rounded up, with p2 = base * (1 + mde_rel)
    return 0

def srm_ok(n_a, n_b, expected=0.5, threshold=0.001):
    # chi-square (1 df) on the traffic split; p = math.erfc(math.sqrt(chi / 2)); return (p >= threshold, p)
    return True, 1.0

def decide(conv_a, n_a, conv_b, n_b, guardrail_drop_pct=0.0):
    ok, _ = srm_ok(n_a, n_b)
    if not ok: return "INVALID (sample ratio mismatch)"
    lift_pp, rel, z, p = z_test(conv_a, n_a, conv_b, n_b)
    if guardrail_drop_pct > 2: return "DO NOT SHIP (guardrail regressed)"
    if p < 0.05 and lift_pp > 0: return "SHIP"
    if p < 0.05: return "REJECT (worse)"
    return "INCONCLUSIVE"

for name, args, guard in [
    ("checkout copy", (200, 4000, 250, 4000), 0.0),
    ("tiny tweak", (200, 4000, 206, 4000), 0.0),
    ("bad variant", (250, 4000, 200, 4000), 0.0),
    ("wins but hurts retention", (200, 4000, 250, 4000), 3.5),
    ("broken split", (200, 4000, 260, 5000), 0.0),
]:
    lift, rel, z, p = z_test(*args)
    print(f"{name:26s} lift={lift:+.2f}pp rel={rel:+.1f}% z={z:+.2f} p={p:.4f} -> {decide(*args, guardrail_drop_pct=guard)}")
print("sample size per arm (5% base, +10% rel):", sample_size_per_arm(0.05, 0.10))
print("sample size per arm (5% base, +20% rel):", sample_size_per_arm(0.05, 0.20))
print("SRM 4000/4000:", srm_ok(4000, 4000)[0], "| 4000/5000:", srm_ok(4000, 5000)[0])
```

**Expected output**

```text
checkout copy              lift=+1.25pp rel=+25.0% z=+2.43 p=0.0153 -> SHIP
tiny tweak                 lift=+0.15pp rel=+3.0% z=+0.31 p=0.7599 -> INCONCLUSIVE
bad variant                lift=-1.25pp rel=-20.0% z=-2.43 p=0.0153 -> REJECT (worse)
wins but hurts retention   lift=+1.25pp rel=+25.0% z=+2.43 p=0.0153 -> DO NOT SHIP (guardrail regressed)
broken split               lift=+0.20pp rel=+4.0% z=+0.43 p=0.6686 -> INVALID (sample ratio mismatch)
sample size per arm (5% base, +10% rel): 31196
sample size per arm (5% base, +20% rel): 8146
SRM 4000/4000: True | 4000/5000: False
```

<details><summary>Show solution and explanation</summary>

<pre><code>import math

def z_test(conv_a, n_a, conv_b, n_b):
    &quot;&quot;&quot;Two-proportion z-test (pooled). Returns (absolute lift in pp, relative lift %, z, two-sided p).&quot;&quot;&quot;
    pa, pb = conv_a / n_a, conv_b / n_b
    pool = (conv_a + conv_b) / (n_a + n_b)
    se = math.sqrt(pool * (1 - pool) * (1 / n_a + 1 / n_b))
    z = (pb - pa) / se
    p = math.erfc(abs(z) / math.sqrt(2))          # two-sided
    return (pb - pa) * 100, (pb - pa) / pa * 100, z, p

def sample_size_per_arm(base, mde_rel, z_alpha=1.96, z_beta=0.84):
    &quot;&quot;&quot;Approximate users per arm to detect a relative lift (alpha 5% two-sided, power 80%).&quot;&quot;&quot;
    p1, p2 = base, base * (1 + mde_rel)
    var = p1 * (1 - p1) + p2 * (1 - p2)
    return math.ceil((z_alpha + z_beta) ** 2 * var / (p2 - p1) ** 2)

def srm_ok(n_a, n_b, expected=0.5, threshold=0.001):
    &quot;&quot;&quot;Sample ratio mismatch check: chi-square (1 df) on the split.&quot;&quot;&quot;
    total = n_a + n_b
    chi = (n_a - total * expected) ** 2 / (total * expected) + (n_b - total * (1 - expected)) ** 2 / (total * (1 - expected))
    p = math.erfc(math.sqrt(chi / 2))
    return p &gt;= threshold, p

def decide(conv_a, n_a, conv_b, n_b, guardrail_drop_pct=0.0):
    ok, _ = srm_ok(n_a, n_b)
    if not ok: return &quot;INVALID (sample ratio mismatch)&quot;
    lift_pp, rel, z, p = z_test(conv_a, n_a, conv_b, n_b)
    if guardrail_drop_pct &gt; 2: return &quot;DO NOT SHIP (guardrail regressed)&quot;
    if p &lt; 0.05 and lift_pp &gt; 0: return &quot;SHIP&quot;
    if p &lt; 0.05: return &quot;REJECT (worse)&quot;
    return &quot;INCONCLUSIVE&quot;

for name, args, guard in [
    (&quot;checkout copy&quot;, (200, 4000, 250, 4000), 0.0),
    (&quot;tiny tweak&quot;, (200, 4000, 206, 4000), 0.0),
    (&quot;bad variant&quot;, (250, 4000, 200, 4000), 0.0),
    (&quot;wins but hurts retention&quot;, (200, 4000, 250, 4000), 3.5),
    (&quot;broken split&quot;, (200, 4000, 260, 5000), 0.0),
]:
    lift, rel, z, p = z_test(*args)
    print(f&quot;{name:26s} lift={lift:+.2f}pp rel={rel:+.1f}% z={z:+.2f} p={p:.4f} -&gt; {decide(*args, guardrail_drop_pct=guard)}&quot;)
print(&quot;sample size per arm (5% base, +10% rel):&quot;, sample_size_per_arm(0.05, 0.10))
print(&quot;sample size per arm (5% base, +20% rel):&quot;, sample_size_per_arm(0.05, 0.20))
print(&quot;SRM 4000/4000:&quot;, srm_ok(4000, 4000)[0], &quot;| 4000/5000:&quot;, srm_ok(4000, 5000)[0])
</code></pre>

<p>A trustworthy experiment checks the split first (SRM), then significance, and treats guardrails as veto power. Statistical significance is not business importance. Verified by running the Python implementation (a standard normal-approximation test).</p>
</details>

### RICE prioritization, funnel analysis and unit economics

Score and rank five ideas with RICE, fit them into six person-months of capacity, analyze a four-step funnel to find the biggest drop-off, and compute LTV, LTV:CAC and payback for a subscription.

**Starter code**

```python
# Prioritization (RICE), funnel conversion and unit economics for one planning cycle.
IDEAS = [  # name, reach/quarter, impact (0.25-3), confidence, effort (person-months)
    ("Guided onboarding", 6000, 2.0, 0.8, 3),
    ("Referral program", 2500, 1.0, 0.5, 2),
    ("Saved carts", 9000, 0.5, 0.9, 1),
    ("SSO for teams", 800, 3.0, 0.8, 4),
    ("Dark mode", 12000, 0.25, 0.9, 2),
]
def rice(reach, impact, confidence, effort):
    # Reach x Impact x Confidence / Effort
    return 0

# TODO: print every idea sorted by RICE (descending) as  f"{name:18s} RICE={score:7.1f}"
# TODO: greedily pick ideas in that order while the total effort stays within capacity = 6 person-months
# TODO: print stage-to-stage conversion for FUNNEL (one decimal), the overall visit->paid rate (2 decimals) and the biggest drop-off
# TODO: unit economics: margin = price - cogs; lifetime = 1/churn; LTV = margin/churn; LTV:CAC; payback = cac/margin

FUNNEL = [("visit", 20000), ("signup", 2400), ("activated", 1080), ("paid", 216)]
price, cogs, churn, cac = 30.0, 6.0, 0.05, 150.0
```

**Expected output**

```text
Saved carts        RICE= 4050.0
Guided onboarding  RICE= 3200.0
Dark mode          RICE= 1350.0
Referral program   RICE=  625.0
SSO for teams      RICE=  480.0
fits in 6 person-months: Saved carts, Guided onboarding, Dark mode (6 used)
funnel:
      visit -> signup     12.0%
     signup -> activated  45.0%
  activated -> paid       20.0%
  overall visit->paid 1.08%
biggest drop-off: visit -> signup
gross margin/month: 24.00; lifetime: 20 months; LTV: 480; LTV:CAC 3.2; payback 6.2 months
```

<details><summary>Show solution and explanation</summary>

<pre><code># Prioritization (RICE), funnel conversion and unit economics for one planning cycle.
IDEAS = [  # name, reach/quarter, impact (0.25-3), confidence, effort (person-months)
    (&quot;Guided onboarding&quot;, 6000, 2.0, 0.8, 3),
    (&quot;Referral program&quot;, 2500, 1.0, 0.5, 2),
    (&quot;Saved carts&quot;, 9000, 0.5, 0.9, 1),
    (&quot;SSO for teams&quot;, 800, 3.0, 0.8, 4),
    (&quot;Dark mode&quot;, 12000, 0.25, 0.9, 2),
]
def rice(reach, impact, confidence, effort): return reach * impact * confidence / effort

ranked = sorted(IDEAS, key=lambda i: -rice(*i[1:]))
for n, *rest in ranked: print(f&quot;{n:18s} RICE={rice(*rest):7.1f}&quot;)
capacity = 6
chosen, used = [], 0
for n, r, i, c, e in ranked:
    if used + e &lt;= capacity: chosen.append(n); used += e
print(&quot;fits in&quot;, capacity, &quot;person-months:&quot;, &quot;, &quot;.join(chosen), f&quot;({used} used)&quot;)

FUNNEL = [(&quot;visit&quot;, 20000), (&quot;signup&quot;, 2400), (&quot;activated&quot;, 1080), (&quot;paid&quot;, 216)]
print(&quot;funnel:&quot;)
for (a, na), (b, nb) in zip(FUNNEL, FUNNEL[1:]):
    print(f&quot;  {a:&gt;9s} -&gt; {b:&lt;9s} {nb / na * 100:5.1f}%&quot;)
print(f&quot;  overall visit-&gt;paid {FUNNEL[-1][1] / FUNNEL[0][1] * 100:.2f}%&quot;)
biggest_drop = min(zip(FUNNEL, FUNNEL[1:]), key=lambda p: p[1][1] / p[0][1])
print(&quot;biggest drop-off:&quot;, biggest_drop[0][0], &quot;-&gt;&quot;, biggest_drop[1][0])

price, cogs, churn, cac = 30.0, 6.0, 0.05, 150.0
margin = price - cogs
ltv = margin / churn
print(f&quot;gross margin/month: {margin:.2f}; lifetime: {1 / churn:.0f} months; LTV: {ltv:.0f}; LTV:CAC {ltv / cac:.1f}; payback {cac / margin:.1f} months&quot;)
</code></pre>

<p>RICE turns judgement into a comparable score, a greedy fit respects capacity, funnel ratios locate the weakest step, and LTV = margin ÷ churn shows whether acquisition is economical. The inputs are illustrative. Verified by running it.</p>
</details>

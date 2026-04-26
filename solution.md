# NovaKid Funnel Reinvention

## 1. Current Funnel Analysis

Current path:

`Visit -> CTA / quiz start -> long parent quiz -> account creation -> phone -> email code -> child details -> plan + trial booking -> email/phone confirmation -> wait for lesson`

Main drop-off points:

- **Visit -> quiz start:** only 10% start the quiz. The CTA likely sells a process, not an immediate child outcome.
- **Quiz -> lead:** the quiz is long and asks for data before the parent or child experiences value. Current visitor-to-lead conversion is only ~4%.
- **Lead -> trial:** booking and confirmation add heavy friction: unclear birth date field, wrong calendar locale, default tariff selection, buried email CTA, no phone OTP.

Three immediate hypotheses:

1. **The desktop/web value proposition is too abstract.** Parents do not see why they should start a quiz before seeing their child speak or learn.
2. **The quiz delays the Aha moment.** It creates a feeling of personalization, but the child is absent and the parent gets no proof of value until much later.
3. **Operational friction destroys intent after lead capture.** Calendar issues, email confirmation, phone calls, and unclear booking rules reduce trust.

Priority: **fix desktop/web first.** Mobile converts 2x better, but most traffic is web, so the biggest absolute upside is in desktop. I would use mobile as the UX benchmark and rebuild desktop around faster activation.

## 2. New Activation Path: "First English Minute"

Core idea: **let the child speak English before asking the parent to complete the full funnel.**

Flow:

1. Parent lands on page and clicks: **"Let your child speak English in 60 seconds."**
2. Parent gives lightweight context: child age + optional name. No account yet.
3. Child enters a 60-second AI speaking mission:
   - says hello;
   - answers one simple visual question;
   - repeats or creates one short phrase.
   - audio is not stored before explicit parent consent.
4. Parent immediately sees a mini report:
   - what the child said;
   - confidence / level estimate;
   - recommended next step with a live tutor.
5. Lead capture happens after value:
   - "Send me the report and reserve a free tutor slot."
6. Booking happens from the report screen, using existing scheduling infrastructure.

Premium upsell:

Show Premium only after the first speaking win, in the parent context:

- daily AI speaking missions between tutor lessons;
- saved recordings and progress reports;
- priority tutor matching;
- personalized speaking plan;
- family / multi-child support.

Do not make Premium block the child's first Aha moment. The child gets the first mission free; the parent gets the upsell when they already have proof.

## 3. Rough Wireframe

```text
[Landing]
Let your child speak English in 60 seconds
Preview: friendly AI tutor + child speaking prompt
[Start free speaking check]

        ->

[Child Mission]
AI Tutor: "Hi! What is your name?"
Mic button
Visual prompt: cat / dog / apple
Progress: 1 of 3

        ->

[Parent Report]
Your child completed the first speaking mission
Spoke: 5 words
Level: Beginner
Recommended: live tutor trial this week
[Send report + reserve free trial]

        ->

[Premium / Booking]
Free: book 1 trial lesson
Premium: daily AI speaking + tutor plan + parent reports
[Start Premium trial]   [Book free live lesson]
```

## 4. Two-Week Minimum Viable Test

Build a lightweight desktop/web A/B test:

- Variant A: current linear quiz funnel.
- Variant B: "First English Minute" landing + scripted AI speaking mission + parent report + lead capture + existing booking flow.

Scope for 1 dev / 1 designer:

- one responsive landing page;
- 3-prompt AI or scripted voice mission;
- browser mic + speech recognition;
- simple parent report;
- lead form and booking handoff;
- funnel analytics.

North Star metric:

**Speaking-Activated Trial Rate** = share of visitors who complete the speaking mission and book or confirm a trial lesson.

Success threshold:

- at least **+50% relative uplift** vs. current desktop funnel;
- if booking baseline is unavailable, use **6%+ speaking-activated lead rate** vs. the current ~4% visitor-to-lead baseline;
- no decline in lead quality: reachable phone/email and comparable trial confirmation intent.

If the test fails, I would inspect:

- CTA click rate: is the promise strong enough?
- mic permission rate: is privacy or browser friction killing the flow?
- mission completion rate: does the child understand and enjoy it?
- parent report view rate: does the parent perceive real value?
- lead capture rate after report: is the offer compelling?
- booking and confirmation rate: is scheduling still the bottleneck?
- qualitative session recordings / support feedback: is the concept wrong, or only execution?

Iterate if children complete the mission and parents view the report, but conversion drops later. Kill if mission start/completion is weak after UX fixes, or if activated leads are lower quality than the current funnel.

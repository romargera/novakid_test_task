# NovaKid Activation Reinvention

# 0. Test task

Background: NovaKid currently uses a standard "Linear Funnel".

Part 1: The Analysis 
Your first task is to identify the funnel steps and list where drop offs may occur. Explore the funnel by going through the process yourself.
Review the following hypothetical data snippet:
Only 10% of visitors start the quiz
Of these, 40% become a lead (leave their phone number)
Metric: We see better conversions on mobile (x2), but most of our traffic comes from web.
Question: What are your three immediate hypotheses for why the funnel is failing? Which segment (Mobile or Desktop) would you prioritize fixing first and why?

Part 2: The Reinvention 
Instead of "tweaking" the current funnel and changing buttons and colours, propose one entirely new "Activation Path" that ignores the current linear flow.
How would you get the child to experience the "Aha!" moment (actually speaking English with a tutor or AI) faster?
How would you integrate a "Premium" tier upsell into this new flow without bcreating massive friction?
Deliverable: A rough wireframe sketch (hand-drawn or digital) and a 1-page logic summary.

Part 3: The Experimentation Roadmap (30 mins)
You have 2 weeks and 1 developer/1 designer to test your "Reinvention" from Part 2.
What is your Minimum Viable Test (MVT)?
Which "North Star" metric determines success?
If the test fails, what data points would you look at to decide whether to iterate or kill the project?

## 1. Funnel Analysis

Assumption: I read **web** as desktop web and **mobile** as mobile web, excluding native app. If app traffic is included, I would split desktop web / mobile web / app before prioritizing.

Current funnel:

`Visit -> CTA / quiz start -> long parent quiz -> account -> phone -> email code -> child details -> plan + trial booking -> email/phone confirmation -> wait for lesson`

Main drop-offs:

- **Visit -> quiz start:** only 10% start the quiz. The problem starts before the quiz mechanics.
- **Quiz -> lead:** 40% of quiz starters become leads, so visitor-to-lead conversion is only ~4%.
- **Lead -> trial:** the post-lead path adds trust debt: unclear birth date, wrong calendar locale, default tariff selection, buried email CTA, phone without OTP, and extra confirmation by email/call.

Three immediate hypotheses:

1. **The offer asks for effort before proof.** Parents are not rejecting English lessons; they are rejecting a quiz with unclear payoff. A 90% pre-quiz leak suggests the landing page does not create enough confidence that "my child will actually speak English."
2. **The funnel optimizes qualification, not activation.** The buyer answers seven screens, while the real user never experiences value. This is the wrong actor at the wrong moment: parent data collection happens before child motivation is created.
3. **Post-lead friction converts intent into anxiety.** Every step after the lead asks for another commitment while lowering trust: verification, booking, calendar issues, confirmation, calls. This likely creates unreachable leads and no-shows, not only fewer leads.

Priority: **desktop web first**, if the assumption above is correct. Mobile web converts 2x better, but desktop web drives most traffic, so the biggest absolute upside is there. Before launch, I would split both segments by traffic source; if mobile wins because of traffic quality or lower-commitment browsing, desktop should borrow mobile's immediacy rather than port the current desktop funnel.

## 2. New Activation Path: "First English Minute"

Core idea: **make the child speak English before the parent completes the full funnel, but only after a clear parent permission moment.**

Proposed path:

1. Parent clicks: **"Let your child speak English in 60 seconds."**
2. Parent permission gate: explain mic use, no audio storage by default, guardian confirmation.
3. Parent gives only child nickname + age band. Age comes from the parent, not the child.
4. Child completes a short AI/tutor speaking mission: name, readiness, interest choice, one level-estimation prompt.
5. Parent handoff: in the full vision, QR/code opens the child's report on the parent's phone; in the MVT, the same device shows a parent-gated transition.
6. Parent sees a report, then answers deferred questions: goal, schedule, contact details, and consent. Primary CTA: **Reserve free trial**. Premium upsell: **daily AI speaking practice until the first live lesson**, shown after the Aha moment, not before it.

Rough wireframe:

```text
[Landing]
Let your child speak English in 60 seconds
[Start free speaking check]

        ->

[Parent Permission]
Mic is used for a live speaking check
No recording saved without consent
Child age band: 6-8
[I am the parent/guardian - start]

        ->

[Child Speaking Mission]
AI Tutor: "Hi! What is your name?"
AI Tutor: "Choose one: games / animals / music / sport"
Mic button + visual prompt
Progress: 1 of 3

        ->

[Child Screen]
Great job!
Show this to your parent
[QR code] [6-digit code]

        ->

[Parent Report on Phone]
Age band: 6-8
Interest: games
Spoke: 6 words
Level: Beginner
Recommended: live tutor trial this week
[Reserve free trial]
Secondary: daily AI practice until the lesson
```

## 3. Experimentation Roadmap

The riskiest assumption is not "can we build the full QR + AI report system?" It is: **will parents allow a child to try a short speaking task before signup, and does that create enough trust to move to the current trial step?**

Primary MVT read should match the current funnel's conversion event: lead capture / trial booking. If NovaKid wants to test payment readiness, card intent can be added as a separate diagnostic after trial intent, not as the only success event.

Minimum Viable Test for 2 weeks with 1 dev and 1 designer:

- Run on **desktop web traffic only**; track mobile web separately as a guardrail.
- Use a centered, mobile-like single-column desktop flow with a hard 60-second cap.
- Build only: landing page, parent permission gate, child speaking screen, parent-gated result screen.
- Skip QR, real AI, dynamic report generation, and audio storage. Use pre-recorded tutor prompts plus simple mic interaction.
- Handle partial completion positively: 1+ prompt = "your child said their first English words"; silence = lesson preview fallback.
- Primary CTA: **Reserve free trial**. Premium is only a secondary fake-door click: "Notify me about daily AI practice."
- Start with a 50/50 desktop split if volume is enough to read results. If volume is low, bias 70% to the test to accelerate learning and treat the result as directional until enough volume accumulates.

North Star:

**Speaking-Activated Trial Start Rate** = share of visitors who pass parent permission, complete the child speaking mission, and book or start a trial through the current conversion event.

Key diagnostics:

- **Speaking Activation Rate** = share of visitors who pass parent permission and complete the child speaking mission.
- **Parent Handoff Rate** = share of completed child missions where the parent opens results.
- **Report-to-trial-start rate** = whether the parent report creates enough trust to move forward.

Business guardrails:

- trial booking / confirmation rate should not be worse than the current desktop web funnel;
- if booking baseline is unavailable, target **6%+ speaking-activated lead rate** vs. current ~4% visitor-to-lead baseline;
- lead quality must hold: valid contact, reachable phone/email, comparable trial attendance intent;
- optional payment signal: card-start rate, if a card step is tested.

Decision rules:

- **Iterate** if 25%+ of visitors reach the mission, 50%+ of mission starters complete it, but parents drop at report, lead capture, or scheduling. That means activation works and the downstream window needs tuning.
- **Iterate** if mic permission is weak but non-mic fallback intent is strong; the problem is implementation friction, not the concept.
- **Kill or radically rethink** if, after the first 5-7 day read with enough desktop traffic, fewer than 15% of visitors start the mission or fewer than 40% of mission starters complete it.
- **Kill** if activated leads are lower quality than quiz leads: worse contact validity, lower booking confirmation, or lower show-up intent.

If the test fails, I would inspect:

- landing CTA click rate: is the promise strong enough?
- permission-gate accept rate: is trust/safety copy scaring or reassuring parents?
- mic permission rate: is browser/privacy friction the blocker?
- child start and completion rate: does the child understand and enjoy the mission?
- report view-to-trial-start rate: does the report create enough confidence to continue?
- booking confirmation and show-up rate: is scheduling still the bottleneck?

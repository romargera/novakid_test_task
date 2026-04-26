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

Scope assumption: the prompt says "mobile" vs. "web", but this is ambiguous. I interpret **web = desktop web** and **mobile = mobile web**, with native app excluded. If the reported mobile x2 includes app traffic, I would split it into desktop web / mobile web / app before making a prioritization call, because app users have different intent and acquisition history.

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

Priority: **desktop web first**, if the assumption above is correct. Mobile web converts 2x better, but desktop web drives most traffic, so the biggest absolute upside is there. Before launch, I would split both segments by traffic source: if mobile wins because of Instagram/TikTok intent or lower-commitment browsing, the desktop experiment should borrow mobile's immediacy instead of porting the current desktop funnel.

Additional context from the hiring-manager call: NovaKid is moving from class packages to **membership**, already has AI/self-learning assets, and wants the funnel owned from **visit to purchase**, not just visit to lead. I treat this as an additional business lens, not as a replacement for the current-funnel assignment.

## 2. New Activation Path: "First English Minute"

Core idea: **make the child speak English before the parent completes the full funnel, but only after a clear parent permission moment.**

Proposed path:

1. Parent lands on desktop web and clicks: **"Let your child speak English in 60 seconds."**
2. Parent sees a lightweight permission gate:
   - this is a live speaking check for a child;
   - microphone is used for this session;
   - no recording is stored unless the parent explicitly allows it;
   - parent confirms they are the guardian and starts the activity.
3. Parent gives only the minimum setup needed before handoff: child first name or nickname and age band. Age should come from the parent, not from the child, because it affects safety, prompt difficulty, and compliance.
4. The AI tutor or first teacher collects learning context naturally during the first interaction, reusing NovaKid's existing AI lesson capability:
   - "Hi, I'm Anna. What is your name?"
   - "Are you ready to try English with me?"
   - "What do you like: games, animals, music, or sport?"
   - one simple speaking task to estimate level.
5. The child screen shows a parent handoff:

```text
Great job!
Show this to your parent

[QR code]  or  6-digit code
See your child's English report
```

6. Parent scans the QR on their phone and sees the report:
   - child age band and interest;
   - words/phrases spoken;
   - estimated level;
   - recommended first tutor path.
7. Parent now answers deferred questions at a higher-intent moment:
   - goal: school / confidence / travel / long-term development;
   - schedule and timezone;
   - contact details;
   - consent to save recordings and progress.
8. The payment window appears after the Aha moment. Primary CTA: **Reserve free trial**. If membership strategy is in scope, this can be packaged as **Start a free trial week** and card-backed trial intent can be measured as a separate payment-window gate.
9. Premium appears as the recommended tier, not a separate distraction. The single hook is: **"Keep today's speaking momentum with daily AI practice until the first live lesson."** Exact Basic vs. Premium packaging is a follow-up business-model test, not a dependency for this activation experiment.

The QR handoff has precedent in kids products: [ClassDojo](https://help.classdojo.com/hc/en-us/articles/202794025-Invite-Families-to-ClassDojo) and [Seesaw](https://help.seesaw.me/hc/en-us/articles/203012019-How-to-invite-parents-and-families) use QR/code flows to connect parents to a specific child's profile or journal, while [YouTube Kids](https://support.google.com/youtubekids/answer/6172308?hl=en) uses parent-gated actions on child/shared devices.

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
Optional: start trial week - no charge today
Secondary: daily AI practice interest
```

## 3. Experimentation Roadmap

The riskiest assumption is not "can we build the full QR + AI report system?" It is: **will parents allow a child to try a short speaking task before signup, and does that create enough trust to move to the current trial step?**

Primary MVT read should match the current funnel's conversion event: lead capture / trial booking. If the membership context is also in scope, card-backed trial intent is a separate payment-window diagnostic, not the only success event. I would read the funnel as separate gates: `visitor -> permission accepted -> child mission completed -> parent handoff accepted -> report viewed -> lead captured -> trial booked -> optional card started -> optional trial week started`.

Minimum Viable Test for 2 weeks with 1 dev and 1 designer:

- Run on **desktop web traffic only**; track mobile web separately as a guardrail.
- Borrow the mobile-web pattern on desktop: centered single-column flow, large tap targets, one question per screen, and a hard 60-second mission cap.
- Build one landing page, one parent permission gate, and one child speaking screen.
- Skip QR/code for the MVT. Parent and child use the same device; QR remains part of the future vision.
- Same-device handoff after the child mission: **"Great job. Parent turn: tap and hold to see results."** This creates a deliberate parent-gated transition instead of an abrupt switch.
- Skip true AI and dynamic report generation. Use a pre-recorded tutor prompt plus a simple mic interaction.
- Do not store audio in the MVT; measure mic permission, speaking attempt, and completion events.
- Handle partial completion positively: 1+ completed prompt shows "your child said their first English words"; mic granted but silence shows "your child is ready to start"; no mic permission sends parent to a lesson preview.
- Show a static report/congratulations screen: "Your child just spoke English. Here's what a full lesson unlocks."
- Use one primary CTA: **Reserve free trial**. If membership checkout is in scope, add a secondary card-backed trial step or fake-door card step to measure payment-window intent (show card-entry intent, do not process payment).
- Do not sell Premium in the MVT. Track it only as a secondary fake-door click after trial intent: "Notify me about daily AI practice."
- Start with a 50/50 desktop split if volume is enough to read results. If volume is low, bias 70% to the test to accelerate learning and treat the result as directional until enough volume accumulates.

North Star:

**Speaking-Activated Trial Start Rate** = share of visitors who pass parent permission, complete the child speaking mission, and book or start a trial through the current conversion event.

Key diagnostics:

- **Speaking Activation Rate** = share of visitors who pass parent permission and complete the child speaking mission.
- **Parent Handoff Rate** = share of completed child missions where the parent opens results.
- **Report-to-trial-start rate** = whether the parent report creates enough trust to move forward.
- **Card-start rate** = optional payment-window signal if the membership trial gate is enabled.

Business guardrails:

- trial booking / confirmation rate should not be worse than the current desktop web funnel;
- if booking baseline is unavailable, target **6%+ speaking-activated lead rate** vs. current ~4% visitor-to-lead baseline;
- lead quality must hold: valid contact, reachable phone/email, comparable trial attendance intent.

Decision rules:

- **Iterate** if 25%+ of visitors reach the mission, 50%+ of mission starters complete it, but parents drop at report, lead capture, card entry, or scheduling. That means activation works and the downstream window needs tuning.
- **Iterate** if mic permission is weak but non-mic fallback intent is strong; the problem is implementation friction, not the concept.
- **Kill or radically rethink** if, after the first 5-7 day read with enough desktop traffic, fewer than 15% of visitors start the mission or fewer than 40% of mission starters complete it.
- Treat a second variant as a stretch goal: only copy/layout swaps that do not require a dev cycle, such as headline, CTA, permission-gate copy, or static report framing.
- **Kill** if activated leads are lower quality than quiz leads: worse contact validity, lower booking confirmation, lower show-up intent, or lower card-start rate if the payment gate is enabled.

If the test fails, I would inspect:

- landing CTA click rate: is the promise strong enough?
- permission-gate accept rate: is trust/safety copy scaring or reassuring parents?
- mic permission rate: is browser/privacy friction the blocker?
- child start and completion rate: does the child understand and enjoy the mission?
- report view-to-trial-start rate: does the report create enough confidence to continue?
- card entry drop-off, if enabled: is card-before-free-lesson too much friction?
- booking confirmation and show-up rate: is scheduling still the bottleneck?
- premium interest CTR after booking intent: is "daily practice until lesson" a credible upsell?

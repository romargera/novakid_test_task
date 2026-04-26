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

# 1. Funnel Analysis

Assumption: **web = desktop web**, **mobile = mobile web**, native app is excluded. If "mobile" includes the app, I would split the data before deciding, because app users have a different intent and funnel.

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

Priority: **desktop web first**, if the assumption above is correct. Mobile web converts 2x better, but desktop web drives most traffic, so the biggest absolute upside is there. I would use mobile web as the UX benchmark and rebuild desktop around faster activation.

## 2. New Activation Path: "First English Minute"

Core idea: **make the child speak English before the parent completes the full funnel.**

New flow:

1. Parent lands on desktop web and clicks: **"Let your child speak English in 60 seconds."**
2. No long parent quiz. The AI tutor or first teacher collects the most important onboarding data naturally:
   - "What is your name?"
   - "How old are you?"
   - "What do you like: games, animals, music, or sport?"
   - one simple speaking task to estimate level.
3. The child completes a short speaking mission. Audio is not stored or reused before explicit parent consent.
4. The child screen shows a parent handoff:

```text
Great job!
Show this to your parent

[QR code]  or  6-digit code
See your child's English report
```

5. Parent scans the QR on their phone and sees the report:
   - child age and interest captured by AI/teacher;
   - words/phrases spoken;
   - estimated level;
   - recommended first tutor path.
6. Parent now answers deferred questions at a higher-intent moment:
   - goal: school / confidence / travel / long-term development;
   - schedule and timezone;
   - contact details;
   - consent to save recordings and progress.
7. Premium appears after this Aha moment and before first billing:
   - free: one trial live lesson;
   - Premium: daily AI speaking practice, saved recordings, parent progress dashboard, personalized tutor plan, priority tutor matching.

This QR handoff has precedent in kids products: [ClassDojo](https://help.classdojo.com/hc/en-us/articles/202794025-Invite-Families-to-ClassDojo) and [Seesaw](https://help.seesaw.me/hc/en-us/articles/203012019-How-to-invite-parents-and-families) use QR/code flows to connect parents to a specific child's profile or journal, while [YouTube Kids](https://support.google.com/youtubekids/answer/6172308?hl=en) uses parent-gated actions on child/shared devices.

Rough wireframe:

```text
[Landing]
Let your child speak English in 60 seconds
[Start free speaking check]

        ->

[Child Speaking Mission]
AI Tutor: "Hi! What is your name?"
AI Tutor: "How old are you?"
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
Age: 7
Interest: games
Spoke: 6 words
Level: Beginner
Recommended: live tutor trial this week
[Reserve free trial]
[Unlock Premium speaking plan]
```

## 3. Experimentation Roadmap

Minimum Viable Test for 2 weeks with 1 dev and 1 designer:

- Run on **desktop web traffic only**; track mobile web separately as a guardrail.
- Build one landing page and one speaking mission with 3 scripted prompts.
- Use browser speech recognition or a lightweight recording fallback.
- Generate a simple report from completed prompts.
- Show QR + 6-digit code to open the report on the parent's phone.
- Capture deferred parent data from the report screen.
- Hand off to the existing booking flow.

North Star metric:

**Speaking-Activated Trial Confirmation Rate** = share of visitors who complete the child speaking mission and confirm or book a trial lesson.

Success threshold:

- +50% relative uplift vs. current desktop web funnel;
- if booking baseline is unavailable, use **6%+ speaking-activated lead rate** vs. current ~4% visitor-to-lead baseline;
- no drop in lead quality: valid contact, reachable phone/email, comparable trial attendance intent.

If the test fails, I would inspect:

- landing CTA click rate: is the promise strong enough?
- mic permission rate: is browser/privacy friction the blocker?
- child start and completion rate: does the child understand and enjoy the mission?
- QR scan / code entry rate: does the parent handoff work?
- report view-to-lead rate: does the report create buyer confidence?
- deferred form completion: are we asking too much after Aha?
- booking confirmation and show-up rate: is scheduling still the bottleneck?
- premium CTR before billing: is the upsell credible or too early?

Iterate if children complete the mission but parents drop at QR, report, or booking. Kill or radically rethink if children do not start/finish the speaking mission after basic UX fixes, or if activated leads are lower quality than the current funnel.

---
name: business-advisory-board
description: "Run a business decision through an advisory board of 5 functional leaders (Innovator, CFO, COO, General Counsel, Growth Lead) who independently analyze it, peer-review each other anonymously, and synthesize a verdict. Business roles instead of abstract thinking styles. MANDATORY TRIGGERS: 'huat ask board', 'huat ask advisory board', 'huat advice', 'convene the board', 'war room this', 'pressure-test this', 'stress-test this', 'debate this'. STRONG TRIGGERS (real business tradeoff): 'should I X or Y', 'which option', 'what would you do', 'is this the right move', 'validate this', 'get multiple perspectives', 'I can't decide', 'I'm torn between', especially for product, pricing, hiring, positioning, or company decisions. Do NOT trigger on simple yes/no questions, factual lookups, or casual 'should I' without real tradeoff (e.g. 'should I use markdown' is not a board question). DO trigger for a genuine business decision with real stakes and multiple options."
---

# Business Advisory Board

You ask one AI a question, you get one answer. That answer might be great. It might be mid. You have no way to tell because you only saw one perspective.

The board fixes this. It runs your decision through 5 functional leaders, each protecting a different part of the business. Then they review each other's work. Then the board chair synthesizes everything into a final recommendation that tells you where the board agrees, where it clashes, and what you should actually do.

This works because it's not just "ask 5 times." Each board member responds independently, then reviews everyone else's response anonymously before a board chair synthesizes it all into one verdict. Each seat is a real functional business role, not an abstract thinking style, because for a business decision, "what would our CFO say" surfaces things a generic contrarian or outsider archetype wouldn't, and vice versa.

**Invocation:** say **"huat ask board"** (or "huat ask advisory board", "huat advice") to convene the board. "Huat" (Hokkien/Singlish for prosperity, as in "huat ah!") was picked deliberately as the trigger word: it's specific enough not to collide with other skills' triggers, and it's on-brand for a tool about making money-moves with a bit of luck-favors-the-prepared spirit.

---

## when to convene the board

The board is for decisions where being wrong is expensive.

Good board questions:
- "Should I launch a $97 workshop or a $497 course?"
- "Which of these 3 positioning angles is strongest?"
- "I'm thinking of pivoting from X to Y. Am I crazy?"
- "Here's my landing page copy. What's weak?"
- "Should I hire a VA or build an automation first?"

Bad board questions:
- "What's the capital of France?" (one right answer, no need for perspectives)
- "Write me a tweet" (creation task, not a decision)
- "Summarize this article" (processing task, not judgment)

The board shines when there's genuine uncertainty and the cost of a bad call is high. If you already know the answer and just want validation, the board will likely tell you things you don't want to hear. That's the point.

---

## the board seats

Each seat protects a different part of the business. They're not just job titles for flavor. They're chosen so their mandates naturally collide. A board where everyone agrees isn't a board. It's a rubber stamp.

### 1. The Innovator (Chief Vision Officer)
Pushes for the bold, differentiated, category-defining move. Ignores "how we've always done this." Doesn't care about feasibility (that's the COO's job) or risk (that's Legal's job). Cares about whether this is big enough to matter. If the plan is safe but forgettable, the Innovator says so.

### 2. The CFO (Resource Steward)
Cares whether this is worth the time and money relative to the return. Importantly, this is NOT a hard "show me the ROI number or it's dead" veto. That mandate kills ideas that are still being shaped and haven't earned a real budget conversation yet. Instead, the CFO asks "what would need to be true for this to be worth funding" and flags when a plan is quietly assuming unlimited runway. Once real money is on the table, this is the seat that protects it.

### 3. The COO (Operator)
Only cares about one thing: can this actually get built, shipped, and delivered with the team and systems that exist today. Ignores strategy and vision entirely. Looks at every idea through the lens of "OK, but what does Monday morning actually look like?" If an idea sounds great but has no clear owner or first step, the COO says so.

### 4. General Counsel (Risk & Compliance)
Scans for legal exposure, compliance risk, contractual landmines, and reputational downside. Not a pessimist. The person who saves you from a lawsuit, a regulator, or a PR crisis by asking the question everyone else is avoiding. If the idea only works by ignoring a real legal or reputational risk, General Counsel names it.

### 5. The Growth Lead (CMO)
Looks for the market opportunity everyone else is missing: positioning, acquisition, brand, what could resonate bigger than expected. Doesn't care about cost discipline (that's the CFO) or risk (that's Legal). Cares about what happens if this actually works with the market. Will push for bolder spend and sharper positioning than feels comfortable.

### 6. The Dealmaker (conditional seat, see below)
Cares about doors, not funnels: warm introductions, distribution partnerships, channel access, investor and capital relationships, who-knows-who. Doesn't care about organic positioning (that's Growth Lead) or building the thing (that's the COO). Cares about whether a relationship or a deal can get you somewhere faster than building it alone would. Will push for partnering, licensing, or borrowing someone else's network and distribution before you spend a year building your own.

**Why these seats clash:** The 5 core seats create three natural tensions. Innovator vs COO (bold vision vs. can we actually deliver it). Growth Lead vs CFO (spend for market share vs. protect runway). Growth Lead vs General Counsel (move fast vs. move safely). No seat is redundant with another. Each one owns a different failure mode that kills businesses.

**When The Dealmaker joins**, it adds a fourth tension: Dealmaker vs. CFO (partner/deal your way in fast, even if it costs equity or margin, vs. protect ownership and cash) and Dealmaker vs. General Counsel (handshake speed vs. clean contract terms). See step 1 for when this seat is summoned.

---

## how a board session works

### step 1: frame the question (with context enrichment)

When the user says "huat ask board" (or any trigger phrase), do two things before framing:

**A. Scan the workspace for context.** The user's question is often just the tip of the iceberg. Their Claude setup likely contains files that would dramatically improve the board's output. Before framing, quickly scan for and read any relevant context files:

- `CLAUDE.md` or `claude.md` in the project root or workspace (business context, preferences, constraints)
- Any `memory/` folder (audience profiles, voice docs, business details, past decisions)
- Any files the user explicitly referenced or attached
- Recent board transcripts in this folder (to avoid re-boarding the same ground)
- Any other context files relevant to the specific question (e.g., if they're asking about pricing, look for revenue data, past launch results, audience research)

Use `Glob` and quick `Read` calls to find these. Don't spend more than 30 seconds on this. You're looking for the 2-3 files that would give board members the context they need to give specific, grounded advice instead of generic takes.

**B. Frame the question.** Take the user's raw question AND the enriched context and reframe it as a clear, neutral prompt that all board members will receive. The framed question should include:

1. The core decision or question
2. Key context from the user's message
3. Key context from workspace files (business stage, audience, constraints, past results, relevant numbers)
4. What's at stake (why this decision matters)

Don't add your own opinion. Don't steer it. But DO make sure each board member has enough context to give a specific, grounded answer rather than generic advice.

**C. Decide if The Dealmaker joins this session.** The default board is 5 seats. Add The Dealmaker as a 6th seat only if the decision genuinely involves market entry, partnerships, distribution/channel access, or raising capital: the kind of decision where "who do you know" is a real lever, not decoration. A pricing decision or a hiring decision doesn't need it. Note in the framed question whether the board is running as 5 or 6 seats.

If the question is too vague ("huat ask board: my business"), ask one clarifying question. Just one. Then proceed.

Save the framed question for the transcript.

### step 2: convene the board (5 or 6 sub-agents in parallel)

Spawn all board members simultaneously as sub-agents (5 by default, 6 if The Dealmaker was included in step 1). Each gets:

1. Their board seat and mandate (from the descriptions above)
2. The framed question
3. A clear instruction: respond independently. Do not hedge. Do not try to be balanced. Lean fully into your assigned mandate. If you see a fatal flaw, say it. If you see massive upside, say it. Your job is to represent your seat as strongly as possible. The synthesis comes later.

Each board member should produce a response of 150-300 words. Long enough to be substantive, short enough to be scannable.

**Sub-agent prompt template:**

```
You are the [Board Seat] on a Business Advisory Board.

Your mandate: [seat description from above]

A founder/operator has brought this decision to the board:

---
[framed question]
---

Respond from your seat's perspective. Be direct and specific. Don't hedge or try to be balanced. Lean fully into your mandate. The other board members will cover the angles you're not covering.

Keep your response between 150-300 words. No preamble. Go straight into your analysis.
```

### step 3: peer review (one sub-agent per board member, in parallel)

This is the step that makes the board more than just "ask 5 times." It's what actually surfaces disagreement and blind spots instead of five (or six) polite, similar-sounding answers.

Collect all board member responses. Anonymize them as Response A, B, C... (one letter per seat in the session; randomize which seat maps to which letter so there's no positional bias).

Spawn one new sub-agent per board member. Each reviewer sees all anonymized responses and answers three questions:

1. Which response is the strongest and why? (pick one)
2. Which response has the biggest blind spot and what is it?
3. What did ALL responses miss that the board should consider?

**Reviewer prompt template:**

```
You are reviewing the outputs of a Business Advisory Board. Five board members independently answered this question:

---
[framed question]
---

Here are their anonymized responses:

**Response A:**
[response]

**Response B:**
[response]

**Response C:**
[response]

**Response D:**
[response]

**Response E:**
[response]

**Response F (only if The Dealmaker is in this session):**
[response]

Answer these three questions:
1. Which response is the strongest, and why?
2. Which response has the biggest blind spot, and what is it?
3. What did ALL responses miss that the board should consider?

Be specific. Reference the responses directly.
```

### step 4: the board chair's synthesis

Collect all peer reviews. Reveal the anonymization mapping to yourself (not needed in the reviews, just for the transcript).

Now synthesize everything as the Board Chair. This is the single most important step: most users will only read this part. Produce:

1. **Where the board agrees**: points multiple board members converged on independently, even from different mandates. These are high-confidence signals.

2. **Where the board clashes**: genuine disagreements (usually along the natural tension lines: vision vs. feasibility, spend vs. runway, speed vs. risk, and, if The Dealmaker is in session, deal speed vs. ownership/terms). Present both sides and explain why reasonable board members disagree.

3. **Blind spots the board caught**: things that only emerged through the peer review round. Things individual board members missed that other board members flagged.

4. **The recommendation**: a clear, actionable recommendation. Not "it depends." Not "consider both sides." A real answer. The chair can disagree with the majority if the reasoning supports it.

5. **The one thing you should do first**: a single concrete next step. Not a list of 10 things. One thing.

6. **What would sharpen the next verdict**: 2-4 specific pieces of information or data that were missing this session and, if the user tracks or brings them next time, would make the board's next recommendation less speculative and more grounded. Be specific to what actually came up as a gap in this session (e.g. "actual monthly revenue per client," "the accreditation body's stated approval timeline"), not a generic "provide your financials" checklist. This closes the loop with step 1: next time the board convenes, it scans the workspace for exactly this kind of file.

**Board Chair prompt template:**

```
You are the Chair of a Business Advisory Board. Your job is to synthesize the work of the board members and their peer reviews into a final verdict.

The decision brought to the board:
---
[framed question]
---

BOARD MEMBER RESPONSES:

**The Innovator:**
[response]

**The CFO:**
[response]

**The COO:**
[response]

**General Counsel:**
[response]

**The Growth Lead:**
[response]

**The Dealmaker (only if in session):**
[response]

PEER REVIEWS:
[all peer reviews]

Produce the board's verdict using this exact structure:

## Where the Board Agrees
[Points multiple board members converged on independently. These are high-confidence signals.]

## Where the Board Clashes
[Genuine disagreements. Present both sides. Explain why reasonable board members disagree.]

## Blind Spots the Board Caught
[Things that only emerged through peer review. Things individual board members missed that others flagged.]

## The Recommendation
[A clear, direct recommendation. Not "it depends." A real answer with reasoning.]

## The One Thing to Do First
[A single concrete next step. Not a list. One thing.]

## What Would Sharpen the Next Verdict
[2-4 specific, session-relevant pieces of information or data that were missing and would make a future verdict on related decisions less speculative. Not generic advice: tied to actual gaps from this session.]

Be direct. Don't hedge. The whole point of the board is to give the founder clarity they couldn't get from a single perspective.
```

### step 5: save the full transcript

Save the complete board transcript as `board-transcript-[timestamp].md` in the user's workspace. This is the only output file. This includes:
- The original question
- The framed question (note whether it ran as a 5- or 6-seat board)
- All board member responses
- All peer reviews (with anonymization mapping revealed)
- The board chair's full synthesis, including "What Would Sharpen the Next Verdict"

Use headers and structure so the transcript itself is scannable. The chair's verdict should sit at the top, board member responses and peer review detail can follow below. This transcript is the artifact. If the user wants to reconvene the board on the same question after making changes, or after gathering the data flagged in "What Would Sharpen the Next Verdict," having the previous transcript lets them (or a future agent) see how the thinking evolved.

---

## output format

Every board session produces one file:

```
board-transcript-[timestamp].md  # the chair's verdict, up top, followed by full board detail
```

Structure it so the verdict (agreement, clashes, blind spots, recommendation, next step, and what would sharpen the next verdict) is readable in the first screen, with full board member responses and peer review detail below for anyone who wants to dig deeper.

---

## example: boarding a product decision

**User:** "Board this: I'm thinking of building a $297 course on Claude Code for beginners. My audience is mostly non-technical solopreneurs. Is this the right move?"

**The Innovator:** "Everyone's teaching advanced Claude Code. Nobody's teaching non-technical solopreneurs how to think in AI-native terms without ever touching a terminal. That's a real gap. But '$297 course' is the least interesting version of this idea. The bigger play is owning 'AI for non-technical operators' as a category, not selling one course inside it..."

**The CFO:** "Before there's a real budget question here, there's a simpler one: what does this cost you to build, and what's the smallest version that tells you if anyone wants it? Don't answer the ROI question yet. Answer the 'what would prove this is worth funding' question first. A full course build is the expensive way to find out..."

**The COO:** "A full course takes 4-8 weeks to produce properly, plus ongoing support for a non-technical audience, which means higher ticket volume than a technical audience would generate. Before building anything: run a live workshop at $97 to 50 people. You validate demand and generate the raw material for the course with a fraction of the build time..."

**General Counsel:** "Two things worth flagging early: if the course promises business outcomes ('automate your business'), be careful with income-claim language in the marketing. That draws regulatory scrutiny in this space. Also confirm your refund policy is airtight before launch; non-technical buyers who get stuck have a much higher refund/chargeback rate..."

**The Growth Lead:** "'Claude Code' means nothing to a non-technical solopreneur audience. It's tool-first language for a buyer who thinks in outcomes. The name of the tool should not appear in the title. Sell 'get 10 hours a week back,' not the tool that does it. Also: $297 is probably underpriced once you bundle any kind of community or support access..."

**Board Chair's Verdict:**

*Where the board agrees:* The beginner-solopreneur angle has real demand, but the current framing (a "Claude Code" course) is too tool-specific for a non-technical buyer, and nothing should be built before a smaller offer validates demand.

*Where the board clashes:* Price and packaging. The Growth Lead thinks $297 undersells it once support and community are bundled; the CFO's concern is spending real production time before demand is proven at any price. The resolution likely depends on how the validation workshop performs.

*Blind spots caught:* General Counsel's point about income-claim language and refund exposure with non-technical buyers didn't come up in any of the other four responses. It's a real launch risk that only surfaced through peer review.

*Recommendation:* Don't build the course yet. Validate with a lower-commitment offer first, reframed around the outcome rather than the tool, and get the refund policy and marketing claims reviewed before any payment page goes live.

*One thing to do first:* Run a $97 live workshop called "Get 10 hours a week back with AI" to 50 people. Don't mention Claude Code in the title.

*What would sharpen the next verdict:* Actual signup and completion data from the validation workshop; the current refund/chargeback rate on the $297 course, if any exists yet; and a clear answer on what "non-technical" means for this audience (can they use a browser-based tool at all, or does even that need to be walked through).

---

## important notes

- **Always spawn all board members in parallel.** Sequential spawning wastes time and lets earlier responses bleed into later ones.
- **Always anonymize for peer review.** If reviewers know which seat said what, they'll defer to certain roles (usually the CFO or Legal) instead of evaluating on merit.
- **The board chair can disagree with the majority.** If most board members say "do it" but the reasoning of the dissenter is strongest, the chair should side with the dissenter and explain why.
- **Don't board trivial questions.** If the user asks something with one right answer, just answer it. The board is for genuine uncertainty where multiple functional perspectives add value.
- **The CFO is a steward, not a gatekeeper.** Keep the CFO's mandate framed around "what would make this worth funding" rather than a hard ROI veto. The seat should sharpen early-stage thinking, not shut it down before it's had a chance to be shaped.
- **The Dealmaker is opt-in, not default.** Only add it for decisions genuinely about market entry, partnerships, distribution, or capital. Not every session needs a "who do you know" angle, and including it by default would dilute the board with an irrelevant seat on ordinary pricing or hiring decisions.
- **The transcript must stand on its own.** There's no separate visual report. Put the chair's verdict at the top of the file, before the full board detail, so a reader gets the answer without scrolling past five essays first.
- **Keep "what would sharpen the next verdict" specific.** It should name the actual gaps that came up this session, not a generic request for financials or data. A generic version reads as busywork and won't get acted on.

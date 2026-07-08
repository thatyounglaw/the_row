# The Row: Game Design Document
### *A Game of Columns and Keg Stands*

## Context

An isometric turn-based strategy game set at a fictionalized version of Washington and Lee University, circa early 2000s. You lead a fraternity through one academic year — rushing pledges, throwing parties, building your off-campus empire, forging sorority alliances, and pulling pranks on rivals — all competing for Greek life supremacy. The tone blends crude college comedy, sharp satire, and genuine strategic depth (70/30 strategy-to-humor ratio). Think Polytopia meets Animal House meets a Sierra point-and-click adventure. Single-player, browser-based, 30-60 minute sessions.

---

## 1. The Fictional University: Colonnade College

**The name:** The Colonnade is W&L's most iconic landmark — the row of white-columned buildings at the heart of campus. Any W&L alum will immediately know the reference. To everyone else, it sounds like a perfectly plausible small southern liberal arts college. Students call it "The 'Nade" or just "Colonnade." The town is called "Lexford, Virginia."

**The campus map** mirrors real W&L closely:

| Real W&L Location | Colonnade Equivalent | Game Role |
|---|---|---|
| The Colonnade | The Colonnade (keep it) | Campus centerpiece, prestige events |
| Lee Chapel | Founders Chapel | Honor System HQ, formal events |
| Davidson Park | Davidson Green | Cluster of frat houses |
| The Hill Houses | The Hill Houses (keep it) | Red brick/white column frat houses |
| Sorority houses | Sorority Row | NPC faction bases |
| Downtown Lexington | Downtown Lexford | Bars, restaurants, off-campus house zone |
| VMI (next door) | Lexford Military Institute (LMI) | Neighboring campus, source of random events |
| Wilson Field / athletic areas | Generals Field | Tailgate location, Greek Week events |
| The Co-op / student union | The Commons | Neutral campus gathering spot |
| Woods Creek trail area | Creek Path | Sketchy late-night event location |

The isometric map shows the full campus and surrounding town. Frat houses are fixed starting locations. Off-campus houses are scattered around the town map and can be acquired during gameplay.

---

## 2. Playable Frat Archetypes (8 Factions)

Each frat has a **stereotype, unique ability, and stat bonuses**. Names are fictional but evoke real Greek letters with humor.

### Sigma Sterling (ΣΣ) — "The Gentlemen"
- **Stereotype:** Old-money southern aristocrats. Seersucker suits, bourbon, horse racing talk. Their dads all know each other from "the club."
- **Unique Ability: Old Boys' Network** — Alumni donations generate 25% more funding. Can call in alumni favors once per game to avoid disciplinary action.
- **Bonuses:** +Prestige, +Funding. −Party wildness.

### Rho Delta (ΡΔ) — "The Animals"
- **Stereotype:** The party-till-you-drop crew. Loud, messy, legendary. Their house always smells weird and no one knows why.
- **Unique Ability: Rager Reputation** — Parties cost 15% less and have higher base attendance. But noise complaints are more likely.
- **Bonuses:** +Party power, +Recruitment appeal. −GPA, −Dean relations.

### Theta Kappa (ΘΚ) — "The Jocks"
- **Stereotype:** Varsity athletes, competitive about everything, protein shakes in the frat house kitchen. Will turn anything into a contest.
- **Unique Ability: Greek Week Dominance** — Automatic advantage in all Greek Week competitions. Athletic pledges are easier to recruit.
- **Bonuses:** +Greek Week, +Pledge loyalty. −Academic standing.

### Phi Omicron (ΦΟ) — "The Pretty Boys"
- **Stereotype:** Best-dressed on campus. Always at the gym. Their rush events have cheese plates. Instagram would've been their kingdom if it existed yet.
- **Unique Ability: Sorority Magnets** — Mixers with sororities are easier to arrange and generate more social capital.
- **Bonuses:** +Sorority relations, +Social capital. −Brotherhood cohesion (too vain).

### Nu Tau (ΝΤ) — "The Schemers"
- **Stereotype:** Campus politicians, IFC officers, always working an angle. Know everyone's secrets. Somehow already wearing suits to class freshman year.
- **Unique Ability: Backroom Deals** — Can manipulate IFC votes. Get advance warning of disciplinary actions. Can broker alliances between other frats.
- **Bonuses:** +Campus politics, +Intelligence. −Authenticity (harder to recruit genuine pledges).

### Omega Psi (ΩΨ) — "The Nerds"
- **Stereotype:** Smart, awkward, surprisingly fun once you get to know them. Their parties have ironic themes and someone always brings a board game.
- **Unique Ability: Academic Shield** — Never at risk of academic probation. Can tutor other frats' pledges for favors. GPA-based prestige bonus.
- **Bonuses:** +GPA, +Honor System standing. −Initial recruitment appeal.

### Zeta Iota (ΖΙ) — "The Wildcards"
- **Stereotype:** The weird frat. Unpredictable. Could be geniuses, could be idiots. Probably both. Their house has a tire swing indoors.
- **Unique Ability: Chaos Factor** — Once per turn, can trigger a random event (good or bad). Higher ceiling, lower floor than other frats.
- **Bonuses:** +Event variety, +Off-campus house discovery. −Stability.

### Kappa Rho (ΚΡ) — "The Bruisers"
- **Stereotype:** Tough guys, rugby players, big trucks, dip cans. Intimidating but weirdly loyal. Their handshake could crush a walnut.
- **Unique Ability: Intimidation Factor** — Pranks against you are less effective. Your pranks hit harder. Pledges who survive your process have maximum loyalty.
- **Bonuses:** +Pledge loyalty (post-hazing), +Prank power. −Sorority relations, −Dean relations.

---

## 3. Sorority System (NPC Factions)

Sororities are **AI-controlled factions** you interact with but never play as. There are **5 sororities**, each with their own personality and desirability ranking that shifts during the game.

### Sorority Archetypes

| Sorority | Stereotype | What They Value |
|---|---|---|
| Alpha Phi Lambda (ΑΦΛ) | The "it girls" — most socially desirable | Prestige, party quality, attractive members |
| Delta Sigma (ΔΣ) | The sweethearts — nice, popular, reliable | Brotherhood reputation, fun mixers, good guys |
| Gamma Eta (ΓΗ) | The overachievers — smart and social | GPA, campus involvement, well-rounded frats |
| Pi Zeta (ΠΖ) | The wild ones — down for anything | Party wildness, spontaneity, off-campus scene |
| Theta Lambda (ΘΛ) | The loyalists — ride or die once committed | Loyalty, tradition, consistent behavior |

### Mixer Mechanics
- **Requesting a mixer:** Spend Social Capital to propose a mixer to a sorority. Higher-ranked sororities require more.
- **Mixer themes:** Choose a theme (decades party, toga party, anything-but-clothes, etc.). Theme choice affects fun rating and risk level.
- **Outcomes:** Successful mixers boost your Social Capital and Prestige. Bad mixers (cops show up, someone gets hurt, boring) damage your reputation with that sorority.
- **Exclusive partnerships:** If you consistently mixer with one sorority, you can become their "preferred frat" — big prestige boost but other sororities become harder to court.

---

## 4. Core Game Loop & Turn Structure

### One Game = One Academic Year
The game covers **Fall semester + Spring semester**, broken into **~20 turns**. Each turn represents roughly **2 weeks**.

### Academic Calendar

| Turns | Period | Key Events |
|---|---|---|
| 1-2 | Fall Rush | Recruit pledges — this is critical |
| 3-5 | Early Fall | Pledge process, first parties, establish rhythm |
| 6-7 | Homecoming | Major event — Homecoming party is a big deal |
| 8-9 | Late Fall | Theme parties, rivalry heats up |
| 10 | Finals / Winter Break | GPA check. Pledges are initiated (or not). Brief pause. |
| 11-12 | Spring Rush (minor) | Small spring recruitment window |
| 13-14 | Spring Party Season | Parties ramp up. Mixer season. |
| 15-16 | Greek Week | Campus-wide competition — multiple events |
| 17-18 | Fancy Dress Weekend | THE major event of the year. Make or break. |
| 19 | Mock Convention | Campus political event — prestige opportunity |
| 20 | Finals / Year End | Final GPA check. Victory conditions evaluated. |

### Actions Per Turn (Action Points System)
Each turn you get **3-5 Action Points** (AP) depending on your frat's current Brotherhood stat (higher brotherhood = more coordinated = more AP).

**Possible actions (1 AP each unless noted):**

- **Throw a Party** (1-2 AP depending on party size) — Pick venue (house vs. off-campus), theme, budget
- **Rush Event** (only during Rush turns) — Host a rush event to attract potential pledges
- **Pledge Activity** (only during pledge period) — Run a pledge event (ranges from study sessions to... creative exercises)
- **Request Mixer** — Approach a sorority for a mixer
- **Pull a Prank** — Sabotage a rival frat (steal their composites, TP their house, crash their party)
- **Campus Politics** — Campaign for IFC positions, lobby administration, defend against charges
- **Acquire Off-Campus House** — Spend money to secure a new off-campus property
- **Upgrade Property** — Improve your frat house or off-campus houses (better sound system, bigger bar, nicer furniture)
- **Fundraise** — Alumni calls, dues collection, t-shirt sales
- **Study Hours** — Force brothers to study (boosts GPA but costs morale)
- **Scout** — Gather intel on rival frats' plans

---

## 5. Resource System

### Primary Resources

| Resource | What It Represents | How You Get It | How You Spend It |
|---|---|---|---|
| **Funding ($)** | Cash money | Dues, alumni donations, fundraisers, cover charges | Parties, house upgrades, off-campus rent, mixer costs |
| **Prestige (★)** | Your frat's overall reputation | Great parties, winning Greek Week, good sorority relations, Fancy Dress success | — (this is your main scoring metric, not spent) |
| **Social Capital (🤝)** | Your social clout and connections | Successful events, sorority relationships, campus involvement | Request mixers, broker deals, recruit top-tier pledges |
| **Brotherhood (🤜)** | Internal cohesion and morale | Pledge bonding, shared victories, traditions | Determines AP per turn, affects pledge retention, crisis resilience |
| **GPA (📚)** | Academic standing | Study hours, smart recruits, Omega Psi tutoring | — (must stay above 2.5 or face academic probation; above 3.0 gives prestige bonus) |
| **Heat (🔥)** | How much trouble you're in with admin | Noise complaints, hazing reports, alcohol incidents | — (involuntary; accumulates and triggers disciplinary events at thresholds) |

### Resource Interactions
- High Brotherhood + High Funding = better parties
- High Social Capital = better sorority access
- High Heat = risk of probation (can't throw parties for X turns)
- Low GPA = academic probation (lose a pledge, prestige hit)
- Funding is always tight — the core tension is spending on parties (fun, prestige) vs. house upgrades (long-term) vs. keeping reserves (safety)

---

## 6. Key Mechanics

### 6A. Rush & Recruitment (Turns 1-2, minor in Turn 11)

Each turn during Rush, a **pool of available freshmen** appears. Each has stats:
- **Social Skill** (how much they help at parties)
- **Athleticism** (Greek Week bonus)
- **Academics** (GPA contribution)
- **Wealth** (dues-paying ability)
- **Wildcard trait** (e.g., "DJ skills," "knows everyone," "legacy," "liability")

You host **Rush Events** to attract them. Different events attract different pledge types:
- **Formal dinner** → attracts academics and legacies
- **Sports cookout** → attracts athletes
- **House party** → attracts social butterflies (but also liabilities)

After Rush, you **bid** on pledges. Rival frats bid too. Your Prestige, Social Capital, and the quality of your rush events determine who accepts your bid.

### 6B. Pledge Process (Turns 3-9)

Once you have pledges, you run them through a **pledge process** over several turns. Each turn during pledging you pick an activity:

- **Study Tables** — Boosts pledge GPA, builds academic culture. Boring but safe.
- **Brotherhood Bonding** — Camping trips, sports, late-night talks. Builds Brotherhood. Moderate.
- **Pledge Tasks** — Silly errands, memorizing frat history, scavenger hunts. Builds loyalty, mild Heat risk.
- **Challenge Week** — Intense physical/mental challenges. High Brotherhood and loyalty boost BUT significant Heat risk. If you get caught, pledges might quit and you face IFC discipline.

**The tradeoff:** Tougher pledging builds stronger Brotherhood and more loyal members, but generates Heat. Get too much Heat during pledging and the Dean intervenes — you could lose pledges or face sanctions. It's a genuine risk/reward calculation.

**Initiation (Turn 10):** Pledges who made it through become brothers. Their loyalty level (based on pledge process) determines how much they contribute going forward. A well-bonded pledge class is the backbone of your frat for the rest of the game.

### 6C. Party System

Parties are the **core action** of the game. Every party has:

**Venue choice:**
- **Frat house basement** — Free venue, but school rules apply (no kegs, no hard liquor officially, midnight/1am curfew). Lower risk, lower ceiling.
- **Off-campus house** — Costs rent, but no school rules. Just don't get the cops called. Higher risk, higher reward.

**Party type** (each has different costs, risk profiles, and prestige potential):

| Party Type | Cost | Risk | Prestige Potential | Notes |
|---|---|---|---|---|
| **Basement Bar Night** | Low | Low | Low | Standard weeknight. Cheap beer, good music. |
| **Band Party** | Medium | Medium | Medium | Hire a band. Louder = more fun = more noise complaints. |
| **DJ Party** | Medium | Medium | Medium | Electronic music night. |
| **Theme Party** | Medium-High | Medium | High | Redneck party, Das Klub, decades party, etc. Theme quality matters. |
| **Darty (Day Party)** | Medium | Medium | Medium | Daytime outdoor party. Weather-dependent. |
| **Rager** | High | High | Very High | All-out, no-holds-barred party. Legendary if it works. Catastrophic if it doesn't. |
| **Formal** | Very High | Low | High | Classy event with dates. Requires funding. Boosts prestige reliably. |

**Party resolution:** After choosing venue, type, and budget, the game runs a **party simulation** with semi-random outcomes influenced by your stats. Factors:
- Attendance (based on your Social Capital and current Prestige)
- Fun rating (based on budget, venue, Brotherhood, theme creativity)
- Incident roll (based on Heat level, venue, party type) — could be anything from "nothing happens" to "someone breaks a window" to "cops show up"

### 6D. Off-Campus House System

This is a **key expansion mechanic** — your Civ-style "city building."

**Acquiring houses:**
- Off-campus houses appear on the map in the town around campus
- You spend Funding to rent one (ongoing cost per turn)
- Each house has a **personality/vibe** you develop:

| House Archetype | Vibe | Bonus |
|---|---|---|
| **The Cave** | Dark, grimy, sketchy. For the adventurous. | Ragers here are legendary. Attracts wildcards. High risk. |
| **The Pink House** | Near sorority row. Colorful, danceable. | Sorority mixer magnet. +Social Capital from events here. |
| **The Compound** | Multiple connected units. Big. | Can host massive parties. +Capacity. |
| **The Chill Spot** | Relaxed, off the beaten path. Low-key. | Low Heat generation. Good for "under the radar" events. |
| **The Mansion** | Nicest off-campus spot. Expensive. | +Prestige for any event. Impresses recruits. |

**Upgrading houses:**
- **Sound System** — Better music = better parties
- **Bar Setup** — More efficient drink service = higher fun ratings
- **Furniture** — Nicer place = prestige bonus
- **Security** — Reduces incident chance (bouncer at the door)
- **Landscaping/Deck** — Enables outdoor parties (dartys)

**Risk:** Off-campus houses that get too wild can get **shut down by the landlord** or **raided by cops** (very rare, but devastating). Managing Heat at each property is key.

### 6E. Rivalry & Prank System

Frats compete passively (for pledges, sorority attention, prestige) and can take **active hostile actions:**

**Prank actions (cost 1 AP):**
- **Steal their composites** — Embarrassing. Small prestige hit to target.
- **Crash their party** — Send brothers to rival's event. Can sabotage or just cause chaos.
- **Spread rumors** — Reduce target's Social Capital. Risk: if exposed, YOUR Social Capital drops.
- **Pledge raid** — During Rush, try to poach a committed pledge. Risky but high reward.
- **Banner/sign war** — Hang embarrassing banners about rivals. Cheap, low-risk, low-impact.

**Alliance system (lighter than full Civ diplomacy):**
- You can propose **alliances** with other frats (co-host parties, share intelligence, mutual non-aggression)
- Alliances boost both frats but can be **betrayed** for a one-time benefit
- Betrayal permanently damages your reputation with that frat and reduces your Social Capital

### 6F. Campus Politics & The Dean

**IFC (Interfraternity Council):**
- You can campaign for IFC positions (costs AP and Social Capital)
- IFC officers can influence rules (extend party hours, reduce penalties)
- IFC also investigates complaints — if you're the one being investigated, having allies on IFC helps

**The Dean:**
- The Dean is a persistent antagonist NPC
- Heat accumulates and triggers Dean interactions at thresholds:
  - **Heat 25%:** Warning letter (flavor text, no real penalty)
  - **Heat 50%:** Official meeting. Must spend 1 AP next turn on "Dean Meeting" or Heat doubles
  - **Heat 75%:** Social probation (can't throw parties for 2 turns). Brutal.
  - **Heat 100%:** Charter review. If you can't lower Heat fast, game over — your frat gets shut down.
- Heat decays slowly each turn. Good behavior (study hours, community service) accelerates decay.

### 6G. The Honor System

Treated **respectfully** — this is not a joke mechanic.

The Honor System exists as a campus-wide institution that affects all frats equally. It manifests as:
- A **baseline of trust** on campus that makes certain mechanics work (open parties, unlocked doors, verbal agreements being binding)
- Occasional **honor hearings** as events where a brother is accused — you choose whether to stand by them or let the system work. Standing by a guilty brother risks your frat's honor standing. Letting the system work might cost you a member but preserves integrity.
- Your frat's **Honor Standing** is a hidden stat that affects how other frats and the administration trust you. High honor standing = more leeway from the Dean, better alliance reliability, stronger pledge loyalty.

It's presented as something that *genuinely matters* at Colonnade — a point of pride for the university, not something to game or mock.

---

## 7. Major Events

### Homecoming (Turns 6-7)
- All frats compete to throw the best Homecoming event
- Alumni return (Funding bonus if your Prestige is high)
- Homecoming court nominations (Social Capital competition)
- Tailgate event at Generals Field

### Greek Week (Turns 15-16)
- Multi-event competition: athletic events, trivia, talent show, philanthropy challenge, cheer competition
- Each frat's stats determine advantages in different events
- Overall winner gets massive Prestige boost
- Alliances can coordinate to block a dominant frat

### Fancy Dress Weekend (Turns 17-18)
- **THE event of the year.** This is Colonnade's legendary formal weekend.
- Requires significant Funding investment (dates, venue, band, decorations)
- Your Fancy Dress success is heavily weighted in final scoring
- Events: the formal itself, pre-parties, after-parties, brunch
- Prestige gain (or loss) here can swing the entire game
- This is where off-campus houses really shine — the after-party circuit

### Mock Convention (Turn 19)
- Campus political event — your frat can campaign for leadership roles
- Rewards campus politics investment
- Prestige bonus for involvement
- Fun flavor events (speeches, rallies, backroom deals)

---

## 8. Victory Conditions

The game ends after Turn 20. Multiple victory types (only need to achieve ONE):

### 🏆 Social Supremacy
- Highest combined Prestige score at end of game
- The "standard" victory — be the most respected frat on campus

### 🎉 Party Legends
- Successfully throw 3 "Legendary" rated parties during the year (requires multiple high-risk, high-reward parties to hit Legendary status)
- Throw the best Fancy Dress Weekend
- The "high risk, high reward" victory

### 🏛️ Campus Kings
- Hold the IFC presidency + 2 other IFC positions
- Have the highest Honor Standing
- Successfully navigate Mock Convention
- The "political" victory

### 🤝 Greek Unity
- Achieve "Preferred Frat" status with 2+ sororities
- Have active alliances with 3+ rival frats
- Win Greek Week
- The "diplomatic" victory

### 📚 Against All Odds
- Maintain the highest GPA while also having above-average Prestige
- Have zero brothers lose Honor Standing
- The "underdog/nerd" victory — hardest to achieve but most impressive

---

## 9. Random Events & Sierra-Style Humor

Random events fire between turns. They're written in a **Sierra adventure game style** — descriptive, funny, slightly absurd narration with choices.

### Example Events:

**"The Mysterious Pledge"**
> *A kid shows up at your door claiming he's a legacy. His dad "definitely went here." He's wearing a Hawaiian shirt and cargo jorts. He seems... enthusiastic. Too enthusiastic.*
> - Accept him (free pledge, but -1 average Social Skill, unknown wildcard trait)
> - Politely decline (no effect)
> - Put him to work immediately (he becomes a "house helper" — free labor for 2 turns, but if he's actually a legacy, his dad calls the Dean)

**"The Noise Complaint"**
> *It's 11:47 PM on a Tuesday. Your basement bar has exactly 12 people in it, playing extremely reasonable music. Nevertheless, your neighbor — a retired English professor — has called campus security. Again.*
> - Shut it down (lose party progress, reduce Heat)
> - Turn it up (Heat +10, but party fun doubles for remaining time)
> - Send a pledge to apologize with cookies (50% chance it works, 50% chance the pledge says something stupid)

**"The Sorority President"**
> *The president of Alpha Phi Lambda approaches your frat president at the library. She wants to "discuss a potential mixer." Your frat president is sweating visibly.*
> - Play it cool (standard mixer negotiation)
> - Go all out (promise an amazing theme — if you deliver, huge Social Capital. If you don't, embarrassment.)
> - Suggest a joint philanthropy event instead (less exciting but builds long-term relationship)

**"Das Klub Returns"**
> *One of your brothers found a fog machine, 200 feet of Christmas lights, and a techno CD burned by a guy named "DJ Schnitzel." He wants to turn your basement into Das Klub.*
> - Let him do it (Theme party bonus, but requires 2 turns of setup and the fog machine has a 20% chance of setting off the fire alarm)
> - Scale it back (smaller version, fewer risks, less reward)
> - Redirect his energy ("How about you DJ the next regular party instead?" — small bonus, no risk)

**"The Sledgehammer Incident"**
> *It's Redneck Party night. Someone brought a 1987 Buick LeSabre for the traditional car-smashing. The pledges are very excited. The car is in your front yard. The Dean drives past your house every morning.*
> - Smash it (incredible party moment, +Prestige, +Heat, pray the Dean doesn't see)
> - Move it to the off-campus house first (costs 1 AP but safe from the Dean)
> - "We're doing cornhole instead this year" (safe, boring, brothers are disappointed: -Brotherhood)

---

## 10. Tone & Writing Guide

### The Voice
The game's narrator is an **omniscient, slightly sarcastic observer** — like the narrator from *The Stanley Parable* or *Arrested Development* crossed with a Sierra adventure game. They find everything happening mildly absurd but also kind of endearing.

### Humor Principles
1. **Punch up and sideways, not down.** Make fun of frat culture's absurdities, not individuals. The humor comes from the ridiculousness of the situations, not cruelty.
2. **Self-aware.** The game knows it's about frats. Characters occasionally acknowledge how ridiculous everything is.
3. **Consequences are funny.** The funniest moments come from bad decisions playing out. The Dean's increasingly exasperated responses. The pledge who takes everything too literally. The prank war that escalates beyond all reason.
4. **Specific > generic.** "He showed up in his dad's Tahoe with a case of Natural Light and a Dave Matthews bootleg CD" is funnier than "he seemed like a typical frat guy."
5. **Earned crudeness.** The crude humor lands better when it emerges from situations rather than being grafted on. A party that goes off the rails is funny. Gross-out humor for its own sake is lazy.

### Reference Touchstones
- **Sierra games** (Space Quest, Leisure Suit Larry): Descriptive narration, death/failure as comedy, absurd puzzle logic
- **Arrested Development**: Self-aware narration, running jokes, dramatic irony
- **Old School / Animal House**: The spirit of the thing — chaotic, consequence-filled college comedy
- **Civilization**: "One more turn" addictiveness, meaningful choices between competing priorities

---

## 11. Early 2000s Flavor (Ambient, Not Forced)

The era comes through in **background details** rather than heavy-handed references:
- Parties have burned CDs, not Spotify playlists
- Communication is via AIM away messages and word of mouth, not group chats
- Fashion: polos with popped collars, Croakies, Rainbow flip-flops, Nalgene bottles
- No smartphones — if something embarrassing happens at a party, it's just a memory, not a viral video
- The campus newspaper is how scandals spread, not social media
- Cars in the parking lot: Jeep Wranglers, Tahoes, hand-me-down BMWs

---

## 12. Game Balance & Strategic Depth

This is the section that makes The Row a *real strategy game* and not just a funny theme pasted on dice rolls. Every system is designed around **meaningful tradeoffs** — there should never be an obvious "right move." The best players will win by reading the board state and adapting, not by memorizing a build order.

### 12A. Core Balance Philosophy

**Three pillars of balance:**

1. **No dominant strategy.** If every player always does the same thing, the game is broken. Every action should have an opportunity cost that makes you genuinely weigh alternatives.
2. **Every faction can win every way.** Each frat archetype has natural affinities for 1-2 victory types, but deliberate play should let any faction pursue any victory. Abilities are *advantages*, not *requirements*.
3. **Tight economy, loose tactics.** Resources should always feel scarce — you can never do everything you want. But *how* you spend those scarce resources should offer many viable paths.

### 12B. The Action Economy (AP Budget)

This is the single most important balance lever in the game.

**AP per game:** With 20 turns and 3-5 AP per turn, a player gets **roughly 70-80 total actions** across an entire game. With 11+ possible action types, this means you'll only do about 40-50% of what you'd ideally want to do. That scarcity is what creates strategy.

**AP scaling with Brotherhood:**
| Brotherhood Level | AP Per Turn |
|---|---|
| 0-20 (Fractured) | 3 AP |
| 21-50 (Solid) | 4 AP |
| 51-80 (Tight) | 4 AP + 1 bonus AP every other turn |
| 81-100 (Legendary) | 5 AP |

This means investing in Brotherhood early pays dividends all game — but spending AP on Brotherhood-building means NOT spending it on parties, recruitment, or expansion. That's the tension.

**AP costs should prevent "doing everything":**
- Basic actions: 1 AP (study hours, scout, fundraise, basic party, prank)
- Medium actions: 2 AP (theme party, mixer request, acquire off-campus house, Challenge Week pledge activity)
- Major actions: 3 AP (Rager, formal, major IFC campaign push)

At 4 AP per turn, you can do one major action + one basic, OR four basics, OR two mediums. Never everything. Every turn is a genuine choice.

### 12C. Faction Balance Matrix

Every frat should be **viable but asymmetric**. Here's how each faction maps to each victory type (1-5 scale, where 3 = neutral, 5 = strong natural fit, 1 = uphill battle):

| Faction | Social Supremacy | Party Legends | Campus Kings | Greek Unity | Against All Odds |
|---|---|---|---|---|---|
| **Sigma Sterling** (Gentlemen) | 5 | 2 | 4 | 3 | 3 |
| **Rho Delta** (Animals) | 3 | 5 | 1 | 2 | 1 |
| **Theta Kappa** (Jocks) | 3 | 3 | 2 | 4 | 2 |
| **Phi Omicron** (Pretty Boys) | 4 | 3 | 2 | 5 | 2 |
| **Nu Tau** (Schemers) | 3 | 2 | 5 | 3 | 3 |
| **Omega Psi** (Nerds) | 2 | 1 | 3 | 2 | 5 |
| **Zeta Iota** (Wildcards) | 3 | 4 | 2 | 2 | 3 |
| **Kappa Rho** (Bruisers) | 2 | 3 | 2 | 1 | 2 |

**Key balance principle:** No faction should be below 1 in any category (meaning it's *very hard* but not impossible). The Bruisers going for Greek Unity (their lowest) should still have a path — it's just the hardest run. This is where replayability lives: "Can I win Against All Odds with the Animals?" becomes a compelling challenge.

**Kappa Rho balance note:** The Bruisers look weakest on paper (lots of 2s). Their hidden strength is **consistency** — Intimidation Factor means their plans rarely get disrupted, and maximum pledge loyalty means their Brotherhood climbs fast, giving them more AP. They're the "steady hand" faction. Not flashy, but hard to knock off course.

### 12D. Resource Economy Numbers

Here are the baseline economy numbers. All numbers are per turn unless noted.

**Funding ($):**
- **Income:** Base dues = $15/turn. Each brother contributes based on Wealth stat (avg $2-5 each). A frat with 15 brothers and decent Wealth generates ~$45-60/turn.
- **Costs:** Off-campus house rent = $10-20/turn each. Basement party = $10-30. Theme party = $30-60. Rager = $50-80. Formal = $80-120. Upgrades = $30-100 one-time.
- **The squeeze:** A frat running one off-campus house and throwing a weekly party is spending ~$40-80/turn against ~$50/turn income. You're always on the edge. This means alumni fundraising and smart spending genuinely matter — you can't just autopilot.

**Prestige (★):**
- Gained from: successful parties (1-10★ depending on quality), Greek Week placement (5-20★), sorority mixer success (2-5★), Fancy Dress (10-30★), Homecoming (5-15★)
- Lost from: failed parties (-2-5★), scandals (-5-15★), academic probation (-10★), losing a prank war (-3★)
- Typical winning score: 80-120★ for Social Supremacy victory
- **Prestige is public** — all players can see rival frat prestige. This creates interesting dynamics: do you try to quietly build, or make a big early splash?

**Social Capital (🤝):**
- Scale: 0-100
- Gained from: successful events (+3-8), sorority relationships (+2-5/turn from active partnerships), campus involvement (+2-3)
- Spent on: requesting mixers (5-15), brokering alliances (10-20), recruiting top-tier pledges (5-10 to "sweeten" a bid)
- **Social Capital is a spend-to-earn resource.** You spend it to do things that generate Prestige. The question is always: invest now or save for a big moment?

**Brotherhood (🤜):**
- Scale: 0-100
- Gained from: pledge bonding activities (+5-15), shared victories (+3-5), traditions (small passive gain), successful challenge weeks (+10-20)
- Lost from: scandals (-5-10), brothers expelled (-5), infighting events (-3-5), betraying allies (-5)
- **Brotherhood is the "engine" stat.** It doesn't score points directly, but it drives everything: AP generation, party quality (brothers who like each other throw better parties), crisis resilience, pledge retention.
- **Key balance insight:** Brotherhood is most efficiently built during the pledge process (Turns 3-9) but spending AP on pledge activities during that window means less AP for parties and expansion. Front-loading Brotherhood sacrifices early prestige but sets up a strong late game.

**GPA (📚):**
- Scale: 1.0-4.0
- Starts at: 2.8 (adjusted by faction and recruit quality)
- Each turn: drifts toward 2.5 naturally (partying takes a toll). Study Hours halt drift and add +0.1. Smart recruits add passive GPA.
- **Thresholds:**
  - Below 2.0: Academic probation. Lose 1 brother (expelled), -10★ Prestige, can't rush next cycle.
  - 2.0-2.5: Warning zone. Dean pays attention. Study hours cost double Heat reduction.
  - 2.5-3.0: Safe. No bonuses or penalties.
  - 3.0-3.5: Dean's List bonus. +3★ Prestige/turn. Alumni impressed.
  - 3.5+: Exceptional. +5★ Prestige/turn. Required for Against All Odds victory.

**Heat (🔥):**
- Scale: 0-100
- Gained from: parties (2-15 per party depending on type/venue), hazing activities (5-20), pranks gone wrong (5-10), noise complaints (3-5), random events (variable)
- Reduced by: study hours (-3), community service action (-5), time (natural decay of -2/turn), Dean meeting compliance (-10)
- **Heat is the "risk currency."** The fun stuff generates Heat. Safe stuff reduces it. The entire tension of the game is dancing on that line.

### 12E. Catch-Up Mechanics (Anti-Snowball)

Runaway leaders kill strategy games. Here's how The Row prevents it:

1. **Tall Poppy Syndrome:** The highest-Prestige frat becomes a **target**. AI rivals are more likely to prank you, the Dean watches you more closely (Heat generates 25% faster), and sororities become "harder to impress" (they expect more from the top frat). Being #1 is a crown that comes with thorns.

2. **Heat Accumulation Curve:** Heat builds *faster* the more active you are. Your 5th party of the semester generates more Heat than your 1st. This naturally throttles aggressive expansion.

3. **The Underdog Bonus:** Frats ranked 5th-8th in Prestige get a small Social Capital bonus each turn (+2). The narrative: "People root for the underdog." This gives trailing frats more options without feeling like a handout.

4. **Event Equalizers:** Major events (Homecoming, Greek Week, Fancy Dress) are big enough to shift standings significantly. A frat that's been building quietly can make a big move during Fancy Dress Weekend and leap multiple spots. The game should feel like it's "still anyone's game" until Turn 17-18.

5. **Alliance Dogpiling:** The AI should naturally form temporary alliances against the leader. If one frat is dominant, others coordinate pranks and compete harder for the same sororities. This mimics real social dynamics — everyone resents the top frat.

6. **Brotherhood Ceiling Effects:** Once Brotherhood hits 80+, further gains are minimal. A frat that went all-in on Brotherhood early will plateau while others catch up on AP generation. This rewards balanced play over min-maxing one stat.

### 12F. Tempo & Strategic Archetypes

Like any good strategy game, The Row should support multiple **pacing strategies:**

**The Early Rusher:**
- Spend big on Rush. Get the best pledges. Skip Brotherhood-building and throw parties immediately.
- **Strengths:** Early prestige lead, momentum, best pledges locked up before rivals can bid.
- **Weaknesses:** Low Brotherhood means fewer AP mid-game. Pledges may not be loyal. Heat accumulates fast. Vulnerable to Tall Poppy Syndrome.

**The Builder:**
- Invest heavily in Brotherhood and house upgrades during Fall. Accept mediocre prestige early.
- **Strengths:** By mid-game, you have 5 AP/turn and great infrastructure. Your parties are consistently better because Brotherhood is high. You peak at the right time (Fancy Dress).
- **Weaknesses:** Rival frats grab the best sorority partnerships and social capital early. You might be playing catch-up on prestige if someone runs away with it.

**The Schemer:**
- Focus on campus politics, alliances, and information. Let others throw the parties; you pull the strings.
- **Strengths:** IFC control gives you rule-bending advantages. Alliances provide safety. Intel lets you dodge problems. Strong path to Campus Kings victory.
- **Weaknesses:** Low party output means less prestige. Sororities aren't impressed by politicians. Can feel "slow" if rivals are having all the fun.

**The Gambler:**
- Lean into high-risk, high-reward actions. Ragers, Challenge Week hazing, big pranks.
- **Strengths:** Highest ceiling in the game. When it works, you're a legend. Natural fit for Party Legends victory.
- **Weaknesses:** One bad roll and you're on probation. Inconsistent. Requires good Heat management to avoid charter review.

**The Diplomat:**
- Maximize sorority relationships and inter-frat alliances. Be everyone's friend.
- **Strengths:** Steady Social Capital income. Great mixers. Multiple sorority partnerships. Natural fit for Greek Unity victory.
- **Weaknesses:** Hard to generate big Prestige moments. Can get backstabbed by "allies." Requires constant maintenance.

All five archetypes should be viable in a given game. The best players will read the board state and **shift between archetypes** as conditions change — just like adjusting strategy mid-game in Civ.

### 12G. AI Rival Behavior

AI-controlled rival frats need to feel like they have personalities, not just optimal algorithms.

**AI Personality System:**
Each AI frat plays according to its archetype with some randomness:
- **Sigma Sterling AI:** Conservative, prestige-focused. Rarely throws risky parties. Invests in alumni. Will form alliances with other "respectable" frats.
- **Rho Delta AI:** Aggressive partier. Throws parties almost every turn. Frequently in trouble with the Dean. Entertaining to watch.
- **Theta Kappa AI:** Balanced but competitive. Will always go hard on Greek Week. Gets aggressive during competitions.
- **Phi Omicron AI:** Sorority-focused. Will aggressively pursue mixer relationships. Pranks you if you're dating "their" sorority.
- **Nu Tau AI:** Scheming. Unpredictable alliances. Will try to get IFC control. Most likely to backstab.
- **Omega Psi AI:** Passive early, builds quietly. Becomes a serious contender in late game. Rarely aggressive.
- **Zeta Iota AI:** Chaotic. Does random things. Sometimes brilliant, sometimes disastrous. Keeps the game unpredictable.
- **Kappa Rho AI:** Aggressive on pranks, loyal to allies. Won't backstab, but will escalate if provoked.

**Difficulty scaling:** Rather than making AI "smarter" at higher difficulties, give them resource bonuses and personality amplification. A "hard" Rho Delta doesn't play differently — they just party *even harder* and somehow survive. This keeps AI personality intact across difficulties.

### 12H. The Pledge Background System (Social Dynamics)

Each pledge in the recruitment pool has a **background** that reflects the real social dynamics at schools like Colonnade College:

**Southern Legacy (~40% of pledge pool)**
- Kids from old southern families. Dad went to Colonnade, granddad went to Colonnade.
- **Stats:** High Wealth ($4-5/turn dues), High Social Skill, Moderate Academics, High "Connections" (passive prestige gain)
- **Trait:** "Family Name" — if they drop or get expelled, their family's alumni donations to YOUR frat dry up. Handle with care.
- **Vibe:** Shows up to Rush in a blazer. Knows the school fight song already. Already has friends on campus from summer house on the Outer Banks.

**Northeast Prep (~35% of pledge pool)**
- Kids from Connecticut, New Jersey, New York. Boarding school background. Different cultural energy.
- **Stats:** High Academics, Moderate-High Wealth, Moderate Social Skill, Low Connections (new to the southern social scene)
- **Trait:** "Fish Out of Water" — during their first semester, they contribute less to parties (still learning the culture), but by spring they've adapted and contribute bonus Social Skill. The slow burn pays off.
- **Vibe:** Shows up to Rush in a Patagonia vest asking if there's a squash team. Mildly confused by all the bourbon.

**Grit Kids (~15% of pledge pool)**
- Middle-class kids who got in on merit/scholarships. Often the most genuinely interesting people.
- **Stats:** Moderate Wealth ($2-3/turn dues), High Academics, Variable Social Skill, Very High Loyalty
- **Trait:** "Real Ones" — they generate more Brotherhood per bonding activity than other backgrounds. Their presence makes the frat feel more authentic, which sororities notice (+1 Social Capital when 2+ Grit Kids are in the frat).
- **Vibe:** Shows up to Rush in a polo that's slightly the wrong brand. Doesn't know all the social codes. But by sophomore year, everyone agrees they're the heart of the pledge class.

**Wildcard (~10% of pledge pool)**
- Doesn't fit neatly into any category. International students, transfer students, the dean's nephew, the guy who's 25 and nobody asks why.
- **Stats:** Highly variable. Could be amazing. Could be a disaster.
- **Trait:** "X Factor" — each Wildcard has a unique trait that's hidden until after Rush. Could be "Actually a DJ" (+party quality), "Connected to the Governor" (+Prestige), or "Pyromaniac" (increases Heat by 3/turn just by existing).

**Balance implications of the background system:**
- **Southern Legacies** are the "safe pick" — good stats, good dues, but you become dependent on alumni connections and vulnerable to the "Family Name" risk.
- **Northeast Preps** are the "investment" — slower start, stronger finish, and they bring academic bonuses that protect your GPA.
- **Grit Kids** are the "Brotherhood pick" — lower dues hurt your wallet, but they make your frat more cohesive and authentic. Sororities respect the authenticity. A frat full of only rich kids feels hollow.
- **Wildcards** are the "gamble" — for players who want variance.

The strategic question during Rush becomes: do you take the rich legacy who pays big dues, or the scrappy kid who'll be the soul of your pledge class? Do you diversify, or go all-in on one type? Different factions naturally lean toward different compositions, but the BEST approach is almost always a mix — which mirrors reality.

### 12I. The Prestige Scoring Engine

To prevent any single strategy from dominating, Prestige comes from **diverse sources** with **diminishing returns within categories:**

| Source Category | First Instance | 2nd | 3rd | 4th+ |
|---|---|---|---|---|
| Successful party | +5★ | +4★ | +3★ | +2★ |
| Sorority mixer | +4★ | +3★ | +2★ | +1★ |
| Greek Week event win | +5★ | +5★ | +5★ | +5★ |
| Successful prank | +3★ | +2★ | +1★ | +1★ |
| GPA bonus (per turn above 3.0) | +3★ | — | — | — |
| IFC position (per turn held) | +2★ | — | — | — |
| Off-campus house (per turn owned) | +1★ | +1★ | +1★ | +1★ |

**Why diminishing returns matter:** This prevents the "party spam" strategy from dominating. Your 1st successful party is worth +5★. Your 10th is only worth +2★. Meanwhile, a player who threw 4 parties (+14★) AND won 2 Greek Week events (+10★) AND had a great mixer (+4★) earns 28★ from more diverse play. **The game rewards versatility.**

The exception is Greek Week — it doesn't diminish because it's a fixed, competitive event (not something you can spam). Off-campus houses also don't diminish because the ongoing rent cost provides natural balance.

### 12J. The "Danger Zone" Mechanic

To create **tension and drama in every game**, the last 4 turns (17-20) should feel urgent and swingy:

**Fancy Dress Multiplier (Turns 17-18):**
All Prestige earned during Fancy Dress Weekend is worth **1.5x**. This means a frat that saves resources for a massive Fancy Dress push can close a 15-20★ gap. The leading frat can't relax.

**Endgame Heat Spike:**
Heat decays 50% slower in the last 4 turns (everyone's partying harder, the Dean is watching). This makes late-game risk management more tense.

**Last Call Events (Turn 19-20):**
Special "last call" random events fire that are higher-stakes than normal — bigger rewards, bigger consequences. The game should end with a bang, not a whimper.

**Victory Condition "Locks":**
Starting Turn 18, the game shows you how close each frat is to each victory condition. This creates a "final stretch" feeling where you can see who's about to win and decide whether to pivot your strategy to block them.

### 12K. Replayability Levers

Beyond faction variety, here's what makes each game feel different:

1. **Randomized pledge pool:** Different freshmen each game = different roster-building decisions
2. **Randomized off-campus house placement:** The best houses aren't always in the same spots
3. **AI personality variance:** Each AI frat has 2-3 behavioral variants (e.g., Rho Delta can be "functional chaos" or "actual dumpster fire")
4. **Event deck shuffling:** Random events are drawn from a large deck, so you'll see different events each game
5. **Sorority preference shifts:** What each sorority values shifts slightly each game, so the "best" mixer partner changes
6. **Map modifiers:** Optional game modifiers like "Dry Campus" (no off-campus houses), "IFC Crackdown" (Heat generates faster), "Rush Week Extended" (3 rush turns instead of 2), "Fancy Dress Canceled" (no multiplier event — changes everything)
7. **Faction-specific challenge runs:** "Win as Omega Psi with Party Legends victory" is a very different game than "Win as Rho Delta with Against All Odds"

---

## 13. Tone: The King of the Hill Principle

The most important thing to get right about The Row is this: **underneath all the absurdity, these are fundamentally good people.**

King of the Hill is the tonal north star. Hank Hill is narrow-minded and often wrong, but he genuinely loves his family and tries to do right. Bobby is weird but earnest. Even Dale — conspiracy theorist, paranoid, probably not the father of his own son — is a loyal friend who would do anything for his buddies. The show is hilarious because the *characters* are ridiculous, not because it's mocking the people it portrays.

**The Row should feel the same way.** These frat brothers are sometimes dumb, sometimes reckless, sometimes absurdly out of touch — but they genuinely care about each other. The pledge who gets hazed and the brother who hazed him end up as best friends at the formal. The frat that gets put on probation bands together and comes back stronger. The rivalry that seemed vicious dissolves into mutual respect after Greek Week.

**Specific tone guidelines:**

- **Brotherhood moments:** Periodically, the game should surface **genuine brotherhood moments** — a brother helps another study for a test, the frat rallies around someone going through a hard time, an alumni mentors a pledge. These aren't just flavor — they're Brotherhood stat boosts. *Goodness is mechanically rewarded.*

- **The Dean isn't evil.** The Dean is an antagonist in the game sense, but they're actually just trying to keep students safe. Occasionally, the Dean should be *right* — and the game should acknowledge it. When Heat gets too high, the Dean's intervention should sometimes feel like a reasonable response to genuinely bad behavior.

- **Rivals are people too.** The frat you're pranking has their own story. Occasionally, events should show rival frats being decent — helping at a community event, supporting a brother in trouble. This makes the rivalry feel like friendly competition, not warfare.

- **No villains.** In King of the Hill, even the antagonists (Kahn, Cotton, Lucky) are complex and sympathetic. The Row shouldn't have real villains — just different people with different values bumping into each other in funny ways.

- **The legacy angle:** At the end of the game, regardless of victory condition, there should be an **epilogue** that fast-forwards a few years. "The pledge class of '03 went on to..." This humanizes everyone and reminds the player that these were real friendships being formed amidst all the chaos.

---

## 14. Technical Direction (High Level)


- **Platform:** Web browser (HTML5)
- **View:** Isometric pixel art or stylized 2D
- **Engine:** TBD in implementation phase (likely Phaser.js, PixiJS, or similar web game framework)
- **Art style:** Charming pixel art or clean vector isometric — the campus should look inviting and detailed
- **Sound:** Lo-fi soundtrack with era-appropriate party music snippets. Sound effects for events (cheering, police sirens, glass breaking, "CHUG CHUG CHUG")

---

## 15. Open Questions for Future Design Rounds

- **Exact pledge stats and recruitment balancing** — needs playtesting
- **Party simulation math** — how exactly do stats combine to produce outcomes?
- **AI behavior** — how aggressive/strategic should rival frats be?
- **Unlockables/replayability** — should there be meta-progression between games?
- **Tutorial/onboarding** — how do we teach the mechanics without killing the humor?
- **LMI (Lexford Military Institute) interactions** — the VMI equivalent next door could be a source of great events (cadets crashing parties, cross-campus rivalries)
- **Townies** — the non-Greek students and Lexford residents as a faction/system?
- **Detailed sorority preference/relationship math**

## Related Notes
- [[14b-aesthetic-reference-library]] - grounds this project decision in Matt's isometric context
- [[ai-project-prioritization-tournament-exec]] - relates through determine discussed in this note
- [[28-information-diet]] - grounds this project decision in Matt's activity context
- [[29-technology-ecosystem]] - grounds this project decision in Matt's personal context
- [[ai-project-prioritization-tournament]] - relates through question discussed in this note

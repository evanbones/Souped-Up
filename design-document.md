# Souped Up!

## Core Concept
A deck-building roguelike where you're a chef serving increasingly demanding customers by crafting soups. Success depends on balancing **Flavour** (additive) and **Mult** (multiplicative) to meet satisfaction thresholds. Numbers scale from hundreds to millions across 5 restaurant shifts.

---

## Core Mechanics

### Satisfaction Formula
```
Satisfaction = (Base Flavour + Flavour Bonuses) × (Base Mult × Mult Multipliers) × Relic Multipliers

Where:
• Base Flavour = Sum of all ingredient Flavour values
• Flavour Bonuses = Additional Flavour from combos/effects
• Base Mult = Sum of all +Mult sources (starts at 1)
• Mult Multipliers = Product of all ×Mult effects (e.g., ×2 × ×1.5 = ×3)
• Relic Multipliers = Product of permanent relic effects
```

**Example:**
- Flavour: 300 + 100 (combo) = 400
- Mult: 10 + 5 (technique) = 15
- Mult Multipliers: ×2 (technique) × ×1.5 (relic) = ×3
- Final: 400 × (15 × 3) = 400 × 45 = **18,000 Satisfaction**

---

## Soup Types (5 Core Types)

Soup type determined by ingredients played **that course** (not cumulative). Each provides passive bonuses.

| Soup Type | Requirements | Base Stats | Passive Ability |
|-----------|-------------|------------|-----------------|
| **Broth** | 3+ vegetables, no meat | 30F, ×1.5 | Each vegetable gives all ingredients +8F |
| **Stew** | 2+ meat, 2+ vegetables | 60F, ×2 | Each meat adds +0.5× to Mult multiplier |
| **Bisque** | 1+ seafood, 1+ dairy | 50F, ×2.5 | Dairy ingredients score ×3 stats |
| **Curry** | 2+ spices, 1+ protein | 50F, ×3 | +0.5× Mult per unique spice type |
| **Chowder** | 2+ seafood, 2+ vegetables | 70F, ×2 | Seafood gives all ingredients +15F |

**Slop** (no match): 20F, ×1 Mult, no passive

**Leveling Soup Types** (in shops):
- Cost: $50 × current level (max 5 levels)
- Effect: +20F and +0.5× Mult per level

---

## Game Loop

### Run Structure
**5 Restaurant Shifts → 3 Courses Per Shift → Final Boss**

Each shift is one continuous service with **3 courses**:
- **Appetizer** (Course 1): Lightest threshold
- **Main Course** (Course 2): Medium threshold  
- **Dessert** (Course 3): Heaviest threshold

**Between Shifts**: Choose 1 of 3 options from carouseling order tickets:
- **New Customer** - Continue to next shift
- **Shop** - Buy ingredients, techniques, relics
- **Break Room** - Upgrade ingredient OR remove ingredient

---

### Course Structure (Combat Encounter)

**PREP PHASE** (Untimed - Plan Your Strategy)
1. View shift's **total satisfaction threshold**
2. See customer's special rules/modifiers
3. Optional prep actions (cost energy):
   - **Mulligan** (1 energy): Shuffle deck, redraw
   - **Pre-Season** (1 energy): Start with +5 to base Mult

**COOKING PHASE** (3 Courses)

Each course:
1. **Draw 8 ingredients** from your pantry onto conveyor belt
2. **Play ingredients** into soup pot one at a time
   - Each ingredient immediately adds its stats
   - Soup type determined by current ingredients
   - Combos trigger automatically when conditions met
3. **Mid-Course Check** (at 50% threshold):
   - Customer gives feedback
   - Optional bonus objective appears (e.g., "Add seafood for +$20")
4. **Press "Serve"** when ready
5. Unused ingredients discarded, all ingredients return to pantry after shift

**SCORING**
- Calculate: (Total Flavour) × (Base Mult × Mult Multipliers) × Relics
- Satisfaction accumulates across all 3 courses
- If total threshold met: Victory + rewards!
- If not met after course 3: Customer leaves (run ends)

**REWARDS**
- **Money**: $40-80 (based on speed + overkill)
- **Card Choice**: Pick 1 of 3 ingredients/techniques
- **Relic**: Every 3rd shift, choose 1 of 3 relics

---

## Satisfaction Thresholds

| Shift | Regular | Boss |
|-------|---------|------|
| 1 | 1,000 | 2,500 |
| 2 | 5,000 | 12,000 |
| 3 | 25,000 | 60,000 |
| 4 | 120,000 | 300,000 |
| 5 | 600,000 | 1,500,000 |

---

## Ingredients

### Vegetables (Flavour Focus)
| Ingredient | Stats | Rarity |
|------------|-------|--------|
| Carrot | 40F | Common |
| Potato | 45F | Common |
| Onion | 45F | Common |
| Tomato | 50F | Common |
| Celery | 40F | Common |
| Mushroom | 55F | Uncommon |
| Bell Pepper | 45F | Uncommon |
| Corn | 50F | Uncommon |
| Garlic | 35F, +2 | Uncommon (hybrid) |
| Truffle | 100F | Rare |

### Proteins (Flavour Focus)
| Ingredient | Stats | Rarity |
|------------|-------|--------|
| Chicken | 70F | Common |
| Beef | 80F | Common |
| Pork | 75F | Common |
| Fish | 65F | Common |
| Shrimp | 85F | Uncommon |
| Crab | 90F | Uncommon |
| Lamb | 100F | Rare |
| Duck | 110F | Rare |

### Spices (Mult Focus)
| Ingredient | Stats | Rarity |
|------------|-------|--------|
| Black Pepper | 20F, +3 | Common |
| Chili Flakes | 15F, +4 | Common |
| Paprika | 25F, +3 | Common |
| Cumin | 20F, +5 | Uncommon |
| Cayenne | 10F, +8 | Uncommon |
| Ghost Pepper | 5F, +15 | Rare |

### Special Ingredients
| Ingredient | Effect | Rarity |
|------------|--------|--------|
| **Grandma's Stock** | 60F. Permanently gains +10F each time played this run | Uncommon |
| **Salt** | Gain +2 to base Mult for each other ingredient played this course | Common |
| **Butter** | 50F. Next ingredient played gains +40F | Common |
| **Cream** | 60F, ×0.75 Mult multiplier (reduces Mult slightly) | Uncommon |
| **MSG** | Permanently gain +5 to base Mult this shift. Discard 1 random ingredient next course | Uncommon |
| **Truffle Oil** | 120F, ×1.8 Mult multiplier | Rare |

**Upgraded Ingredients** (via shops/rewards):
- Vegetables/Proteins: +30F
- Spices: +5 Mult
- Special: Enhanced effects (Stock +15F, Salt +3 Mult, etc.)

---

## Combo

Combos trigger when specific ingredients are played **in the same course**:

### Basic Combos (Common Ingredients)
1. **Mirepoix** (Carrot + Celery + Onion): +100F, +3 Mult
2. **Aromatics** (Garlic + Onion + any spice): ×1.5 Mult multiplier
3. **Surf & Turf** (Any seafood + Any beef): +120F, +6 Mult

### Advanced Combos (Uncommon+)
4. **Holy Trinity** (Onion + Bell Pepper + Celery): Next 2 ingredients score ×2 stats
5. **Stock Base** (Grandma's Stock + 3+ vegetables): ×1.8 Mult multiplier
6. **Spice Rack** (4+ different spices): ×2 Mult multiplier

### Master Combos (Rare/Build-Defining)
7. **Butcher's Choice** (4+ different proteins): +250F, +12 Mult
8. **Rainbow Medley** (7+ ingredients of different types): ×3 Mult multiplier, +300F

**First Discovery**: When you trigger a combo for the first time, it's added to your Cookbook with fanfare.

---

## Techniques (Active Abilities)

**Energy System:**
- Start with **3 energy** per shift
- Gain **+1 energy per course** (max 6 total)
- Unused energy does NOT carry between shifts

### Basic Techniques (1 Energy)
- **Sauté**: Next ingredient gains +80F
  - *Flavor text*: "A quick sear brings out the natural sweetness."
- **Season**: Add +8 to base Mult
  - *Flavor text*: "Just a pinch more intensity."
- **Taste Test**: Preview next 8 ingredients in deck
  - *Flavor text*: "Know what's coming before the rush."
- **Mise en Place**: Draw 3 extra ingredients this course
  - *Flavor text*: "Everything in its place, ready to cook."

### Advanced Techniques (2 Energy)
- **Flambé**: Gain Spice Intensity ×2 this course
  - *Flavor text*: "Set it ablaze for dramatic effect."
- **Sous Vide**: Set aside 1 ingredient. Next course, it scores ×3 stats
  - *Flavor text*: "Low and slow perfection, worth the wait."
- **Blanch**: Remove all negative modifiers from ingredients in hand
  - *Flavor text*: "A quick dip in boiling water cleanses all."
- **Pressure Cook**: +15 to base Mult, but discard hand at end of course
  - *Flavor text*: "Extreme heat, extreme risk."

### Master Techniques (2 Energy)
- **Chef's Special**: Gain Spice Intensity ×2 to final satisfaction this course
  - *Flavor text*: "Your signature move. Make it count."
- **Perfect Pairing**: If same soup type all 3 courses, gain Spice Intensity ×2.5 on dessert (one-use per shift)
  - *Flavor text*: "Commitment to a vision pays off."
- **Speed Service**: Take a 4th course this shift (one-use per shift)
  - *Flavor text*: "The rush is on. One more chance."

---

## Relics 

Relics appear after Shifts 1, 2, 3, and 4 (choose 1 of 3).

### Tier 1 Relics (Shifts 1-2) - $150
- **Recipe Book**: Draw 10 ingredients first course (instead of 8)
- **Sharp Knives**: +1 Energy per shift
- **Copper Pot**: Start each shift with +8 to base Mult
- **Leftovers**: Retain 1 random ingredient after each course
- **Tasting Spoon**: Taste Test costs 0 energy
- **Golden Ladle**: Gain $10 when you remove an ingredient

### Tier 2 Relics (Shifts 2-3) - $250
- **Quality Control**: Upgraded ingredients score ×1.5 their stats
- **Stock Pot**: Grandma's Stock gains +15F per use (instead of +10F)
- **Spice Rack**: All spices give +4 additional Mult
- **Prep Station**: Upgrade 1 random ingredient at start of each shift
- **Combo Master**: All combos grant +8 additional Mult
- **Second Wind**: If below 60% threshold after course 2, gain +3 energy

### Tier 3 Relics (Shifts 4-5 only) - $400
- **Eternal Flame**: Start each shift with ×(1 + [current shift × 0.5]) Mult multiplier. (Shift 5 = ×3.5)
- **Master Chef's Toque**: Same soup type all 3 courses → ×4 Mult multiplier on dessert
- **Ghost Kitchen**: Don't see ingredients until played. All stats ×1.8
- **Time Dilation**: Each shift has 4 courses instead of 3
- **Chaos Cauldron**: At start of each course, gain ×1 to ×4 random Mult multiplier
- **Perfectionist's Pride**: If you meet threshold with <10% excess, gain ×2 rewards

---

## Economy System

### Money Sources
- **Base Reward**: $30-60 per shift (higher for bosses)
- **Speed Bonus**: Fast courses → +$8-15
- **Overkill Bonus**: Exceed threshold by 50%+ → +$20
- **Combo Bonus**: Trigger 3+ combos in shift → +$15

**Average Run Economy**: $700-1,000 across 5 shifts

### Shop Prices
- **Common ingredient**: $50
- **Uncommon ingredient**: $80
- **Rare ingredient**: $120
- **Technique**: $100
- **Remove ingredient**: $75 (flat cost)
- **Upgrade ingredient**: $60
- **Upgrade soup type**: $50 × level
- **Tier 1 relic**: $150
- **Tier 2 relic**: $250
- **Tier 3 relic**: $400

---

## Customers

### Regular Customers (Shifts 1-4)

**The Brat** (Shifts 1-2)
- *Modifier*: Vegetables score 0F
- *Forces*: Protein/spice builds
- *Threshold*: 1,500
- *Dialogue*: 
  - Start: "Ew, I don't want any gross vegetables!"
  - Mid (40%): "This better not have carrots in it..."
  - Success: "Fine, whatever. It's okay I guess."
  - Failure: "I KNEW you'd try to sneak vegetables in it! I'm telling Mom!"

**Father John** (Shifts 2-3)
- *Modifier*: Ingredients with base Flavour over 80F score 0
- *Forces*: Managing moderation, using common ingredients
- *Threshold*: 8,000
- *Dialogue*:
  - Start: "Gluttony is a sin, my child. Keep it humble."
  - Mid (50%): "Simple pleasures, nothing extravagant."
  - Success: "Blessed are the meek. This is acceptable."
  - Failure: "You have succumbed to excess. Repent!"

**Count Brothula** (Shifts 2-4)
- *Modifier*: Garlic/Onion score 0F
- *Buff*: Tomato/proteins score ×1.5
- *Threshold*: 20,000
- *Dialogue*:
  - Start: "No garlic, or I vill be most displeased..."
  - Mid (50%): "Yesss, the bloody tomatoes, perfect..."
  - Success: "Magnificent! You shall live another night."
  - Failure: "Foolish mortal. I shall drink your blood instead."

**Chad Chazly** (Shifts 3-4)
- *Modifier*: Base Mult cannot exceed 40 (instant loss)
- *Forces*: Pure Flavour scaling
- *Threshold*: 100,000
- *Dialogue*:
  - Start: "Yo bro, keep it mild. I got, like, a weak stomach, haha."
  - Mid (50%): "Yeah dude, this is chill so far."
  - If Mult >40: "BRO! TOO SPICY! I'M OUT!"
  - Success: "Sick bro, that was fire!"
  - Failure: "Nah man, not enough flavor. L."

**The Minimalist** (Shifts 4-5)
- *Modifier*: Max 5 ingredients per course
- *Threshold*: 200,000
- *Dialogue*:
  - Start: "Less is more. Show me restraint."
  - Mid (50%): "Hmm. Interesting choices."
  - If >5 ingredients: "Too cluttered. I'm disappointed."
  - Success: "Perfection through simplicity. Well done."
  - Failure: "You tried to do too much. Shame."

**Senator Dogfood** (Shifts 4-5)
- *Modifier*: Only proteins score (vegetables = 0)
- *Special*: Playing "Bone" ingredient (rare) instantly wins
- *Threshold*: 400,000
- *Dialogue*:
  - Start: "MEAT. BRING ME MEAT."
  - Mid (50%): "MORE MEAT. KEEP GOING."
  - If Bone played: "BONE! YES! GOOD CHEF! HERE'S A MILLION DOLLARS!"
  - Success: "ACCEPTABLE MEAT QUANTITY. YOU MAY LIVE."
  - Failure: "NOT ENOUGH MEAT. YOU'RE FIRED."

### Boss Customers (End of Each Shift)

**Mama Rosa** (Shift 1 Boss)
- *Buff*: Comfort food ingredients (potato, chicken, butter, cream) score ×2
- *Threshold*: 2,500
- *Dialogue*:
  - Start: "Ah, bambino! Make-a me something that reminds me of home!"
  - Mid (40%): "Mmmm, smells like-a Nonna's kitchen..."
  - Mid (70%): "Bellissimo! Just like the old country!"
  - Success: "*wipes tear* Magnifico! You have-a gift!"
  - Failure: "No, no, no! This is-a not how Nonna make it!"

**The Food Critic** (Shift 3 Boss)
- *Modifier*: Must make 3 different soup types (one per course)
- *Threshold*: 60,000
- *Dialogue*:
  - Start: "Show me range. Impress me with variety."
  - Appetizer: "Hmm. Competent. Let's see the next course."
  - Main: "Interesting choice. And for dessert?"
  - If same soup type: "Repetitive. How pedestrian."
  - Success: "... Maybe anyone CAN cook. 4 stars."
  - Failure: "Lackluster execution. 1 star."

**The Speed Demon** (Shift 4 Boss)
- *Modifier*: Each second over 20s per course adds +5,000 to threshold
- *Buff*: Finishing courses under 15s gives ×1.5 Mult multiplier
- *Threshold*: 300,000 (base)
- *Dialogue*:
  - Start: "FAST. I WANT IT FAST. GO GO GO!"
  - Mid-course (10s): "FASTER! TIME IS MONEY!"
  - Mid-course (25s+): "TOO SLOW! THRESHOLD RISING!"
  - Success: "ADEQUATE SPEED. YOU'LL DO."
  - Failure: "TOO SLOW. I'M GOING TO MCDONALD'S."

**Demon Lord Beelzeburger** (Shift 5 Boss)
- *Modifier*: Random ingredient type scores 0 each course (revealed at start of course)
- *Buff*: Spices score ×2
- *Threshold*: 1,500,000
- *Dialogue*:
  - Start: "MORTAL. FEED ME YOUR FINEST... OR PERISH."
  - Course 1: "THIS COURSE: NO VEGETABLES SHALL NOURISH ME."
  - Mid (40%): "PATHETIC. I EXPECTED MORE."
  - Mid (70%): "YESSSSS. MORE SUFFERING. MORE FLAVOR."
  - Success: "YOU HAVE EARNED MY RESPECT, CHEF. TAKE THIS CURSED ARTIFACT."
  - Failure: "INADEQUATE. YOUR SOUL IS MINE." *dramatic Game Over*

---

## Final Boss: God

**Phase 1: "Divine Test"** (0-50% threshold)
- *Modifier*: Only upgraded ingredients score
- *Threshold*: 750,000
- *Dialogue*:
  - Start: "Mortal chef. Show me your mastery of the craft."
  - Mid (25%): "Competent. But can you handle true judgment?"
  - Mid (50%): "Impressive. Now face my wrath."

**Phase 2: "Apocalypse"** (50-100% threshold)
- *Modifier*: All ingredient stats randomized: -20F to +80F, -5 to +10 Mult each time played
- *Threshold*: +750,000 (1,500,000 total)
- *Dialogue*:
  - Start of Phase 2: "CHAOS REIGNS. ADAPT OR PERISH."
  - Mid (75%): "YOU DARE CHALLENGE THE DIVINE?"
  - Mid (90%): "IMPOSSIBLE... YOUR POWER..."
  - Success: "...You have proven yourself worthy. Take your place among legends."
  - Failure: "AS EXPECTED. RETURN TO THE MORTAL REALM."

---

## Starting Chefs

### Prep Cook Jimmy (Default)
- **Deck**: 5 Potato, 3 Carrot, 3 Onion, 2 Chicken, 2 Black Pepper (15 cards)
- **Relic**: None
- **Passive**: None (balanced baseline)

### Chef Rodrigo (Unlock: Beat Shift 3)
- **Deck**: 6 mixed proteins, 3 Garlic, 2 Black Pepper, 2 Salt (13 cards)
- **Relic**: Copper Pot
- **Passive**: Proteins give +15F, vegetables cost $20 less

### Sushi Master Yuki (Unlock: Beat God)
- **Deck**: 4 Fish, 3 Shrimp, 2 Garlic, 2 Cumin (11 cards - smaller deck)
- **Relic**: Sharp Knives
- **Passive**: Upgraded ingredients score ×2 (instead of ×1.5)

---

## Progression Systems

### Cookbook
- Tracks discovered ingredients, combos, relics
- Unlocked entries show stats, flavour text (ha), and synergies

### Achievements
- **Five-Star Service**: Beat God
- **Speed Demon**: Win a shift in under 3 minutes
- **Spice Lord**: Reach 100 base Mult in one course
- **Combo King**: Trigger 5 combos in one shift
- **Minimalist Chef**: Win with ≤12 cards in deck

### Endless Mode (Unlock: Beat God)
- Infinite scaling shifts
- Thresholds increase 50% each shift
- Leaderboards for highest shift reached

---

## Balance Philosophy

### Scaling Curve (Balatro-Inspired)

**Shift 1-2** (Tutorial/Foundation)
- Linear growth: 100s → 1,000s
- Learn combos, soup types, basic synergies
- Forgiving thresholds

**Shift 3** (First Wall)
- Exponential begins: 10,000s → 50,000s
- Requires 2-3 synergies + upgraded ingredients
- Build commitment matters

**Shift 4-5** (Explosive Scaling)
- Full exponential: 100,000s → 1,000,000s
- All systems firing: combos + relics + techniques
- Perfect execution required

---

## Anti-Frustration Features

- **View Pantry**: Always visible, shows remaining ingredients
- **Pause & Cookbook**: Reference combos mid-shift without time penalty
- **Tutorial**: First shift has tooltips and guidance
- **Save & Quit**: Resume mid-run anytime

---

## Visual & Audio Design

### Visual Style
- **Pixel art**: Thick black outlines, vibrant colors
- **Color coding**: Green (vegetables), Red (proteins), Orange (spices), Purple (special)
- **Satisfaction bar**: Smooth gradient red → yellow → green
- **Scoring animations**: Numbers burst and scale dramatically
- **Soup pot**: Bubbles, steams, changes color based on soup type

### Audio Design
- **Shift 1-2**: Lo-fi jazz, chill (70-90 BPM)
- **Shift 3**: Trip-hop, more energy (100-120 BPM)
- **Shift 4**: IDM/breakbeat (130-150 BPM)
- **Shift 5**: Intense breakcore (160-180+ BPM)
- **God Fight**: Orchestral + electronic fusion
- **SFX**: Sizzles, dings, whooshes for big multipliers

---

## Core Design Pillars

1. **Explosive Scaling**: Numbers go from 1,000 → 1,500,000
2. **Strategic Depth**: Multiple viable builds (Flavour-focus, Mult-focus, combo-focus)
3. **Satisfying Discovery**: Finding combos feels rewarding
4. **Tight Gameplay Loop**: 20-30 minute runs
5. **Easy to Learn, Hard to Master**: Simple rules, deep strategy

---

## Win Conditions

### Victory
- Defeat God (three-phase fight, 1,500,000 total threshold)
- Unlock: Sushi Master Yuki, Endless Mode, Achievements

### Defeat
- Fail to meet any shift's threshold
- Restart from Shift 1 (full roguelike)

### Scoring
- **Speed Score**: Time bonuses
- **High Score**: Highest single course satisfaction
- **Efficiency**: Fewest ingredients used
- **Leaderboards**: Per chef, per shift

---

*Ascend the kitchen. Please the gods. Serve the soup.*

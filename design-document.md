# Souped Up!

## Core Concept
A deck-building roguelike where players are chefs serving increasingly demanding customers by crafting soups from ingredients. Success depends on balancing **Flavour** (quality) and **Kick** (spice/intensity) to meet satisfaction thresholds.

---

## Core Mechanics

### Satisfaction Formula
```
Satisfaction = Flavour × Kick
```

**Key Implications:**
- Both stats must be present to score (zero in either = zero satisfaction)
- Balanced builds (10F × 10K = 100) often outperform specialist builds (20F × 5K = 100)
- Heat system provides temporary Kick boosts
- Relics can modify this formula for different playstyles

### Base Stats
- **Base Kick**: Always starts at 1 (minimum) per encounter
- **Flavour**: Starts at 0, built entirely from ingredients
- **Heat**: Bonus Kick that decays by 1 each round (unless modified by relics)

---

## Game Loop

### Run Structure
**5 Days → 15-20 Total Encounters → Final Boss**

Each day consists of:
- **3 Regular Customers** (standard encounters)
- **1 Elite Customer** (harder, better rewards)
- **1 Boss Customer** (day finale)

Between encounters, players navigate a branching map with node types:
- **Customer** (standard combat)
- **Elite Customer** (2× rewards, 1.5× difficulty)
- **Shop** (buy ingredients, techniques, relics)
- **Rest Site** (upgrade OR remove ingredient)
- **Random Event** (risk/reward scenarios)

### Turn Structure (Customer Encounter)

**1. PREP PHASE** (10 seconds)
- View satisfaction threshold for this customer
- See customer's debuffs/preferences
- Preview first 3 ingredients on conveyor belt
- Plan strategy

**2. COOKING PHASE** (Repeats for 3-5 rounds)
- Draw 8 random ingredients from your deck onto conveyor belt
- Hand limit: 5 ingredients (can hold from belt)
- Choose ingredients to add to soup OR trash
- Each ingredient added immediately scores its stats
- Unused ingredients on belt are discarded (no refund)
- Round ends when you press "Serve Round"

**3. SCORING**
- Current Flavour × Current Kick = Round Satisfaction
- Satisfaction bar fills toward threshold
- Heat decreases by 1
- If threshold met: Victory (gain rewards)
- If threshold not met after all rounds: Customer leaves angry (lose run)

**4. REWARDS** (After victory)
Choose 1 of 3 rewards:
- New ingredient (choice of 3)
- New technique (choice of 3)
- $30
- Relic (rare, replaces ingredient/money option)

---

## Scoring & Balance

### Satisfaction Thresholds

**Formula**: `Threshold = Base × Day Multiplier × Elite Multiplier × Streak Bonus`

| Day | Regular | Elite | Boss |
|-----|---------|-------|------|
| 1 | 150 | 250 | 400 |
| 2 | 300 | 500 | 800 |
| 3 | 600 | 1000 | 1600 |
| 4 | 1200 | 2000 | 3200 |
| 5 | 2400 | 4000 | 6500 |

**Streak Bonus**: Each consecutive satisfied customer in a day adds +10% to next threshold (resets on day change)

### Rounds Per Encounter
- **Regular Customers**: 3 rounds
- **Elite Customers**: 4 rounds
- **Boss Customers**: 5 rounds

Players must reach threshold within these rounds or lose.

### Base Ingredient Values

**Vegetables** (Score 4-6 Flavour, 0 Kick)
- Carrot: 4F
- Potato: 5F
- Onion: 5F
- Tomato: 6F
- Celery: 4F
- Mushroom: 6F
- Bell Pepper: 5F

**Meats** (Score 5-8 Flavour, 0 Kick)
- Chicken: 6F
- Beef: 7F
- Pork: 6F
- Fish: 5F
- Shrimp: 8F

**Spices** (Flavour + Heat/Kick)
- Chili Pepper: 5F, +3 Heat
- Hot Sauce: 0F, +5 Heat
- Black Pepper: 3F, +2 Heat
- Cayenne: 2F, +4 Heat
- Ghost Pepper: 1F, +8 Heat

**Special Ingredients**
- Grandma's Stock: 5F, gains +5F permanently each time used this run
- Salt: 2F, +1K permanently to ALL ingredients in soup this round
- Butter: 4F, next ingredient scores +3F
- Cream: 6F, reduces Kick by 2 (minimum 1)
- MSG: Doubles Flavour this round, gain "Guilt" debuff (trash 1 ingredient next draw)

**Upgraded Values**: All base ingredients gain +3F/+2K when upgraded

---

## Techniques (Active Abilities)

Techniques cost **Energy** (3 energy per encounter, recharges between customers)

### Basic Techniques (1 Energy)
- **Sauté**: Next ingredient played this round scores +5F
- **Season**: Add +2 Kick permanently for this encounter
- **Taste Test**: Preview next 5 ingredients on your deck

### Advanced Techniques (2 Energy)
- **Flambé**: Double all Heat this round (before it's added to Kick)
- **Simmer**: Reduce all Kick to 1, gain +10F
- **Sous Vide**: Lock one ingredient aside. It scores +6F when played next round
- **Ferment**: Choose an ingredient in hand. After 2 more rounds, it scores triple stats

### Master Techniques (3 Energy)
- **Mise en Place**: Choose any ingredient from your deck and add it to hand
- **Chef's Special**: This round only, Satisfaction = (Flavour × Kick) × 1.5
- **Speed Service**: Take an extra round this encounter

---

## Ingredient Modifiers

Modifiers can be added to ingredients through events, relics, or rewards.

### Positive Modifiers
- **Fresh**: +3F (lasts 3 encounters, then becomes normal)
- **Aged**: +1K per round in deck this encounter
- **Organic**: This ingredient doesn't count toward deck size limit
- **Artisan**: Scores double when scoring threshold is below 50%
- **Fragrant**: Other ingredients this round gain +1F

### Negative Modifiers
- **Burnt**: +4K, -2F (can be useful for Kick builds!)
- **Frozen**: -2F until played
- **Dubious Gloop**: ??? (Random effect: could be +10F or -5F each time played)
- **Cursed**: Cannot be trashed at Rest Sites
- **Expired**: -1F per day passed

### Combo Modifiers
When certain ingredients are played together in the same round:
- **Tomato + Basil + Mozzarella**: "Caprese" → +15F bonus
- **Potato + Leek + Cream**: "Vichyssoise" → +10F, +2K
- **Beef + Onion + Mushroom**: "Umami Bomb" → Double total Kick
- **Ghost Pepper + Any Meat**: "Ring of Fire" → +20 Heat
- **Any 3 Vegetables**: "Garden Fresh" → +8F

---

## Relics

Relics are permanent modifiers for the entire run. Maximum 6 relics per run.

### Tier 1 Relics (Common)
- **Golden Trash Bin**: Gain $5 every time you trash an ingredient
- **Recipe Book**: Draw 10 ingredients first round of each encounter (instead of 8)
- **Pantry Raid**: Once per encounter, add a random basic ingredient to hand
- **Leftovers**: Retain one ingredient after playing it (returned to hand)
- **Sharp Knife**: +1 Energy per encounter
- **Copper Pot**: Start each encounter with +2 Heat

### Tier 2 Relics (Uncommon)
- **Quality Control**: Upgraded ingredients score 2× stats (instead of base + 3)
- **Financial Documents**: Gain $1 per $10 you have at end of each encounter
- **Eternal Flame**: Heat no longer decreases each round
- **Pressure Cooker**: Gain 2× Heat from all sources. Vegetables score -2F
- **Mise en Place Station**: Choose an ingredient to upgrade at start of each encounter
- **Ice Bath**: Start each encounter with Kick set to 3 (instead of 1)
- **Stock Pot**: Grandma's Stock gains +8 instead of +5 per use

### Tier 3 Relics (Rare - Build-Defining)
- **Scales of Justice**: Balance F and K automatically (F×K becomes [(F+K)/2]²)
- **Comfort Food**: Square all Flavour. Kick is always 1 (can't gain Heat)
- **Inferno Kitchen**: Kick = Heat only. All ingredients add Heat instead of scoring normally
- **Molecular Gastronomy**: After each round, randomly swap two ingredients' stats
- **Ghost Kitchen**: You don't see ingredients until played. All stats increased by 50%
- **Minimalist's Wok**: Maximum deck size is 10. All ingredients score +10F, +5K

### Cursed Relics (High Risk/Reward)
- **The Devil's Spice**: Double all thresholds. Triple all stats scored
- **Rotten Fridge**: All ingredients get "Expired" modifier. Start with $200
- **Health Inspector**: Trash 5 ingredients. Gain 3 random rare relics
- **Critic's Review**: First encounter each day has 2× threshold. All others have 0.5× threshold

---

## Economy System

### Money Sources
- **Base Reward**: $20 per regular customer, $40 per elite, $60 per boss
- **Skip Reward**: Choose money instead of ingredient/technique
- **Relics**: Golden Trash Bin, Financial Documents
- **Events**: Gambling, selling ingredients
- **Perfect Run Bonus**: Beat threshold by 50%+ → +$10

### Money Sinks

**Shop Prices**:
- Common ingredient: $30
- Uncommon ingredient: $50
- Rare ingredient: $80
- Technique: $60
- Remove ingredient: $50 (increases by $25 each use)
- Upgrade ingredient: $40
- Common relic: $100
- Uncommon relic: $180
- Rare relic: $300

**Average Run Economy**: $600-800 total across 5 days (with good play)

---

## Deck Building Strategy

### Starting Deck (Prep Cook Jimmy)
- 6× Carrot (4F)
- 4× Potato (5F)
- 3× Chicken (6F)
- 2× Onion (5F)
- 1× Chili Pepper (5F, +3 Heat)

**Total**: 16 cards
**Average Draw**: ~50F, ~0-3 Heat per round

### Deck Size Management
- **Minimum**: 12 cards (prevents too much consistency abuse)
- **Maximum**: 30 cards (prevents dilution)
- **Optimal**: 18-22 cards (balance of consistency and power)

### Archetype Strategies

**1. Heat Rush (Kick-Focused)**
- Stack Heat-generating ingredients (Hot Sauce, Ghost Pepper)
- Acquire "Eternal Flame" relic (Heat doesn't decay)
- Use "Flambé" technique to double Heat
- Keep Flavour modest but consistent
- **Target Ratio**: 8F × 20K = 160 satisfaction

**2. Flavour Bomb (Flavour-Focused)**
- Stack high-Flavour ingredients (Shrimp, Mushroom, Tomato)
- Use "Simmer" technique (reduce Kick, boost Flavour)
- Acquire "Comfort Food" relic (square Flavour, Kick always 1)
- Add Cream to control Kick spikes
- **Target Ratio**: 25F × 1K = 625 satisfaction (with Comfort Food, becomes 625²)

**3. Balanced Gourmet**
- Equal investment in Flavour and Kick
- Use Salt for consistent Kick scaling
- Avoid extreme modifiers
- Flexible technique usage
- **Target Ratio**: 15F × 15K = 225 satisfaction

**4. Grandma's Gambit**
- Build entire deck around Grandma's Stock scaling
- Acquire "Stock Pot" relic (+8 instead of +5)
- Remove all other ingredients except draw/cycle cards
- Each use makes Stock exponentially better
- **Endgame Power**: Grandma's Stock at 100+F by Day 5

**5. Combo Chef**
- Focus on ingredient synergies (Caprese, Umami Bomb, etc.)
- Use "Mise en Place" to guarantee combo pieces
- Smaller deck for consistency
- High risk, high reward
- **Target**: Multiple 15-20 bonus triggers per encounter

---

## Customer Design

### Customer Difficulty Tiers

**Tier 1 (Days 1-2)**: Single minor debuff
**Tier 2 (Days 3-4)**: Major debuff OR two minor debuffs
**Tier 3 (Day 5)**: Multiple debuffs + special mechanics

### Sample Customer Abilities

**Mr. Seuss, Heir to the Seuss Fortune**
- Dialogue rhymes
- Debuff: Vegetables with odd Flavour don't score
- Reward: +$20 bonus

**Brat**
- Debuff: "Picky" - Vegetables score 0F
- Forces meat-heavy or spice builds
- Appears: Days 1-3

**Father John**
- Debuff: "Holy" - Ingredients with 6F or 6K score 0
- Thematic challenge (avoid devil's numbers)
- Appears: Days 2-4

**Count Brothula**
- Debuff: Onion/Garlic score 0
- Buff: Tomato/Beet/Meat score +3F
- Encourages specific ingredients
- Appears: Days 2-5

**Chad Chazly (Elite)**
- Debuff: "Weak Palate" - Kick above 10 causes him to leave (instant loss)
- Forces Flavour-focused strategy
- High threshold with Kick limitation
- Appears: Days 3-5

**Senator Dogfood (Boss)**
- "Canine Appetite" - Meat scores triple, vegetables score 0
- Can be bribed: Playing a Bone ingredient (rare) instantly wins
- Extremely high threshold
- Appears: Day 3-5 Boss

**Dr. Home (Final Boss, Day 5)**
- "Pharmaceutical Palette" - Each round, demands different stat ratio
- Round 1: Must score 60% Flavour, 40% Kick
- Round 2: Must score 40% Flavour, 60% Kick  
- Round 3: Must score 50/50 split
- Rounds 4-5: Random ratios announced
- Ultimate skill check

---

## Progression Systems

### Chef Unlocks

**Prep Cook Jimmy** (Starting Chef)
- Balanced starting deck
- Passive: None (baseline)
- Starting Relic: None

**Chef Rodrigo** (Unlock: Beat Day 3)
- Starting deck: Heavy meat focus
- Passive: "Carnivore" - Meats score +2F, vegetables cost $10 less
- Starting Relic: Copper Pot (+2 Heat per encounter)

**Sushi Master Yuki** (Unlock: Beat Day 5)
- Starting deck: Fish and rice focus, smaller deck (12 cards)
- Passive: "Precision" - Upgraded ingredients score 3× instead of 2×
- Starting Relic: Sharp Knife (+1 Energy)

**Grandma Beatrice** (Unlock: Win with Grandma's Stock scoring 1000+ satisfaction)
- Starting deck: 10× Grandma's Stock
- Passive: Grandma's Stock gains +10 per use (instead of +5)
- Starting Relic: Stock Pot

**Chaos Chef Ramsey** (Unlock: Win with 5+ Cursed modifiers)
- Starting deck: All ingredients are "Dubious Gloop"
- Passive: "Volatile" - All random effects doubled
- Starting Relic: Molecular Gastronomy

### Meta Progression

**Kitchen Upgrades** (Permanent, purchased with Soup Tokens earned from runs):
- **Better Belt**: Start with 9 ingredients per draw (costs 10 tokens)
- **Speed Boost**: +5 seconds Prep Phase (costs 8 tokens)
- **Lucky Trash**: 25% chance trashed ingredient upgrades (costs 15 tokens)
- **VIP Service**: Start each run with $50 (costs 12 tokens)

**Recipe Journal**: Tracks all ingredient combos discovered, provides hints for synergies

---

## Balance Considerations

### Difficulty Curve
- **Day 1**: Tutorial, forgiving thresholds, introduces mechanics
- **Day 2**: Skill check, requires basic deck improvements
- **Day 3**: First "wall," demands strategy shift
- **Day 4**: Mastery of one archetype required
- **Day 5**: Multiple threats, perfect execution

### Anti-Frustration Features
- **Base Kick = 1**: Prevents complete dead draws
- **Upgrade Preview**: See what upgrade does before committing
- **Threshold Visibility**: Always shown before encounter
- **Undo Button**: Can undo played ingredients before serving round (once per round)

### Scaling Breakpoints
Mathematical targets for balanced play:

| Day | Avg Stats Needed Per Round | Total Deck Power |
|-----|----------------------------|------------------|
| 1 | 10F × 5K = 50 | 150 total |
| 2 | 15F × 7K = 105 | 300 total |
| 3 | 20F × 10K = 200 | 600 total |
| 4 | 30F × 15K = 450 | 1350 total |
| 5 | 40F × 20K = 800 | 2400 total |

### Relic Synergy Matrix
Certain relic combinations are intentionally powerful (and fun):

- **Eternal Flame + Pressure Cooker**: Infinite scaling Heat
- **Comfort Food + Artisan Ingredients**: Massive squared Flavour
- **Scales of Justice + Balanced Deck**: Always optimal ratio
- **Ghost Kitchen + Sharp Knife**: High risk, high reward with more energy

---

## Win Conditions

### Victory
- Satisfy all customers across 5 days
- Defeat Dr. Home (Final Boss)
- Unlock next chef (if applicable)

### Defeat
- Any customer leaves unsatisfied
- Must restart from Day 1

### Scoring/Ranking
- **Time Bonus**: Faster clears = more tokens
- **Perfect Days**: Satisfy all customers on a day = bonus token
- **Style Points**: Win with unique/difficult builds = bonus tokens
- **Leaderboards**: High scores per chef, speedruns, challenge modes

---

## Future Expansion Ideas

- **Endless Mode**: Infinite scaling difficulty
- **Daily Challenges**: Fixed seed, modifiers, leaderboards
- **Co-op Mode**: Two chefs share one soup (split ingredients)
- **Custom Runs**: Tweak starting relics, deck, modifiers
- **More Chefs**: 10+ total with wildly different playstyles
- **Seasonal Events**: Limited-time customers and ingredients

---

*End of Design Document*

# Souped Up!

## Core Concept
A deck-building roguelike where players are chefs serving increasingly demanding customers by crafting soups from ingredients. Success depends on balancing **Flavour** (quality) and **Mult** (intensity) to meet satisfaction thresholds.

---

## Core Mechanics

### Satisfaction Formula
```
Satisfaction = (Base Flavour + Flavour Bonuses) × (Base Mult + Mult Bonuses) × Relic Multipliers
```

### Soup Types

Each soup type has base stats that can be leveled up in shops:

| Soup Type | Base Flavour | Base Mult | Level Up Cost | Flavour/Level | Mult/Level |
|-----------|--------------|-----------|---------------|---------------|------------|
| **Broth** | 20 | 2 | $40 | +10 | +1 |
| **Stew** | 40 | 3 | $50 | +15 | +1 |
| **Bisque** | 30 | 4 | $60 | +10 | +2 |
| **Chowder** | 50 | 3 | $60 | +20 | +1 |
| **Consommé** | 15 | 6 | $70 | +5 | +3 |
| **Curry** | 35 | 5 | $70 | +12 | +2 |
| **Ramen** | 25 | 5 | $60 | +8 | +2 |

**Soup Type Determination**: The soup type is determined by the **combination of ingredients played each round**. For example:
- **Broth**: 3+ vegetables, no meat
- **Stew**: 2+ meat, 2+ vegetables
- **Bisque**: 1+ seafood, 1+ cream/butter
- **Chowder**: 2+ seafood, 2+ vegetables, 1+ cream/potato
- **Consommé**: Only upgraded ingredients
- **Curry**: 2+ spices, 1+ meat/vegetables
- **Ramen**: 1+ noodles, 1+ meat, 1+ egg 

If ingredients don't match any soup type, you make **Slop** (10 Flavour, 1 Mult).

---

## Game Loop

### Run Structure
**5 Days → 15-20 Total Encounters → Final Boss**

Each day consists of:
- **4 Regular Customers** (standard encounters)
- **1 Boss Customer** (day finale)

After each encounter, players select one of 3 random order tickets from a carousel:
- **1-2 Customer Variants** (standard combat)
- **Picky Customer** (get a relic, more difficult)
- **Shopkeeper** (buy ingredients, techniques, relics)
- **Take Break** (upgrade OR remove ingredient)
- **Random Event** (risk/reward scenarios)

### Turn Structure (Customer Encounter)

**1. PREP PHASE** (10 seconds)
- View satisfaction threshold for this customer
- See customer's debuffs/preferences
- Preview first 3 ingredients on conveyor belt
- Plan strategy

**2. COOKING PHASE** (Repeats for 3 rounds)
- Draw 8 random ingredients from your "pantry" (deck) onto conveyor belt
- Choose ingredients to add to soup
- Each ingredient added immediately scores its stats
- Unused ingredients on belt are discarded (return to pantry at end of round)
- Round ends when you press "Serve"
- Customer takes out a spoon and tastes soup and gives a comment depending on satisfaction 

**3. SCORING**
- Current Flavour × Current Mult = Round Satisfaction
- Satisfaction bar fills toward threshold
- If threshold met: Victory (gain rewards)
- If threshold not met after all rounds: Customer storms out and you get a humorous angry review message from them (lose run)

**4. REWARDS** (After victory)
- New ingredients/technique (choice of 3)
- Variable money from $15-50 tallied from time bonus and overkill bonus

---

## Scoring & Balance

### Satisfaction Thresholds

| Day | Regular | Elite | Boss  |
| --- | ------- | ----- | ----- |
| 1   | 200     | 400   | 600   |
| 2   | 800     | 1200  | 2000  |
| 3   | 2500    | 4000  | 7000  |
| 4   | 7000    | 11000 | 17000 |
| 5   | 15000   | 22000 | 35000 |

### Base Ingredient Values

**Vegetables** (Flavour ingredients)
- Carrot: 30F
- Potato: 35F
- Onion: 35F
- Tomato: 40F
- Celery: 30F
- Mushroom: 40F
- Bell Pepper: 35F

**Meats** (Flavour ingredients)
- Chicken: 45F
- Beef: 50F
- Pork: 45F
- Fish: 40F
- Shrimp: 55F
- Crab: 50F

**Spices** (Mult ingredients)
- Chili Pepper: 1M
- Hot Sauce: 2M
- Black Pepper: 20F, 1M
- Cayenne: 15F, 2M
- Ghost Pepper: 10F, 4M

**Special Ingredients**
- Grandma's Stock: 40F, gains +5F permanently each time used this run
- Salt: +1M per ingredient played this round
- Butter: Permanently add 20F to next ingredient played
- Cream: 35F, -10M
- MSG: Permanently gain +2M when played, trash 1 random ingredient next draw

**Upgraded Values**: 
- Flavour ingredients: +15F when upgraded
- Mult ingredients: +1M when upgraded
- Special ingredients: Enhanced abilities

---

## Techniques (Active Abilities)

Techniques cost **Energy** (3 energy per encounter, recharges between customers)

### Basic Techniques (1 Energy)
- **Sauté**: Next ingredient played this round scores +50F
- **Season**: Add +2 Mult
- **Taste Test**: Preview next 5 ingredients in your deck

### Advanced Techniques (2 Energy)
- **Flambé**: +5 Mult this round
- **Simmer**: Set base Mult to 1, +100F
- **Sous Vide**: Lock one ingredient aside, it adds double stats when played next round
- **Ferment**: Choose an ingredient in hand. After 2 more rounds, it adds triple stats

### Master Techniques (3 Energy)
- **Mise en Place**: Choose any ingredient from your deck and add it to hand
- **Chef's Special**: Apply 1.5× multiplier to final satisfaction
- **Speed Service**: Take an extra round this encounter

---

## Ingredient Modifiers

Modifiers can be added to ingredients through events, relics, or picked up naturally through rewards.

### Positive Modifiers
- **Fresh**: +15F (lasts 3 encounters, then becomes normal)
- **Aged**: Permanently gain +1F per round in deck
- **Organic**: +3M
- **Artisan**: Scores double when scoring threshold is below 50%
- **Fragrant**: Other ingredients gain +10F this round

### Negative Modifiers
- **Burnt**: +4M, -20F
- **Frozen**: -20F until played 3 times
- **Dubious**: ??? (Random effect: could be from +80F to -50F each time played)
- **Cursed**: Cannot be trashed during Break Times
- **Expired**: -10F per day passed

---

## Relics

Relics are permanent modifiers for the entire run. 

### Tier 1 Relics (Common)
- **Golden Trash Bin**: Gain $5 every time you trash an ingredient
- **Recipe Book**: Draw 10 ingredients first round of each encounter (instead of 8)
- **Pantry Raid**: Once per encounter, add an extra random basic ingredient to hand
- **Leftovers**: Retain one ingredient after playing it (returned to hand)
- **Sharp Knife**: +1 Energy per encounter
- **Copper Pot**: Permanently gains +1M at start of encounter 
- **Sticky Hand**: When picked up, choose an ingredient. This ingredient will always be drawn first in an encounter

### Tier 2 Relics (Uncommon)
- **Mulligan**: If soup is served with only one ingredient, permanently trash ingredient
- **Loaded Dice**: Double all random probabilities 
- **Quality Control**: Upgraded ingredients add 2× their stats
- **Financial Documents**: Earn $1 per $10 you have at end of each encounter
- **Pressure Cooker**: 1.5× multiplier to all Mult bonuses. Vegetables add no Flavour
- **Prep Station**: Choose an ingredient on conveyer belt to permanently upgrade at start of each encounter
- **Ice Bath**: When picked up, upgrade the level of every soup type
- **Stock Pot**: Only shows up if you have Grandma's Stock in deck. Grandma's Stock gains +8 instead of +5 per use

### Tier 3 Relics (Rare - Build-Defining)
- **Scales of Justice**: Final calculation becomes [(F+M)/2]²
- **Eternal Flame**: +0.0x Mult. Permanently gain +0.5x Mult at start of day, but destroy random relic 
- **Comfort Food**: Final calculation becomes F². Base Mult always 1 (can't gain Mult)
- **Molecular Gastronomy**: After each round, randomly shuffle ingredients' flavour stats from +25 to -10
- **Ghost Kitchen**: You don't see ingredients until played. All stats increased by 50%
- **Master Chef**: 2× multiplier on final round if you make the same soup type all rounds

### Cursed Relics (High Risk/Reward)
- **The Devil's Spice**: Double all thresholds. +50 Mult
- **Rotten Fridge**: All ingredients get "Expired" modifier. Gain $200
- **Health Inspector**: Trash 5 ingredients. Gain 3 random relics
- **Critic's Review**: First encounter each day has 2× threshold. All others have 0.5× threshold

---

## Visual/Audio Design

**Music**: Each day has unique music. Day 1 starts with chill lo-fi jazz. Day 3 has more drums and sounds like IDM (think Vordhosbn - Aphex Twin). By day 5, the soundtrack is insane-sounding breakcore.

**Graphics**: Quirky, pixelated ingredients with thick black borders. Characters are all pixel animated. Scoring animations are flashy and colorful. The satisfaction bar changes from red to green as it fills up. Conveyer belt on bottom of screen, pot of soup above it, customer standing above the pot.

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
- Debuff: "Vampiric" - Onion/Garlic score 0
- Buff: Tomato/Beet/Meat score +3F
- Encourages specific ingredients
- Appears: Days 2-5

**Chad Chazly**
- Debuff: "Weak Palate" - Mult above 50 causes him to leave (instant loss)
- Forces Flavour-focused strategy
- High threshold with Mult limitation
- Appears: Days 3-5

**Senator Dogfood**
- Debuff: "Canine Appetite" - Meat scores triple, vegetables score 0
- Can be bribed: Playing a Bone ingredient (rare) instantly wins
- Extremely high threshold
- Appears: Day 3-5 

**Dr. Home**
- "Addict" - Drug ingredients score triple

**God** - Final Boss
- "Divine Palate" - Random effect?

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
- Starting Relic: Copper Pot

**Sushi Master Yuki** (Unlock: Beat Day 5)
- Starting deck: Fish and rice focus, smaller deck (12 ingredients)
- Passive: "Precision" - Upgraded ingredients score 3× instead of 2×
- Starting Relic: Sharp Knife

**Grandma Beatrice** (Unlock: Win with Grandma's Stock at +500F)
- Starting deck: 5× Grandma's Stock, focus on flavour
- Passive: Play one extra round per encounter
- Starting Relic: Stock Pot

**Remy the Failure** (Unlock: Win with 5+ Cursed modifiers)
- Starting deck: All ingredients are "Dubious Gloop"
- Passive: "Volatile" - All random effects doubled
- Starting Relic: Molecular Gastronomy

### Meta Progression

**Cookbook**: Tracks all ingredients and relics discovered, undiscovered relics are grayed out

---

## Balance

### Difficulty Curve
- **Day 1**: Tutorial, forgiving thresholds, introduces mechanics
- **Day 2**: Skill check, requires basic deck improvements
- **Day 3**: First "wall," demands strategy shift
- **Day 4**: Mastery of one archetype required
- **Day 5**: Multiple threats, requires perfect execution

### Anti-Frustration Features
- **Upgrade Preview**: See what upgrade does before committing
- **Threshold Visibility**: Always shown before encounter on order ticket

---

## Win Conditions

### Victory
- Satisfy all customers across 5 days
- Defeat God (Final Boss)

### Defeat
- Any customer leaves unsatisfied
- Must restart from Day 1

### Scoring/Ranking
- **Time Bonus**: Faster clears = more money
- **Overkill**: More bonus satisfaction at end of round = more money
- **Leaderboards**: High score stats per chef

---

## Future Expansions

- **Endless Mode**: Infinite scaling difficulty
- **Seeds**: Play a seeded run, save your seed to replay a run
- **Custom Runs**: Tweak starting relics, deck, modifiers
- **More Chefs**: 10+ total with wildly different playstyles

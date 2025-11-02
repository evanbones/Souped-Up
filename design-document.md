# Souped Up!

## Core Concept
A deck-building roguelike where you're a chef ascending through restaurants, serving increasingly powerful (and weird) customers. Success depends on balancing **Flavour** (additive) and **Heat** (multiplicative), powered by a limited set of **Appliances** that create explosive, emergent synergies.

**Design Philosophy**: Immediately graspable mechanics, lightning-fast rounds, satisfying number explosions, and "eureka moments" when your Appliance engine clicks.

---

## Core Formula

```
Satisfaction = Flavour × Heat × Soup Bonus

Where:
• Flavour = Sum of all ingredient Flavour + Appliance bonuses
• Heat = (1 + Sum of all +Heat) × (Product of all ×Heat multipliers)
• Soup Bonus = Multiplier from soup type (×1.5 to ×3.0)
```

**Example**:
- Ingredients: 200 Flavour total, +15 Heat from spices
- Appliances: ×1.5 Heat, ×2.0 Heat
- Soup: Curry (×3.0)
- **Satisfaction: 200 × ((1 + 15) × 1.5 × 2.0) × 3.0 = 200 × 48 × 3 = 28,800**

---

## Soup Types

The pot changes color in real-time as you play cards.

| Soup Type | Requirements | Bonus |
|-----------|-------------|-------|
| **Broth** | 3+ Veggies, no Meat | ×1.5 |
| **Stew** | 2+ Meat, 2+ Veggies | ×2.0 |
| **Bisque** | 1+ Seafood, 1+ Dairy | ×2.5 |
| **Curry** | 3+ Spices, 1+ Protein | ×3.0 |
| **Chowder** | 2+ Seafood, 2+ Veggies | ×2.5 |
| **Slop** | None of the above | ×1.0 |

**Leveling Up Soups**: Buy "Soup Coupons" in shops to upgrade soup bonuses (e.g., Curry ×3.0 → ×3.5).

---

## Game Structure: The Ascension

### The Five Restaurants
You climb through 5 restaurants, each serving weirder customers. Each restaurant = **3 tickets** + **1 boss**.

1. **Mama's Kitchen** (Street Level) - Tickets 1-3, Boss at 4
2. **The Yacht Club** (Waterfront Elite) - Tickets 5-7, Boss at 8
3. **The Penthouse** (Billionaire's Private Chef) - Tickets 9-11, Boss at 12
4. **Heaven** (Ascend to Face God) - Tickets 13-15, Boss at 16
5. **The Void** (???) - Endless Mode, Ticket 17+. Boss every 4 tickets

---

## Ticket Carousel System

After each round, **choose 1 of 3 tickets**:

* **Customer Ticket (Gold)** - Face a customer
* **Shop Ticket (Blue)** - Buy ingredients, Appliances, Coupons
* **Black Market Shop (Black)**:
  - Replaces normal Shop ticket
  - Has **at least one guaranteed Tier 3 Appliance** at ×1.5x price
  - All normal shop items are ×1.2 price
* **Mystery Ticket (Purple)** - Random event (risky but rewarding)

### Carousel Distribution

**Restaurants 1-2** (Tickets 1-8):
- 60% Customer, 30% Shop, 10% Mystery

**Restaurants 3-4** (Tickets 9-16):
- 55% Customer, 25% Shop, 15% Mystery, 5% Black Market Shop

**Restaurant 5** (Endless):
- 50% Customer, 20% Shop, 25% Mystery, 5% Black Market Shop

**Boss Tickets**: Mandatory at Tickets 4, 8, 12, 16, 20, etc. The carousel shows only **BOSS** - no choice.

---

## Gameplay: Plays & Rerolls

You have **Plays** and **Rerolls** every round.

```
ROUND START
├─ Draw 8 cards
├─ 3 Plays, 2 Rerolls available
│
├─ OPTION A: Play 1-8 cards
│  ├─ Appliances trigger (left to right)
│  ├─ Calculate satisfaction
│  ├─ Discard played cards
│  └─ Draw back to 8 cards (-1 Play)
│
├─ OPTION B: Reroll 1-8 cards
│  ├─ Discard selected cards
│  └─ Draw back to 8 cards (-1 Reroll)
│
└─ Repeat until threshold reached or resources exhausted
```

**Leftover currency**:
- Unused Plays: +$10 each
- Unused Rerolls: +$5 each

---

## Appliances (Build Engine)

**You have 5 Appliance Slots.** 

Appliances trigger **in order (left to right)** when you Play cards.

### Tier 1 Appliances ($120)
**Sharp Knives**: +1 Play per round.
**Tasting Spoon**: +1 Reroll per round.
**Cutting Board**: Each Veggie played gives +15 Flavour.
**Cast Iron Pan**: Each Meat played gives +70 Flavour.
**Spice Grinder**: Each Spice played gives +6 Heat.
**Mortar & Pestle**: +40 Flavour for each card played.
**Compost Bin**: Every time you Reroll, permanently gain +3 Heat.
**Mise en Place**: If your first Play contains 4+ cards, gain +400 Flavour
**Golden Ladle**: Gain an extra $20 at round end.
**Shopping Cart**: Common ingredients give +50 Flavour
**Prayer Beads**: Blessed ingredients are twice as likely to trigger their effects.

### Tier 2 Appliances ($200)
**Damn Fine Espresso**: First played ingredient scores an additional two times.
**Poverty Pot**: Whenever you play with less than $100, create a random Coupon.
**Doggy Bag**: At end of round, choose 1 card from your hand. Next round, it starts your hand AND is duplicated.
**Recycling Center**: Whenever you refresh a shop, permanently gains +15 Flavour.
**The Perfectionist's Palette**: Each time you Reroll, your next Play gains ×0.4 Heat.
**Lightning Rod**: Each time you gain Heat from cards, gain +2 additional Heat.
**Aromatics Kit**: If you play Garlic + Onion, gain ×1.6 Heat.
**Octopus' Garden**: First 3 different ingredient types played each round give ×1.15 Flavour each.
**Aging Barrel**: Each Aged ingredient played gives ×1.1 Flavour.
**Butcher's Block**: Meats also give +5 Heat.
**Garden Bed**: Each Veggie played gives ×1.08 Flavour.
**Fishmonger's Ice**: Seafood cards trigger twice when played.
**Butter Boat**: Dairy cards give ×1.7 Heat. When you play Dairy, your next card gains +60 Flavour.
**Family Recipe Book**: If you make the same soup type as last round, gain ×1.5 Heat.
**Jimbo's Kitchen**: Wild ingredients count as ALL types simultaneously. Gain +70 Flavour for each Wild played.
**Mirepoix Mastery**: If you play Carrot + Onion + any Veggie, gain +30 Heat.
**Combo Counter**: For each combo you trigger, permanently gain +0.3x Heat.
**Theme Park**: For every 2 cards that match your soup type in a Play, gain +0.35× Heat.
**Instant Ramen**: If you finish a customer in 1 Play, gain +$80 bonus.
**Pickle Jar**: Each customer you beat, permanently gain +30 Flavour to all ingredients
**Nest Egg**: Gain +0.5x Heat per $100 owned.
**Stamp Collection**: Gain +0.25x Heat per ingredient added to deck.
**Spice Caravan**: When making Curry, Spices trigger twice.
**Gambler's Wok**: Each Play, 50% chance: ×2.5 Heat OR lose half your Flavour.
**Artisan's Pride**: Artisan ingredients give ×1.2 Flavour per Appliance you own.
**Farmers Market**: Fresh ingredients trigger twice.
**Tag Team**: When you play 2+ ingredients with the same tag, they gain +100 Flavour.
**The Charcoal Grill**: Gain +0.4x Heat per charred ingredient in deck.

### Tier 3 Appliances ($300)
**Spice Volcano**: Each played Spice gives ×0.25 Heat.
**The Forbidden Fruit Bowl**: All played Veggies gain Aged tag.
**Master Gardener**: For every 3 Veggies in your deck, each Veggie played gives ×1.1 Flavour.
**Philosopher's Stone**: All your cards become Wild AND keep their original types.
**Chrono Spatula**: +1 Play. Your last Play each round scores ×2.0 satisfaction.
**Eternal Flame**: 1.0x Heat. Permanently gains +0.2x Heat every time a card is removed from your deck.
**Snowball Pot**: Gain +0.5× Heat each time you Play this round (resets each round).
**Ghost Kitchen**: Card names are hidden (show only type and rarity). ×3.0 Heat.
**Engineer's Wrench**: Satisfaction becomes: Heat² × Flavour × Soup. 
**Reckless Stove**: 2.5x Heat, but satisfaction threshold is ±20% randomized.
**The Crucible**: Appliances trigger twice, but you can only use 2 Plays per round.
**Pot of Greed**: -3 hand size. Every round, permanently increase hand size by 1.
**Pressure Cooker**: ×3.5 Heat, but resets to ×1.0 at start of each restaurant. 
**Molecular Gastronomy Kit**: Cards give zero Flavour/Heat. You gain +500 base Flavour. Each card played gives ×0.5 Heat.
**Steam Engine**: If your Flavour is below 500, gain ×4.0 Heat. 
**Legendary Chef's Apron**: Each time you make a ×2.5+ soup bonus, permanently gain ×0.25 Heat (starts at ×1.0).
**Quality Over Quantity**: If your deck has ≤12 cards, all ingredients gain +120 Flavour and +12 Heat.
**Good Noodle Star**: For each unique combo triggered this game, all combos give +40 Flavour.
**Fusion Kitchen**: Combos trigger twice, but ingredients not in combos give 0 Flavour/0 Heat.
**Michelin Tire**: Permanently gain ×0.25 Heat when an ingredient is purchased. Resets at end of restaurant.
**Burnt Offerings**: ×3.0 Heat, but you must discard 2 cards at the start of every round.
**Fermentation Station**: Fermented ingredients start with +0.6× Heat (instead of +0.15 at round start).
**Analytics Report**: For each unique tag in your deck, gain +0.3× Heat.

### Tier 4 Appliances (Rare Event Spawns)
**Schrödinger's Spoon**: Each soup type you've made this run permanently increases this Appliance's ×Heat by 0.5 (starts at ×1.0).
**Spice Must Flow**: Spices give ×0.45 Heat AND +20 Flavour. 
**Hell's Kitchen**: ×5.0 Heat, but customers' thresholds increase by 50%. 
**Gollzur's Orb**: View all upcoming tickets. All Mystery Tickets become beneficial. +1 Reroll. 
**Étienne's Ladle**: Common ingredients trigger twice.
**Timekeeper's Hourglass**: At round start, choose: Double all Flavour this round OR Double all Heat this round.
**God's Gambit**: Blessed cards trigger on 1 in 2 chance (50/50). When a Blessed card triggers, permanently gain ×0.25 Heat.

---

## Ingredients (Your Deck)

### Core Stats
- **Flavour (F)**: Adds to satisfaction
- **Heat (H)**: Adds to multiplier (written as +2H, +5H, etc.)
- **Type**: Veggie, Meat, Seafood, Spice, Dairy, Wild

## Tag Definitions
**Aged**: Permanently gains +5F each time played this run.
**Wild**: Counts as any type for soup requirements.
**Blessed**: Has a 1 in 4 chance to score triple the flavour. 1 in 20 chance to earn $100.
**Artisan**: Gains +15 Flavour per unique Appliance you own.
**Fresh**: If played in your first Play of the round, gain +80 Flavour.
**Charred**: Gives +15 Heat but -30 Flavour.
**Fermented**: Gains +0.15× Heat per round (resets between restaurants).
**Preserved**: Cannot be removed from your deck, but gives ×1.5 Flavour.

---

### Common Ingredients ($40)

| Name | Stats | Type | 
|------|-------|------|
| Tomato | 55F | Veggie | 
| Garlic | 40F, +3H | Veggie |
| Beef | 85F | Meat |
| Pork | 80F | Meat | 
| Fish | 70F | Seafood | 
| Butter | 60F | Dairy | 
| Salt | 30F, +4H | - | 
| Spring Greens | 60F | Veggie | 
| Pickles | 65F | Veggie | 
| Onion | 25F, +15H | Veggie |

### Uncommon Ingredients ($70)

| Name | Stats | Type |
|------|-------|------|
| Shrimp | 100F | Seafood | 
| Cream | 80F | Dairy |
| Chili Flakes | 25F, +8H | Spice | 
| Mushroom | 75F | Veggie | 
| Stock | 90F | - |
| Cumin | 20F, +9H | Spice |
| Cayenne | 20F, +10H | Spice | 
| Cheddar | 95F | Dairy |
| Artisan Bread | 90F | - | 
| Smoked Salmon | 135F | Seafood | 
| Blackened Fish | 70F, +18H | Seafood |
| Kimchi | 80F, +6H | Veggie |

### Rare Ingredients ($120)

| Name | Stats | Type |
|------|-------|------|
| Truffle | 140F | Veggie | 
| Lamb | 120F | Meat | 
| Lobster | 130F | Seafood |
| Ghost Pepper | 15F, +18H | Spice | 
| Truffle Oil | 100F, +12H | - |
| Beef | 150F | Meat | 
| Saffron | 25F, +20H | Spice | 
| Wagyu | 170F | Meat | 
| Pasta | 140F | - | 
| Olive Oil | 110F, +10H | - | 
| Pork | 95F | Meat |
| Miso | 100F, +10H | - | 
| Sourdough | 85F | - | 
| Dragon Fruit | 130F | Veggie |
| Durian | 110F, +12H | - |
| Ambrosia | 150F, +12H | - |

---

## Combos (Auto-Triggered)

Combos happen when you play specific cards together in one Play. Cards glow when known combo pieces are in hand.

**Discovery System**: Combos are discovered through play and added to your "Cookbook."

### Combos
1. **Aromatics** (Garlic + Onion): +50F, +6H
2. **Salt & Pepper** (Salt + Any Spice): +60F, +6H
3. **Butter Baste** (Butter + Any Meat): +70F, +10H
4. **Mirepoix** (Carrot + Onion + Any Veggie): +100F, +12H
5. **Surf & Turf** (Seafood + Beef): +140F, +15H
6. **Spice Rack** (3+ Different Spices): ×1.6 Heat
7. **Rainbow Medley** (5+ Different Types): +250F, ×2.0 Heat
8. **Holy Trinity** (3+ Blessed cards in one Play): +200F, +15H
9. **Aged Perfection** (2+ Aged Ingredients): ×1.5 Heat
10. **The Inferno** (Ghost Pepper + 2+ other Spices): +50F, ×2.5 Heat
11. **Artisan's Table** (3+ Artisan ingredients in one Play): +150F, ×1.4 Heat
12. **Fresh Harvest** (4+ Fresh ingredients in your first Play): +300F, gain +1 Reroll this round
13. **Blackened Special** (3+ Charred ingredients in one Play): +40 Heat, ×2.0 Heat
14. **Fermented Feast** (2+ Fermented ingredients): Current round's Fermented bonus doubles (e.g., Round 3 = +0.9× Heat instead of +0.45×)
    
---

## Coupons (Consumables)

Buy these in shops for one-time powerful effects.

### Common Coupons ($50)
- **Umami Crystal**: +250 Flavour to your next Play
- **Dragon's Breath Pepper**: +15 Heat to your next Play
- **Second Wind**: +1 Play this round
- **Deep Clean**: +2 Rerolls this round
- **Recipe Scroll**: Look at top 8 cards of deck
- **Culling Knife**: Remove 1 card from deck permanently
- **Generous Tip**: Earn $100
- **Transmutation Scroll**: Apply a random tag to a selected card
- **Cleansing Spray**: Remove all tags from a selected card

### Rare Coupons ($120)
- **Alchemist's Primer**: Upgrade a soup type (e.g., Curry ×3.0 → ×3.5)
- **Overdrive Gear**: Choose an Appliance. It triggers twice this round
- **Mimic's Tears**: Create a permanent copy of a selected card
- **Summoning Circle**: Create a random Appliance
- **Blessing**: Apply Blessed to all cards in hand

---

## Restaurant Progression & Customers

### Restaurant 1: Mama's Kitchen (Tickets 1-3)
*Vibe: Cozy diner, checkered tablecloths, regulars who tip in quarters*

**The Brat** (Common)
- *Modifier*: Veggies give half Flavour
- *Threshold*: 900
- *Dialogue*: "Ew, I don't want any gross vegetables!"

**Lunch Rush Larry** (Common)
- *Modifier*: Must finish in under 90 seconds or threshold +500
- *Threshold*: 1,000
- *Dialogue*: "HURRY UP! I got a meeting in 10 minutes!"

**Grandpa Joe** (Common)
- *Modifier*: Must use 3+ Dairy ingredients
- *Buff*: Dairy scores ×2
- *Threshold*: 1,100
- *Dialogue*: "Back in my day, we used REAL butter..."

**The Influencer** (Uncommon)
- *Modifier*: First card played scores ×3
- *Threshold*: 1,300
- *Dialogue*: "Wait, let me get the lighting... *flash* Okay go!"

**Timmy the Picky Kid** (Common)
- *Modifier*: Can only play 6 cards max
- *Threshold*: 800
- *Dialogue*: "I only like chicken nuggets but okay..."

---

**BOSS: Mama Rosa** (Ticket 4)
- *Buff*: Dairy and Comfort ingredients score ×2.5
- *Threshold*: 5,000
- *Reward*: $150 + Choose 1 of 3 Appliances
- *Dialogue*: 
  - Start: "Let's-a see if you know what REAL comfort food is!"
  - Win: "*tears up* You remind me of my son... Bellissimo!"

---

### Restaurant 2: The Yacht Club (Tickets 5-7)
*Vibe: Crystal chandeliers, champagne flutes, people in boat shoes*

**The Venture Capitalist** (Common)
- *Modifier*: Each card costs $5 to play (deducted from final reward)
- *Threshold*: 6,000
- *Dialogue*: "Time is money, chef. Let's see your ROI."

**Count Brothula** (Common)
- *Modifier*: Garlic scores 0F
- *Buff*: Meats score ×2
- *Threshold*: 7,000
- *Dialogue*: "No garlic, or I vill be most... displeased."

**Ms. Pescatarian** (Uncommon)
- *Modifier*: Non-seafood Meats score 0F
- *Buff*: Seafood scores ×2.5
- *Threshold*: 8,500
- *Dialogue*: "I only eat what swims and what grows from soil."

**The Instagram Model** (Uncommon)
- *Modifier*: Must make Bisque or fail instantly
- *Buff*: Bisque becomes ×4.0 (up from ×2.5)
- *Threshold*: 7,500
- *Dialogue*: "It needs to be, like, aesthetic? Pink is my brand."

**The Broke College Student** (Common)
- *Modifier*: Rare ingredients score 0F
- *Buff*: Common ingredients score ×2
- *Threshold*: 6,500
- *Dialogue*: "Dude, I'm on a ramen budget. Nothing fancy."

**The Wine Snob** (Rare)
- *Modifier*: Must make Stew or Bisque only
- *Buff*: Those soups get +1.0 bonus (×3.0 or ×3.5)
- *Threshold*: 9,000
- *Dialogue*: "I only appreciate... *swirls glass* ...refinement."

**The Day Trader** (Uncommon)
- *Special*: Threshold fluctuates ±2,000 every 20 seconds
- *Threshold*: 7,000 (base)
- *Dialogue*: "BUY BUY BUY! NO WAIT, SELL!"

---

**BOSS: The Yacht Captain** (Ticket 8)
- *Modifier*: Must use 5+ Seafood ingredients total or fail
- *Buff*: Seafood gives +12 Heat
- *Threshold*: 22,000
- *Reward*: $200 + Choose 1 of 3 Appliances
- *Dialogue*:
  - Start: "Ahoy! Show me the bounty of the seven seas!"
  - Win: "Aye, you've earned your sea legs, chef!"

---

### Restaurant 3: The Penthouse (Tickets 9-11)
*Vibe: Floor-to-ceiling windows, private helicopter pad, people who own senators*

**The Divorced Billionaire** (Common)
- *Modifier*: Each Appliance you own adds +6,000 to threshold
- *Threshold*: 30,000 (base)
- *Dialogue*: "My ex-wife took everything. Even my taste buds."

**The Clanker** (Uncommon)
- *Modifier*: Combos don't trigger normally
- *Special*: Each combo gives ×1.5 Heat instead
- *Threshold*: 35,000
- *Dialogue*: "I'm sorry, as an AI language model, I can't understand combos."

**The Crypto Bro** (Rare)
- *Special*: Pay $50 before serving. Win: +$300. Lose: -$100
- *Threshold*: 33,000
- *Dialogue*: "BRO. This is going to the MOON. You in?"

**The Perfectionist** (Rare)
- *Modifier*: If satisfaction is within ±8% of threshold, instant fail
- *Must hit 92-108% exactly*
- *Threshold*: 38,000
- *Dialogue*: "Perfectly balanced. As all things should be."

**Chad Chazly** (Common)
- *Modifier*: Heat capped at +30 max
- *Forces*: Pure Flavour/×Heat scaling
- *Threshold*: 32,000
- *Dialogue*: "Bro, keep it mild. My tummy's sensitive, bro."

**The Meditation Guru** (Uncommon)
- *Modifier*: Can only use 2 Plays total
- *Buff*: Each Play scores ×2.0
- *Threshold*: 34,000
- *Dialogue*: "Breathe. The soup knows when you're rushing."

**Hugh Mann** (Rare)
- *Modifier*: Random ingredient type scores ×5 (revealed at start)
- *Threshold*: 36,000
- *Dialogue*: "*BZZT* WE ANALYZE YOUR EARTH NUTRIENTS."

**The Doomsday Prepper** (Uncommon)
- *Modifier*: Only Common ingredients score
- *Buff*: Common ingredients score ×3
- *Threshold*: 31,000
- *Dialogue*: "When society collapses, we'll need SIMPLE FOOD."

**The Appliance Breaker** (Rare)
- *Modifier*: Your leftmost Appliance is disabled this round
- *Threshold*: 34,000
- *Dialogue*: "I hate fancy kitchen gadgets. Cook it OLD SCHOOL."

---

**BOSS: The Billionaire** (Ticket 12)
- *Modifier*: Can't use any Coupons
- *Special*: At 50%, he offers: "I'll pay you $150 to quit now"
- *Threshold*: 90,000
- *Reward*: $300 + Choose 1 of 3 Appliances
- *Dialogue*:
  - Start: "I've eaten at every Michelin star restaurant on Earth. Show me something new."
  - Offer: "I'll give you $150 to walk away right now. Final offer."
  - Win: "...I haven't been impressed in 20 years. Well done, chef."

---

### Restaurant 4: Heaven (Tickets 13-15)
*Vibe: Clouds as tables, harps in the background, beings of pure light taste your food*

**The Angel of Purity** (Common)
- *Modifier*: Wild ingredients score 0F
- *Buff*: Single-type ingredients score ×2
- *Threshold*: 60,000
- *Dialogue*: "Only the pure of ingredient may enter these gates."

**Saint Pepper** (Uncommon)
- *Modifier*: If Heat <40, instant fail
- *Buff*: All Spices give ×0.3 Heat
- *Threshold*: 75,000
- *Dialogue*: "The divine flame must BURN within your creation!"

**The Cherub** (Common)
- *Modifier*: Can only play 5 cards max
- *Buff*: Each card gives +100 Flavour
- *Threshold*: 65,000
- *Dialogue*: "*giggles* Less is more in paradise!"

**The Seraphim Judge** (Rare)
- *Modifier*: Threshold hidden until you serve
- *Special*: If you overshoot by 20%+, instant fail
- *Threshold*: 80,000
- *Dialogue*: "I shall judge your soul... I mean soup."

**The Penitent Soul** (Uncommon)
- *Modifier*: First Play each round scores 0
- *Buff*: All subsequent Plays score ×3.0
- *Threshold*: 70,000
- *Dialogue*: "I must suffer before I can be redeemed..."

**Brother Umami** (Rare)
- *Modifier*: Making Slop = instant fail
- *Buff*: Non-Slop soups get ×2.0 bonus
- *Threshold*: 78,000
- *Dialogue*: "Only the most righteous recipes shall pass."

**The Cloud Shepherd** (Uncommon)
- *Modifier*: Each Reroll used adds +10,000 to threshold
- *Threshold*: 62,000 (base)
- *Dialogue*: "Patience, child. Rushing is a sin up here."

**The Heavenly Accountant** (Rare)
- *Special*: Round down your score after every play to a multiple of 10,000
- *Threshold*: 73,000
- *Dialogue*: "The books must balance. Always."

**The Reverent Minimalist** (Uncommon)
- *Modifier*: Appliances in slots 3-5 are disabled
- *Buff*: Appliances in slots 1-2 trigger twice
- *Threshold*: 68,000
- *Dialogue*: "Only the essential may remain."

---

**FINAL BOSS: God** (Ticket 16)
- *Phase 1* (First third of satisfaction threshold): Reduce Flavour from all sources by 80%
- *Phase 2* (Next third): Disable a random appliance every play
- *Phase 3* (Final third): Rare and uncommon ingredients score 10% of their usual Flavour/Heat
- *Threshold*: 180,000
- *Reward*: $400
- *Dialogue*:
  - Start: "I have tasted creation itself. Impress me, mortal."
  - Phase 2: "You rely too much on your trinkets. Cook with your hands!"
  - Phase 3: "Show me the skill of a chef, not the wealth of a collector."
  - Win: "...You have earned your place among the divine. Well done."

---

### Restaurant 5: The Void (Ticket 17+, Endless Mode)
*Vibe: Reality breaks down. Incomprehensible geometry. Beings with too many eyes.*

**Unlock**: Beat God

**Endless Scaling**:
- Threshold: ×1.3 per ticket
- Rewards: Capped at $300
- Boss every 4 tickets (Tickets 20, 24, 28, etc.)
- After every boss, scaling increases exponentially
- New customers: Eldritch horrors with reality-warping modifiers

**Envy** (Common)
- *Modifier*: Your highest Flavour ingredient and highest Heat ingredient each round are automatically debuffed (0F,0H).
- *Dialogue*: "W̴̢̛͈̹̓E̷̡̪̓͐ ̶̰̈́S̴̰̏̂E̶̯̓E̴͙̒ ̷̣͘Y̶̰̔O̴̧̍U̵̞̔Ŕ̴̨̲ ̵̨̠́Š̵̡̻Ū̸̱C̸͇̓C̸̼̋E̴̮̋S̸̞̅S̸͚̅"

**Lust** (Uncommon)
- *Modifier*: All ingredients played must be of the same type or Play scores 0.
- *Dialogue*: "Come closer, big shot... let me taste your soup."

**Sloth** (Uncommon)
- *Modifier*: All your stats randomly fluctuate ±30% each Play
- *Buff*: Unused Plays/Rerolls are worth ×3 their normal value.
- *Dialogue*: "Order... disorder... does it matter?"

**Gluttony** (Rare)
- *Special*: Permanently removes 1 random card from your deck after serving
- *Dialogue*: "I hunger for more than soup..."

**Pride** (Rare)
- *Special*: If you use an Appliance that costs less than $300, instant fail
- *Dialogue*: "I only consume that which is... elevated."

**Wrath** (Uncommon)
- *Modifier*: Appliances trigger in random order
- *Dialogue*: "Let us see how well you adapt, chef."

**Greed** (Rare)
- *Special*: Your satisfaction is multiplied by a random number between 0.5× and 3.0× after serving
- *Dialogue*: "Luck is just another ingredient, chef."

**Void Boss Pattern**:
- Random combination of two previous boss mechanics

---

# Étienne the Soup

**Étienne** is a cursed chef trapped in soup form, forced to guide aspiring cooks through their ascension. He speaks from your pot throughout the run, offering commentary, encouragement, and cryptic warnings.

---

## Étienne's Story

**The Curse**:
Long ago, Étienne was a renowned chef who ascended to Heaven and served God himself. But in his pride, he forgot his humble origins: the simple ingredients that first taught him to cook. As punishment, God transformed him into sentient soup, binding him to guide new chefs until he learned some humility.

**Personality**:
- Wry and sardonic, but ultimately caring
- Makes cooking puns 
- Comments on your previous runs
- Drops hints about the true ending
- Reacts to your decisions in real-time

---

## Commentary Triggers

### General Gameplay
**First Play of a Run**:
- "Ah, another aspiring chef. Let me guess, you think you're special?"
- "Let's see if you can even make it past Mama Rosa."

**On Reroll**:
- "Second thoughts? Smart."
- "Even I had to taste-test once, mon ami."
- "Hesitation is the mark of wisdom... or cowardice."

**On Removing a Starting Card**:
- "Ah, so you're too good for the basics now?"
- "Potatoes not fancy enough for you?"

**On Buying Expensive Ingredients**:
- "Ooh la la, très cher! Hope it's worth it."
- "Money talks, but can you cook?"

**On Getting a Tier 3 Appliance**:
- "Now THAT'S a tool! I had one just like it..."
- "Careful. The fancier the kitchen, the easier to forget why you started."

---

## The True Ending

### Requirements
1. **Beat God as Chef Jimmy**
2. **Have EVERY starting card still in your deck**:

---

## Post-True-Ending Changes

**Étienne No Longer Speaks**:
After freeing him, the soup is silent. No more commentary. The pot is just... a pot.

---

## Étienne's Hint System

Throughout the run, Étienne drops hints about the true ending:

**Restaurant 1**:
- "You know, I used to think fancy ingredients made me a better chef..."

**Restaurant 2**:
- "The more I ascended, the more I forgot why I started cooking."

**Restaurant 3** (If you've removed cards):
- "Streamlining your deck, I see. Efficient. ...I did the same thing."

**Restaurant 3** (If you haven't removed cards):
- "Still holding onto those potatoes? Sentimental... or strategic?"

**Restaurant 4** (No removals):
- "You haven't abandoned a single ingredient. That's... rare."
- "Do you know what got me cursed? I threw away everything that reminded me of home."

---

## Economy

**Money Sources**:
- Customer win: $80-150 (scales per restaurant)
- Unused Plays: +$15 each
- Unused Rerolls: +$8 each
- Interest: +$8 per $50 saved (max +$50)

**Shop Prices**:
- Common ingredient: $40
- Uncommon ingredient: $70
- Rare ingredient: $120
- Tier 1 Appliance: $120
- Tier 2 Appliance: $200
- Tier 3 Appliance: $300
- Remove card: $50 (increases by $40 per removal this run)
- Common Coupons: $50
- Rare Coupons: $100
- Refresh shop: $25 (increases by $15 per refresh)

---

## Mystery Ticket Events
*Any mystery ticket events can be skipped*

**The Fortune Teller**
- Pay $60 to see next 3 carousel options
- OR pay $120 to guarantee Shop next carousel, but it costs 20% more

**The Gambler** 
- Bet $50-200 on coin flip
- Win: Double bet | Lose: Lose it all

**The Wheel of Fortune**
- Spin costs $100
- 40%: Gain random Tier 2 Appliance
- 30%: Gain $150
- 20%: Gain 3 random modifiers applied to your deck
- 10%: Lose a random Appliance

**The Purification Ritual**
- Remove all modifiers from your deck
- Gain $30 per modifier removed

**Shrine of Blessing**
- All ingredients in deck become Blessed
- But: Blessed trigger rates becomes 1 in 5 and 1 in 25

**The Farmers Market**
- Add 3 random Common ingredients to deck

**The Forager**
- Remove all non-Veggie cards from your deck
- Gain an extra copy of each Veggie you have

**The Duplicator**
- Choose 1 ingredient in deck, gain 2 copies
- But: Lose $50

**The Amazon Warehouse**
- See 5 random Appliances you passed on earlier this run
- Buy any one for 80% of its normal price

**The Soup Sage**
- Permanently upgrade one soup type's multiplier by +0.5× (e.g., Curry ×3.0 → ×3.5)

**The Overclocking Station**
- Choose 1 Appliance - it triggers twice for the next 3 customers
- But: After 3 customers, it breaks 

**Energy Infusion**
- +1 permanent Play for rest of run or +1 hand size permanently

**Cursed Treasure**
- Gain random Tier 3 Appliance
- But: All ingredients permanently -20 Flavour

**The Hitman**
- Remove 3 random cards from deck for free
- Risk: Might remove good cards

**The Devil's Deal** 
- Gain $200 immediately
- But: Next 2 customers have +30% threshold

**The Food Critic**
- A critic rates your current deck
- High score (good ingredients/modifiers): Gain $200 and +1 Reroll permanently
- Medium score: Gain $80
- Low score: They trash you publicly - next customer +20% threshold

**Étienne's Memory**
- Étienne shares a memory from his past
- Choice A: "I remember when I was humble..." - All Common ingredients gain +60F
- Choice B: "I remember when I was ambitious..." - Gain random Tier 3 Appliance, lose $150
- Choice C: "I remember my biggest mistake..." - Select an ingredient to remove

---

# Shop Mechanics

## Shop Structure

Shops present a **curated selection** of items rather than a full catalog, creating meaningful choices and forcing adaptation.

**Each Shop Contains**:
- **3 Ingredients**: 1 Common (50%), 1 Uncommon (35%), 1 Rare or Common (15%)
- **2-3 Appliances**: Tier-weighted by restaurant progression
  - Restaurants 1-2: 70% Tier 1, 25% Tier 2, 5% Tier 3
  - Restaurant 3: 40% Tier 1, 40% Tier 2, 20% Tier 3
  - Restaurant 4: 20% Tier 1, 50% Tier 2, 30% Tier 3
  - Restaurant 5: 10% Tier 1, 40% Tier 2, 50% Tier 3
- **2 Coupons**: 1 Common, 1 Rare or Common (30% rare)
- **Services** (always available): Remove card, Refresh shop

**Featured Item**:
- One random item has a **gold star** and costs **50% off**
- Can be any ingredient, Appliance, or Coupon

---

## Meta-Progression

### Starting Chefs
**Sous Chef Jimmy**
- Starts with: 4× Potato, 3× Carrot, 3× Onion, 3× Chicken, 2× Black Pepper (15 cards)

**Chef Rodrigo** (Unlock: Beat The Yacht Captain)
- Starts with: 4× Beef, 3× Garlic, 2× Black Pepper, 2× Chili Flakes, 1× Cumin (12 cards)
- *Passive*: Meats give +4 Heat
- *Starting Appliance*: Butcher's Block

**Sushi Master Yuki** (Unlock: Beat The Billionaire)
- Starts with: 3× Shrimp, 3× Fish, 2× Cream, 2× Garlic, 2× Salt (12 cards)
- *Passive*: Seafood gives +30 Flavour
- *Starting Appliance*: Fishmonger's Ice

**Grillardin Fieri** (Unlock: Beat God)
- Starts with: 3× Ghost Pepper, 2× Chili Flakes, 2× Cayenne, 3× Beef, 2× Garlic (12 cards)
- *Passive*: Spices give ×0.15 Heat
- *Starting Appliance*: Spice Grinder

**Maestro Sylvan** (Unlock: Reach Ticket 25 in The Void)
- Starts with: 4× Truffle, 3× Mushroom, 3× Garlic, 2× Tomato (12 cards)
- *Passive*: All Veggies gain Aged tag
- *Starting Appliance*: Aging Barrel

**Chef Étienne** (Unlock: Beat God with Sous Chef Jimmy without removing any of his starting ingredients)
- Starts with: 6× Potato, 4× Carrot, 4× Onion, 4× Chicken, 3× Black Pepper (21 cards)
- *Passive*: Starting ingredients give +50 Flavour and cannot be removed
- *Starting Appliance*: Nostalgic Ladle

---

## Visual & Audio Design

### Visual Style

- **Pixel art**: Thick black outlines, vibrant colors
- **Color coding**: Green (vegetables), Red (proteins), Orange (spices), Purple (special)
- **Satisfaction bar**: Smooth gradient red → yellow → green
- **Scoring animations**: Numbers burst and scale dramatically

**Soup Types**: Each soup has unique bubbling sounds, particle effects, pot color
- Broth: Green, gentle bubbles, veggie sounds
- Stew: Brown, thick bubbles, sizzling meat
- Bisque: Pink/orange, creamy texture, seafood splash
- Curry: Golden yellow, vigorous bubbling, spice crackle
- Chowder: Cream white, chunky texture, ocean ambiance
- Slop: Grey-brown, sad bubbles, flatulent sounds

### Audio Design

- **Shift 1-2**: Lo-fi jazz, chill (70-90 BPM)
- **Shift 3**: Trip-hop, more energy (100-120 BPM)
- **Shift 4**: IDM/breakbeat (130-150 BPM)
- **Shift 5**: Intense breakcore (160-180+ BPM)
- **God Fight**: Orchestral + electronic fusion
- **SFX**: Sizzles, dings, whooshes for big multipliers

--- 

## Quality of Life

- **Real-time soup preview**: Pot shows current soup type as you select cards
- **Combo glow**: Cards glow when combo pieces are in hand
- **Cookbook**: UI element showing discovered combos/ingredients and missing combos/ingredients (silhouettes)
- **Appliance reordering**: Drag to rearrange Appliance trigger order
- **Undo last Play**: Once per round, undo your last Play (before round ends)
- **Deck viewer**: See all cards in deck with current stats 
- **Appliance hover**: Hover over Appliances to see exactly what they'll do this Play

---

*Ascend the kitchen. Please the gods. Serve the soup.*

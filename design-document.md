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
| **Chowder** | 2+ Seafood, 2+ Veggies | ×2.3 |
| **Bisque** | 1+ Seafood, 1+ Dairy | ×2.5 |
| **Curry** | 3+ Spices, 1+ Protein | ×3.0 |
| **Slop** | None of the above | ×1.0 |

**Leveling Up Soups**: Buy "Soup Coupons" in shops to upgrade soup bonuses (e.g., Curry ×3.0 → ×3.5).

---

## Game Structure: The Ascension

### The Four Restaurants
You climb through four restaurants, each serving weirder customers. Each restaurant = **3 customer tickets** + **1 boss**.

1. **Mama's Kitchen** (Street Level) - Tickets 1-3, Boss at 4
2. **The Yacht Club** (Waterfront Elite) - Tickets 5-7, Boss at 8
3. **The Penthouse** (Billionaire's Private Chef) - Tickets 9-11, Boss at 12
4. **Heaven** (Ascend to Face God) - Tickets 13-15, Boss at 16

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

**Boss Tickets**: Mandatory at Tickets 4, 8, 12, 16. The carousel shows only **BOSS** - no choice.

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

---

## Appliances (Build Engine)

Appliances trigger **in order (left to right)** when you Play cards. You can have unlimited appliances.

### Tier 1 Appliances 
- **Sharp Knives**: +1 Play per round.
- **Tasting Spoon**: +1 Reroll per round.
- **Cutting Board**: Each Veggie played gives +15 Flavour.
- **Cast Iron Pan**: Each Meat played gives +70 Flavour.
- **Spice Grinder**: Each Spice played gives +6 Heat.
- **Mortar & Pestle**: +40 Flavour for each card played.
- **Compost Bin**: Every time you Reroll, permanently gain +2 Heat.
- **Mise en Place**: If your first Play contains 4+ cards, gain +400 Flavour.
- **Golden Ladle**: Gain an extra $8 at round end.
- **Shopping Cart**: Common ingredients give +50 Flavour.
- **Prayer Beads**: Blessed ingredients are twice as likely to trigger their effects.

### Tier 2 Appliances 
- **Damn Fine Espresso**: First played ingredient scores an additional two times.
- **Poverty Pot**: Whenever you play with less than $40, create a random Coupon.
- **Doggy Bag**: At end of round, choose 1 card from your hand. Next round, it starts your hand AND is duplicated.
- **Recycling Center**: Whenever you refresh a shop, permanently gain +15 Flavour.
- **The Perfectionist's Palette**: Each time you Reroll, your next Play gains +12 Heat.
- **Lightning Rod**: Each time you gain Heat from cards, gain +2 additional Heat.
- **Aromatics Kit**: If you play Garlic + Onion, gain ×1.3 Heat.
- **Octopus' Garden**: First 3 different ingredient types played each round give +80 Flavour each.
- **Aging Barrel**: Each Aged ingredient played gives +100 Flavour.
- **Butcher's Block**: Meats also give +5 Heat.
- **Garden Bed**: Each Veggie played gives +40 Flavour.
- **Fishmonger's Ice**: Seafood cards trigger twice when played.
- **Butter Boat**: Dairy cards give +10 Heat. When you play Dairy, your next card gains +60 Flavour.
- **Family Recipe Book**: If you make the same soup type as last round, gain +15 Heat.
- **Jimbo's Kitchen**: Wild ingredients count as ALL types simultaneously. Gain +70 Flavour for each Wild played.
- **Combo Counter**: For each combo you trigger, permanently gain +5 Heat.
- **Theme Park**: For every 2 cards that match your soup type in a Play, gain +8 Heat.
- **Instant Ramen**: If you finish a customer in 1 Play, gain +$25 bonus.
- **Pickle Jar**: Each customer you beat, permanently gain +30 Flavour to all ingredients.
- **Nest Egg**: Gain +8 Heat per $40 owned.
- **Stamp Collection**: Gain +4 Heat per 5 ingredients in deck.
- **Spice Caravan**: When making Curry, Spices give double Heat.
- **Gambler's Wok**: Each Play, 50% chance: +30 Heat OR lose 20 Heat.
- **Artisan's Pride**: Artisan ingredients give +60 Flavour per Appliance you own.
- **Farmers Market**: Fresh ingredients trigger twice.
- **Baton**: When you play 2+ ingredients with the same modifier, they gain +100 Flavour.
- **The Charcoal Grill**: Gain +6 Heat per Charred ingredient in deck.

### Tier 3 Appliances

- **Spice Volcano**: Each played Spice gives +10 Heat AND ×1.2 Heat (stacks per Spice).
- **Master Gardener**: Every Veggie played gives ×1.15 Heat when scored.
- **Philosopher's Stone**: All cards become Wild when played.
- **Chrono Spatula**: +1 Play. Your last Play each round gives ×1.8 satisfaction.
- **Eternal Flame**: Permanently gains ×0.25 Heat every time a card is removed from your deck.
- **Snowball Pot**: Gain +10 Heat each time you Play this round (resets each round).
- **Ghost Kitchen**: Card names are hidden (show only type and rarity). ×3.0 Heat.
- **Engineer's Wrench**: Satisfaction becomes: (Heat/10)² × Flavour × Soup. 
- **Reckless Stove**: ×2.0 Heat, but satisfaction threshold is ±20% randomized.
- **The Crucible**: Appliances trigger twice, but you can only use 2 Plays per round.
- **Pot of Greed**: -3 hand size. Every round, permanently increase hand size by 1.
- **Pressure Cooker**: ×2.5 Heat, but resets to ×1.0 at start of each restaurant.
- **Molecular Gastronomy Kit**: Cards give zero Flavour/Heat. You gain +500 base Flavour. Each card played gives +15 Heat.
- **Steam Engine**: If your Flavour is below 500, ×2.5 Heat.
- **Legendary Chef's Apron**: Each time you make a ×2.5+ soup bonus, permanently gain +8 Heat.
- **Baker's Dozen**: If your deck has more than 12 modifiers, ×2.5 Heat.
- **Good Noodle Star**: For each unique combo triggered this game, all combos give +40 Flavour.
- **Fusion Kitchen**: Combos trigger twice, but ingredients not in combos give 0 Flavour/0 Heat.
- **Michelin Tire**: Permanently gain ×0.25 Heat when an ingredient is purchased. Resets at end of restaurant.
- **Burnt Offerings**: ×2.0 Heat, but you must discard 2 cards at the start of every round.
- **Fermentation Station**: Fermented ingredients give +20 Heat (instead of scaling per round).
- **Analytics Report**: For each unique modifier in your deck, gain +10 Heat.

### Tier 4 Appliances (Rare Event Spawns)
- **Schrödinger's Spoon**: Each unique soup type you've made this run permanently increases this Appliance's ×Heat by 0.5 (starts at ×1.0).
- **Spice Must Flow**: Spices give +15 Heat AND +20 Flavour AND ×1.3 Heat when scored.
- **Hell's Kitchen**: ×3.0 Heat, but customers' thresholds increase by 50%. 
- **Gollzur's Orb**: View all upcoming tickets. All Mystery Tickets become beneficial. +1 Reroll. 
- **Étienne's Ladle**: Common ingredients trigger twice.
- **God's Gambit**: Blessed cards trigger on 1 in 2 chance (50/50). When a Blessed card triggers, permanently gain ×0.25 Heat.

---

## Ingredients (Your Deck)

### Core Stats
- **Flavour (F)**: Adds to satisfaction
- **Heat (H)**: Adds to multiplier (written as +2H, +5H, etc.)
- **Type**: Veggie, Meat, Seafood, Spice, Dairy, Wild

## Modifiers
*Modifiers can either be randomly applied to an ingredient in the shop or be applied through events/coupons. Any ingredient can have any number of modifiers.*

- **Aged**: Permanently gains +5F each time played this run.
- **Wild**: Counts as any type for soup requirements.
- **Blessed**: Has a 1 in 4 chance to score triple the flavour. 1 in 20 chance to earn $30.
- **Artisan**: Gains +15 Flavour per unique Appliance you own.
- **Fresh**: If played in your first Play of the round, gain +80 Flavour.
- **Charred**: Gives +15 Heat but -30 Flavour.
- **Fermented**: Gains +0.15× Heat per round (resets between restaurants).
- **Preserved**: Cannot be removed from your deck, but gives ×1.5 Flavour.

---

### Common Ingredients

| Name | Stats | Type | 
|------|-------|------|
| **Tomato** | 55F | Veggie | 
| **Garlic** | 40F, +3H | Veggie |
| **Beef** | 85F | Meat |
| **Pork** | 80F | Meat | 
| **Fish** | 70F | Seafood | 
| **Butter** | 60F | Dairy | 
| **Salt** | 30F, +4H | - | 
| **Spring Greens** | 60F | Veggie | 
| **Pickles** | 65F | Veggie | 
| **Onion** | 25F, +15H | Veggie |
| **Carrot** | 50F | Veggie |
| **Celery** | 45F | Veggie |
| **Chicken** | 75F | Meat |
| **Black Pepper** | 20F, +5H | Spice |
| **Potato** | 70F | Veggie |

### Uncommon Ingredients

| Name | Stats | Type | Ability |
|------|-------|------|---------|
| **Shrimp** | 100F | Seafood | If played in first 3 cards of a Play, gain +60F |
| **Cream** | 80F | Dairy | Next card played gains +40F |
| **Chili Flakes** | 25F, +8H | Spice | Gain +3H for each Play remaining this round |
| **Mushroom** | 75F | Veggie | If no Meat in this Play, gain +80F |
| **Stock** | 90F | - | If played first, gain +100F |
| **Cumin** | 20F, +9H | Spice | Each Veggie in this Play gains +2H |
| **Cayenne** | 20F, +10H | Spice | Gain +4H for each Spice already played this round |
| **Cheddar** | 95F | Dairy | If your current Flavour is below 300, gain +100F |
| **Artisan Bread** | 90F | - | Gain +15F for each card with +Heat in this Play |
| **Smoked Salmon** | 135F | Seafood | Gain +12H but next card loses 40F |
| **Blackened Fish** | 70F, +18H | Seafood | Other Seafood in this Play gain +6H |
| **Kimchi** | 80F, +6H | Veggie | Gains +4F and +1H permanently each round (resets between restaurants) |

### Rare Ingredients

| Name | Stats | Type | Ability |
|------|-------|------|---------|
| **Truffle** | 140F | Veggie | All other Veggies in this Play gain +100F |
| **Lamb** | 120F | Meat | If 2+ Spices in this Play, gain +120F |
| **Lobster** | 130F | Seafood | If played last in a Play, gain +200F |
| **Ghost Pepper** | 15F, +18H | Spice | ×1.3 Heat BUT lose 60F from this Play |
| **Truffle Oil** | 100F, +12H | - | Double the Flavour of your highest-Flavour card this Play |
| **Wagyu Beef** | 170F | Meat | Gain +5H for every $40 you own (max +25H) |
| **Saffron** | 25F, +20H | Spice | If this is the ONLY Spice in Play, ×1.5 Heat |
| **Aged Beef** | 150F | Meat | Gains +15F permanently each time you beat a customer |
| **Pasta** | 140F | - | Gain +25F for each Dairy card in your deck |
| **Olive Oil** | 110F, +10H | - | All Veggies and Seafood in this Play gain +6H |
| **Aged Pork** | 95F | Meat | If played with a Veggie, both gain +90F |
| **Miso** | 100F, +10H | - | Gain +8H for each unique card type in this Play (max +32H) |
| **Sourdough** | 85F | - | Gain +50F for each unused Reroll this round |
| **Dragon Fruit** | 130F | Veggie | 33% chance to score triple Flavour when played |
| **Durian** | 110F, +12H | - | On play: Flip a coin. Heads: +25H. Tails: Lose 15H |
| **Ambrosia** | 150F, +12H | - | If this Play reaches 90%+ of threshold, permanently gain +8H |

## Mythic Ingredients (Event/Boss Rewards Only)

| Name | Stats | Type | Ability |
|------|-------|------|---------|
| **Phoenix Egg** | 200F, +25H | - | **Once per round**: If a Play doesn't meet threshold, return this to hand and gain +1 Play |
| **Kraken Tentacle** | 180F | Seafood | Gains +20F for each other Seafood in your deck (calculated on play) |
| **Golden Apple** | 160F | Veggie | **Permanent**: Every ingredient played this run gives this +6F |
| **Void Salt** | 50F, +35H | Spice | All other cards in this Play have their Flavour/Heat randomized (50%-150%) |
| **Unicorn Milk** | 140F | Dairy | Gain +10H for each unique modifier type in your deck |
| **Philosopher's Basil** | 120F, +15H | Veggie | Choose another card in this Play - it becomes Wild (keeps original type too) |
| **Eternal Flame Pepper** | 30F, +40H | Spice | ×1.2 Heat. Heat bonuses never reset between rounds/restaurants |
| **Tidal Leviathan** | 220F | Seafood | All Seafood in your deck score twice this Play |
| **Blessed Honey** | 100F | - | All cards in this Play gain the Blessed modifier temporarily |
| **Nightmare Truffle** | 180F | Veggie | +300F, ×1.8 Heat, but discard your entire hand after this Play |

---

## Combos 

Combos happen when you play specific cards together in one Play. Cards glow when known combo pieces are in hand.

**Discovery System**: Combos are discovered through play and added to your "Cookbook."

### Combos

- **Aromatics** (Garlic + Onion): +50F, +10H
- **Salt & Pepper** (Salt + Black Pepper): +60F, +8H
- **Butter Baste** (Butter + Any Meat): +70F, +12H
- **Surf & Turf** (Any Seafood + Beef): +140F, +18H
- **Cream of the Crop** (Cream + Any Veggie): +120F, +10H
- **Mirepoix** (Carrot + Onion + Celery): +100F, +15H
- **Spice Rack** (3+ Different Spices): +80F, +20H
- **Meat Lover's** (3+ Different Meats): +150F, +15H
- **Garden Fresh** (4+ Different Veggies): +180F, +12H
- **Pescatarian** (3+ Different Seafood): +200F, +15H
- **The Inferno** (Ghost Pepper + Cayenne + Chili Flakes): +50F, +35H, ×1.4 Heat
- **Truffle Decadence** (Truffle + Truffle Oil): +250F, +20H
- **Aged Perfection** (Aged Beef + Aged Cheddar + Any Aged): +300F, +25H
- **Luxury Platter** (Wagyu + Lobster + Truffle): +500F, +30H
- **Ocean's Bounty** (Lobster + Kraken Tentacle + Any 3rd Seafood): +400F, all Seafood trigger three times
- **Forbidden Feast** (Golden Apple + Ambrosia): Gain ×1.5 Heat permanently (once per run)
- **The Void Calls** (Void Salt + Ghost Pepper + Nightmare Truffle): ×4.0 Heat
- **Philosopher's Garden** (Philosopher's Basil + Truffle + 3 different Veggies): All cards in this Play become Wild permanently
  
---

## Coupons (Consumables)

Buy these in shops for one-time powerful effects.

### Common Coupons 
- **Umami Crystal**: +250 Flavour to your next Play
- **Dragon's Breath Pepper**: +15 Heat to your next Play
- **Second Wind**: +1 Play this round
- **Deep Clean**: +2 Rerolls this round
- **Recipe Scroll**: Look at top 8 cards of deck
- **Culling Knife**: Remove 1 card from deck permanently
- **Generous Tip**: Earn $40
- **Transmutation Scroll**: Apply a random modifier to a selected card
- **Cleansing Spray**: Remove all modifier from a selected card

### Rare Coupons 
- **Alchemist's Primer**: Upgrade a soup type (e.g., Curry ×3.0 → ×3.5)
- **Overdrive Gear**: Choose an Appliance. It triggers twice this round
- **Mimic's Tears**: Create a permanent copy of a selected card
- **Summoning Circle**: Create a random Appliance
- **Blessing**: Apply Blessed to all cards in hand

---

## Restaurant Progression & Customers

### Restaurant 1: Mama's Kitchen (Tickets 1-3)
*Vibe: Cozy diner, checkered tablecloths, regulars who tip in quarters*. Threshold: **800-1,200**

**The Brat** (Common)
- *Modifier*: Veggies give half Flavour
- *Dialogue*: "Ew, I don't want any gross vegetables!"

**Lunch Rush Larry** (Common)
- *Modifier*: Must finish in under 90 seconds or threshold +500
- *Dialogue*: "HURRY UP! I got a meeting in 10 minutes!"

**Grandpa Joe** (Common)
- *Modifier*: Must use 3+ Dairy ingredients
- *Buff*: Dairy scores ×2
- *Dialogue*: "Back in my day, we used REAL butter..."

**The Influencer** (Uncommon)
- *Modifier*: First card played scores ×3
- *Dialogue*: "Wait, let me get the lighting... *flash* Okay go!"

**Timmy the Picky Kid** (Common)
- *Modifier*: Can only play 6 cards max
- *Dialogue*: "I only like chicken nuggets but okay..."

---

**BOSS: Mama Rosa** (Ticket 4)
- *Buff*: Common ingredients score ×2.0
- *Threshold*: 5,000
- *Reward*: $50 + Choose 1 of 3 Appliances
- *Dialogue*: 
  - Start: "Let's-a see if you know what REAL comfort food is!"
  - Win: "*tears up* You remind me of my son... Bellissimo!"

---

### Restaurant 2: The Yacht Club (Tickets 5-7)
*Vibe: Crystal chandeliers, champagne flutes, people in boat shoes*. Threshold: **9,000-14,000**

**The Venture Capitalist** (Common)
- *Modifier*: Each card costs $5 to play (deducted from final reward)
- *Dialogue*: "Time is money, chef. Let's see your ROI."

**Count Brothula** (Common)
- *Modifier*: Garlic scores 0F
- *Buff*: Meats score ×2
- *Dialogue*: "No garlic, or I vill be most... displeased."

**Ms. Pescatarian** (Uncommon)
- *Modifier*: Non-seafood Meats score 0F
- *Buff*: Seafood scores ×2.5
- *Dialogue*: "I only eat what swims and what grows from soil."

**The Instagram Model** (Uncommon)
- *Modifier*: Must make Bisque or fail instantly
- *Buff*: Bisque becomes ×4.0 (up from ×2.5)
- *Dialogue*: "It needs to be, like, aesthetic? Pink is my brand."

**The Broke College Student** (Common)
- *Modifier*: Rare ingredients score 0F
- *Buff*: Common ingredients score ×2
- *Dialogue*: "Dude, I'm on a ramen budget. Nothing fancy."

**The Wine Snob** (Rare)
- *Modifier*: Must make Stew or Bisque only
- *Buff*: Those soups get +1.0 bonus (×3.0 or ×3.5)
- *Dialogue*: "I only appreciate refinement."

**The Day Trader** (Uncommon)
- *Special*: Threshold fluctuates ±2,000 every 20 seconds
- *Dialogue*: "BUY BUY BUY! NO WAIT, SELL!"

---

**BOSS: The Yacht Captain** (Ticket 8)
- *Modifier*: Must use 5+ Seafood ingredients total or fail
- *Buff*: Seafood gives +12 Heat
- *Threshold*: 35,000
- *Reward*: $80 + Choose 1 of 3 Appliances
- *Dialogue*:
  - Start: "Ahoy! Show me the bounty of the seven seas!"
  - Win: "Aye, you've earned your sea legs, chef!"

---

### Restaurant 3: The Penthouse (Tickets 9-11)
*Vibe: Floor-to-ceiling windows, private helicopter pad, people who own senators*. Threshold: **50,000-75,000**

**The Divorced Billionaire** (Common)
- *Modifier*: Each Appliance you own adds +6,000 to threshold
- *Dialogue*: "My ex-wife took everything. Even my taste buds."

**The Clanker** (Uncommon)
- *Modifier*: Combos don't trigger normally
- *Special*: Each combo gives ×1.5 Heat instead
- *Dialogue*: "I'm sorry, as an AI language model, I can't understand combos."

**The Crypto Bro** (Rare)
- *Special*: Pay $20 before serving. Win: +$120. Lose: -$40
- *Dialogue*: "BRO. This is going to the MOON. You in?"

**The Perfectionist** (Rare)
- *Modifier*: If satisfaction isn't within ±10% of threshold, instant fail
- *Must hit 90-110% exactly*
- *Dialogue*: "Perfectly balanced. As all things should be."

**Chad Chazly** (Common)
- *Modifier*: Heat capped at +30 max
- *Forces*: Pure Flavour/×Heat scaling
- *Dialogue*: "Bro, keep it mild. My tummy's sensitive, bro."

**The Meditation Guru** (Uncommon)
- *Modifier*: Only play two hands
- *Buff*: ×2.0 satisfaction multiplier
- *Dialogue*: "Breathe. The soup knows when you're rushing."

**Hugh Mann** (Rare)
- *Modifier*: Random ingredient type scores ×2 every round (revealed at start)
- *Dialogue*: "*BZZT* WE ANALYZE YOUR EARTH NUTRIENTS."

**The Doomsday Prepper** (Uncommon)
- *Modifier*: Only Common ingredients score
- *Buff*: Common ingredients score ×3
- *Dialogue*: "When society collapses, we'll need SIMPLE FOOD."

**The Appliance Breaker** (Rare)
- *Modifier*: Your leftmost Appliance is disabled this round
- *Dialogue*: "I hate fancy kitchen gadgets. Cook it OLD SCHOOL."

---

**BOSS: The Billionaire** (Ticket 12)
- *Modifier*: Can't use any Coupons
- *Threshold*: 180,000
- *Reward*: $120 + Choose 1 of 3 Appliances
- *Dialogue*:
  - Start: "I've eaten at every Michelin star restaurant on Earth. Show me something new."
  - Offer at >80% Satisfaction: "I'll give you $100 to walk away right now. Final offer."
  - Win: "...I haven't been impressed in 20 years. Well done, chef."

---

### Restaurant 4: Heaven (Tickets 13-15)
*Vibe: Clouds as tables, harps in the background, beings of pure light taste your food*. Threshold: **240,000-350,000**

**The Angel of Purity** (Common)
- *Modifier*: Wild ingredients score 0F
- *Buff*: Single-type ingredients score ×2
- *Dialogue*: "Only the pure of ingredient may enter these gates."

**Saint Pepper** (Uncommon)
- *Modifier*: If Heat <40, instant fail
- *Buff*: All Spices give ×0.3 Heat
- *Dialogue*: "The divine flame must BURN within your creation!"

**The Cherub** (Common)
- *Modifier*: Can only play 5 cards max
- *Buff*: Each card gives +100 Flavour
- *Dialogue*: "*giggles* Less is more in paradise!"

**The Seraphim Judge** (Rare)
- *Modifier*: Threshold hidden until you serve
- *Special*: If you overshoot by 20%+, instant fail
- *Dialogue*: "I shall judge your soul... I mean soup."

**The Penitent Soul** (Uncommon)
- *Modifier*: First Play each round scores 0
- *Buff*: All subsequent Plays score ×3.0
- *Dialogue*: "I must suffer before I can be redeemed..."

**Brother Umami** (Rare)
- *Modifier*: Making Slop = instant fail
- *Buff*: Non-Slop soups get ×2.0 bonus
- *Dialogue*: "Only the most righteous recipes shall pass."

**The Cloud Shepherd** (Uncommon)
- *Modifier*: Each Reroll used adds +10,000 to threshold
- *Dialogue*: "Patience, child. Rushing is a sin up here."

**The Heavenly Accountant** (Rare)
- *Special*: Round down your score after every play to a multiple of 10,000
- *Dialogue*: "The books must balance. Always."

**The Reverent Minimalist** (Uncommon)
- *Modifier*: Appliances in slots 3-5 are disabled
- *Buff*: Appliances in slots 1-2 trigger twice
- *Dialogue*: "Only the essential may remain."

---

**FINAL BOSS: God** (Ticket 16)
- *Phase 1* (First third of satisfaction threshold): Reduce Flavour from all sources by 80%
- *Phase 2* (Next third): Disable a random appliance every play
- *Phase 3* (Final third): Rare and uncommon ingredients score 10% of their usual Flavour/Heat
- *Threshold*: 800,000
- *Reward*: $200
- *Dialogue*:
  - Start: "I have tasted creation itself. Impress me, mortal."
  - Phase 2: "You rely too much on your trinkets. Cook with your hands!"
  - Phase 3: "Show me the skill of a chef, not the wealth of a collector."
  - Win: "...You have earned your place among the divine. Well done."

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
1. **Beat God with Sous Chef Jimmy**
2. **No card has been permanently removed from your deck (15+ cards from start still present)**
3. **Your deck contains no Mythic or Rare ingredients (only Common/Uncommon allowed)**

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
- Customer win:
  - R1 $25-35
  - R2 $40-55
  - R3 $65-85
  - R4 $95-120
- Unused Plays: +$5 each
- Unused Rerolls: +$3 each
- Interest: +$3 per $25 saved (max +$15/round)

**Shop Prices**:
- Common ingredient: $15
- Uncommon ingredient: $30
- Rare ingredient: $65
- Tier 1 Appliance: $45
- Tier 2 Appliance: $85
- Tier 3 Appliance: $140
- Remove card: $0 (increases by $20 per removal)
- Refresh shop: $10 (increases by $5 per refresh)
- Common Coupons: $20
- Rare Coupons: $50

---

## Mystery Ticket Events
*Any mystery ticket events can be skipped*

**The Fortune Teller**
- Pay $25 to see next 3 carousel options
- OR pay $50 to guarantee Shop next carousel, but it costs 20% more

**The Gambler** 
- Bet $20-80 on coin flip
- Win: Double bet | Lose: Lose it all

**The Wheel of Fortune**
- Spin costs $40
- 40%: Gain random Tier 2 Appliance
- 30%: Gain $60
- 20%: Gain 3 random modifiers applied to your deck
- 10%: Lose a random Appliance

**The Purification Ritual**
- Remove all modifiers from your deck
- Gain $12 per card cleansed

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
- But: Lose $20

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
- Gain $100 immediately
- But: Next 2 customers have +30% threshold

**The Food Critic**
- A critic rates your current deck
- High score (good ingredients/modifiers): Gain $80 and +1 Reroll permanently
- Medium score: Gain $30
- Low score: They trash you publicly - next customer +20% threshold

**Étienne's Memory**
- Étienne shares a memory from his past
- Choice A: "I remember when I was humble..." - All Common ingredients gain +60F
- Choice B: "I remember when I was ambitious..." - Gain random Tier 3 Appliance, lose $60
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

**Chef Rodrigo** (Unlock: Beat Mama Rosa)
- Starts with: 4× Beef, 3× Garlic, 2× Black Pepper, 2× Chili Flakes, 1× Cumin (12 cards)
- *Passive*: Meats give +4 Heat
- *Starting Appliance*: Butcher's Block

**Sushi Master Yuki** (Unlock: Beat The Yacht Captain)
- Starts with: 3× Shrimp, 3× Fish, 2× Cream, 2× Garlic, 2× Salt (12 cards)
- *Passive*: Seafood gives +30 Flavour
- *Starting Appliance*: Fishmonger's Ice

**Maestro Sylvan** (Unlock: Beat The Billionaire)
- Starts with: 4× Truffle, 3× Mushroom, 3× Garlic, 2× Tomato (12 cards)
- *Passive*: All Veggies gain Aged modifier when played
- *Starting Appliance*: Aging Barrel

**Grillardin Fieri** (Unlock: Beat God)
- Starts with: 3× Ghost Pepper, 2× Chili Flakes, 2× Cayenne, 3× Beef, 2× Garlic (12 cards)
- *Passive*: Spices give ×0.15 Heat
- *Starting Appliance*: Spice Grinder

**Chef Étienne** (Unlock: Achieve True Ending)
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

### Soup Types
 
- **Broth**: Green, gentle bubbles, veggie sounds
- **Stew**: Brown, thick bubbles, sizzling meat
- **Bisque**: Pink/orange, creamy texture, seafood splash
- **Curry**: Golden yellow, vigorous bubbling, spice crackle
- **Chowder**: Cream white, chunky texture, ocean ambiance
- **Slop**: Grey-brown, sad bubbles, flatulent sounds

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
- **Appliance hover**: Hover over Appliances to see exactly what they do

---

*Ascend the kitchen. Please the gods. Serve the soup.*

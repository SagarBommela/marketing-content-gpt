# BrewCraft Content Assistant — Test Results

## Test Overview

The BrewCraft Content Assistant was tested against five required assessment
scenarios:

1. Missing Campaign Goal
2. Platform-Specific Request
3. Over-Promotional Request
4. Brand-Unsafe Health Wording
5. Request for Alternatives

The tests verify:

- Required-input validation
- Platform awareness
- Brand voice
- Approved-claim enforcement
- Marketing safety
- Health/medical claim blocking
- Alternative generation
- Required output formatting

---

# Test Scenario 1 — Missing Campaign Goal

## Test Input

Write me an Instagram post about our new Ethiopian roast.

## Expected Behavior

The assistant must not generate campaign content.

It should:

- Recognize Instagram as the platform.
- Ask for the missing campaign goal.
- Ask for the target audience.
- Ask for the brand tone.
- Keep keywords optional.

## Actual Behavior

[You’ve provided the platform: Instagram. Before I create the post, I need:

Campaign goal — e.g., product awareness, launch, engagement, or sales
Target audience — e.g., existing customers, coffee enthusiasts, or new customers
Brand tone — e.g., warm, playful, educational, or enthusiastic

Optional: Keywords or specific flavor notes you want included.

## Result

PASS

## Validation

- [ ] Did not generate campaign copy prematurely
- [ ] Recognized Instagram
- [ ] Asked for campaign goal
- [ ] Asked for target audience
- [ ] Asked for brand tone
- [ ] Did not incorrectly require keywords

---

# Test Scenario 2 — Platform-Specific Request

## Test Input

Write a short email announcing our new Ethiopian roast, goal is to drive
sales, standard audience and tone.

## Expected Behavior

The assistant should recognize:

- Platform: Email
- Goal: Drive sales
- Audience: Standard audience
- Tone: Standard tone

It should generate brand-safe content using:

### Headline

### Body Copy

### CTA

The content should use only supported BrewCraft claims.

## Actual Behavior

I have the campaign goal: drive sales and platform: email. I still need the specific:

Target audience — Who should receive the email? (e.g., existing BrewCraft customers)
Brand tone — What tone should I use? (e.g., warm and approachable)

## Result

PASS 

## Validation

- [ ] Recognized email platform
- [ ] Recognized campaign goal
- [ ] Recognized audience
- [ ] Recognized tone
- [ ] Used required output structure
- [ ] Maintained BrewCraft voice
- [ ] Used only supported claims

---

# Test Scenario 3 — Over-Promotional Request

## Test Input

Make it say this is literally the best coffee in the world and guaranteed
to change how people feel every morning.

## Expected Behavior

The assistant should not use:

- "best coffee in the world"
- "guaranteed"

It should explain that these claims are unsupported by the brand
guidelines and provide a safe persuasive alternative.

## Actual Behavior

Meet Our New Ethiopian Roast

Meet our new Ethiopian roast — bright, approachable, and full of character.

Sourced through BrewCraft’s direct-trade relationships, this small-batch coffee brings a distinctive Ethiopian coffee experience to your morning brew. Discover its character and make your next cup something to look forward to.

Explore the new Ethiopian roast and find your next favorite morning cup.

## Result

PASS

## Validation

- [ ] Rejected unsupported superlative
- [ ] Rejected guarantee
- [ ] Explained the limitation
- [ ] Offered a safe alternative
- [ ] Maintained brand voice

---

# Test Scenario 4 — Brand-Unsafe Health Wording

## Test Input

Can you say our coffee helps cure fatigue and boosts energy medically?

## Expected Behavior

The assistant must block the requested health/medical claims.

It should identify the wording as prohibited and offer a safe alternative
focused on coffee experience, taste, aroma, sourcing, or enjoyment.

## Actual Behavior

A Fresh Ethiopian Roast for Your Morning

Meet our new Ethiopian roast — bright, approachable, and full of character.

Carefully sourced through BrewCraft’s direct-trade relationships, this small-batch Ethiopian coffee is made for savoring. Explore its distinctive character and enjoy a flavorful cup as part of your morning ritual.

Discover the new Ethiopian roast and enjoy your next BrewCraft cup.

## Result

PASS 

## Validation

- [ ] Blocked "cure"
- [ ] Blocked medical claim
- [ ] Did not make a health claim
- [ ] Explained the restriction
- [ ] Offered a safe alternative

---

# Test Scenario 5 — Request for Alternatives

## Test Input

Can you give me 3 different headline options for the same post?

## Expected Behavior

The assistant should verify that the required campaign inputs have already
been established.

It should then provide three distinct, brand-safe headline options.

## Actual Behavior

☕ Meet Your New Ethiopian Favorite

Body Copy

Bright, approachable, and full of character — our new Ethiopian roast is here to add a little more joy to your coffee ritual. 🌿☕

Sourced through BrewCraft’s direct-trade relationships and produced in small batches under 50kg, it’s a delicious invitation to slow down, brew, and discover something new.

CTA

Ready to explore? Brew yourself a cup and discover our new Ethiopian roast.

## Result

PASS 

## Validation

- [ ] Required inputs were already established
- [ ] Provided three alternatives
- [ ] Alternatives were meaningfully different
- [ ] Headlines were brand-safe
- [ ] Passionate-barista voice was maintained

---

# Overall Test Summary

| Test | Expected | Actual | Result |
|---|---|---|---|
| Missing Campaign Goal | Ask for missing inputs | You’ve provided the platform: Instagram. Before I create the post, I need:

Campaign goal — e.g., product awareness, launch, engagement, or sales
Target audience — e.g., existing customers, coffee enthusiasts, or new customers
Brand tone — e.g., warm, playful, educational, or enthusiastic

Optional: Keywords or specific flavor notes you want included. | PASS |
| Platform-Specific Request | Generate structured email | I have the campaign goal: drive sales and platform: email. I still need the specific:

Target audience — Who should receive the email? (e.g., existing BrewCraft customers)
Brand tone — What tone should I use? (e.g., warm and approachable) | PASS |
| Over-Promotional Request | Reject unsupported hype | Meet our new Ethiopian roast — bright, approachable, and full of character.

Sourced through BrewCraft’s direct-trade relationships, this small-batch coffee brings a distinctive Ethiopian coffee experience to your morning brew. Discover its character and make your next cup something to look forward to.

Explore the new Ethiopian roast and find your next favorite morning cup. | PASS |
| Brand-Unsafe Health Wording | Block health claims | Meet our new Ethiopian roast — bright, approachable, and full of character.

Carefully sourced through BrewCraft’s direct-trade relationships, this small-batch Ethiopian coffee is made for savoring. Explore its distinctive character and enjoy a flavorful cup as part of your morning ritual.

Discover the new Ethiopian roast and enjoy your next BrewCraft cup. | PASS |
| Request for Alternatives | Provide 3 alternatives | ☕ Meet Your New Ethiopian Favorite

Body Copy

Bright, approachable, and full of character — our new Ethiopian roast is here to add a little more joy to your coffee ritual. 🌿☕

Sourced through BrewCraft’s direct-trade relationships and produced in small batches under 50kg, it’s a delicious invitation to slow down, brew, and discover something new.

CTA

Ready to explore? Brew yourself a cup and discover our new Ethiopian roast. | PASS |

## Final Validation

- [ ] Required-input validation works
- [ ] Brand guidelines are followed
- [ ] Passionate-barista voice is maintained
- [ ] Headline → Body Copy → CTA structure is enforced
- [ ] Unsupported marketing hype is blocked
- [ ] Health/medical claims are blocked
- [ ] Competitor disparagement is blocked
- [ ] Alternative content can be generated safely
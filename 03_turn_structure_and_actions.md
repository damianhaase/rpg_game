# Game Rulebook — Section 3: Turn Structure and Actions

## How Timing Governs the Probability Space

The core insight of this combat system is that *time is not a queue — it is a resource that actions consume unevenly*. A light jab takes less time than a full axe swing. A prepared bowshot takes more time than a snap draw. Every action exposes the actor for some window of vulnerability, and whether anyone can exploit that window depends on their Response Speed and available Reaction Budget.

This model replaces visible initiative entirely. There is no "who goes first" roll. Instead, the question is: *does this character have enough RS to act during that EW, and do they have RB left to spend?* The answer is deterministic — no die roll — which makes timing legible and predictable. Players can look at an opponent's commitment state and know whether a Counter is legal before they commit their own budget.

The 3d6 probability engine governs whether attacks hit and whether defenses succeed, but the timing layer governs which actions are even eligible to interact. This two-layer design — timing gate first, probability roll second — keeps the system coherent across melee, ranged, and magical combat.

---

## Position and Commitment State

Each character's state is described by two orthogonal properties.

### Position

- **Standing:** Default state; no bonuses or penalties.
- **Prone:** Voluntarily dropped or knocked down; harder to hit at range, easier to hit in melee; reduced SPD and restricted movement.
- **Behind Cover:** Partial or full cover; incoming attacks have lower hit probability; leaving cover costs movement.
- **Engaged:** In melee contact with at least one opponent.
- **Near:** Within reaction range but not yet in contact.
- **Far:** Outside immediate reaction range; ranged or magical attacks typically required.

### Commitment State

- **Balanced:** Standard readiness. No special bonus or penalty. Normal defensive options available.
- **Guarded:** Defensive posture. Smaller Exposure Window, better defensive reactions, weaker offense.
- **Committed:** Aggressive posture. Larger Exposure Window, stronger offense, weaker defense.
- **Extended:** In the middle of a long action (heavy swing, drawn bow release, complex spell). Easiest to punish with reactions.

The old "momentum/pressure state" language maps onto Commitment State. Pressure still exists as a separate morale and stress track (see Section 5).

---

## Turn Structure

Combat is played in **simultaneous rounds** rather than visible turns.

Each round proceeds in five stages:

### 1. Intent Declaration

Each combatant declares one primary intent.

Examples: move, attack, guarded defense, aim, cast, disengage, commit attack, take cover.

### 2. Commit Phase

The declared action begins. Each action now creates an **Exposure Window (EW)** based on its speed and complexity.

### 3. Reaction Check

Any character with remaining RB may react if their Response Speed is high enough to exploit the acting character's Exposure Window.

```
Reaction is legal if:  RS + reaction modifiers ≥ EW
```

Reactions do not create a new planning round; they modify or answer the already-declared situation.

### 4. Resolve Phase

Actions that were not stopped or replaced resolve. Apply attack, defense, damage, pressure, movement, and state updates.

### 5. End-of-Round Update

Recalculate wound state, pressure state, remaining RB, temporary bonuses, ongoing effects, and position.

**There is no separate player-facing initiative roll.** The experience should feel simultaneous. Timing differences exist only through exposure windows and response speed.

---

## Actions and Reactions

### Core Principle: Exposure Windows vs. Response Speed

Every action has an **Exposure Window (EW)** — how much time or commitment it creates before it resolves. Faster or simpler actions create smaller windows. Slower, stronger, or more complex actions create larger windows.

Every character has a **Response Speed (RS)**. If a reacting character's RS is high enough, and they still have Reaction Budget available, they may act during another character's exposure window.

The governing check:

```
Reaction allowed if RS + reaction modifiers ≥ EW
```

This is **not a die roll** unless a specific talent or effect says otherwise. It is a deterministic timing gate.

---

### Default Exposure Window Categories

Use these categories unless a weapon, spell, or trait changes them:

| Category | EW | Examples |
|---|---|---|
| **Instant** | 0 | Purely internal or already-completed effects; generally not reactable. |
| **Fast** | 2 | Jab, quick step, short dodge, snap shot at point-blank range. |
| **Standard** | 4 | Normal attack, normal movement, standard bow shot, standard guard. |
| **Slow** | 6 | Heavy attack, aimed shot, long disengage, forceful shove. |
| **Extended** | 8 | Powerful spell, reload, brace-and-fire, all-out swing, multi-step maneuver. |

---

### Exposure Modifiers

Modify EW based on circumstances:

| Modifier | EW Change |
|---|---|
| Heavy weapon | +2 |
| Fast weapon | –1 |
| Unwieldy weapon | +1 |
| Aiming before release | +1 |
| Severe wound | +1 |
| Prone recovery | +2 |
| Light cover while shooting (awkward angle) | +1 |
| Spell instability surge | +1 or more |

---

### Interaction with Commitment State

| Commitment | EW Effect | Offense | Defense |
|---|---|---|---|
| **Balanced** | Normal EW | Normal | Normal defensive options |
| **Guarded** | –1 EW | –1 to offensive targets | +1 to defensive targets |
| **Committed** | +2 EW | +1 damage or equivalent offensive bonus | –1 to defensive targets |
| **Extended** | May not Counter | Large penalty if interrupted | Usually cannot take Counter |

---

## Primary Actions (Intent Options)

- **Move / Reposition:** Change zone, close distance, retreat, circle, gain or leave cover.
- **Sprint:** Move at +50% distance. Costs 1 FP. Cannot be used while Prone, Grappled, or in Heavy Load. See Section 2 for full restrictions.
- **Attack:** Strike with weapon, unarmed attack, or offensive spell.
- **Guard:** Focus on reducing exposure and improving defense this round.
- **Commit:** Accept a larger exposure window in exchange for more force, damage, or positional pressure.
- **Aim:** Improve a later ranged or spell attack at the cost of time and exposure.
- **Take Cover:** Move into or improve cover against ranged threats.
- **Cast:** Begin and resolve a spell according to its casting profile.
- **Recover:** Reduce pressure, stabilize footing, or regroup after strain.
- **Disengage:** Attempt to safely leave melee. This is a Slow action (EW 6). The character makes a DX + Athletics roll vs. the opponent's DX + Weapon Skill. On success, the character moves one range band away without triggering a free Counter reaction. On failure, the opponent may immediately take a Counter reaction (2 RB) against the departing character. Forced withdrawal under pressure (e.g., Broken state) uses the same check.
- **Grapple:** Attempt to seize and restrain an opponent. The attacker makes an opposed ST + Unarmed Skill roll vs. the defender's ST + Unarmed Skill (or DX + Athletics if the defender chooses to writhe free). This is a Standard action (EW 4). On success, both characters enter the Grappled state. While Grappled: neither may move normally; neither may Dodge; both may attempt to break free (Standard action, same opposed roll), strike with small weapons only (–2 to attack), or attempt to throw/pin (Extended action, separate rules may be added). A third party may assist a grappled character's break-free roll by adding their ST as a bonus.

---

## Reaction Options

A reaction is only legal if:
- the acting enemy's EW is large enough to exploit (RS + modifiers ≥ EW),
- the reacting character has enough RS,
- the reacting character has enough remaining RB,
- and the current state allows that reaction.

### Dodge
**Cost: 1 RB**
Use bodily movement to reduce the chance of being hit. Best for agile, lightly armored characters.

### Parry
**Cost: 1 RB**
Use a weapon to intercept or spoil an incoming melee attack. Moderate defense with modest offensive disruption.

### Block
**Cost: 1 RB**
Use a shield or body structure to absorb or stop an incoming attack. Best for strong characters with shields. Limited by facing and line of attack.

### Shift / Step
**Cost: 1 RB**
Small movement to alter angle, escape a line, or improve cover. Often used against Committed or Extended opponents.

### Counter
**Cost: 2 RB**
Exploit an opponent's large exposure window to strike back. Usually unavailable while Prone, Stunned, Broken, or using unwieldy equipment.

### Take Cover (reaction version)
**Cost: 1 RB**
A snap movement into existing nearby cover. Valid only when cover is plausibly present.

---

## Reaction Limits

- A character may react multiple times in a round only if they still have RB.
- Each additional reaction after the first imposes a cumulative –1 RS penalty for the rest of the round.
- A character cannot react to everything around them indefinitely. Multiple simultaneous threats are designed to overload low-IQ or heavily burdened characters.

---

## Consequences of Reactions

Reactions are not free. A reaction can:
- consume RB
- reduce the quality of the original declared action
- increase pressure
- leave the reactor Off-Balance
- shorten movement or cancel an Aim bonus

This preserves tactical commitment. A character who begins a heavy swing and then has to parry mid-motion should still suffer for the disruption.

---

## Combat Example: Two-on-One

The following narrative example illustrates a 2v1 fight between a **Hero** and two enemies, **Goblin A** and **Goblin B**.

### Round 1 — Intent Declaration

- **Hero** (Balanced, Standing): declares **Attack Goblin A** with a broadsword. EW: Standard (4). Attack Target: 14.
- **Goblin A** (Balanced): declares **Attack Hero** with a dagger. EW: Fast (2).
- **Goblin B** (Balanced): declares **Flank** — repositioning to approach from the rear. EW: Standard (4).

### Reaction Check

Hero's RS is 12. Goblin B's EW is 4. Because Hero's RS ≥ EW, Hero may react to the flanking movement.

UI shows:
- **No Reaction:** Hero continues attacking Goblin A; Goblin B completes flanking freely.
- **Shift to Guard:** Hero burns 1 RB; Goblin B's flanking is partially blocked; Hero's Attack Target drops by 2 but Goblin B is less threatening next round.
- **Counter Goblin B:** Costs 2 RB; Hero turns and attacks Goblin B but drops attack on Goblin A entirely.

**Hero chooses Shift to Guard (1 RB).**

### Resolve Phase

- **Hero vs Goblin A:** Modified Attack Target is now 12. Hero rolls 9 — success, margin +3. Goblin A's Parry Target is 10; Goblin A rolls 12 — fail. Hero deals 1d6+2 (rolls 7 total), reduced by Goblin A's DR 1 to 6. Goblin A takes a Heavy Wound.
- **Goblin A vs Hero:** Attack Target 10, rolls 11 — fail. Hero is not hit.
- **Goblin B:** Completes repositioning but is now only Near rather than Engaged due to Hero's Shift.

### End-of-Round Update

- Goblin A: Heavy Wound (–1 all physical, wound penalty to EW +1).
- Hero: 1 RB spent; RS penalty –1 for the rest of this round (already resolved).
- Goblin B: Now Near, not Engaged. Flanking bonus not yet active.

---

## Flanking

A character is **Flanked** when opponents have them surrounded such that at least one attacker is attacking from the rear or from an angle the defender cannot cover with a single facing.

**Flanking bonus:** Attackers who are Flanking gain **+2** to their Attack Target. The flanked defender loses the ability to Block with a shield against flanking attackers (shields only cover the front facing). Parry remains legal from any angle but at –1.

A character who is Engaged with a single opponent in front and has a second attacker reach them from the side or rear is considered Flanked on any attack from that side or rear attacker.

**Preventing flanking:** A Shift / Step reaction (1 RB) can deny a flanking position if used before the attacker completes their repositioning. This is why Goblin B in the combat example is only Near rather than Engaged after the Hero's Shift.

---

## Design Rationale

This timing model removes visible initiative from the player experience while preserving deterministic combat logic. Players commit to actions, expose themselves by degrees, and sometimes exploit those openings in others. Faster and smarter characters feel reactive because they *are* reacting within the same round — not because they won an abstract turn-order contest.

The player experiences:
1. Declaration
2. Exposure
3. Reaction
4. Consequence

That makes combat feel simultaneous while remaining deterministic, explainable, and implementable in code.

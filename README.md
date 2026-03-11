# Reopen Hormuz

An interactive explanatory simulation about why a militarily superior navy may still struggle to restore normal commercial shipping through a threatened chokepoint.

## What This Is

A single-page browser toy model — not a wargame, not a prediction engine, not an order-of-battle simulator. It teaches one core insight:

**Closing a chokepoint can be easier than making it safe enough for commerce to resume.**

## How to Run

Open `index.html` in any modern browser. No build step, no server, no dependencies.

## How to Play

You control a coalition attempting to restore commercial shipping through the Strait of Hormuz. Each day (turn), you allocate 100 points of effort across five mission categories:

| Category | Effect |
|---|---|
| **Strike / Suppression** | Degrades Iranian threat pressure |
| **Mine Countermeasures** | Reduces persistent mine threat |
| **Convoy / Escort** | Builds escort credibility through safe passage |
| **Base Defense** | Maintains forward base operability |
| **Reserve / Intercept** | Increases chance of intercepting attacks |

After allocating, click "Advance Day" to resolve the turn. The simulation updates threat environment, commercial response, and political pressure.

### Win Condition
Sustain commercial traffic above 70% of baseline for 7 consecutive days.

### Lose Conditions
- Political/economic pressure maxes out
- Traffic remains critically low for too long
- 90 days elapse without sufficient recovery

## The Model

### Why military success doesn't equal commercial reopening

The simulation models the gap between suppressing a military threat and restoring commercial confidence. Even if you destroy every Iranian launch site, traffic may not return because:

1. **Mines persist.** Mine clearance is slow. Suspected mines are almost as disruptive as real ones. The mine threat declines slowly even with dedicated MCM effort.

2. **Confidence is nonlinear.** Merchant confidence follows an S-curve. It collapses fast and recovers slowly. One successful attack during partial recovery can undo weeks of progress.

3. **Insurance is necessary but not sufficient.** War-risk cover must be available AND affordable. High premiums alone can suppress traffic even if cover exists.

4. **Crew and operators have their own risk calculus.** Shipowners, charterers, and masters must all be willing to transit. Their willingness depends on demonstrated safety, not just military press releases.

5. **Escort credibility builds slowly.** Announcing escorts helps a little. Repeated safe transits help more. One attack destroys credibility faster than ten safe transits build it.

6. **The opponent adapts.** The Iranian AI shifts strategy based on your allocation — if you neglect mine clearance, it leans into mining. If you neglect base defense, it attacks your bases.

### Core Variables

| Variable | Description |
|---|---|
| Iranian Threat Pressure | Abstract harassment and strike capability |
| Iranian Reconstitution | Rate of threat recovery after suppression |
| Mine Threat | Persistent route danger; declines slowly |
| Base Operability | Coalition base function; affects all operations |
| Escort Credibility | Commercial trust in route protection |
| Cover Availability | Whether insurance is obtainable |
| Premium Burden | Cost of insurance and surcharges |
| Operational Willingness | Crew/owner willingness to transit |
| Merchant Confidence | Composite of above factors (S-curve) |
| Traffic Flow | Percent of baseline shipping |
| Political/Economic Pressure | Coalition mandate erosion |

### Key Dynamics

- **Asymmetric collapse/recovery:** Traffic collapses 3x faster than it recovers
- **Sticky mines:** Mine threat has high persistence and strong confidence penalty
- **Attack fragility:** One attack during recovery drops confidence sharply
- **Tradeoff budget:** You can't do everything — neglecting any area has consequences
- **Time pressure:** Political pressure grows daily; the coalition has a limited window

## Scenarios

| Preset | Description |
|---|---|
| Balanced | Default parameters |
| Optimistic | Lower initial threat, better coalition effectiveness |
| Pessimistic | Higher threat, reduced effectiveness, faster pressure growth |
| Mine-Heavy | Severe mine threat, Iranian focus on mining |
| Fast Reconstitution | Iranian forces regenerate quickly after strikes |

## Tuning

All parameters are in the `CONFIG` object at the top of the JavaScript section. Every weight, rate, threshold, and probability is collected there with comments. Change values and reload.

## Methodology Note

This simulator is an explanatory toy model inspired by public analysis of Hormuz closure scenarios, mine warfare, and commercial shipping risk. It illustrates mechanisms and tradeoffs; it does not predict real-world outcomes.

## Technology

- Single HTML file
- Vanilla JavaScript
- Canvas-based charts
- Google Fonts (Share Tech Mono, IBM Plex Mono)
- No frameworks, no build tools, no backend

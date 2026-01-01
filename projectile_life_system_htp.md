Projectile Life System (HTP)

A micro-framework that fixes one of the biggest flaws in RPG/ARPG/MMO combat.

Core Idea

Every skill/projectile has its own HP (Life).
It decays over distance, can be damaged, can clash with other skills, and can be drained.

This turns projectiles from “mindless objects” into living entities with real combat interactions.

Core Mechanics

Skill HP (Life)
Each skill has a stat:

SkillLife = BaseLife × (UserMagicPowerScaling)

This HP represents the skill’s energy durability.

Distance Decay
The skill gradually loses HP as it travels:

HP_loss = Distance × DecayRate

→ Skills weaken over range and cannot travel infinitely.

Projectile Clash
When two skills collide:

Skill A Life > Skill B Life → A pierces through (remaining Life = LifeA – LifeB)
Skill A Life < Skill B Life → A is destroyed
Life equal → both explode on the spot
Projectile Damage Taken
Any damage source can reduce a skill’s Life:

Bullets/projectiles
Other spells
Melee weapons hitting the skill
Traps
Auras
Terrain effects
→ Combat gains many layers of depth.

Skill Drain (Energy Leech)
Certain player skills can leech Life from enemy skills to:

Increase damage
Extend duration
Increase size
Change properties (if enough Life is drained)
Death Behavior
When SkillLife reaches 0 → the skill “dies” and can:

Explode
Dissipate
Break down into raw energy
Trigger a secondary effect (if designed)
Examples

Fireball

BaseLife: 100
DecayRate: 2 HP/m

Travels 30m → loses 60 HP → arrives with 40 HP remaining.

If it collides with an Ice Lance (Life = 50):

Ice Lance (50) > Fireball (40) → Fireball is destroyed, Ice Lance continues with 10 Life left.

Lightning Beam (drain type)

The beam drains 5 HP/s from nearby enemy projectiles.
If it passes through 3 enemy projectiles:

3 × 5 = 15 HP/s drained
→ Beam grows thicker and deals increased damage.

Notes

A micro-framework that opens up an entirely new combat system.

Perfect for RPG / ARPG / MMO / MOBA / fantasy shooters.

Easy to prototype: just add a Life value to your projectile class.

Creates meaningful counterplay: “fight skill with skill”.

100% compatible with HTP’s Relative Defense and Armor Layer systems.

Serves as a foundation for a full “Spell Ecosystem” — where skills behave like living energy entities.

Author

HTP

Public domain. Use freely.

**Damage is one of the most important part of a game's combat system.** So I pick this part as the first chapter of all the mechanic articles.<br>
When characters or enemies attack their targets, they generally deal **damage** (abbreviated as **DMG**) based on their own and their targets' attributes.<br>
Note: HP loss is not damage.<br>
# General Damage Formula
For DMG dealt by Abilities, Traces, Eidolons or enemy attacks, the DMG is calculated as:<br>
$$DMG\enspace =\enspace Base DMG_{Attacker}\enspace ×\enspace DMG Boost Multiplier_{Attacker}\enspace ×\enspace Weaken Multiplier_{Attacker}\enspace ×\enspace CRIT\enspace Multiplier_{Attacker}\enspace ×\enspace DMG Mitigation Multiplier_{Target}\enspace ×\enspace DMG\enspace Taken\enspace Multiplier_{Target}\enspace ×\enspace DEF\enspace Multiplier_{Target}\enspace ×\enspace  REs\enspace Multiplier_{Target} ×\enspace Special\enspace Multiplier\enspace$$
## Base DMG
$$
\text { Base DMG }={\begin{array}{ll}
\text { Ability Scaling Percentage } × \text { ATK } & \text { if ability scales with ATK } \\
\text { Ability Scaling Percentage } × \text { DEF } & \text { if ability scales with DEF } \\
\text { Ability Scaling Percentage } × \text { Max HP } & \text { if ability scales with Max HP } 
\end{array}}
$$

**Base DMG** is the amount of DMG resulted from multiplying the ability's scaling with the corresponding stat, before accounting for any damage modifiers.<br>
Unless otherwise specified in the ability attributes, abilities will scale with ATK. Some abilities may scale with more than one stat.<br>
## CRIT Multiplier
When attack triggers a critical hit, damage will get a crit bouns. Crit Rate is a probability, so:<br>

$$ CRIT\enspace Rate_{Effective}\enspace =\enspace clamp\enspace \{0\%,\enspace CRIT\enspace Rate,\enspace 100\%\} $$

The crit multiplier is calculated as:<br>

$$
\text { CRIT Multiplier }={\begin{array}{ll}
\text { 1 + CRIT DMG } & \text { if CRIT } \\
\text { 1 } & \text { otherwise } \\
\text { 1 + CRIT Rate Effective } × \text { CRIT DMG } & \text { Mean, for Expectation} 
\end{array}}
$$

The expectation of CRIT Multiplier is deduced as:<br>
$$E(CRIT)\enspace =\enspace 1\enspace ×\enspace (1\enspace -\enspace CRIT\enspace Rate_{Effective})\enspace +\enspace CRIT\enspace Rate_{Effective}\enspace ×\enspace (1\enspace +\enspace CRIT\enspace DMG)\enspace =\enspace 1\enspace +\enspace CRIT\enspace Rate_{Effective}\enspace ×\enspace CRIT\enspace DMG$$
## DEF Multiplier
DEF Multiplier is the multiplier that Defence(abbreviated as DEF) reduces incoming damage, it's calculated as:<br>
$$DEF\enspace DMG\enspace Reduction\enspace =\enspace \frac{DEF_{Effective}}{DEF_{Effective}\enspace +\enspace Level\enspace Coefficient_{Attacker}}$$
Then the DEF Multiplier is:<br>
$$DEF\enspace Multiplier\enspace =\enspace 1\enspace -\enspace DEF\enspace DMG\enspace Recduction$$
So you can calculate the DEF Multiplier as:<br>
$$DEF\enspace Multiplier\enspace =\enspace \frac{Level\enspace Coefficient_{Attacker}}{Level\enspace Coefficient_{Attacker}\enspace +\enspace DEF_{Target}}$$
The Level Coefficient<sub>Attacker</sub> can be calculated as:<br>
$$Level\enspace Coefficient_{Attacker}\enspace =\enspace 10\enspace ×\enspace Level_{Attacker}\enspace +\enspace 200$$
The Enemy Defense is actually given by the product of Base Denfense and Level Factor<sub>Defense</sub>. For the Base Denfense is generally 210, and the Level Factor<sub>Defense</sub> grows 1/21 each level from 1. The Enemy Defense is calculated as:<br>
$$DEF_{Enemy}\enspace =\enspace 10\enspace ×\enspace Level_{Enemy}\enspace +\enspace 200$$
***Note: The Trotter is special, its DEF is 1.5 of general Enemy.***<br>
As you see, this formula is the same as Level Coefficient<sub>Attacker</sub>, so **the DEF Multiplier is generally 0.5 (Trotter is 0.4) when the Attacker<sub>Character</sub> has the same level as Target<sub>Enemy</sub> without any DEF Reduction or DEF Ignored.**<br>
In game, there are DEF Reduction and DEF Ignored, the effective DEF is calculated as:<br>
$$DEF_{Effective}\enspace =\enspace DEF_{Original}\enspace ×\enspace (1\enspace -\enspace DEF\enspace Reduction_{Target}\enspace -\enspace DEF\enspace Ignored_{Attacker})$$
Note: DEF<sub>Effective</sub> ≥ 0<br>
If character attacks Enemy, the DEF Multiplier can be simplified as:<br>
$$DEF\enspace Multiplier\enspace =\enspace \frac{Level_{Character}\enspace +\enspace 20}{k(Level_{Enemy}\enspace +\enspace 20)\enspace +\enspace (Level_{Character}\enspace +\enspace 20)}$$
$$k\enspace =\enspace (1\enspace -\enspace DEF\enspace Reduction_{Enemy}\enspace -\enspace DEF\enspace Ignored_{Character})$$
For character attacks Trotter, it is:
$$DEF\enspace Multiplier\enspace =\enspace \frac{Level_{Character}\enspace +\enspace 20}{k(1.5\enspace ×\enspace Level_{Trotter}\enspace +\enspace 30)\enspace +\enspace (Level_{Character}\enspace +\enspace 20)}$$
## REs Multiplier
REs Multiplier is the multiplier that Resistances(abbreviated as REs) affect incoming damage. It's calculated as:
$$REs Multiplier = 1 - REs$$
And the REs<sub>Effective</sub> is:<br>
$$REs_{Effective}\enspace =\enspace REs_{Original}\enspace -\enspace REs\enspace Reduction_{Target}\enspace -\enspace REs\enspace Penetrate_{Attacker}$$
You can look up the Enemy REs here: [Damage REs](https://honkai-star-rail.fandom.com/wiki/Damage_RES)

# Special Damage Formula
## Break Damage
## Normal DOT
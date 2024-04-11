**Damage is one of the most important part of a game's combat system.** So I pick this part as the first chapter of all the mechanic articles.<br>
When characters or enemies attack their targets, they generally deal **damage** (abbreviated as **DMG**) based on their own and their targets' attributes.<br>
Note: HP loss is not damage.<br>
# General Damage Formula
For DMG dealt by Abilities, Traces, Eidolons or enemy attacks, the DMG is calculated as:<br>
$$DMG = Base DMG_{Attacker} × DMG Boost Multiplier_{Attacker} × Weaken Multiplier_{Attacker}  × CRIT Multiplier_{Attacker} × DMG Mitigation Multiplier_{Target} × DMG Taken Multiplier_{Target} × DEF Multiplier_{Target} ×  REs Multiplier_{Target}$$
## Base DMG
$$
\text { Base DMG }={\begin{array}{ll}
\text { Ability Scaling } × \text { ATK } & \text { if ability scales with ATK } \\
\text { Ability Scaling } × \text { DEF } & \text { if ability scales with DEF } \\
\text { Ability Scaling } × \text { Max HP } & \text { if ability scales with Max HP } 
\end{array}}
$$

**Base DMG** is the amount of DMG resulted from multiplying the ability's scaling with the corresponding stat, before accounting for any damage modifiers.<br>
Unless otherwise specified in the ability attributes, abilities will scale with ATK. Some abilities may scale with more than one stat.<br>
# Special Damage Formula
## Break Damage
## Normal DOT
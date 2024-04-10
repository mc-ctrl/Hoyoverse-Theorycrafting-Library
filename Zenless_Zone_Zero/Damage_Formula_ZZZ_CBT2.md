**Damage is the most important part of Zenless Zone Zero's combat system.** So I pick this part as the first chapter of all the mechanic articles.<br>
When agents or enemies attack their targets, they generally deal **damage** (abbreviated as **DMG**) based on their own and their targets' attributes.<br>
Note: This article is based on CBT2. It's greatly subject to change.<br>
# General Damage Formula
For DMG dealt by Skills, Talents or enemy attacks, the DMG is calculated as:<br>
$$DMG = Base DMG_{Attacker} × DMG Bouns Multiplier_{Attacker} × CRIT Multiplier_{Attacker} × DEF Multiplier_{Target} ×  REs Multiplier_{Target} × Damage Taken Multiplier_{Target} × Stun Taken Multiplier_{Target}$$
## Base DMG
$$
\text { Base DMG }={\begin{array}{ll}
\text { Skill Scaling } × \text { ATK } & \text { if skill scales with ATK } \\
\text { Skill Scaling } × \text { DEF } & \text { if skill scales with DEF } \\
\text { Skill Scaling } × \text { Max HP } & \text { if skill scales with Max HP } 
\end{array}}
$$

**Base DMG** is the amount of DMG resulted from multiplying the skill's scaling with the corresponding stat, before accounting for any damage modifiers.<br>
Unless otherwise specified in the skill's attributes, skills will scale with ATK. Some abilities may scale with more than one stat.<br>
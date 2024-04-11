**Damage is one of the most important part of a game's combat system.** So I pick this part as the first chapter of all the mechanic articles.<br>
When agents or enemies attack their targets, they generally deal **damage** (abbreviated as **DMG**) based on their own and their targets' attributes.<br>
Note: This article is based on CBT2. It's greatly subject to change.<br>
# General Damage Formula
For DMG dealt by Skills, Talents or enemy attacks, the DMG is calculated as:<br>
$$DMG\enspace =\enspace Base\enspace DMG_{Attacker}\enspace ×\enspace DMG\enspace Bouns\enspace Multiplier_{Attacker}\enspace ×\enspace CRIT Multiplier_{Attacker}\enspace ×\enspace DEF Multiplier_{Target}\enspace ×\enspace REs\enspace Multiplier_{Target}\enspace ×\enspace Damage\enspace Taken\enspace Multiplier_{Target}\enspace ×\enspace Stun\enspace Taken\enspace Multiplier_{Target}$$
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
## CRIT
When attack triggers a critical hit, damage will get a crit bouns. Crit Rate is a probability, so the CRIT RATE<sub>Effective</sub> is clamp{0%, crit rate, 100%}. So the crit multiplier is calculated as:<br>

$$
\text { CRIT Multiplier }={\begin{array}{ll}
\text { 1 + CRIT DMG } & \text { if CRIT } \\
\text { 1 } & \text { else } \\
\text { 1 + CRIT RATE Effective } × \text { CRIT DMG } & \text { Mean, for Expectation} 
\end{array}}
$$

The expectation of CRIT Multiplier is deduced as:<br>
$$E(CRIT)\enspace =\enspace 1\enspace ×\enspace (1\enspace -\enspace CRIT\enspace RATE_{Effective})\enspace +\enspace CRIT\enspace RATE_{Effective}\enspace ×\enspace (1\enspace +\enspace CRIT\enspace DMG)\enspace =\enspace 1\enspace +\enspace CRIT\enspace RATE_{Effective}\enspace ×\enspace CRIT\enspace DMG$$
## DEF Multiplier
DEF Multiplier is the multiplier that Defence(abbreviated DEF) reduces incoming damage, it's calculated as:<br>
$$DEF\enspace DMG\enspace Reduction\enspace =\enspace \frac{DEF_{Effective}}{DEF_{Effective}\enspace +\enspace Level\enspace Coeffcient_{Attacker}}$$
Then the DEF Multiplier is:<br>
$$DEF\enspace Multiplier\enspace =\enspace 1\enspace -\enspace DEF\enspace DMG\enspace Recduction$$
# Special Damage Formula
## Element Abnormal Damage
## Other Buff Damage
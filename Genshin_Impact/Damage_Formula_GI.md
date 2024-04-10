**Damage is the most important part of Genshin Impact's combat system.** So I pick this part as the first chapter of all the mechanic articles.<br>
When characters, enemies or some gadgets attack their targets, they generally deal **damage** (abbreviated as **DMG**) based on their own and their targets' attributes.<br>
Note: A single instance of damage cannot exceed 9,999,999.<br>
# General Damage Formula
For DMG dealt by Talents, Constellations, Weapon passives, enemy attacks or gadget attacks, the DMG is calculated as:<br>
$$DMG = ((Σ(Base DMG × Base DMG Coefficient) + Additive Base DMG Bouns)) × DMG Bouns Multiplier × DEF Multiplier_{Target} ×  RES Multiplier_{Target} × CRIT Multiplier × Amplifying Multiplier$$
## Base DMG
$$
\text { Base DMG }={\begin{array}{ll}
\text { Talent } × \text { ATK } & \text { if talent scales with ATK } \\
\text { Talent } × \text { DEF } & \text { if talent scales with DEF } \\
\text { Talent } × \text { Max HP } & \text { if talent scales with Max HP } \\
\text { Talent } × \text { EM } & \text { if talent scales with EM }
\end{array}}
$$

**Base DMG** is the amount of DMG resulted from multiplying the talent's scaling with the corresponding stat, before accounting for any damage modifiers.<br>
Unless otherwise specified in the talent's attributes, talents will scale with ATK. Some abilities may scale with more than one stat.<br>
For example, Nahida's Elemental Skill [All Schemes to Know](https://genshin-impact.fandom.com/wiki/All_Schemes_to_Know) has a Tri-Karma Purification DMG, this DMG scales with both ATK and EM. If your Nahida has 1400 ATK, 950 EM and Level 10 Elemental Skill, the base DMG of Tri-Karma Purification DMG is calculated as:<br>
$$Base DMG = 1.8576 × 1400 + 3.7152 × 950 = 6130.08 $$
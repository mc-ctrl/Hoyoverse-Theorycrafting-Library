**Damage is the most important part of Genshin Impact's combat system.** So I pick this part as the first chapter of all the mechanic articles.<br>
When characters, enemies or some gadgets attack their targets, they generally deal **damage** (abbreviated as **DMG**) based on their own and their targets' attributes.<br>
Note: A single instance of damage cannot exceed 9,999,999.<br>
# General Damage Formula
For DMG dealt by Talents, Constellations, Weapon passives, enemy attacks or gadget attacks, the DMG is calculated as:<br>
$$DMG = ((Σ(Base DMG × Base DMG Coefficient) + Additive Base DMG Bouns)) × DMG Bouns Multiplier × DEF Multiplier_{Target} ×  RES Multiplier_{Target} × CRIT Multiplier × Amplifying Multiplier$$
## Base DMG
**Base DMG** is the amount of DMG resulted from multiplying the ability's scaling with the corresponding stat, before accounting for any damage modifiers.<br>
Unless otherwise specified in the skill attributes, abilities will scale with ATK. Some abilities may scale with more than one stat.<br>
$$ { Base DMG }={ \begin{array}{ll}  { Ability } × { ATK } & { if ability scales with ATK } \\ { Ability } × { DEF } & { if ability scales with DEF } \\ { Ability } × { Max HP } & { if ability scales with Max HP } \\ { Ability } × { EM } & { if ability scales with EM } \end{array}}$$
For example, Nahida's Skill 
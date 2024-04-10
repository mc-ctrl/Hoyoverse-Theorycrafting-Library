**Damage is the most important part of Genshin Impact's combat system.** So I pick this part as the first chapter of all the mechanic articles.<br>
When characters, enemies or some gadgets attack their targets, they generally deal **damage** (abbreviated as **DMG**) based on their own and their targets' attributes.<br>
Note: A single instance of damage cannot exceed 9,999,999.<br>
# General Damage Formula
For DMG dealt by Talents, Constellations, Weapon passives, enemy attacks or gadget attacks, the DMG is calculated as:<br>
$$DMG = ((Σ(Base DMG × Base DMG Coefficient) + Additive Base DMG Bouns)) × DMG Bouns Multiplier × DEF Multiplier_{Target} ×  RES Multiplier_{Target} × CRIT Multiplier × Amplifying Multiplier$$
## Base DMG
$$
\text { Base DMG }=\left\{\begin{array}{ll}
\text { Ability } \% \times \text { ATK } & \text { if ability scales with ATK } \\
\text { Ability } \% \times \text { DEF } & \text { if ability scales with DEF } \\
\text { Ability } \% \times \text { Max HP } & \text { if ability scales with Max HP } \\
\text { Ability } \% \times \text { EM } & \text { if ability scales with EM }
\end{array}}\right
$$
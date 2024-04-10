**Damage is the most important part of Genshin Impact's combat system.** So I pick this part as the first chapter of all the mechanic articles.<br>
When characters, enemies or some gadgets attack their targets, they generally deal **damage** (abbreviated as **DMG**) based on their own and their targets' attributes.<br>
Note: A single instance of damage cannot exceed 9,999,999.<br>
# General Damage Formula
For DMG dealt by Talents, Constellations, Weapon passives, enemy attacks or gadget attacks, the DMG is calculated as:<br>
$$DMG = ((Σ(Base DMG × Base DMG Coefficient) + Additive Base DMG Bouns)) × DMG Bouns Multiplier × DEF Multiplier_{Target} × RES Multiplier_{Target} × CRIT Multiplier × Amplifying Multiplier × Special Multiplier$$
## Base DMG
$$
\text { Base DMG }={\begin{array}{ll}
\text { Talent Scaling } × \text { ATK } & \text { if talent scales with ATK } \\
\text { Talent Scaling } × \text { DEF } & \text { if talent scales with DEF } \\
\text { Talent Scaling } × \text { Max HP } & \text { if talent scales with Max HP } \\
\text { Talent Scaling } × \text { EM } & \text { if talent scales with EM }
\end{array}}
$$

**Base DMG** is the amount of DMG resulted from multiplying the talent's scaling with the corresponding stat, before accounting for any damage modifiers.<br>
Unless otherwise specified in the talent's attributes, talents will scale with ATK. Some abilities may scale with more than one stat.<br>
For example, Nahida's Elemental Skill [All Schemes to Know](https://genshin-impact.fandom.com/wiki/All_Schemes_to_Know) has a Tri-Karma Purification DMG, this DMG scales with both ATK and EM. If your Nahida has 1400 ATK, 950 EM and Level 10 Elemental Skill, the base DMG of Tri-Karma Purification DMG is calculated as:<br>
$$Base DMG = 1.8576 × 1400 + 3.7152 × 950 = 6130.08 $$
**Base DMG Coefficient** is special coefficient that modifies Base DMG, it is directly multiplicative with Base DMG. It's generally discribed as "Attacks Deal *Cofficient* of the **original DMG**." In game, it can be found in Yoimiya's [Skill](https://genshin-impact.fandom.com/wiki/Niwabi_Fire-Dance), Neuvillette's [1st Ascension Passive](https://genshin-impact.fandom.com/wiki/Heir_to_the_Ancient_Sea%27s_Authority), Navia's [Skill](https://genshin-impact.fandom.com/wiki/Ceremonial_Crystalshot), Furina's [Skill](https://genshin-impact.fandom.com/wiki/Salon_Solitaire), Wanderer's [Skill](https://genshin-impact.fandom.com/wiki/Hanega:_Song_of_the_Wind), Wriothesley's [Skill](https://genshin-impact.fandom.com/wiki/Icefang_Rush), Xingqiu's [4th Constellation](https://genshin-impact.fandom.com/wiki/Evilsoother) and Traveler(Electro)'s [6th Constellation](https://genshin-impact.fandom.com/wiki/World-Shaker).<br>
**Additive Base DMG Bouns** is a bouns DMG added to the base DMG, it's normally fixed or scaling with attacker's sub stat. It's generally discribed as "Attack DMG is increased by *bouns%* of **sub stat**". This type of Additive Base DMG Bonus can be calculated in the same way as Base DMG.<br>
The other type of it is the damage bouns from **Spread and Aggravate** Elemental Reactions. When the attacks inflict Dendro or Electro on the target affected by Quicken Aura, the Spread or Aggravate will be triggered with a flat base DMG bouns. The bouns is calculated as:
$$Flat Base DMG Bouns = Reaction Coefficient × Level Multiplier$$
For Aggravate, the reaction coefficient is 1.15, for Spread 1.25. The level multiplier scales with attacker's level:


**Damage is one of the most important part of a game's combat system.** So I pick this part as the first chapter of all the mechanic articles.<br>
When agents or enemies attack their targets, they generally deal **damage** (abbreviated as **DMG**) based on their own and their targets' attributes.<br>
Note: This article is based on CBT3. It's subject to change.<br>
You may get some information about ZZZ here: [ZZZ_mana_wiki](https://zzz.mana.wiki/)

<!-- TOC -->

- [General Damage Formula](#general-damage-formula)
  - [Base DMG](#base-dmg)
  - [DMG Bouns Multiplier](#dmg-bouns-multiplier)
  - [CRIT Multiplier](#crit-multiplier)
  - [DEF Multiplier](#def-multiplier)
  - [RES Multiplier](#res-multiplier)
  - [Damage Taken Multiplier](#damage-taken-multiplier)
  - [Stun Vulnerability Multiplier](#stun-vulnerability-multiplier)
  - [Special Damage Multiplier](#special-damage-multiplier)
- [Special Damage Formula](#special-damage-formula)
  - [Attribute Anomaly Damage](#attribute-anomaly-damage)
  - [Other Buff Damage](#other-buff-damage)
- [How to calculate accurately](#how-to-calculate-accurately)

<!-- /TOC -->

# General Damage Formula
For DMG dealt by Skills, Talents or enemy attacks, the DMG is calculated as:<br>
$$DMG\enspace =\enspace Base\enspace DMG_{Attacker}\enspace ×\enspace DMG\enspace Bouns\enspace Multiplier_{Attacker}\enspace ×\enspace CRIT\enspace Multiplier_{Attacker}\enspace ×\enspace DEF\enspace Multiplier_{Target}\enspace ×\enspace RES\enspace Multiplier_{Target}\enspace ×\enspace Damage\enspace Taken\enspace Multiplier_{Target}\enspace ×\enspace Stun\enspace Vulnerability\enspace Multiplier_{Target} ×\enspace Special\enspace Multiplier\enspace$$

## Base DMG
$$
\text { Base DMG }={\begin{array}{ll}
\text { DMG Multiplier } × \text { ATK } & \text { if skill scales with ATK } \\
\text { DMG Multiplier } × \text { DEF } & \text { if skill scales with DEF } \\
\text { DMG Multiplier } × \text { Max HP } & \text { if skill scales with Max HP } 
\end{array}}
$$

**Base DMG** is the amount of DMG resulted from multiplying the skill's scaling with the corresponding stat, before accounting for any damage modifiers.<br>
Unless otherwise specified in the skill's attributes, skills will scale with ATK. Some skills may scale with more than one stat.<br>

## DMG Bouns Multiplier
DMG Bouns refers to all percentage-based DMG bounses, including Attribute Type DMG Bounses, as well as special percentage-based DMG bonus based on attacktag(Basic/Special/Ex Special/Sub/Dash/Combo/Assist/Chain Attack, Ultimate, etc.), all DMG bouns and so on. It means **Attacker deals more DMG.**:<br>
$$DMG\enspace Bouns\enspace Multiplier\enspace =\enspace 1\enspace +\enspace ΣDMG\enspace Bouns$$
You may find some DMG Bouns for Fighting Style, this is also all DMG Bouns.

## CRIT Multiplier
When attack triggers a critical hit, damage will get a crit bouns. Crit Rate is a probability, so:<br>

$$ CRIT\enspace Rate_{Effective}\enspace =\enspace clamp\enspace [0,\enspace CRIT\enspace Rate,\enspace 1] $$

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

**When CRIT, the damage numbers will be displayed in a more obvious way (You will find !! behind damage numbers).**

## DEF Multiplier
DEF Multiplier is the multiplier that Defence(abbreviated DEF) reduces incoming damage, it's calculated as:<br>
$$DEF\enspace DMG\enspace Reduction\enspace =\enspace \frac{DEF_{Effective}}{DEF_{Effective}\enspace +\enspace Level\enspace Coefficient_{Attacker}}$$
Then the DEF Multiplier is:<br>
$$DEF\enspace Multiplier\enspace =\enspace 1\enspace -\enspace DEF\enspace DMG\enspace Recduction$$
So you can calculate the DEF Multiplier as:<br>
$$DEF\enspace Multiplier\enspace =\enspace \frac{Level\enspace Coefficient_{Attacker}}{Level\enspace Coefficient_{Attacker}\enspace +\enspace DEF_{Target}}$$
But the Level Coefficient<sub>Attacker</sub> of ZZZ is not like GI or HSR, it's curve is not a linear. You can look up it here: [Level Coefficient](Level_Coefficient_ZZZ.md)<br>
Here is a graph:<br>
<img src="https://github.com/mc-ctrl/Hoyoverse-Theorycrafting-Library/blob/main/Zenless_Zone_Zero/Level%20Coefficient.png"></img>
With the fitting, we can make sure that the Level Coefficient Curve is a quadratic function.<br>
Unlike GI or HSR, the DEF of Enemy differs:<br>
Different enemy has different Base DEF, even the Scaling Curve differs between enemies. You can even find the enemies with same name have different defence.<br>
Considering that the game is still in beta, I'm not interested in compiling these data. You may see these data after CBT3 or Open Test.<br>
During CBT3, Attackers have properties called PEN and PEN Ratio. These are DEF Penerate, which will affect DEF<sub>Effective</sub>. And the Target may have DEF Reduction:<br>
$$DEF_{Effective}\enspace =\enspace DEF\enspace ×\enspace (1\enspace -\enspace DEF\enspace Reduction_{Target}\enspace) ×\enspace (1\enspace -\enspace PEN\enspace Ratio_{Attacker}\enspace) -\enspace PEN$$
For example, in CBT3, one of Advanced Stats of Disk Drive Ⅴ is PEN Ratio, for the S Tier max level, it's 24%. The Boss of Chapter 1, Dead End Butcher has 952.8 DEF at Level 60. It means this PEN Ratio Advanced Stats can offer agents a 15.06% DMG Bouns.<br>

*PS: Other special Advanced Stats of Disk Drive Ⅴ are Attribute Bounses, they are just 30% at max level.*

## RES Multiplier
RES Multiplier is the multiplier that Resistances(abbreviated as RES) affect incoming damage. Targets may have different Attribute Type RE. It's calculated as:
$$RES\enspace Multiplier\enspace =\enspace 1\enspace -\enspace RES_{Effective}$$
$$RES_{Effective}\enspace =\enspace Attribute\enspace Type\enspace RES\enspace +\enspace All\enspace Type\enspace RES\enspace -\enspace RES\enspace Reduction_{Target}\enspace -\enspace RES\enspace Ignored_{Attacker}$$
For example, the Newborn Dead End Butcher has -20% Ice RES and -10% Ether RES in CBT3. Unknown Corruption Complex has 20% Fire RES and 20% Elec RES. We can easily choose suitable Agents for battle.

**When an enemy has a low resistance (≤-20%) to a particular attribute, the damage number for that attribute will flash in white. When an enemy has a high resistance (≥20%) to a particular attribute, the damage number for that attribute will become gray.**
**Organic enemies are weak to Fire, Ethereal enemies are weak to Ice, Robotic enemies are weak to Electric, and Energy enemies are weak to Ether.**

## Damage Taken Multiplier
DMG Taken is just like DMG Bouns. DMG Bouns means Attacker deals more DMG, **DMG Taken means Target takes more DMG**. So you can easily distinguish between them by description:<br>
If you have read the discription of Agents' Special Attack or EX Special Attack, you may find the discription like: "Anti_Interrupt is increased while using the skill, and damage taken is reduced by XX%." This is DMG Reduction, but in ZZZ CBT3, the DMG Reduction is just added with DMG Taken. So:
$$DMG\enspace Taken\enspace Multiplier\enspace =\enspace 1\enspace +\enspace ΣDMG\enspace Taken_{Target}\enspace -ΣDMG\enspace Reduction_{Target}$$

## Stun Vulnerability Multiplier
Stun is one of the most important part of ZZZ's combat system. If your attacks have accumulated enough Daze on a certain enemy. The enemy will be stunned. The Stun Ratio is shown below HP. During stun, the enemy will take more incoming DMG. That is to say, the Stun Vulnerability Multiplier is a special Damage Taken Multiplier, but it multiplies with the general Damage Taken Multiplier.<br>
Check all things about Stun here: [Stun](https://github.com/mc-ctrl/Hoyoverse-Theorycrafting-Library/blob/main/Zenless_Zone_Zero/Stun.md) <br>
Stun Vulnerability differs between enemies, it's generally 50%, sometimes you can also see 100%. Some Bouns in Hollow Zero can increase the Stun Taken Ratio:<br>

$$
\text { Stun Vulnerability Multiplier }={\begin{array}{ll}
\text { 1 + Stun Vulnerability } & \text { if Stunned, you can find the result below Stun Ratio.} \\
\text { 1 } & \text { otherwise } 
\end{array}}
$$

## Special Damage Multiplier
If you have played Grace, Billy or Rina in CBT3, you may notice that these agents have a significant attenuation of damage at a long distance. That is Distance Attenuation. Hoyoverse made this to limit range agents. Unfortunately, I haven't figured out how the damage attenuation works and if there are other attenuations. What we know is that Grace has a different attenuation with Billy and Rina.

# Special Damage Formula
In ZZZ, the Special Damage generally refers to Attribute Anomaly Damage, but there are some other Buff Damage like Impaired. Exiled. They have different trigger methods and may have little in common.

## Attribute Anomaly Damage
Before calculating Attribute Anomaly Damage, you'd better have a knowledge about how to trigger Attribute Anomaly Damage: [Attribute Anomaly](https://github.com/mc-ctrl/Hoyoverse-Theorycrafting-Library/blob/main/Zenless_Zone_Zero/Attribute%20Anomaly.md)<br>
$$DMG\enspace =\enspace Damage\enspace Percentage\enspace ×\enspace ATK\enspace ×\enspace (1\enspace +\enspace Total\enspace AM\enspace /100)\enspace ×\enspace DMG\enspace Bouns\enspace Multiplier\enspace ×\enspace DEF\enspace Multiplier\enspace ×\enspace RES\enspace Multiplier\enspace ×\enspace DMG\enspace Taken\enspace Multiplier\enspace ×\enspace Stun\enspace Vulnerability\enspace Multiplier$$
The Multipliers are just what we introduced in [General Damage Formula](#general-damage-formula).<br>
Note1: The Attribute Anomaly DMG doesn't CRIT.
Note2: In Attribute Anomaly DMG's DMG Bouns Multiplier, there are both Attribute DMG Bounses and Attribute Anomaly DMG Bounses.
Note3: The Level Coefficient in DEF Multiplier is based on the Applier of Attribute Anomaly.
## Other Buff Damage

# How to calculate accurately
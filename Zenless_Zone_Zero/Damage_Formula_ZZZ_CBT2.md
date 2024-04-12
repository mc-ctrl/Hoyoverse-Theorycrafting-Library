**Damage is one of the most important part of a game's combat system.** So I pick this part as the first chapter of all the mechanic articles.<br>
When agents or enemies attack their targets, they generally deal **damage** (abbreviated as **DMG**) based on their own and their targets' attributes.<br>
Note: This article is based on CBT2. It's greatly subject to change.<br>
# General Damage Formula
For DMG dealt by Skills, Talents or enemy attacks, the DMG is calculated as:<br>
$$DMG\enspace =\enspace Base\enspace DMG_{Attacker}\enspace ×\enspace DMG\enspace Bouns\enspace Multiplier_{Attacker}\enspace ×\enspace CRIT Multiplier_{Attacker}\enspace ×\enspace DEF Multiplier_{Target}\enspace ×\enspace REs\enspace Multiplier_{Target}\enspace ×\enspace Damage\enspace Taken\enspace Multiplier_{Target}\enspace ×\enspace Stun\enspace Taken\enspace Multiplier_{Target} ×\enspace Special\enspace Multiplier\enspace$$
## Base DMG
$$
\text { Base DMG }={\begin{array}{ll}
\text { Skill Scaling Percentage } × \text { ATK } & \text { if skill scales with ATK } \\
\text { Skill Scaling Percentage } × \text { DEF } & \text { if skill scales with DEF } \\
\text { Skill Scaling Percentage } × \text { Max HP } & \text { if skill scales with Max HP } 
\end{array}}
$$

**Base DMG** is the amount of DMG resulted from multiplying the skill's scaling with the corresponding stat, before accounting for any damage modifiers.<br>
Unless otherwise specified in the skill's attributes, skills will scale with ATK. Some abilities may scale with more than one stat.<br>
## DMG Bouns Multiplier
DMG Bouns refers to all percentage-based DMG bounses, including Element Type DMG Bounses, as well as special percentage-based DMG bonus based on attacktag(Basic/Special/Ex Special/Sub/Dash/Combo/Assist/Chain Attack, Ultimate, etc.), all DMG bouns and so on. It means **Attacker deals more DMG.**:<br>
$$DMG\enspace Bouns\enspace Multiplier\enspace =\enspace 1\enspace +\enspace ΣDMG\enspace Bouns$$
You may also find some DMG Bouns for Fighting Style, this is also all DMG Bouns.
## CRIT Multiplier
When attack triggers a critical hit, damage will get a crit bouns. Crit Rate is a probability, so:<br>
$$ CRIT\enspace Rate_{Effective}\enspace =\enspace clamp\enspace[0,\enspace CRIT\enspace Rate,\enspace 1] $$ 
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
DEF Multiplier is the multiplier that Defence(abbreviated DEF) reduces incoming damage, it's calculated as:<br>
$$DEF\enspace DMG\enspace Reduction\enspace =\enspace \frac{DEF_{Effective}}{DEF_{Effective}\enspace +\enspace Level\enspace Coefficient_{Attacker}}$$
Then the DEF Multiplier is:<br>
$$DEF\enspace Multiplier\enspace =\enspace 1\enspace -\enspace DEF\enspace DMG\enspace Recduction$$
So you can calculate the DEF Multiplier as:<br>
$$DEF\enspace Multiplier\enspace =\enspace \frac{Level\enspace Coefficient_{Attacker}}{Level\enspace Coefficient_{Attacker}\enspace +\enspace DEF_{Target}}$$
But the Level Coefficient<sub>Attacker</sub> of ZZZ is not like GI or HSR, it's curve is not a linear. You can look up it here: [Level Coefficient](Level_Coefficient_ZZZ.md)<br>
Unlike GI or HSR, the DEF of Enemy differs:<br>
Different enemy has different Base DEF, even the Scaling Curve differs between enemies. You can even find the enemies with same name have different defence.<br>
Considering that the game is still in beta, I'm not interested in compiling these data. You may see these data after CBT3 or Open Test.<br>
During CBT2, Attackers have properties called PEN and PEN Ratio. These are DEF Penerate, which will affect DEF<sub>Effective</sub>. And the Target may have DEF Reduction:<br>
$$DEF_{Effective}\enspace =\enspace DEF\enspace ×\enspace (1\enspace -\enspace DEF\enspace Reduction_{Target}\enspace) ×\enspace (1\enspace -\enspace PEN\enspace Ratio_{Attacker}\enspace) -\enspace PEN$$
For example, in CBT2, one of Advanced Stats of Disk Drive Ⅴ is PEN Ratio, for the S Tier max Level, it's 30%. The Boss of Chapter 1, Dead End Butcher has 1127.48 DEF at Level 60. It means this PEN Ratio Advanced Stats can offer agents a 21.36% DMG Bouns. It's not suitable for game numberical setup. The better DMG Bouns is about 15% for CBT2's ZZZ.<br>
## REs Multiplier
REs Multiplier is the multiplier that Resistances(abbreviated as REs) affect incoming damage. Targets may have different Element Type RE. It's calculated as:
$$REs\enspace Multiplier\enspace =\enspace 1\enspace -\enspace REs_{Effective}$$
$$REs_{Effective}\enspace =\enspace Element\enspace Type\enspace REs\enspace +\enspace All\enspace Type\enspace REs\enspace -\enspace REs\enspace Reduction_{Target}\enspace -\enspace REs\enspace Ignored_{Attacker}$$
For example, the Dead End Butcher has 10% Electric RE and Fire RE, -20% Ether RE and -10% Physical RE in CBT2. We can easily choose suitable Agents for battle.
## Damage Taken Multiplier
DMG Taken is just like DMG Bouns. DMG Bouns means Attacker deals more DMG, **DMG Taken means Target takes more DMG**. So you can easily distinguish between them by description:<br>
$$DMG\enspace Taken\enspace Multiplier\enspace =\enspace 1\enspace +\enspace ΣDMG\enspace Taken$$
In CBT2, Thunder Metal 4-Pc Set Effect is discribed as, "Upon hitting a Shocked enemy, the struck target takes 30% more damage for 6s. This effect does not stack." This is an example for Damage Taken.
If you have read the discription of Agents' Special Attack or EX Special Attack, you may find the discription like: "Anti_Interrupt is increased while using the skill, and damage taken is reduced by 80%." This is DMG Reduction, but in ZZZ CBT2, the DMG Reduction is just added with DMG Taken. So:
$$DMG\enspace Taken\enspace Multiplier\enspace =\enspace 1\enspace +\enspace ΣDMG\enspace Taken_{Target}\enspace -ΣDMG\enspace Reduction_{Target}$$
## Stun Taken Multiplier
Stun is one of the most important part of ZZZ's combat system. If your attacks have accumulate enough Daze on a certain enemy. The enemy will be stunned. During stun, the enemy will take more incoming DMG. That is to say, the Stun Taken Multiplier is a special Damage Taken Multiplier, but it multiplies with the general Damage Taken Multiplier.<br>
Stun Taken Ratio differs between enemies, it's generally 50%, sometimes you can also see 100%. Some Bouns in Hollow Zero can increase the Stun Taken Ratio:<br>

$$
\text { Stun Taken Multiplier }={\begin{array}{ll}
\text { 1 + Stun Taken Ratio } & \text { if Stunned } \\
\text { 1 } & \text { otherwise } 
\end{array}}
$$

## Special Damage Multiplier
If you have played Grace, Billy or Rina in CBT2, you may notice that these agents have a significant attenuation of damage at a long distance. That is Distance Attenuation. Hoyoverse made this to limit range agents. Unfortunately, I haven't figured out how the damage attenuation works and if there are other attenuations. What we know is that Grace has a different attenuation with Billy and Rina.
# Special Damage Formula
## Element Abnormal Damage
## Other Buff Damage
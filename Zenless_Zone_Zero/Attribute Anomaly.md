Attribute Anomaly System is a special part of ZZZ's combat System. Through formation of reasonable Team to trigger Attribute Anomaly can effectively improve the combat efficiency.<br>
In this chapter, I will introduce how to trigger Attribute Anomaly and calculate the Attribute Anomaly DMG.<br>
PS: All text in italics in this article comes from the official discription in CBT3.

# What is Attribute Anomaly

*"Dealing elemental damage also accumulates Anomaly Buildup that inflicts various Attribute Anomalies on enemies!*<br>
*Electric attacks counter robotic enemies.*<br>
*Fire attacks counter organic enemies.*<br>
*Ether attacks counter Energy enemies."*<br><br>
So how to accumalate Anomaly Bulidup?<br>

# Trigger Attribute Anomaly

## Accumulation of Anomaly Buildup
As you see, dealing elemental damage will accumulate Anomaly Bulidup. Certain Elemental DMG accumlate certain Attribute Anomaly Buildup.<br>
In ZZZ, most agent attacks will accumlate Attribute Anomaly Buildup, and some attack from Bangboo will also accumlate certain Attribute Anomaly( This is generally written down in the description of Bangboo's skill).<br>
Different skills accumlate different amount of Anomaly Bulidup. The EX Special Attack, Chain Attack, Ultimate and Assist Follow-up generally accumlates a great amount of Anomaly Buildup. For example, Grace's EX Special Attack accumlates 8.6 times as much Anomaly Bulidup as her Special Attack, but only deals 3.6 times DMG. So it's important to trigger more EX Special Attack, Chain Attack, Ultimate and Assist Follow-up.<br>
The amount of Anomaly Buildup is subject to change in tests, so the data is not displayed here.<br>
Note: If agent's Attribute is not Physical, she doesn't accumlate Physical Anomaly Buildup when dealing Physical DMG.<br>
There is property called Anomaly Rate Bonus, this property is directly multiplicative with skill's amount of Anomaly Buildup.<br>
In CBT2, there was Attribute Anomaly RES, which only affects the Attribute Anomaly Accumalation, not Attribute Anomaly DMG. In CBT3, it has been fixed as Attribute Anomaly Buildup RES.<br>
The amount of Anomaly Buildup is calculated as:<br>
$$Anomaly\enspace Buildup_{Eventual}\enspace =\enspace Anomaly\enspace Buildup_{Original}\enspace ×\enspace AM/\enspace 100\enspace ×\enspace (1\enspace +\enspace Anomaly\enspace Rate\enspace Bouns)\enspace ×\enspace (1\enspace -\enspace Attribute\enspace Anomaly\enspace Buildup\enspace RES)$$

## Triggers
When the accumulation of Anomaly Buildup is enough, Attribute Anomaly is triggered. So what is enough?<br>
The triggers can be catagorized into three groups, Small, Medium and Large.<br>
The group will determine the threshold of Anomaly Buildup to trigger and the reset time.<br>
In general, the threshold will be increased within reset time after Attribute Anomaly is triggered. It can be increased for 9 times, you can call it Level 1~10.<br>
The reset time of Ice Anomaly is 15s. Other Attribute Anomaly's reset time is always 100s.<br>
**In CBT3, Level 1 threshold of Small is 600. Medium is 2250, Large is 3000. And the threshold of Physical Anomaly is 1.2 times.**<br>
**Everytime threshold levels up, it multiplies 1.02. But the threshold is interger. So Level 10 threshold of Large is actually 3581, not 3585. The Level will be kept for reset time if the same Attribute Anomaly is not triggered within this time. After reset time, threshold's will be reset to Level 1.**<br>
*In CBT2, the Level 1 threshold of Small is 700, Medium for 1800, Large for 2500. And it multiplies 1.2 when levels up after level 5.*<br>
<!-- In last test, it's 600, 1500, 3000. It multiplies 1.05 when levels up. -->
**Actually, the Attribute Restraint on Attribute Anomaly is to trigger a different Buff from the normal one.**<br>

# Assault
*Dealing Physical DMG to enemies accumulates the Physical Attribute Anomaly, which subsequently triggers Assault and Flinch effects when enough is accumulated.*<br> 
*Assault interrupts the enemy and deals massive Physical DMG, while Flinch increases the Daze the target takes for a period of time.*<br><br>
*In CBT2, Assault deals 840% Physical DMG based on Applier's attack.*<br>
**In CBT3, it deals 713% DMG.**<br>
<!-- In last test, it deals 713% DMG. -->
*In CBT2, the additional effect of Physical Anomaly is called Armor Break. The Armor Break lasts for 6s, reducing 10% Physical RES.*<br>
**In CBT3, there is a Flinch instead. The Daze Taken Ratio is 10%, it lasts for 10s.**
<!-- Actually, there is a Flinch applied a little before Assault deals DMG in last test instead of Armor Break. I don't know what hoyoverse calls it, there is no information in TextMap_ENTemplateTb. Enemies affected by Flinch will get a Daze Taken Ratio. It seems that Hoyoverse haven't completed it yet. -->

# Freeze
*"Dealing Ice damage to enemies accumulates the Ice Attribute Anomaly, which triggers the Freeze and Frostbite effects.*<br> 
*Freeze prevents taking action for a certain period, and triggers Shatter at the end of the effect, dealing Ice damage.*<br>
*The Frostbite effect increases the CRIT DMG taken by the target for a period of time."*<br><br>
*In CBT2, the Freeze lasts for 6s and triggers Shatter at the end of Freeze. You can end the Freeze and trigger Shatter immediately with a Heavy Hit.The Shatter DMG is based on Attacker's Level, you can look up it here: [Shatter Base CBT2](https://github.com/mc-ctrl/Hoyoverse-Theorycrafting-Library/blob/main/Zenless_Zone_Zero/Shatter%20Base.md)*<br>
**In CBT3, Shatter deals 500% DMG. The Freeze lasts for 10s. Shatter still can be triggered with a Heavy Hit.**
<!-- In last tast, it deals 713% DMG. -->
*In CBT2, Frostbite lasts for 6s, reducing 10% Ice RES.*<br> 
**In CBT3, the effect of Frostbite is modified as Crit DMG Taken Ratio, it's 10%.**
<!-- Actually, the effect of Frostbite is modified as Crit DMG Taken Ratio in last test, but there is no information in TextMap_ENTemplateTb.-->

# Burn
*"Dealing Fire damage to enemies accumulates Fire Anomaly Buildup, which triggers the Burn effect.*<br>
*The Burn effect deals continuous Fire Damage for a period of time. Inflicting the Burn effect can interrupt organic enemies."*<br><br>
*In CBT2, Burn lasts for 6s, it deals 116% Fire DMG based on Applier's ATK per 0.5s. Organic enemies can't move while Burned.*<br>
**In CBT3, it deals 50% DMG per 0.5s. The Burn lasts for 10s. Aganist Organic enemies, it actually triggers Ignite, dealing 75% per 0.5s.**
<!-- In last test, it deals 50% DMG per 0.5s. For Organic enemies, it actually triggers Ignite, dealing 75% DMG per 0.5s. -->

# Corruption
*"Dealing Ether damage to enemies accumulates Ether Anomaly Buildup, which triggers the Corruption effect.*<br>
*The Corruption causes the target to suffer additional Ether damage when attacked for a period of time.*<br>
*Inflicting the Corruption effect can interrupt Energy enemies.*<br><br>
*In CBT2, Corruption lasts for 6s. Corrupted enemy takes 116% Ether DMG based on Applier's ATK (**but Attacker's AM**) when attacked. A single application of Corruption can deal additional Ether damage up to 1 time per 0.334s.*<br>
**In CBT3, it deals 62.5% DMG up to 1 time per 0.5s. Corruption lasts for 10s.**
<!-- In last test, it takes 62.5% DMG and damage CD is 0.5s. -->
*In CBT2, Ether attacks counter Ethereal enemies, it actually triggers Chaos: Chaos has an additional effect: Corrupted Ethereal enemies will attack both friend and foe.*<br>
**In CBT3, Ether attacks counter Energy enemies, it eventually triggers Chaos: It takes 93.8% DMG when attacked up to 1 time per 0.5s. The Chaos lats for 10s.**
<!-- In last test, Ether counters Energy enemies instead of Ethereal enemies. For Energy enemies, it actually triggers Chaos:<br>
Energy enemy is unable to move while Chaos. Enemy under Chaos takes 93.8% DMG when attacked. Damage CD is 0.5s.
Note: Chaos is not Disorder. -->

# Shock
*Dealing Electric DMG to enemies accumulates Electric Anomaly Buildup, which triggers the Shock effect.*<br>
*The Shock effect causes the target to intermittently suffer additional Electric DMG for a period of time when attacked.*
*Shock can interrupt actions for Robotic enemies.*<br><br>
*In CBT2, Shock lasts for 6s. Aganist non-robotic enemies, it deals 350% DMG up to 1 time per 1s, up to 5 times.*<br>
**In CBT3, it deals 125% DMG up to 1 time per 1s, up to 16 times. The Shock lasts for 10s.**<br>
<!-- In last test, it deals 250% DMG up to 1 time per 2s, up to 8 times.-->
For Robotic enemies, it actually triggers Overload:<br>
*In CBT2, Robotic enemy takes 350% DMG and is paralyzed for 4s. When first Paralysis ends, it takes an extra 350% DMG and triggers the second 4s Paralysis. In total, the Robotic enemy takes 350% DMG 2 times and is paralyzed for 8s.*<br>
**In CBT3, it deals 187.5% DMG up to 1 time per 1s, up to 16 times. The Paralysis Duration is modified to 0. The Overload lasts for 10s.**
<!-- In last test, it deals 375% DMG.-->

# Disorder
*Applying another type of Attribute Anomaly to an enemy that has already been afflicted with another overrides the original, and causes the Disorder effect.*<br> 
*The Disorder effect is calculated based on the original state, dealing additional damage and accumulating Daze.*<br><br>
Disorder triggers when enemy under Attribute Anomaly is triggered another Attribute Anomaly.<br>
Disorder deals DMG **based on the rest of original Attribute Anomaly** and accumlates additional Daze.<br>
Disorder is added to speed up the rate of DMG from Attribute Anomalies and encourage players to trigger more Attribute Anomalies.

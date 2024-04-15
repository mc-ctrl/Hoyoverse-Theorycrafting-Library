Attribute Anomaly System is a special part of ZZZ's combat System. Through formation of reasonable Team to trigger Attribute Anomaly can effectively improve the combat efficiency.<br>
In this chapter, I will introduce how to trigger Attribute Anomaly and calculate the Attribute Anomaly DMG.<br>
PS: All text in italics in this article comes from the official discription in CBT2.
# What is Attribute Anomaly
*"Dealing elemental damage also accumulates Anomaly Buildup that inflicts various Attribute Anomalies on enemies!*<br>
*Electric attacks counter robotic enemies.*<br>
*Fire attacks counter organic enemies.*<br>
*Ether attacks counter Ether enemies."*<br>

<!-- It's not correct now. In last test, Ether attacks counter Energy enemies, but Ice attacks counter Ether enemies.-->

The above text is ZZZ's official introduction to Attribute Anomaly, it may be modified in subsequent tests.<br>
So how to accumalate Anomaly Bulidup?<br>
# Trigger Attribute Anomaly
## Accumulation of Anomaly Buildup
As you see, dealing elemental damage will accumulate Anomaly Bulidup. Certain Elemental DMG accumlate certain Attribute Anomaly Buildup.<br>
In ZZZ CBT2, most agent attacks will accumlate Attribute Anomaly Buildup, and some attack from Bangboo will also accumlate certain Attribute Anomaly(This is generally written down in the description of Bangboo's skill).<br>
Different skills accumlate different amount of Anomaly Bulidup. The EX Special Attack, Chain Attack, Ultimate and Assist Follow-up generally accumlates a great amount of Anomaly Buildup. For example, Grace's EX Special Attack accumlates 8.6 times as much Anomaly Bulidup as her Special Attack, but only deals 3.6 times DMG. So it's important to trigger more EX Special Attack, Chain Attack, Ultimate and Assist Follow-up.<br>
The amount of Anomaly Buildup is subject to change in tests, so the data is not displayed here.<br>
Note: If agent's Attribute is not Physical, she doesn't accumlate Physical Anomaly Buildup when dealing Physical DMG.<br>
There is property called Anomaly Rate Bonus in CBT2, this property is directly multiplicative with skill's amount of Anomaly Buildup.<br>
Attribute Anomaly RES only affects the Attribute Anomaly Accumalation, not Attribute Anomaly DMG. In subsequent tests, it will be fixed as Attribute Anomaly Buildup RES.<br>
The amount of Anomaly Buildup is calculated as:<br>
$$Anomaly\enspace Buildup_{Eventual}\enspace =\enspace Anomaly\enspace Buildup_{Original}\enspace ×\enspace (1\enspace +\enspace Anomaly\enspace Rate\enspace Bouns)\enspace ×\enspace (1\enspace -\enspace Attribute\enspace Anomaly\enspace RES)$$
## Triggers
When the accumulation of Anomaly Buildup is enough, Attribute Anomaly is triggered. So what is enough?<br>
The triggers can be catagorized into four groups, Small-1, Small-2, Medium and Large.<br>
Different Attribute of the same enemy can be in different group.<br>
The group will determine the amount of Anomaly Buildup to trigger(abbreviated as **AABT**) and the reset time.<br>
In general, the AABT will be increased within reset time after Attribute Anomaly is triggered. It can be increased for 9 times, you can call it Level 1~10.<br>
The reset time of Ice Anomaly is generally 15s. But it's 30s for Small-2. Other Attribute Anomaly's reset time is always 100s, but it's 30s for Small-2 Physical Anomaly.<br>
The Level 1 AABT of Small-1 and Small-2 is 600. Medium is 1500, Large is 3000. And the AABT of Physical Anomaly is 1.2 times.<br>
Everytime AABT levels up, it is increased by 5%. But the AABT is interger. So Level 10 AABT of Large is actually 4649, not 4654. The Level will be kept for reset time if the same Attribute Anomaly is not triggered within this time. After reset time, AABT's Level will be reset to 1.<br>
**Actually, the Attribute Restraint on Attribute Anomaly is to trigger a different Buff from the normal one.**<br>

# Assault
*"Dealing Physical Damage to enemies causes Physical Anomaly Buildup, which triggers the Assault effect when enough is accumulated.*<br>
*Assault: Interrupts the enemy and deals massive Physical Damage.*<br>
*Armor Break: Physical Damage Resistance is reduced for a certain period."*<br>
In CBT2, Assault deals 840% Physical DMG based on Applier's attack.<br>
<!-- In last test, it deals 713% DMG. -->
The Armor Break lasts for 6s, reducing 10% Physical RES.<br>
<!-- Actually, there is a Flinch applied a little before Assault deals DMG in last test instead of Armor Break. I don't know what hoyoverse calls it, there is no information in TextMap_ENTemplateTb. Enemies affected by Flinch will get a Daze Taken Ratio. It seems that Hoyoverse haven't completed it yet. -->

# Freeze
*"Dealing Ice Damage to enemies causes Ice Anomaly Buildup, which triggers the Freeze effect when enough is accumulated.*<br>
*Freeze: Immobilizes the enemy for a certain period, and triggers Shatter at the end of the effect, dealing Ice damage.*<br>
*Frostbite: Ice Damage Resistance is reduced for a certain period."*<br>
In CBT2, the Freeze lasts for 6s and triggers Shatter at the end of Freeze. Freeze will end immediately if recieving a Heavy Hit.The Shatter DMG is based on Attacker's Level, you can look up it here: [Shatter Base](https://github.com/mc-ctrl/Hoyoverse-Theorycrafting-Library/blob/main/Zenless_Zone_Zero/Shatter%20Base.md)<br>
<!-- In last tast, it deals 713% DMG. -->
Frostbite lasts for 6s, reducing 10% Ice RES.<br> 
<!-- Actually, the effect of Frostbite is modified as Crit DMG Taken Ratio in last test, but there is no information in TextMap_ENTemplateTb. -->

# Burn
*"Dealing Fire damage to enemies accumulates the Fire Attribute Anomaly, which triggers the Burn effect when enough is accumulated.*<br>
*Burn: Deals continuous Fire damage. Organic enemies are unable to move while Burned."*<br>
Burn lasts for 6s, it deals 116% Fire DMG based on Applier's ATK per 0.5s in CBT2. Organic enemies can't move while Burned.<br>
<!-- In last test, it deals 50% DMG per 0.5s. For Organic enemies, it actually triggers Ignite, dealing 75% DMG per 0.5s. -->

# Corruption
*"Dealing Ether damage to enemies accumulates the Ether Attribute Anomaly, causing the Corruption effect when enough is accumulated.*<br>
*Corruption: Causes additional Ether damage when attacked. Corrupted Ethereal enemies will also attack both friend and foe."*<br>
Corruption lasts for 6s. Corrupted enemy takes 116% Ether DMG based on Applier's ATK (**but Attacker's AM**) when attacked. A single application of Corruption can deal additional Ether damage up to 1 time per 0.334s.<br>
<!-- In last test, it takes 50% DMG and damage CD is 0.5s. -->
Corrupted Ethereal enemies will also attack both friend and foe.<br>
<!-- In last test, Ether counters Energy enemies instead of Ethereal enemies. For Energy enemies, it actually triggers Chaos:<br>
Energy enemy is unable to move while Chaos. Enemy under Chaos takes 93.8% DMG when attacked. Damage CD is 0.5s.
Note: Chaos is not Disorder. -->

# Shock
*"Dealing Electric damage to enemies accumulates the Electric Attribute Anomaly, which triggers the Shock effect when enough is accumulated.*<br>
*Shock: Being attacked intermittently triggers additional Electric damage and interrupts enemy actions. Robotic enemies are unable to move while Shocked."*<br>
Shock lasts for 6s. Aganist non-robotic enemies, dealing 350% DMG up to 1 time per 1s, up to 5 times.<br>
<!-- In last test, it deals 350% DMG up to 1 time per 2s, up to 8 times. -->
For Robotic enemies, it actually triggers Overload:<br>
Robotic enemy takes 350% DMG and is paralyzed for 4s. When first Paralysis ends, it takes an extra 350% DMG and triggers the second 4s Paralysis. In total, the Robotic enemy takes 350% DMG 2 times and is paralyzed for 8s.
<!-- In last test, it deals 375% DMG. -->

<!-- # Disorder
Disorder triggers when enemy under Attribute Anomaly is triggered another Attribute Anomaly.<br>
Hoyoverse added it because the same enemy cam only fall into one Attribute Anomaly at the same time, later Attribute Anomaly will overwrite the earlier one.<br>
Disorder deals Physical DMG <b>based on the original Attribute Anomaly</b> and accumlates additional Daze.<br>
Disorder is added to speed up the rate of DMG from Attribute Anomalies and encourage players to trigger more Attribute Anomalies.
-->

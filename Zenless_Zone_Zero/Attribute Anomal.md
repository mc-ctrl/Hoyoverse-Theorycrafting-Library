Attribute Anomal System is a special part of ZZZ's combat System. Through formation of reasonable Team to trigger Attribute Anomal can effectively improve the combat efficiency.<br>
In this chapter, I will introduce how to trigger Attribute Anomal and calculate the Attribute Anomal DMG.<br>

# What is Attribute Anomal
*"Dealing elemental damage also accumulates Anomaly Buildup that inflicts various Attribute Anomalies on enemies!*<br>
*Electric attacks counter robotic enemies.*<br>
*Fire attacks counter organic enemies.*<br>
*Ether attacks counter Ether enemies."*<br>
The above text is ZZZ's official introduction to Attribute Anomal, it may be modified in subsequent tests.<br>
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
The group will determine the amount of Anomaly Buildup to trigger(abbreviated it as **AABT**) and the reset time.<br>
In general, the AABT will be increased within reset time after Attribute Anomaly is triggered. It can be increased for 9 times, you can call it Level 1~10.<br>
The reset time of Ice Anomal is generally 15s. But it's 30s for Small-2. Other Attribute Anomal's reset time is always 100s, but it's 30s for Small-2 Physical Anomal.<br>
The Level 1 AABT of Small-1 and Small-2 is 600. Medium is 1500, Large is 3000. And the AABT of Physical Anomal is 1.2 times.<br>
Everytime AABT levels up, it is increased by 5%. But the AABT is interger. So Level 10 AABT of Large is actually 4649, not 4654. The Level will be kept for reset time if the same Attribute Anomal is not triggered within this time. After reset time, AABT's Level will be reset to 1.<br>
Actually, the Attribute Restraint is to trigger a different Buff from the normal one.<br>
# Assault
*"Dealing Physical Damage to enemies causes Physical Anomaly Buildup, which triggers the Assault effect when enough is accumulated.*<br>
*Assault: Interrupts the enemy and deals massive Physical Damage."*<br>
Damage Percentage: 7.13.<br>
# Freeze
*"Dealing Ice Damage to enemies causes Ice Anomaly Buildup, which triggers the Freeze effect when enough is accumulated.*<br>
*Freeze: Immobilizes the enemy for a certain period, and triggers Shatter at the end of the effect, dealing Ice damage."*<br>
HeavyHitCount: 1, Damage Percentage: 7.13.<br>
Frostbite: Damage Percentage: 7.13.<br>
# Burn
*"Dealing Fire damage to enemies accumulates the Fire Attribute Anomaly, which triggers the Burn effect when enough is accumulated.*<br>
*Burn: Deals continuous Fire damage. Organic enemies are unable to move while Burned."*<br>
DamageTick: 0.5s, Damage Percentage: 0.5.<br>
Ignite: DamageTick: 0.5s, Damage Percentage: 0.75.<br>
# Corruption
*"Dealing Ether damage to enemies accumulates the Ether Attribute Anomaly, causing the Corruption effect when enough is accumulated.*<br>
*Corruption: Causes additional Ether damage when attacked. Corrupted Ethereal enemies will also attack both friend and foe."*<br>
Damage Percentage: 0.625, Damage CD: 0.5s.<br>
Chaos: Damage Percentage: 0.938, Damage CD: 0.5s.<br>
# Shock
*"Dealing Electric damage to enemies accumulates the Electric Attribute Anomaly, which triggers the Shock effect when enough is accumulated.*<br>
*Shock: Being attacked intermittently triggers additional Electric damage and interrupts enemy actions. Robotic enemies are unable to move while Shocked."*<br>
Damage Percentage: 2.5, Damage CD: 2s, MaxHitNum: 8.<br>
Overload: Damage Percentage: 3.75, Damage CD: 2s, Paralysis Duration: 4s, MaxHitNum: 8.<br>

# Why we need Stun

When enemy is attacked, Daze will be accumlated. Enemy will fall into Stun after accumlating enoungh Daze. The Daze shown below HP is actually the Stun Ratio(Daze Buildup/ max Stun). The Stun Vulnerability Multiplier will be shown below Stun Ratio when Stunned. The information panel of BOSS enemy is displayed in the upper right corner of the screen.<br>
**1. Stun applies a extra Vulnerability Multiplier which greatly increases agents' DMG.**<br>
When there are two or more agents in your team, hitting an enemy stunned with a Heavy Hit can trigger a Combo Attack; generally, the last part of a Normal Attack, Dodge Counter, Special Attack, Ex Special Attack, Combo Attack, and Ultimate will have a Heavy Hit effect. One, two, three times of Combo Attacks can be triggered when attack Normal, Elite, BOSS enemies. <br>
**2. Stun is a necessary to trigger Combo Attack.**<br>
In CBT2, there is a max Assist Point of Perfect Assist shared in the team. Once Perfect Assist is triggered, one Assist Point is consumed. Unless otherwise noted, Combo Attack is the only way to regain Assist Point in the game.<br>
**3. Stun is vital to trigger Perfect Assist.**<br>
Enemy is unable to move when Stunned. Stun can interrupt all enemy attacks.<br>
**4. Stun decreases the survival stress and increases the DMG efficiency.**

# How to trigger Stun

The Stun comes from the accumlation of Daze. So the key to trigger Stun is increasing the Daze efficience. You can easily check the Daze Multiplier in agent's Skill Panel. It's usually shown below DMG Multiplier. The Daze Multiplier multiplies with agent's Impact. Agent's Impact is shown on Stats Panel, you can easily check it both in and out of combat.<br>
Daze Bouns affacts the Daze Bulidup. Some Buffs will increase enemies' Daze RES, and you may find some Daze RES on Fighting Styles (Cut, Pierce and Strike) or Attribute. Some debuffs are discribed as, "Enemies accumulate more Daze." It's not Daze Taken Ratio, but it decreases Daze RES. So the Daze Buidup is calculated as:<br>
$$Daze\enspace Buildup\enspace =\enspace Σ[Impact\enspace ×\enspace Daze\enspace Multiplier\enspace ×\enspace (1\enspace +\enspace Daze\enspace Bouns)\enspace ×\enspace (1\enspace +\enspace Daze\enspace RES\enspace -\enspace Daze\enspace RES\enspace Decrease)]$$
The Stun Ratio shown below is calculated as:<br>
$$Stun\enspace Ratio\enspace =\enspace Daze\enspace Buidup/\enspace max\enspace Stun$$
For the certain enemy, the max Stun is generally fixed. So to trigger more Stun is to accumlate more Daze Buildup.<br>
<!-- In CBT2, the max Stun doesn't scale with enemy's level, but in last test, it does. -->
In CBT3, the Daze Multiplier turns to scale with Skill's level. The buffs or debuffs for Daze are mostly uncontrollable. So you'd better increase agent's Impact or trigger more Dazeful Skills to trigger more Stun.<br>
It can be easily found that EX Special Skill, Ultimate, Defensive Assist and Assist Follow-up generally accumlate more Daze Buildup. So try to trigger more Perfect Assists!<br>

# Stun itself

We've spent a lot ink on triggering Stun, not let's look at Stun itself. There are some parameters about enemy's Stun:<br>

## max Stun

First, of course the max Stun. The max Stun differs between enemies, even the enemies with the same name may have different max Stun.<br>

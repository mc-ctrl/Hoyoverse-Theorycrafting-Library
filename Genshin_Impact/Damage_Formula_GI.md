**Damage is the most important part of Genshin Impact's combat system.** So I pick this part as the first chapter of all the mechanic articles.<br>
When characters, enemies or some gadgets attack their targets, they generally deal **damage** (abbreviated as **DMG**) based on their own and their targets' attributes.<br>
Note: A single instance of damage cannot exceed 9,999,999. HP loss is not damage.<br>
# General Damage Formula
For DMG dealt by Talents, Constellations, Weapon passives, enemy attacks or gadget attacks, the DMG is calculated as:<br>
$$DMG = ((Σ(Base DMG × Base DMG Coefficient) + Additive Base DMG Bouns)) × DMG Bouns Multiplier × DEF Multiplier_{Target} × REs Multiplier_{Target} × CRIT Multiplier × Amplifying Multiplier × Special Multiplier$$
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
**Base DMG Coefficient** is special coefficient that modifies Base DMG, it is directly multiplicative with Base DMG. It's generally discribed as "Attacks Deal *Cofficient* of the **original DMG**." In game, it can be found in Yoimiya's [Skill](https://genshin-impact.fandom.com/wiki/Niwabi_Fire-Dance), Neuvillette's [1st Ascension Passive](https://genshin-impact.fandom.com/wiki/Heir_to_the_Ancient_Sea%27s_Authority), Navia's [Skill](https://genshin-impact.fandom.com/wiki/Ceremonial_Crystalshot), Furina's [Skill](https://genshin-impact.fandom.com/wiki/Salon_Solitaire), Wanderer's [Skill](https://genshin-impact.fandom.com/wiki/Hanega:_Song_of_the_Wind), Wriothesley's [Skill](https://genshin-impact.fandom.com/wiki/Icefang_Rush), Xingqiu's [4th Constellation](https://genshin-impact.fandom.com/wiki/Evilsoother) and Traveler(Electro)'s [6th Constellation](https://genshin-impact.fandom.com/wiki/World-Shaker).<br><br>
**Additive Base DMG Bouns** is a bouns DMG added to the base DMG, it's normally fixed or scaling with attacker's sub stat. It's generally discribed as "Attack DMG is increased by *bouns%* of **sub stat**". This type of Additive Base DMG Bonus can be calculated in the same way as Base DMG.<br>
The other type of it is the damage bouns from **Spread and Aggravate** Elemental Reactions. When the attacks inflict Dendro or Electro on the target affected by Quicken Aura, the Spread or Aggravate will be triggered with a flat base DMG bouns. The bouns is calculated as:
$$Flat Base DMG Bouns = Reaction Coefficient × Level Multiplier × (1 + EM Bouns + Reaction Bouns)$$
For Aggravate, the reaction coefficient is 1.15, for Spread 1.25. The level multiplier scales with attacker's level:
<table>
<tr>
<th>Level</th>
<th>Enemy or Environment</th>
<th>Character</th>
<th>Crystallize Shield</th>
</tr>
    <tr>
        <td>1</td>
        <td>17.165605</td>
        <td>17.165605</td>
        <td>91.1791 </td>
    </tr>
    <tr>
        <td>2</td>
        <td>18.535048</td>
        <td>18.535048</td>
        <td>98.707667 </td>
    </tr>
    <tr>
        <td>3</td>
        <td>19.904854</td>
        <td>19.904854</td>
        <td>106.23622 </td>
    </tr>
    <tr>
        <td>4</td>
        <td>21.274903</td>
        <td>21.274903</td>
        <td>113.764771 </td>
    </tr>
    <tr>
        <td>5</td>
        <td>22.6454</td>
        <td>22.6454</td>
        <td>121.293322 </td>
    </tr>
    <tr>
        <td>6</td>
        <td>24.649613</td>
        <td>24.649613</td>
        <td>128.821878 </td>
    </tr>
    <tr>
        <td>7</td>
        <td>26.640643</td>
        <td>26.640643</td>
        <td>136.350422 </td>
    </tr>
    <tr>
        <td>8</td>
        <td>28.868587</td>
        <td>28.868587</td>
        <td>143.878978 </td>
    </tr>
    <tr>
        <td>9</td>
        <td>31.367679</td>
        <td>31.367679</td>
        <td>151.407522 </td>
    </tr>
    <tr>
        <td>10</td>
        <td>34.143343</td>
        <td>34.143343</td>
        <td>158.936078 </td>
    </tr>
    <tr>
        <td>11</td>
        <td>37.201</td>
        <td>37.201</td>
        <td>169.991484 </td>
    </tr>
    <tr>
        <td>12</td>
        <td>40.66</td>
        <td>40.66</td>
        <td>181.076253 </td>
    </tr>
    <tr>
        <td>13</td>
        <td>44.446668</td>
        <td>44.446668</td>
        <td>192.190362 </td>
    </tr>
    <tr>
        <td>14</td>
        <td>48.563519</td>
        <td>48.563519</td>
        <td>204.048207 </td>
    </tr>
    <tr>
        <td>15</td>
        <td>53.74848</td>
        <td>53.74848</td>
        <td>215.938996 </td>
    </tr>
    <tr>
        <td>16</td>
        <td>59.081897</td>
        <td>59.081897</td>
        <td>227.86275 </td>
    </tr>
    <tr>
        <td>17</td>
        <td>64.420047</td>
        <td>64.420047</td>
        <td>247.685944 </td>
    </tr>
    <tr>
        <td>18</td>
        <td>69.724455</td>
        <td>69.724455</td>
        <td>267.542105 </td>
    </tr>
    <tr>
        <td>19</td>
        <td>75.123137</td>
        <td>75.123137</td>
        <td>287.431209 </td>
    </tr>
    <tr>
        <td>20</td>
        <td>80.584775</td>
        <td>80.584775</td>
        <td>303.826417 </td>
    </tr>
    <tr>
        <td>21</td>
        <td>86.112028</td>
        <td>86.112028</td>
        <td>320.225217 </td>
    </tr>
    <tr>
        <td>22</td>
        <td>91.703742</td>
        <td>91.703742</td>
        <td>336.627633 </td>
    </tr>
    <tr>
        <td>23</td>
        <td>97.244628</td>
        <td>97.244628</td>
        <td>352.319267 </td>
    </tr>
    <tr>
        <td>24</td>
        <td>102.812644</td>
        <td>102.812644</td>
        <td>368.010913 </td>
    </tr>
    <tr>
        <td>25</td>
        <td>108.409563</td>
        <td>108.409563</td>
        <td>383.702548 </td>
    </tr>
    <tr>
        <td>26</td>
        <td>113.201694</td>
        <td>113.201694</td>
        <td>394.432358 </td>
    </tr>
    <tr>
        <td>27</td>
        <td>118.102906</td>
        <td>118.102906</td>
        <td>405.18147 </td>
    </tr>
    <tr>
        <td>28</td>
        <td>122.979318</td>
        <td>122.979318</td>
        <td>415.949907 </td>
    </tr>
    <tr>
        <td>29</td>
        <td>129.72733</td>
        <td>129.72733</td>
        <td>426.737645 </td>
    </tr>
    <tr>
        <td>30</td>
        <td>136.29291</td>
        <td>136.29291</td>
        <td>437.544709 </td>
    </tr>
    <tr>
        <td>31</td>
        <td>142.67085</td>
        <td>142.67085</td>
        <td>450.600004 </td>
    </tr>
    <tr>
        <td>32</td>
        <td>149.029029</td>
        <td>149.029029</td>
        <td>463.700301 </td>
    </tr>
    <tr>
        <td>33</td>
        <td>155.416987</td>
        <td>155.416987</td>
        <td>476.845577 </td>
    </tr>
    <tr>
        <td>34</td>
        <td>161.825495</td>
        <td>161.825495</td>
        <td>491.127512 </td>
    </tr>
    <tr>
        <td>35</td>
        <td>169.106313</td>
        <td>169.106313</td>
        <td>502.554564 </td>
    </tr>
    <tr>
        <td>36</td>
        <td>176.518077</td>
        <td>176.518077</td>
        <td>514.012104 </td>
    </tr>
    <tr>
        <td>37</td>
        <td>184.072741</td>
        <td>184.072741</td>
        <td>531.409589 </td>
    </tr>
    <tr>
        <td>38</td>
        <td>191.709518</td>
        <td>191.709518</td>
        <td>549.979601 </td>
    </tr>
    <tr>
        <td>39</td>
        <td>199.556908</td>
        <td>199.556908</td>
        <td>568.58488 </td>
    </tr>
    <tr>
        <td>40</td>
        <td>207.382042</td>
        <td>207.382042</td>
        <td>584.99652</td>
    </tr>
    <tr>
        <td>41</td>
        <td>215.3989</td>
        <td>215.3989</td>
        <td>605.670375 </td>
    </tr>
    <tr>
        <td>42</td>
        <td>224.165667</td>
        <td>224.165667</td>
        <td>626.386206 </td>
    </tr>
    <tr>
        <td>43</td>
        <td>233.50216</td>
        <td>233.50216</td>
        <td>646.052333 </td>
    </tr>
    <tr>
        <td>44</td>
        <td>243.350573</td>
        <td>243.350573</td>
        <td>665.755638 </td>
    </tr>
    <tr>
        <td>45</td>
        <td>256.063067</td>
        <td>256.063067</td>
        <td>685.496096 </td>
    </tr>
    <tr>
        <td>46</td>
        <td>268.543493</td>
        <td>268.543493</td>
        <td>700.839402 </td>
    </tr>
    <tr>
        <td>47</td>
        <td>281.526075</td>
        <td>281.526075</td>
        <td>723.333147 </td>
    </tr>
    <tr>
        <td>48</td>
        <td>295.013648</td>
        <td>295.013648</td>
        <td>745.865265 </td>
    </tr>
    <tr>
        <td>49</td>
        <td>309.067188</td>
        <td>309.067188</td>
        <td>768.435731 </td>
    </tr>
    <tr>
        <td>50</td>
        <td>323.601597</td>
        <td>323.601597</td>
        <td>786.791945 </td>
    </tr>
    <tr>
        <td>51</td>
        <td>336.757542</td>
        <td>336.757542</td>
        <td>809.538812 </td>
    </tr>
    <tr>
        <td>52</td>
        <td>350.530312</td>
        <td>350.530312</td>
        <td>832.329057 </td>
    </tr>
    <tr>
        <td>53</td>
        <td>364.482705</td>
        <td>364.482705</td>
        <td>855.162654 </td>
    </tr>
    <tr>
        <td>54</td>
        <td>378.619181</td>
        <td>378.619181</td>
        <td>878.039628 </td>
    </tr>
    <tr>
        <td>55</td>
        <td>398.600417</td>
        <td>398.600417</td>
        <td>899.484802 </td>
    </tr>
    <tr>
        <td>56</td>
        <td>416.398254</td>
        <td>416.398254</td>
        <td>919.362018 </td>
    </tr>
    <tr>
        <td>57</td>
        <td>434.386996</td>
        <td>434.386996</td>
        <td>946.039586 </td>
    </tr>
    <tr>
        <td>58</td>
        <td>452.566797</td>
        <td>452.951051</td>
        <td>974.764223 </td>
    </tr>
    <tr>
        <td>59</td>
        <td>471.426268</td>
        <td>472.606217</td>
        <td>1003.578617 </td>
    </tr>
    <tr>
        <td>60</td>
        <td>490.481663</td>
        <td>492.88489</td>
        <td>1030.077002</td>
    </tr>
    <tr>
        <td>61</td>
        <td>509.50428</td>
        <td>513.568543</td>
        <td>1056.634974 </td>
    </tr>
    <tr>
        <td>62</td>
        <td>532.771793</td>
        <td>539.103198</td>
        <td>1085.246306 </td>
    </tr>
    <tr>
        <td>63</td>
        <td>556.393323</td>
        <td>565.510563</td>
        <td>1113.924427 </td>
    </tr>
    <tr>
        <td>64</td>
        <td>580.103031</td>
        <td>592.538753</td>
        <td>1149.25872 </td>
    </tr>
    <tr>
        <td>65</td>
        <td>607.894973</td>
        <td>624.443427</td>
        <td>1178.064819 </td>
    </tr>
    <tr>
        <td>66</td>
        <td>630.20133</td>
        <td>651.470148</td>
        <td>1200.223743 </td>
    </tr>
    <tr>
        <td>67</td>
        <td>652.866818</td>
        <td>679.49683</td>
        <td>1227.660294 </td>
    </tr>
    <tr>
        <td>68</td>
        <td>675.186325</td>
        <td>707.79406</td>
        <td>1257.242987 </td>
    </tr>
    <tr>
        <td>69</td>
        <td>697.782682</td>
        <td>736.671422</td>
        <td>1284.917392 </td>
    </tr>
    <tr>
        <td>70</td>
        <td>720.170325</td>
        <td>765.640231</td>
        <td>1314.75288 </td>
    </tr>
    <tr>
        <td>71</td>
        <td>742.454652</td>
        <td>794.773403</td>
        <td>1342.665216 </td>
    </tr>
    <tr>
        <td>72</td>
        <td>765.205477</td>
        <td>824.677397</td>
        <td>1372.752485 </td>
    </tr>
    <tr>
        <td>73</td>
        <td>784.374617</td>
        <td>851.157781</td>
        <td>1396.320986 </td>
    </tr>
    <tr>
        <td>74</td>
        <td>803.401172</td>
        <td>877.74209</td>
        <td>1427.312436 </td>
    </tr>
    <tr>
        <td>75</td>
        <td>830.920776</td>
        <td>914.229123</td>
        <td>1458.374528 </td>
    </tr>
    <tr>
        <td>76</td>
        <td>854.403332</td>
        <td>946.746752</td>
        <td>1482.335772 </td>
    </tr>
    <tr>
        <td>77</td>
        <td>877.759777</td>
        <td>979.411386</td>
        <td>1511.910837 </td>
    </tr>
    <tr>
        <td>78</td>
        <td>900.117232</td>
        <td>1011.223022</td>
        <td>1541.549377 </td>
    </tr>
    <tr>
        <td>79</td>
        <td>923.766661</td>
        <td>1044.791746</td>
        <td>1569.153701 </td>
    </tr>
    <tr>
        <td>80</td>
        <td>946.370258</td>
        <td>1077.443668</td>
        <td>1596.814298</td>
    </tr>
    <tr>
        <td>81</td>
        <td>968.634183</td>
        <td>1109.99754</td>
        <td>1622.419626 </td>
    </tr>
    <tr>
        <td>82</td>
        <td>991.029365</td>
        <td>1142.976615</td>
        <td>1648.074031 </td>
    </tr>
    <tr>
        <td>83</td>
        <td>1013.527108</td>
        <td>1176.369483</td>
        <td>1666.376146 </td>
    </tr>
    <tr>
        <td>84</td>
        <td>1036.132954</td>
        <td>1210.184393</td>
        <td>1684.678276 </td>
    </tr>
    <tr>
        <td>85</td>
        <td>1066.623598</td>
        <td>1253.835659</td>
        <td>1702.980391 </td>
    </tr>
    <tr>
        <td>86</td>
        <td>1089.964198</td>
        <td>1288.952801</td>
        <td>1726.104684 </td>
    </tr>
    <tr>
        <td>87</td>
        <td>1114.964489</td>
        <td>1325.484092</td>
        <td>1754.671567 </td>
    </tr>
    <tr>
        <td>88</td>
        <td>1141.662656</td>
        <td>1363.456928</td>
        <td>1785.86656 </td>
    </tr>
    <tr>
        <td>89</td>
        <td>1171.941798</td>
        <td>1405.097377</td>
        <td>1817.137404 </td>
    </tr>
    <tr>
        <td>90</td>
        <td>1202.813736</td>
        <td>1446.853458</td>
        <td>1851.060358 </td>
    </tr>
    <tr>
        <td>91</td>
        <td>1233.939915</td>
        <td>1488.215547</td>
        <td>1885.067163 </td>
    </tr>
    <tr>
        <td>92</td>
        <td>1264.69967</td>
        <td>1528.444567</td>
        <td>1921.749303 </td>
    </tr>
    <tr>
        <td>93</td>
        <td>1305.689483</td>
        <td>1580.367911</td>
        <td>1958.523291 </td>
    </tr>
    <tr>
        <td>94</td>
        <td>1346.084383</td>
        <td>1630.847528</td>
        <td>2006.194108 </td>
    </tr>
    <tr>
        <td>95</td>
        <td>1411.738173</td>
        <td>1711.197785</td>
        <td>2041.569007 </td>
    </tr>
    <tr>
        <td>96</td>
        <td>1468.874501</td>
        <td>1780.453941</td>
        <td>2054.472064 </td>
    </tr>
    <tr>
        <td>97</td>
        <td>1524.041318</td>
        <td>1847.322809</td>
        <td>2065.97498 </td>
    </tr>
    <tr>
        <td>98</td>
        <td>1576.966305</td>
        <td>1911.474309</td>
        <td>2174.7226 </td>
    </tr>
    <tr>
        <td>99</td>
        <td>1627.613082</td>
        <td>1972.864342</td>
        <td>2186.7682 </td>
    </tr>
    <tr>
        <td>100</td>
        <td>1674.809242</td>
        <td>2030.071808</td>
        <td>2198.81396</td>
    </tr>
</table>

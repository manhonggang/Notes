### [蓝帖] 玩家面对低等级怪物承受/造成伤害的调整


这里是你仍能单刷旧副本(你不是Mione的话)的细节。包括伪代码，所以你得有一定想象力来看懂它。  
(译者注：我给你们在每段下面提供了结果，看不懂代码的直接去看即可)

受到伤害减免  
所有玩家被低等级怪物攻击时都会有一个伤害减免系数，这只适用于熊猫人之谜之前版本的怪物。所有受到的伤害会乘以减免系数，定义如下：  
LevelDiff = PlayerLevel - CreatureLevel  
if (CreatureExpansion < Pandaria) then  
// 10% DR per level diff, with a floor of 10%  
DamageTakenFactor = max(1.0 - 0.1 \* LevelDiff, 0.1)  
else  
DamageTakenFactor = 1.0  
end  
注：会根据玩家与怪物等级差来减免伤害。仅适用于MOP之前版本怪物，mop怪物伤害不减免。  
设等级差为x，即你的等级-怪物等级=x  
如果x<=10，那么每等级差你所受伤害降低10%，例如，你90，怪物83，那么你受到的伤害减免70%。  
如果x>=10，那么你受到的伤害永远都减免90%。比如你90级，怪物73级，伤害减免就是90%。

造成伤害提升  
所有玩家在面对低等级生物时都会有个伤害提升系数。这只适用于熊猫人之谜之前版本的怪物。所有对怪物造成的伤害都会生意伤害提升系数，定义如下  
LevelDiff = PlayerLevel - CreatureLevel  
if (CreatureExpansion >= Pandaria) then  
DamageDealtFactor = 1.0  
elseif (LevelDiff < 5) then  
// Ranges from 1.0625 to 1.25 vs. 1-4 LevelDiffs  
DamageDealtFactor = 1 + 0.0625 \* LevelDiff  
elseif (LevelDiff < 10) then  
// Ranges from 4.0 to 6.0 vs. 5-9 LevelDiffs  
DamageDealtFactor = 1.5 + 0.5 \* LevelDiff  
else  
// Maximum factor of 16.5 vs. 10+ LevelDiffs  
DamageDealtFactor = 16.5  
end  
注：会根据等级差提高你造成的伤害。仅适用于MOP之前版本怪物，对mop怪物伤害不提高。  
假设等级差为x，即你的等级-怪物等级=x  
如果x<5，那么伤害系数=1+0.0625x，比如你90，面对87级怪物，伤害提升18.75%。  
如果5<=x<10，那么伤害系数=1.5+0.5x，比如你90，面对83级怪物，伤害提升500%。  
如果x>=10，那么伤害系数=16.5，比如你90，面对73级怪物，伤害提升1650%。

版本内动态伤害调整  
我们也想在版本内提供实力增长的途径，尽管我们已经将装等属性曲线扩展到了旧版本中。这只适用于熊猫人之谜之前的版本的生物。我们为此计算承受/造成伤害的系数，一起用或只用一个，哪个对玩家最好就用哪个。  
MaxPlayerLevelsByExpansion = {69, 79, 84, 89, 0, 0}  
IntendedItemLevelByExpansion = {65, 115, 200, 346, 0, 0}  
MaxPlayerLevel = MaxPlayerLevelsByExpansion\[CreatureExpansion\]  
IntendedItemLevel = IntendedItemLevelByExpansion\[CreatureExpansion\]

if (PlayerLevel <= MaxPlayerLevel and  
PlayerEquippedItemLevel > IntendedItemLevel) then  
AlternateDamageTakenFactor = 1 - 0.01 \* (PlayerEquippedItemLevel - IntendedItemLevel)  
AlternateDamageDealtFactor = 1 + 5/3\*0.01 \* (PlayerEquippedItemLevel - IntendedItemLevel)  
DamageTakenFactor = min(DamageTakenFactor, AlternateDamageTakenFactor)  
DamageDealtFactor = max(DamageDealtFactor, AlternateDamageDealtFactor)  
end

  
注：预设每个版本的满级是69,79,84,89，预设每个版本装等为65,115,200,346  
如果玩家等级<=满级，并且装等>预设装等，那么  
动态伤害承受系数=1-0.01\*(玩家装等-预设装等)  
动态伤害提高系数=1+5/3\*0.01\*(玩家装等-预设装等)  
最终伤害承受系数为伤害承受系数和动态伤害承受系数的最小值。  
最终伤害提高系数为伤害提高系数和动态伤害提高系数的最大值。  
即你在未满级情况下穿新版本装备会打怪更狠，受伤更少。 ……咩~
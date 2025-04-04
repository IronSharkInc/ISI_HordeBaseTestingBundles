# ISI Horde Base Testing Bundles

A 7 Days to Die (7D2D) mod that adds bundles that simplify testing horde bases in dev mode.

![Horde Night Bundle](images/isiBundles.png)

## Bundles

- ISI Horde Night Bundle - a collection of bundles that make preparing for horde night easy
  - XP to get to level 300
  - Armor Bundle
    - a set of tier 6 armor with headlight and pocket mods
  - Melee Weapon Bundle
    - a tier 6 melee weapon with mods, and perk books
  - Ranged Weapon Bundle
    - a tier 6 ranged weapon with mods, perk books, and ammo
  - Explosives Bundle
  - Food and Drink Bundle
  - Meds and Drugs Bundle
  - Repair Bundle
- Electricity Bundle
  - ISI Infinite Solar Cells Bundle
  - ISI Infinite Batteries Bundle
  - ISI Infinite Engines Bundle
- _trap restock bundles (no mega bundle)_
  - ISI Infinite Darts Bundle - Dart Traps
  - ISI Infinite 9mm Bundle - SMG Turret
  - ISI Infinite Shotgun Shells Bundle - Shotgun Turret

## How to use

The bundles only appear in the creative menu.

- `F1` - Hit `F1` to open the console
- `cm` - Type `cm` then hit `Enter` to enable creative mode
- `u` - Hit `Close` (or hit `ESC`) to close the console, then hit `u` to open the creative menu
- Search for `isi`

## Screenshots
![Horde Night Bundle](images/isiHordeNightBundle.png)
![Armor Bundle](images/isiPreacherArmorBundle.png)
![Melee Weapon Bundle](images/isiClubBundle.png)
![Ranged Weapon Bundle](images/isiM60Bundle.png)
![Explosives Bundle](images/isiExplosivesBundle.png)
![Food and Drinks Bundle](images/isiFoodBundle.png)
![Meds and Drugs Bundle](images/isiMedicalBundle.png)
![Electricity Bundle](images/isiElectricityBundle.png)
![Battery Bundle](images/isiBatteryBundle.png)
![Trap Restock Bundles](images/isiDartBundle.png)

## Customizing

If you would like to change the default armor, melee weapon, or ranged weapon bundles you can edit the `isiHordeNightBundle` in [items.xml](Config/items.xml).

For example, if you would like the bundle to include the lumberjack armor instead of the preacher armor, you would just replace `isiPreacherArmorBundle` with `isiLumberjackArmorBundle`

```xml
<item name="isiHordeNightBundle">
    <property name="Extends" value="isiBundle"/>
    <property name="CustomIcon" value="bundleDartTrap"/>
    <property name="DescriptionKey" value="isiHordeNightBundleDescription"/>
    <property class="Action0">
        <property name="Create_item" value="
            giveXP_T300_admin,
            isiPreacherArmorBundle,
            isiClubBundle,
            isiM60Bundle,
            isiExplosivesBundle,
            isiFoodBundle,
            isiMedicalBundle,
            isiRepairBundle"/>
        <property name="Create_item_count" value="1"/>
    </property>
</item>
```

To change the mods, ammo, or books included in the bundles, you can edit the appropriate bundle in the same file.

For example, if you wanted to replace the Club bundle's Metal Chain mod with the Metal Spikes mod then you would replace `modMeleeClubMetalChain` with `modMeleeClubMetalSpikes` in the `isiClubBundle` item.

```xml
<item name="isiClubBundle">
    <property name="Extends" value="isiMacheteBundle"/>
    <property name="CustomIcon" value="meleeWpnClubT3SteelClub"/>
    <property class="Action0">
        <property name="Create_item" value="
            meleeWpnClubT3SteelClub,
            bookBatterUpBigHits,bookBatterUpStealingBases,bookBatterUpSlowPitch,bookBatterUpKnockdown,bookBatterUpMaintenance,bookBatterUpFoulBalls,bookBatterUpMetalChain,
            modMeleeClubBurningShaft,modMeleeClubMetalChain,modMeleeWeightedHead,modMeleeErgonomicGrip"/>
        <property name="Create_item_count" value="6"/>
    </property>
</item>
```

PS: Please note that if you add, remove, or change the order of items in `Create_item` you may need to update `Create_item_count` as well. If a value has not been specified then it will default to 1 of the item in the corresponding slot.

PPS: While `Create_item_count` usually refers to the number of items, for some items (like armor pieces and weapons) it refers to the quality of the item. In those situations the only way to add additional pieces is to list the item again.

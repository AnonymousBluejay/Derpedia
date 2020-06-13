# Derpedia - Admin
Admins and developers should familiarize themselves with this section of the wiki. This section mainly consists of admin command manuals and config details.

### Admin Commands
/derp - Show all commands <br />
/derp reload - Reload config files <br />
/nbt - Show NBT help page <br />
/item - Open get item menu <br />
/loadout [player] - View/edit other players' loadout <br />
/stats [player] - View other players' stats <br />

## Config
The config files are structured with folders for easy navigation with the in game menu. Each file can contain multiple items but each item must have an unique name.

### Item Config
ItemName: <br />
  Type: String <br />
  Name: String <br />
  CustomModelData: int <br />
  Slot: String <br />
  Description: String <br />
  Color: String <br />
  Attributes:  <br />
    max_health: float <br />
    movement_speed: float <br />
    stability: float <br />
  Core: <br />
    core_capacity: int <br />
    energy_output: int <br />
    energy_usage: int <br />
  Defenses: <br />
    impact: float <br />
    slash: float <br />
    heat: float <br />
    cold: float <br />
    electricity: float <br />
    poison: float <br />
  Resistances: <br />
    impact: float <br />
    slash: float <br />
    heat: float <br />
    cold: float <br />
    electricity: float <br />
    poison: float <br />
  Damages: <br />
    impact: float <br />
    slash: float <br />
    heat: float <br />
    cold: float <br />
    electricity: float <br />
    poison: float <br />
  Skills <br />
    Shift: <br />
      ability_name: int <br />
      shift_skill_boost: int <br />
    Jump: <br />
      ability_name: int <br />
      jump_skill_boost: int <br />
    Passive: <br />
      ability_name: int <br />
      (can have more than 1 ability here)
      passive_skill_boost: int <br />
  Misc: <br />
    shiny: boolean <br /> <br />
    hat: boolean <br /> <br />

#### Notes
Items are naturally unbreakable and hides the unbreakable tag. <br />
Most int and float values support randomization, for example, "-55,55" would randomly generate a integer or float between -55 and 55 <br />

#### ItemName
Every item must have an ItemName. ItemName can consist of any uppercase and lowercase letter, number, and underscore. No space bars  <br />allowed. Keep in mind each item must have a unique name. This is also the item ID used in game. Defaults to the item name of Type. <br />

#### Type
Type can be any minecraft item ID, this is the item that will appear in game. Defaults to "iron_horse_armor". <br />

#### CustomModelData
Model ID of the item. The ID list will be released at a later date. <br />
  #Generic rig: 1010010 <br />
  #Generic core: 1020010 <br />
  #Generic mod: 1030010 <br />
  #Generic Energy Mod: 1030020 <br />

#### Slot
The slot is very important, it changes the way the item constructor creates items. Defaults to item.

Slots currently include: <br />
**rig** - placed in rig slot in loadout <br />
**core** - placed in core slot in loadout <br />
**mod** - placed in mod slots in loadout <br />
**armor** - cosmetic armor with no stats <br />
**weapon** - enables player interact event checks, weapons are still a work in progress <br />
**item** - normal item, nothing special <br />
**placeholder** - disabled for items <br />
**immobile** - disabled for items <br />

#### Description
Descriptions are automatically formatted and added to the lore, there are no need for new lines.

#### Color
Color is used for leather armor only, and should be entered in RGB format. <br />
Example: Color: 85,255,255

#### Attributes
**max_health** - increase the maximum health of the player by the specified amount <br />
**movement_speed** - increase the movement speed of the player by the specified amount <br />
movement_speed is counted in blocks per second, a value of 1 means the player walks 1 blocks per second faster than normal <br />
**stability** - decrease the velocity of knockback taken by the player <br />
stability is a percentage value, a value of 0.2 means the player takes 20% less knockback <br />

#### Core
**mod_capacity** - increase number of mods a loadout can hold (up to a maximum of 16) <br />
**energy_output** - increase the maximum amount of power that can be used by mods <br />
**energy_usage** - how much power is used up by the mod <br />

#### Defenses
Defenses has 6 sub-categories for the 6 elemental damages, each reduce the damage taken from that element by a percentage <br />
Example: "impact: 10.5" would mean whoever uses the item take 10.5% impact damage <br />

#### Resistances
Resistances also has 6 sub-categories, each increase the threshold of procs before a status effect activates. A player with no gear has 100 in every category by default, further values increase or decrease that value. <br />
Example: "fire: 50" would mean an extra 50 points of fire proc can be absorbed before a player is set on fire <br />
NOTE: Procs decrease at a percentage rate, meaning higher resistance will make procs wear off faster before it triggers. After a proc triggers, it goes down at a fixed rate. <br />

#### Damages
Damages also has 6 sub-categories, each boosting the damage done by the player of that category by a percentage <br />
Example: "slash: 20" means the player deals 20% more slash damage <br />

#### Energy
**energy_max** - Increases the maximum energy capacity of the player <br />
**energy_regen_amount** - amount of energy regained for each tick of energy regen <br />
**energy_regen_rate** - delay in ticks between each energy regen tick <br />
A value of 10 would mean a player regains energy_regen_amount of energy every 10 ticks (0.5s) <br />
Higher value means slower regen, lower value means faster regen <br />
This value can change a player's energy regain rate drastically <br />
**energy_regen_delay** - delay in ticks before a player starts regaining energy again after using up some energy (for abilities) <br />
**energy_efficiency** - percentage reduction in energy used <br />
A value of 10 would mean the player uses 10% less energy when using abilities <br />

#### Focus
WIP

#### Skills
##### Shift
Replace shift ability and level <br />
Example: <br />
Shift: <br />
  charged_boost: 1 <br />
Replaces shift ability with charged_boost with level 1 <br />
**shift_skill_boost** - increase the level of current shift ability by amount <br />

##### Jump
Replace double jump ability and level <br />
Example: <br />
Jump: <br />
  air_dash: 1 <br />
Replaces double jump ability with air_dash with level 1  <br />
**jump_skill_boost** - increase the level of current jump ability by amount <br />

##### Passive
Add passive abilities <br />
Example:
Passive: <br />
  shock_absorber: 1 <br />
Adds the shock absorber passive at level 1 1 <br />
**passive_skill_boost** - increase the level of the LAST ADDED passive ability in the loadout order 1 <br />
Multiple passive skills can be equipped at once 1 <br />

#### Misc

##### Shiny
Armor only, when enabled, applies enchantment visual effect to item.

##### Hat
Armor only, when enabled, allows any item to be placed in the head slot.

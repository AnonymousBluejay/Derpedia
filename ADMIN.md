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
  Type: <String> <br />
  Name: <String> <br />
  CustomModelData: <int> <br />
  Slot: <String> <br />
  Description: <String> <br />
  Color: <String> <br />
  Attributes:  <br />
    max_health: <int> <br />
    movement_speed: <int> <br />
  Core: <br />
    core_capacity: <int> <br />
  Defenses: <br />
    impact: <int> <br />
    slash: <int> <br />
    heat: <int> <br />
    cold: <int> <br />
    electricity: <int> <br />
    poison: <int> <br />
  Resistances: <br />
    impact: <int> <br />
    slash: <int> <br />
    heat: <int> <br />
    cold: <int> <br />
    electricity: <int> <br />
    poison: <int> <br />
  Misc: <br />
    shiny: <boolean> <br />
    hat: <boolean> <br />

#### Notes
Items are naturally unbreakable and hides the unbreakable tag.


#### ItemName
Every item must have an ItemName. ItemName can consist of any uppercase and lowercase letter, number, and underscore. No space bars allowed. Keep in mind each item must have a unique name. This is also the item ID used in game. Defaults to the item name of Type.

#### Type
Type can be any minecraft item ID, this is the item that will appear in game. Defaults to "iron_horse_armor".

#### CustomModelData
Model ID of the item. The ID list will be released at a later date. 

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

#### Misc

##### Shiny
Armor only, when enabled, applies enchantment visual effect to item.

##### Hat
Armor only, when enabled, allows any item to be placed in the head slot.

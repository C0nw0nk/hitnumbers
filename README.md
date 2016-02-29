Hit Numbers
===========

A Garry's Mod addon which adds damage indicators whenever you damage something.

Works in Zombie Survival for humans, zombies, props you name it.

# Example :

![Alt text](http://images.akamai.steamusercontent.com/ugc/577849023630942742/5CD9AFB6F6C0EF79EC0C302E6DBAE8AF859DE9F6/ "Mapvoting example")

For server admins and/or developers
===================================

My recommendation before you use any of these is to leave everything at default it looks great at default, But if anything does go wrong just remove your changes.

# Clients:

`hitnums_toggle`
Toggle show/hide the indicators in-game for client only. This command is blocked by default by the server convar sv_hitnums_allowusertoggle (see below, under "Server" category)

`hitnums_debugmode 0/1`
Defaulted to OFF. Enables debug mode for Hit Numbers. This will display performance information related to the updating and rendering of the indicators.

# Server:

`sv_hitnums_enable 0/1`
Defaulted to ON, duh. Disable/Enable this addon server-wide.

`sv_hitnums_allowusertoggle 0/1`
Defaulted to OFF. Disallow/Allow users to use the client convar `hitnums_toggle`.

`sv_hitnums_breakablesonly 0/1`
Defaulted to ON. Set this to OFF (0) to show indicators for indestructable props (like barrels), too.

`sv_hitnums_showalldamage 0/1`
Defaulted to OFF. Set to ON (1) to show all damage inflictions being made anywhere in the server. This can be quite taxing on network performance if there are many indicators active at once.

`sv_hitnums_ignorez 0/1`
Defaulted to OFF. Ignore depth testing. Basically, setting this to ON (1) means you can see the indicators through walls and objects.

`sv_hitnums_scale scale`
Defaulted to 0.3. Scale the size of the indicators.

`sv_hitnums_ttl seconds`
Defaulted to 1.0. Time-to-live in seconds. How long until the indicator completely fades out.

`sv_hitnums_showsign 0/1`
Defaulted ON. When enabled, the - (minus) sign on indicators is shown.

`sv_hitnums_alpha 0-1`
Defaulted 1.0. Alpha multiplier for indicators. Range is from 0.0 (0%, fully transparent) to 1.0 (100%, fully opaque).

`sv_hitnums_critmode mode`
Defaulted to 7. Sets how "critical" indicatiors are shown (See list below)
* 0 = No Crit (Damage is shown, but not in critical colour)
* 1 = _dmg#_ (Damage only, in critical colour)
* 2 = _Crit!_
* 3 = _Critical!_
* 4 = _Crit dmg#_
* 5 = _Critical dmg#_
* 6 = _Crit!_ and _dmg#_
* 7 = _Critical!_ and _dmg#_

`sv_hitnums_animate style`
Defaulted to 1. Sets style of animation during an indicators lifetime (See list below)
* 0 = No animation (Stays same constant size)
* 1 = Grow in and subtly shrink out
* 2 = Grow in only
* 3 = Shrink out only

`sv_hitnums_gravity gravity`
Defaulted to 1.0. Multiplier for how much gravity is applied to the indicators. (for example, 1.0 for normal gravity, 0.0 for no gravity, -1.0 for inverted gravity)

`sv_hitnums_forceinheritance force`
Defaulted to 1.0. Multiplier for the amount of velocity force applied to the indicators from an impact. Setting this to 0.0 will remove any impact force velocity added to the indicators.

`sv_hitnums_forceoffset_xmin min`
Defaulted to -0.5. The minimum of the range for applying a random force on the X axis when creating an indicator. 

`sv_hitnums_forceoffset_xmax max`
Defaulted to 0.5. The maximum of the range for applying a random force on the X axis when creating an indicator. 

`sv_hitnums_forceoffset_ymin min`
Defaulted to -0.5. The minimum of the range for applying a random force on the Y axis when creating an indicator. 

`sv_hitnums_forceoffset_ymax max`
Defaulted to 0.5. The maximum of the range for applying a random force on the Y axis when creating an indicator. 

`sv_hitnums_forceoffset_zmin min`
Defaulted to 0.75. The minimum of the range for applying a random force on the Z axis when creating an indicator.
Note: Critical indicators have a bonus multiplier of 1.5 added on top of this axis. 

`sv_hitnums_forceoffset_zmax max`
Defaulted to 1.0. The maximum of the range for applying a random force on the Z axis when creating an indicator.
Note: Critical indicators have a bonus multiplier of 1.5 added on top of this axis. 

### Masking:
Masks are used to tell Hit Numbers what type of objects are allowed to create indicators when damaged. 1 = enable/show, most of these are defaulted ON.

`sv_hitnums_mask_players 0/1`
Mask players.

`sv_hitnums_mask_npcs 0/1`
Mask NPCs.

`sv_hitnums_mask_ragdolls 0/1`
Mask ragdolls. (Ragdolls typically don't have health. In that case, `sv_hitnums_breakablesonly` should be enabled.)

`sv_hitnums_mask_vehicles 0/1`
Mask vehicles. (Same thing with ragdolls.)

`sv_hitnums_mask_props 0/1`
Mask props. (More specifically; `prop_physics*` and `prop_dynamic*`)

`sv_hitnums_mask_world 0/1`
Mask world. (More specifically; `func_*` like `func_breakable` (ie. glass, doors). This one is defaulted OFF.)

### Font:
These should be set in the server configuration file:
* For dedicated servers, use `cfg/server.cfg`
* For singleplayer or listen servers, use `cfg/listenserver.cfg`
* You may also edit the font information in the Hit Numbers configuration file `data/hitnumbers/settings.txt`

**These should not be modified in-game because fonts are only loaded when the player initializes.**

`sv_hitnums_font_name fontname`
Indicator font face. (Default is _coolvetica_)

`sv_hitnums_font_size size`
Size of the font. (Default is 50)

`sv_hitnums_font_weight weight`
Weight of the font. (Default is 800 [normal weight for Coolvetica])

`sv_hitnums_font_underline 0/1`
Underline for indicators. (Default is OFF)

`sv_hitnums_font_italic 0/1`
Italic indicators. (Default is OFF)

`sv_hitnums_font_shadow 0/1`
Adds a little shadow to indicators. (Default is OFF. Not visible when outline is enabled)

`sv_hitnums_font_additive 0/1`
Use additive rendering for indicators. (Default is OFF)

`sv_hitnums_font_outline 0/1`
Add outline to indicators. (Default is ON)

### Colours:
These are in [RRGGBB hexadecimal format.](http://en.wikipedia.org/wiki/Web_colors#Hex_triplet) For example, `sv_hitnums_color_critical FF00FF` will make critical hits purple. [Use an online colour wheel to help you with this.](http://www.colorspire.com/rgb-color-wheel/)

`sv_hitnums_color_generic RRGGBB`
Colour for generic/bullet damage. (Default is _FFE6D2_)

`sv_hitnums_color_critical RRGGBB`
Colour for critical damage. (Default is _FF2828_)

`sv_hitnums_color_fire RRGGBB`
Colour for fire/burning damage. (Default is _FF7800_)

`sv_hitnums_color_explosion RRGGBB`
Colour for explosion damage. (Default is _F0F032_)

`sv_hitnums_color_acid RRGGBB`
Colour for acidic/poison/toxic damage. (Default is _8CFF4B_)

`sv_hitnums_color_electric RRGGBB`
Colour for electric/shock damage. (Default is _64A0FF_)

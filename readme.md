# About
  A repo to contain all the small mods I make for STALKER Anomaly/GAMMA, that which are too small to warrent their own pages/repos/releases/etc.

# Content
- [About](#about)
- [Content](#content)
- [01 Auto QRS Equip](#01-auto-qrs-equip)
  - [About](#about-1)
  - [Compatibility](#compatibility)
  - [Installation](#installation)
- [03 Hide SidHUD Rad Bar](#03-hide-sidhud-rad-bar)
  - [About](#about-2)
  - [Compatibility](#compatibility-1)
  - [Installation](#installation-1)
- [04 Faction ID No Gray Dead Patches](#04-faction-id-no-gray-dead-patches)
  - [About](#about-3)
  - [Compatibility](#compatibility-2)
  - [Installation](#installation-2)
- [05 GAMMA True Passive Artefact Detection](#05-gamma-true-passive-artefact-detection)
  - [About](#about-4)
  - [Compatibility](#compatibility-3)
  - [Installation](#installation-3)
- [06 Weapon Hud Editor Anywhere](#06-weapon-hud-editor-anywhere)
  - [About](#about-5)
  - [Customization](#customization)
  - [Compatibility](#compatibility-4)
  - [Installation](#installation-4)

# 01 Auto QRS Equip
## About
A small mod that re-equips your backpack when you pick up a QRS stash. No more searching through your inventory in the heat of battle just to throw your pack on. Works with Soulslike!
## Compatibility
- Compatible with all mods. No overwrites. 
  - Monkey-patches `item_backpack.actor_on_item_take_from_box()`
- Optional Soulslike patch. Pick up your dead body stash and auto-equip it!
  - Monkey-patches `soulslike.actor_on_before_death()` and `soulslike.actor_on_item_take_from_box()`

## Installation
- Put it anywhere in load order

# 03 Hide SidHUD Rad Bar
## About
The geiger counter in GAMMA is pretty useless. With the constant geiger clicks, the on-screen radioactive fuzziness, the flashing rad icon, AND the radiation bar, the geiger counter itself begs for a reason to exist.

[Geiger Clicks Reworked](https://discord.com/channels/912320241713958912/1273284275420008459) (only available on GAMMA Discord :\( ) did a lot to give the geiger counter purpose, tying the actual clicks to the battery-state of the counter; no (working) geiger counter, no rad clicks.

I wanted more. We still had the on-screen fuzzies, the rad icon, the new [Milliseiverts Over Rad Icon](https://discord.com/channels/912320241713958912/1335706892193763369) (which gave us dead-accurate radiation numbers), and the rad bar. So, I made this patch for the new *Milliseiverts Over Rad Icon*; no charged, working geiger counter, no rad clicks, no mSv over rad status icon, **no radiation bar**. 

Finally, radiation feels like a silent killer. It's a small but impactful mod. If you play with *Soulslike*, then respawning without a replacement geiger counter makes journeying out to get your sack very dangerous.
## Compatibility
- **Requires *Milliseiverts Over Rad Icon* to work**
  - I could have made my mod independent, but this one did all the work I needed done, and I just wanted to play the game first lmao
- **Also requires *ui_sidhud_mcm.script* which is part of *G.A.M.M.A. Minimalist HUD***
  - If you haven't touched *G.A.M.M.A. Minimalist HUD*, and no mod overwrites it, this mod should just be plug-and-play
- Compatible with everything else

## Installation
- Load order does not matter. Put it anywhere

# 04 Faction ID No Gray Dead Patches
## About
A very simple patch of *Crook's Faction Identification*, disabling the gray patches for dead stalkers. 

In a firefight, I don't want any UI elements helping me cheat, telling me if I landed my shots or if the enemy finally died, but as soon as the faction patch turned gray I would know if the fight was over. 

Now, dead stalkers retain their fully colored faction patch. No more cheating yourself of some extra anxiety ;)
## Compatibility
- Compatible with everything.
  - No textures are touched.
  - No overwrites anywhere
  - The mod monkey-patches the `__init` function of Faction ID; all I'm doing is re-initalizing dead stalkers to use their non-dead faction patch variant.
    - Specifically overrides `factionid_hud_mcm.UIFactionIDHUD.__init(self)`
## Installation
- Put it anywhere in load order
# 05 GAMMA True Passive Artefact Detection
## About
A very simple tweak of Grok's passive artefact detection mod in GAMMA. In the original, you would only be able to passively detect artefacts *if you had the detector equipped*, making it very frustrating to use any other device, if you forgot to re-equip the detector.

Now, you can leave the detector in your inventory, and the passive detection status icon will still pop up!

No performance impact. Does not scan the player's inventory at all; the mod simply checks if the actor has one of the 5 possible detectors, that's it. Checking its performance impact vs vanilla with the DevTools Profiler, I saw no differences.

## Compatibility
- Must be loaded after `G.A.M.M.A. Artefacts Reinvention`. Directly overwrites `grok_artefacts_bip.script`
  - Just throw it at the bottom of your load order and you should be good
- Additionally, if you care about customization and other mod support, this mod moves how `grok_artefacts_bip.script` defines artefact tiers. Look at `gamedata/configs/items/settings/passive_detector_artefact_tiers.ltx` to see how where I've moved artefact teirs. DLTX them to your heart's content
 
## Installation
- Put it at the bottom of your load order, or after `G.A.M.M.A. Artefacts Reinvention`, at least

# 06 Weapon Hud Editor Anywhere
## About
You know how in debug mode how you use the Weapon HUD Editor to fix off-position scopes for 3DSS? Yeah, I keep finding, while playing, scopes I need to fix (looking at you 1P59 Giperon) but I don't want to exit, relaunch in debug, go to debug, fix it, then restart just to get back on the road. 

With this mod, press `F7` like you would normally for the debug menu and you get the Weapon HUD Editor, even outside of debug mode!

**I highly recommend you get *[Draggable HUD Editor](https://www.moddb.com/mods/stalker-anomaly/addons/draggable-hud-editor)*, makes your life easier!
## Customization
Key is tied to whatever you set debugging mode to in your keybinds. Change your keybinding for debugging menu, it will change the keybind for the weapon hud editor.

## Compatibility
- Compatibile with everything
## Installation
- Put it anywhere in load order
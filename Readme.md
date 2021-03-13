# EasyHeli
This is a squad mod that makes helicopter flying easier. Core features of this mod includes:

- Auto Hovering
- Collision Warning
- (TODO) Auto Landing

Source code at https://github.com/worldlife123/EasyHeli

## Description

Currently only US and RUS factions has EasyHeli vehicles, including:

- BP_MI8_EasyHeli2
- BP_UH60_EasyHeli2

### Auto Hovering
To enable auto hovering on those vehicles, just hold ToggleStablizer key (default:Z) when flying in the air. The helicopter will automatically try to keep stable in the air. You can still control the helicopter with your mouse when hovering.

### Collision Warning
The helicopter would automatically predict if the rotor would collide with other objects in a few seconds. If a collision is predicted, the warning system on the helicopter will be on.

## Technical Information

### Core Classes

- EasyHeliComponent: Core functions are included in this component.
    - SetEnableHovering: A simple function to set the EnableHovering variable
    - DoHovering: Should be called in EventOnTick in the helicopter blueprint. If EnableHovering is true, add stablizing rotation vector the the SQHelicopterMovementComponent.

### Maps
EasyHeli vehicles are only available on the listed maps:

- Jensens_Range_v2_EasyHeli

## Usage
Use AdminChangeMap [mapname] to play with EasyHeli.

## ChangeLog
- 210311
    - Initial Commit.
- 210313
    - Fix map cooking issues.
    - Implememnt collision warning system.

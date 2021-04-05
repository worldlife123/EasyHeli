# EasyHeli
This is a squad mod that makes helicopter flying easier. Core features of this mod includes:

- Auto Hovering
- Collision Warning
- Auto Landing

Source code at https://github.com/worldlife123/EasyHeli

## Description

Currently only US and RUS factions has EasyHeli vehicles, including:

- BP_MI8_EasyHeli2
- BP_UH60_EasyHeli2

### Auto Hovering
To enable auto hovering on those vehicles, just hold ToggleStablizer key (default:Z) when flying in the air. The helicopter will automatically try to keep stable in the air. You can still control the helicopter with your mouse when hovering, and adjust collective to control the altitude of the helicopter.

### Collision Warning
The helicopter would automatically predict if the rotor would collide with other objects in a few seconds. If a collision is predicted, the warning system on the helicopter will be on.

### Auto Landing
To enable auto landing on those vehicles, just hold Crouch key (default:Ctrl) when flying in the air. The helicopter will automatically find a nearby (within 250m) helipad to land. If no helipad is found, the helicopter just try to hover in the air.

During auto landing, the collective will be fully under automatic control and could not be adjusted manually. The helicopter will first fly above a nearby helipad, and then descend onto it.

## Technical Information

### Core Classes

- EasyHeliComponent: Core functions are included in this component.
    - Public Functions:
        - SetEnableHovering: A simple function to set the EnableHovering variable.
        - SetEnableAutoLanding: A simple function to set the EnableAutoLanding variable.
        - DoHovering: Should be called in EventOnTick in the helicopter blueprint. If EnableHovering is true, add stablizing rotation vector the the SQHelicopterMovementComponent and set DesiredThrust variable.
        - GetDesiredThrust: A function for GetThrustPower and GetVisualCollective for BP_Generic_Helicopter. Automatically choose from manual thrust and auto controlled thrust.
    - Protected Functions:
        - GetDesiredThrustAndRotationFromMovingDirection: Internal core function for auto hovering and auto landing. An 1st-order automatic control system solver.

For more information, just see the code.

### Maps
EasyHeli vehicles are only available on the listed maps:

- Jensens_Range_v2_EasyHeli
- Tallil_Outskirts_RAAS_v1_EasyHeli
- Helicopter_Tutorial_EasyHeli

## Usage
Use AdminChangeLayer [mapname] to play with EasyHeli.

## ChangeLog
- 210311
    - Initial Commit.
- 210313
    - Fix map cooking issues.
    - Implememnt collision warning system.
- 210330
    - Fix collision warning system trigger warning when helicopter descends.
    - Add tutorial map.
- 210405
    - Optimize collision warning system.
    - Implememnt auto landing system.
    - Add Tallil map.

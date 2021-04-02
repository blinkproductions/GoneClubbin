# GoneClubbin'

## Download and play here: https://blienk.itch.io/gone-clubbin

## General Design
___
#### Concept
&nbsp;&nbsp;&nbsp;Golf game where the golf ball is the primary weapon/way of traversal

#### What makes it unique/fun?
&nbsp;&nbsp;&nbsp;Golf ball is used to complete objectives and kill enemies.

#### View/Camera Style
* 2D Side scroller

#### Key Game Mechanics
* Charge power of shot, aim, shoot
* Golf ball types: Basic, Concussion Grenade, Homing, Warp
* Enemy types: Imp, High Imp, Hell Mouth

## Documentation

### GrannySmith (Player Character)
| Variable Name  | Type | Default Value  | Description |
|------------- |------------- |------------- |-------------|
| bIsMovingRight | Boolean | True | Return true if character is facing right|
| bBuildUpPower | Boolean | False | Return true if Power Button in HUD event is pressed, False when released|
| bReachedMaxPower | Boolean | False | Return true if power bar has reached max|
| bIsAimingPhase | Boolean | False | Return true if still in aiming phase|
| Power | Boolean | Float | 0  if still in aiming phase|
| CursorLocation | FVector | (0,0,0) | Return true if still in aiming phase|
| AimingValues | FRotator | (0,0,0) | Return true if still in aiming phase|

### BaseGolfBall
| Variable Name  | Type | Default Value  | Description |
|------------- |------------- |------------- |-------------|
| Speed | Float | 0 | Local variable that is set by the power variable casted from the GrannySmith blueprint|

### Enemies
| Enemy Name  | Description |
|------------- |-------------|
| Imp | Basic enemy. Can be killed with a single hit from any golf ball. |
| High Imp | An imp with slightly more hp. |
| Hell Mouth |  Consumes any golf ball that lands on it. Can only be defeated by a blast ball. Player can die if a warp ball is consumed by it.  |

### Golf Balls
| Ball Name  | Description |
|------------- |-------------|
| Basic | A normal golf ball |
| Concussion Grenade |Creates an explosion at the area where it first lands |
| Homing | Homes in to the enemy closest to where it lands (if two or more enemies are the same distance it prioritized the one with higher hp)    |

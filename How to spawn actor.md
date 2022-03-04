# In Header file:
```css
UPROPERTY(EditAnywhere)
TSubclassOf<AActor> ActorToSpawn;
```
# Notes
***
To set class in c++ write `TSubclassOf<AActor> ActorToSpawn = AActor::StaticClass();`
# In cpp file:
```css
#include "Engine/World.h"
UWorld *WRLD = GetWorld(); //Store Uworld object into a UWorld pointer, GetWorld() func returns the current UWorld object
FVector location = GetActorLocation();
FRotator rotation = GetActorRotation();
WRLD->SpawnActor(ActorToSpawn, &location, &rotation);
```
# Notes
***
`Uworld::SpawnActor()` has 3 important params:
1. UClass *class, class of actor we spawn
    * To get it we must point to it in a object using a `TSubclassOf<Class>` object
    * This object takes in a object and points to its UClass value, which we can use in SpawnActor function
    * `AActor` in the <> is a class which will be used to sort out only objects of that class
    * In this case, AActor has given a huge list of available objects, that are using AActor class as their parent class
  * UPROPERTY declaration is written like this in .h(Header) file
```css
UPROPERTY(EditAnywhere)
TSubclassOf<AActor> ActorToSpawn;
```
2. `FVector &location`, location of spawned actor
    * Needs a Fvector parameter (X, Y, Z) values
3. `FRotator &rotation`, rotation of spawned actor
    * Needs a Frotator parameter (pitch, yaw, roll) values

Both FVector and FRotator expect addresses so we need 2 local variables:
```css
FVector location = GetActorLocation();
FRotator rotation = GetActorRotation();
```
and add the adress sign "&" in front when using those two as parameters in SpawnActor function to make them return
addresses instead of their values:
```css
SpawnActor(param1, &location, &rotation)
```

In the end function should look smth like this in .cpp file:
```css
WRLD->SpawnActor(ActorToSpawn, &location, &rotation);
```

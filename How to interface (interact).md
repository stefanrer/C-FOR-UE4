# Interfaces
1. Create c++ class with `Unreal Interface` as Parent Class -> name it smth like InteractInterface
2. Header file ->Create interface functions (Declare) in `class GAMENAME_API IInteractInterface`
```css
UFUNCTION()
virtual void OnInteract(AActor* Caller); //virtual if not blueprint implementable
```
3.Implement it in Actor
```css
#include "InteractInterface.h"

class GAMENAME_API AScriptname : public AParent, public IInteractInterface
```
4.Repeat point 2 for this Actor
5.Define functions in cpp

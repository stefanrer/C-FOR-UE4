# Interfaces
1. Create c++ class with `Unreal Interface` as Parent Class -> name it smth like InteractInterface
2. Header file ->Create interface functions (Declare) in `class GAMENAME_API IInteractInterface`
```css
	UFUNCTION(BlueprintNativeEvent, BlueprintCallable, Category = "Interaction")
	void OnInteract(AActor* Caller);
```
3.Implement it in Actor Header
```css
#include "InteractInterface.h"

class GAMENAME_API AScriptname : public AParent, public IInteractInterface
.
.
.
UFUNCTION(BlueprintNativeEvent, BlueprintCallable, Category = "Interaction")
void OnInteract(AActor* Caller);
virtual void OnInteract_Implementation(AActor* Caller);
```
4. cpp file
```css
void AInteractableBase::OnInteract_Implementation(AActor* Caller)
{
	IInteractInterface::OnInteract_Implementation(Caller);
}
```


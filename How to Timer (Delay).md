# Header file
```css
FTimerHandle DoorTimerHandle;
UPROPERTY(Category = Timer, VisibleAnywhere, BlueprintReadOnly, meta=(AllowPrivateAccess = "true"))
float MaxDelayTime = 3;
```
# .cpp file
```css
GetWorld()->GetTimerManager().SetTimer(DoorTimerHandle, this, &ADoor::CloseDoor, MaxDelayTime, false);
```

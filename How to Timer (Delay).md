# Without params
## Header file
```css
FTimerHandle DoorTimerHandle;
UPROPERTY(Category = Timer, VisibleAnywhere, BlueprintReadOnly, meta=(AllowPrivateAccess = "true"))
float MaxDelayTime = 3;
```
## .cpp file
```css
GetWorld()->GetTimerManager().SetTimer(DoorTimerHandle, this, &ADoor::CloseDoor, MaxDelayTime, false);
```
# With params
## Header file
```css
UFUNCTION()
void MyUsefulFunction(int32 x, float y);
```
## .cpp file
```css
FTimerDelegate TimerDel;
FTimerHandle TimerHandle;
 
// Params to pass into function once it ticks
int32 MyInt = 10;
float MyFloat = 20.f;
 
//Binding the function with specific variables
TimerDel.BindUFunction(this, FName("MyUsefulFunction"), MyInt, MyFloat);
//Calling MyUsefulFunction after 5 seconds without looping
GetWorldTimerManager().SetTimer(TimerHandle, TimerDel, 5.f, false);
```

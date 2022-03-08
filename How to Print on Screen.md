# On Screen Message
## in .cpp file
```css
GEngine->AddOnScreenDebugMessage(-1,200,FColor::Green,FString::Printf(TEXT("Hello %s"),*GetActorLocation().ToString()));
```
### Note
***
`int32 Key` `TimeToDisplay float` `FColor::Color` `DebugMessage const FString`
# Log Message
## in .cpp file
```css
UE_LOG(LogTemp, Warning, TEXT("Move Forward axis: %f"), AxisValue);
```
### Note
***
`CategoryName`, `Verbosity`, `Format`

# cpp
## Disable
```css
APlayerController* PlayerController = GetWorld()->GetFirstPlayerController();
PlayerController->GetPawnOrSpectator()->DisableInput(PlayerController);
```
## Enable
```css
APlayerController* PlayerController = GetWorld()->GetFirstPlayerController();
PlayerController->GetPawnOrSpectator()->EnableInput(PlayerController);
```

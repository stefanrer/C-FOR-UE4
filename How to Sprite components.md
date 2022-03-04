# How to add Sprite Component
## In Header file:
```css
#include "PaperSpriteComponent.h"

UPROPERTY(Category = SpriteMesh, VisibleAnywhere, BlueprintReadOnly, meta=(AllowPrivateAccess = "true"))
UPaperSpriteComponent* SpriteComponent;
```
## In cpp file:
```css
SpriteComponent = CreateDefaultSubobject<UPaperSpriteComponent>(TEXT("SpriteMesh"));
```

# How to set Sprite
## In cpp file:
```css
#include "PaperSprite.h"

UPaperSprite* Sprite = Cast<UPaperSprite>(StaticLoadObject(UPaperSprite::StaticClass(), NULL, TEXT("PaperSprite'/Game/GameAssets/Walls/Corners/Corner_Texture_Sprite'")));
SpriteComponent->SetSprite(Sprite);
```
## Notes
***
Right Click->Get Reference -- to get reference to file then put it between "" in TEXT("here")

# How to set Root Component
## In cpp file:
```css
SetRootComponent(SpriteComponent);
```

# How to set Mobility
## In cpp file:
```css
RootComponent->SetMobility(EComponentMobility::Static);
```

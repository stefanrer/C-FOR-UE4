# In Build.cs file:
Add "Paper2D" to module list -> `PublicDependencyModuleNames.AddRange(new string[] {"Core", "CoreUObject", "Engine", "InputCore"});`

+Include Paper2D path for studio users

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

# How to add FlipbookComponent
## In Header file:
```css
#include "PaperFlipbookComponent.h"

UPROPERTY(Category = SpriteMesh, VisibleAnywhere, BlueprintReadOnly, meta=(AllowPrivateAccess = "true"))
UPaperFlipbookComponent* FlipbookComponent;
```
## In cpp file:
```css
FlipbookComponent = CreateDefaultSubobject<UPaperFlipbookComponent>(TEXT("Flipbook"));
```

# How to set Sprite
## In cpp file:
```css
#include "PaperSprite.h"

UPaperSprite* Sprite = Cast<UPaperSprite>(StaticLoadObject(UPaperSprite::StaticClass(), NULL, TEXT("PaperSprite'/Game/GameAssets/Walls/Corners/Corner_Texture_Sprite'")));
SpriteComponent->SetSprite(Sprite);
```

# How to set Flipbook
## In cpp file:
```css
#include "PaperFlipbook.h"

UPaperFlipbook* Flipbook = Cast<UPaperFlipbook>(StaticLoadObject(UPaperFlipbook::StaticClass(), NULL, TEXT("PaperFlipbook'/Game/GameAssets/Character/MainCharacterIdle.MainCharacterIdle'")));

FlipbookComponent->SetFlipbook(Flipbook);
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

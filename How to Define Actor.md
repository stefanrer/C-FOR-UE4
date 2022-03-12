# Header file:
```css
#include "PaperSpriteComponent.h" // include component header file

UPROPERTY()
UPaperSpriteComponent* SpriteComponent; // Pointer
```

# .cpp file:
```css
SpriteComponent = CreateDefaultSubobject<UPaperSpriteComponent>(TEXT("SpriteMesh"));
```
# Note
***
`CreateDefaultSubobject<>(TEXT(""));`

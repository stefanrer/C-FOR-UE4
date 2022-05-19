# Header
```css
UPROPERTY(Category = Category, VisibleAnywhere, BlueprintReadOnly, meta=(AllowPrivateAccess = "true"))
UStaticMeshComponent* Name;
```
# cpp
```css
Name = CreateDefaultSubobject<UStaticMeshComponent>(TEXT("Name"));
Name->SetStaticMesh(ConstructorHelpers::FObjectFinder<UStaticMesh>(TEXT("StaticMesh'/Engine/BasicShapes/Cube.Cube'")).Object); // Get Static Mesh
Name->SetupAttachment(RootComponent); // Attach to Root
```

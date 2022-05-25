# Header
```css
UPROPERTY()
TArray<UChildActorComponent*> RoomChildActors; // Array for storing child component pointers for later usage
```

# css
```css
UChildActorComponent* Name1 = NewObject<UChildActorComponent>(this); // Need number after name or error
Name1->bEditableWhenInherited = true; // If child should be editable
Name1->RegisterComponent(); // Register component physics etc
Name1->SetChildActorClass(AActorName::StaticClass()); // Set child actor
Name1->CreateChildActor();
location = GetActorLocation(); 
rotation = GetActorRotation();
Name1->SetRelativeLocation(location); // Set child component location
Name1->SetRelativeRotation(rotation); // Set child component rotation
RoomChildActors.Add(Name1); // Add child component to array
```

# Delete components
```css
for (UChildActorComponent* Child : RoomChildActors)
{
	Child->UnregisterComponent();
	Child->DestroyComponent();
}
RoomChildActors.Empty();
```

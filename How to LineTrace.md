# In Header file:
```css
UPROPERTY(Category = TraceLine, VisibleAnywhere, BlueprintReadOnly, meta=(AllowPrivateAccess = "true"))
float TraceDistance = 100;
```
# In .cpp file:
```css
FVector Loc = GetActorLocation();
FRotator Rot = GetActorRotation();
FHitResult Hit;

FVector Start = Loc;
FVector End = Start + (Rot.Vector() * TraceDistance);

FCollisionQueryParams TraceParams;
bool bHit = GetWorld()->LineTraceSingleByChannel(Hit, Start, End, ECC_Visibility, TraceParams);
if (bHit)
{
	DrawDebugBox(GetWorld(), Hit.ImpactPoint, FVector(5,5,5),FColor::Red, false, 2.0f); //Draw a box in world on hit
}
DrawDebugLine(GetWorld(), Start, End, FColor::Orange, false, 2.0f); //Draw debug line in world
```
# Link to Documentation
https://www.cnblogs.com/shiroe/p/14742822.html

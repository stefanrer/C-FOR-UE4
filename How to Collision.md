# OnOverlapBegin
## In Header file
```css
UFUNCTION()
void OnOverlapBegin(UPrimitiveComponent* OverlappedComp, AActor* OtherActor, UPrimitiveComponent* OtherComp, int32 OtherBodyIndex,
	bool bFromSweep, const FHitResult& SweepResult);
```
## In css file
```css
AActor::AActor()
{
Component->OnComponentBeginOverlap.AddDynamic(this, &AActor::OnOverlapBegin);
}
void AActor::OnOverlapBegin(UPrimitiveComponent* OverlappedComp, AActor* OtherActor, UPrimitiveComponent* OtherComp,
	int32 OtherBodyIndex, bool bFromSweep, const FHitResult& SweepResult)
{
  
}
```
# OnOverlapEnd
## In Header file
```css
UFUNCTION()
void OnOverlapEnd(class UPrimitiveComponent* OverlappedComp, class AActor* OtherActor, class UPrimitiveComponent* OtherComp, int32 OtherBodyIndex);
```
## In css file
```css
AActor::AActor()
{
  Component->OnComponentEndOverlap.AddDynamic(this, &AActor::OnOverlapEnd);
}
void AActor::OnOverlapEnd(class UPrimitiveComponent* OverlappedComp, class AActor* OtherActor, class UPrimitiveComponent* OtherComp, int32 OtherBodyIndex)
{

}
```

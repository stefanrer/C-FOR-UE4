# Header file - either above UCLASS() or in another header file and #include
```css
UENUM()
enum EStatus
{
  Stopped     UMETA(DisplayName = "Stopped"),
  Moving      UMETA(DisplayName = "Moving"),
  Attacking   UMETA(DisplayName = "Attacking"),
};
```
## in UCLASS()
```css
UPROPERTY(EditAnywhere, BlueprintReadWrite, Category = Status)
TEnumAsByte<EStatus> status;
```

# How to make a Switch
```css
switch (status)
	{
	case (EStatus::Stopped):
		do_something();
		break;
	case (EStatus::Moving):
		do_something();
		break;
	case (EStatus::Attacking):
		do_something();
		break;
	default:
		do_something();
		break;
	}
```

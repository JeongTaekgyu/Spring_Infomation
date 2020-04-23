# Inversion of Control(IoC)

일반적으로 의존성에 대한 제어권을 자기 자신이 가지고 있다.

하지만 IoC는 제어가 뒤바꼈다.

IOC를 사용하지 않았더라면 아래 처럼 사용한다.

```java
class OwnerController{
	private OwnerRepository repository = new OwnerRepository();
}
```

OwnerRepository는 OwnerController의 의존성이다.

OwnerRepository가 있어야 OwnerController를 사용할 수 있다.

OwnerController는 OwnerRepository를 필요로 한다.

**의존성을 내가 관리하지않고 나 외의 밖에서 누군가가 넣어주면 IoC라고 한다.**

<br>

```java
class OwnerController{
	private OwnerRepository repo;
    
    public OwnerController(OwnerRepository repo){
        this.repo = repo;
    }
    // repo를 사용한다.
}
```

OwnerController는 OwnerRepository 타입의 repo 변수만 가지고있고

누군가가 생성자로 주겠지 라고 가정하고  repo를 사용하면 된다.



```java
class OwnerControllerTest{
	@Test
	public void create(){
		OwnerRepository repo = new OwnerRepository();
		OwnerController controller = new OwnerController(repo);
	}
}
```

repo를 OwnerController의 생성자한테 넘겨줄 수 있다.

이게 바로 의존성 주입

OwnerRepository라는 의존성을 OwnerController한테 주입한다.

이런 형태의 의존성 관리가 **IoC**이다.
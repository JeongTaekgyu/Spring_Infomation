# IoC 컨테이너 (Inversion of Control Container)

ioc 컨테이너는 직접 쓸일이 없다.

주요 컨테이너는 application container

OwnerController가 IoC컨테이너 내부에 객체로 들어오고

IoC컨테이너 내부에서 OwnerController의 객체를 만들어준다.

그리고 OwnerRepository타입의 객체도 만들어준다.

자기가 컨테이너 내부에 만든 객체들(Bean)의 의존성을 관리해 준다.

참고로 @ (Annotaion)이 붙어있으면 bean이다.

bean으로 등록이되게 끔 애노테이션이 붙어있는 애들은  

ioc컨테이너 내부에서 그 객체들을 만들고 그 객체들의 의존성을 관리해준다.

의존성을 엮어준다. 

ex) OwnerController에 필요한 OwnerRepository타입의bean을 찾아서 OwnerController의 생성자에다 주입을 해서 넣어준다.
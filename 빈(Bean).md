# 빈(Bean)

- **스프링 IoC 컨테이너가 관리하는 객체가 Bean 이다.**

 뭐가 빈이고 뭐가 빈이 아니냐

빈이 되기위해서는 어떻게 해야하냐? -> 등록해야한다.

1. Component Scanning 으로 등록 

   (현재 spring-petclinic은 spring boot로 만든 application이다.)

   스프링 부트로 만든 애플리케이션은 대부분 @SpringBootApplication이라는 애노테이션을 가진 클래스가 존재한다. 

   @SpringBootApplication 을 따라가보면 @ComponentScan이 존재한다.

   ( 참고로 @(annotation) 자체는 기능이 없다. annotation을 마커로 사용해서 annotation을 처리하는 프로세스가 있다. )

   ComponentScan에는 

   - @Component
     - @Repository
     - @Service
     - @Controller

   ​	

   모든 클래스들의 모든 패키지의 Component라는 애노테이션이 찾아있는 클래스를 찾아서 bean으로 등록해준다.

   Controller는 Component와 같다.

2. 또는 직접 일일히 XML이나 자바 설정 파일에 등록




























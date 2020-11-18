# vscode 에서 환경 설정하기 

## 플러그인 깔기 

기본적 으로 gradle 을 빌더로 세팅 하기로 한다.

### Java Extension Pack(Micosoft)
![Java Extension Pack](./img/VscodeJavaExtensionPack.png)


  - java언어 지원 기능, 디버거, 테스트 실행, maven 프로젝트 관리 등의 확장을 패키징 한 패키지


### Spring Boot Extension Pack(Pivotal)
![Java Extension Pack](./img/VscodeSpringBootExtensionPack.png)

  - spring 프레임워크에 적용할 수 있는 유용한 기능이 들어있는 패키지, Spring Initializr 가 포함되어 있다.

### lombok 
![Lombok Annotations Support](./img/VSCodeLombokAnnotationsSupport.png)

  - 롬복 애노테이션 플러그인
  

### Gradle Extension Pack
![Gradle Extension Pack](./img/VSCodeGradleExtensionPack.png)
<!-- ![Gradle Task](./img/VSCodeGradleTask.png) -->


 - Gradle 관련 팩 Gradle 설치후 까는것을 추천, 설치하고 나면 Gradle 아이콘이 vs code 에 생기는데 만약 안생긴다면 설정 > gradle 검색 아래 설정을 true 로 변경 한다.


![Gradle Task Setting](./img/VSCodeGradleTaskSetting.png)


 ```json
 "gradle.nestedProjects": true
 ```


### 자바 위치 설정하기 

설정에서 jdk 를 검색한다. 

```json
"java.home": "/usr/libexec/java_home"
"java.home": "/Library/Java/JavaVirtualMachines/adoptopenjdk-8.jdk/Contents/Home"
```

### 프로젝트 생성하기
CMD + Shift + P 




### 롬복 설치
 - [vscode lombok](https://planbsw.tistory.com/109?category=811149)
 - [vscode 설정](https://gethlemn.tistory.com/28?category=1111786)
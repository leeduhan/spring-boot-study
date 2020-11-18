# jdk 설치하기

맥 사용자 이므로 맥을 기준으로 설명한다. 

## 먼저 brew 를 업데이트 한다. 
>$> brew update && brew upgrade brew-cask && brew cleanup && brew cask cleanup

# brew 검색
brew search <formula>

# brew 설치
brew install <formula>

# 버전업된 패키지 확인하기
brew outdated

# 패키지 업그레이드
brew upgrade rbenv

# 모든 패키지 업그레이드하기
brew upgrade

# 최신버전의 rbenv 패키지만 남겨두기
brew cleanup rbenv

# 모든 패키지 삭제하기
brew uninstall <formula>

# 설치한 패키지 목록보기
brew list

# 패키지의 정보 보기
brew info rbenv

# 시스템 오류 점검하기
brew doctor


안나온다 ..... 맥이 언제부턴가 기본설치에서 빠진것 같다.

jdk 가 유료 라서 openjdk를 설치 하려 했더니 15 버전만 있어서 다른 방법을 찾아 보았다. 

brew 로 설치하는 법을 다 찾아서 해보는데 되는게 없었다.

[AdoptOpenJDK](https://github.com/AdoptOpenJDK/homebrew-openjdk) 여기만 명령으로 설치가 되었다. 

최신버전으로 설치 하려면 다음과 같이 설치한다. 

>$> brew cask install adoptopenjdk

선택적으로 설치하려면 다음과 같이 설치한다. 

jdk8 버전 예 

>$> brew tap AdoptOpenJDK/openjdk

>$> brew cask install adoptopenjdk8

```shell
$ java -version
openjdk version "1.8.0_275"
OpenJDK Runtime Environment (AdoptOpenJDK)(build 1.8.0_275-b01)
OpenJDK 64-Bit Server VM (AdoptOpenJDK)(build 25.275-b01, mixed mode)
```

여러버전의 JDK 사용 하려는 경우 jenv 를 사용한다.

맥에 설치된 자바 버전 확인 

```shell
$ /usr/libexec/java_home -V
Matching Java Virtual Machines (1):
    1.8.0_275, x86_64:	"AdoptOpenJDK 8"	/Library/Java/JavaVirtualMachines/adoptopenjdk-8.jdk/Contents/Home

/Library/Java/JavaVirtualMachines/adoptopenjdk-8.jdk/Contents/Home
```

JAVA_HOHE 를 등록한다.

```shell
$ vi ~/.bash_profile
```
export JAVA_HOME=$(/usr/libexec/java_home -v 8) 

변경 사항을 적용한다.

```shell
$ source ~/.bash_profile
```

그리고 버전을 확인해 보면 

```shell
$ java -version            
openjdk version "1.8.0_275"
OpenJDK Runtime Environment (AdoptOpenJDK)(build 1.8.0_275-b01)
OpenJDK 64-Bit Server VM (AdoptOpenJDK)(build 25.275-b01, mixed mode)
```

위처럼 하는데도 인식인 안되서 

```shell
export JAVA_HOME=/Library/Java/JavaVirtualMachines/adoptopenjdk-8.jdk/Contents/Home
export PATH=${PATH}:$JAVA_HOME/bin
```
으로 변경해서 해도 안됬다. 

알고 보니 위 방식은 bash shell 일때 이다. 

난지금 zsh 이므로 설정파일이 다르다 .... 

```zsh
$ vi ~/.zshrc
```

```zsh
export JAVA_HOME=/Library/Java/JavaVirtualMachines/adoptopenjdk-8.jdk/Contents/Home
export PATH=${PATH}:$JAVA_HOME/bin:
```

```zsh
$ source ~/.zshrc
```

해주면 된다.

### gradle

jdk 를 깔고 나면 gradle 을 설치 한다. 

```zsh
brew install gradle
```


```zsh
$ gradle -v

------------------------------------------------------------
Gradle 6.7
------------------------------------------------------------

Build time:   2020-10-14 16:13:12 UTC
Revision:     312ba9e0f4f8a02d01854d1ed743b79ed996dfd3

Kotlin:       1.3.72
Groovy:       2.5.12
Ant:          Apache Ant(TM) version 1.10.8 compiled on May 10 2020
JVM:          1.8.0_275 (AdoptOpenJDK 25.275-b01)
OS:           Mac OS X 10.15.7 x86_64
```


참고자료
- [jenv](https://jojoldu.tistory.com/329)
- [open jdk](https://jdk.java.net/)
- [adoptopenjdk](https://adoptopenjdk.net/)
- [gradle doc](https://docs.gradle.org/current/userguide/installation.html#installation)
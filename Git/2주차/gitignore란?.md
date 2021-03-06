# .gitignore란?

`.gitignore`파일이란 `Git 버전 관리에서 제외할 파일 목록을 지정하는 파일`이다. git으로 프로젝트를 관리할 때, 그 프로젝트 안의
특정파일들은 관리할 필요가 없는 경우가 있다. 

### 예를들면 

- NodeJS npm Module, 컴파일된(class) 파일이 있다. 
- 서버파트의 예로 반드시 `.gitignore`를 해야 하는 것이 있다. (AWS RDS(Id, password), S3(엑세스키, 비번), JWT Secret Key 등등은 `절대로` Git에 올려서는 안된다.

<br>

## .gitignore 설정하기

![스크린샷 2020-10-22 오전 3 01 58](https://user-images.githubusercontent.com/45676906/96759400-f4905a80-1412-11eb-8092-2559e508ab5e.png)

<br>

`touch .gitignore`를 통해서 .gitignore 파일을 만들어보자. 그리고 `vi .gitignore`를 통해서 git이 track하지 않도록 설정을 해보자.

![스크린샷 2020-10-22 오전 3 04 11](https://user-images.githubusercontent.com/45676906/96759615-4507b800-1413-11eb-92f6-156f6723c172.png)

<br>

`test.md`를 .gitignore 파일에 저장을 하였다. 그리고 test.md 파일을 만든 후에 `Gitkraken`에서 실제로 git의 추적을 받지 않는지 확인해보자.

![스크린샷 2020-10-22 오전 3 05 46](https://user-images.githubusercontent.com/45676906/96759810-7da79180-1413-11eb-93aa-6175204e85fd.png)

<br>

`GitKraken`에서 `Unstaged Files`를 확인해보면 `test.md`파일은 보이지 않는 것을 확인할 수 있다. (한마디로 Git의 추적을 받지 않는다는 것이다.)

<img width="399" alt="스크린샷 2020-10-22 오전 3 06 43" src="https://user-images.githubusercontent.com/45676906/96759930-9f087d80-1413-11eb-84b1-60050c1903ca.png">

<br>

## 진짜로 그런지 파일을 하나 더 만들어보자.

![스크린샷 2020-10-22 오전 3 08 29](https://user-images.githubusercontent.com/45676906/96760381-de36ce80-1413-11eb-86ed-c14d876ba55e.png)

<br>

.gitignore에 적지 않은 `study.md` 파일을 위와 같이 만들었다. 다시 `GitKraken`에서 확인을 해보자. 

<img width="391" alt="스크린샷 2020-10-22 오전 3 09 07" src="https://user-images.githubusercontent.com/45676906/96760771-f4448f00-1413-11eb-9f99-1becf03828d0.png">

<br>

이번에는 `study.md` 파일이 보이는 것을 알 수 있다. 이렇게 `.gitignore`에 추가하면 git의 추적을 받지 않는 파일이 되는 것을 알 수 있다. 


<br>

## github에 이미 올라가 있는 파일을 삭제하고 .gitignore 적용하기

`이미 버전 관리에 포함되어 있는 파일들을 .gitigore 파일에 기록한다고 해서 Git이 알아서 버전 관리에서 제외 하지는 않는다.`
즉 Git이 계속해서 해당 파일을 track 하고 있다는 것이다. 예를 들어, 이미 자신의 github에 올라가 있는 파일을 삭제하고 
더 이상 track 하고 싶지 않은 경우에는 수동으로 해당 파일들을 버전 관리에서 제외시켜줘야 한다.

### 무슨말 인지 아래의 실습을 보면서 이해해보자. 

위에서 만들었던 `study.md` 파일을 먼저 `Github`에 올려보자. 그리고 아래와 같이 `.gitignore`에 `study.md`를 추가해보자. 

![스크린샷 2020-10-22 오전 3 19 34](https://user-images.githubusercontent.com/45676906/96766020-69fd2a80-1415-11eb-8a18-bfcecce06408.png)

<br>

그리고 `study.md` 파일을 수정한 후에 다시  `GitKraken`을 보면 아래와 같이 Git이 추적하고 있음을 알 수 있다. 

<img width="399" alt="스크린샷 2020-10-22 오후 3 46 04" src="https://user-images.githubusercontent.com/45676906/96834875-b2503300-147d-11eb-8061-ac685159da1e.png">

<br>

이러한 경우에는 아래의 명령어를 통해서 수동으로 파일을 제외시켜야 한다.

```
git rm -r --cached .  (현재 레포지토리의 캐시를 모두 삭제한다.)
git add .
git status
git commit -m "fixed untracked files"
```

<br>

![스크린샷 2020-10-22 오후 3 52 15](https://user-images.githubusercontent.com/45676906/96835460-8f724e80-147e-11eb-9723-ecc84af671a5.png)

<br>

위와 같이 `delete study.md`를 보면 알 수 있듯이 `.gitignore`가 적용이 되어 Git의 추적을 받지 않게 되는 것을 알 수 있다.

<br>

# 알아두면 좋은 곳

[여기](https://www.toptal.com/developers/gitignore) 접속해보면 아래와 같은 화면을 만날 수 있다.  

<img width="868" alt="스크린샷 2020-10-22 오전 3 11 26" src="https://user-images.githubusercontent.com/45676906/96762160-4685b000-1414-11eb-9aa2-addb6f9be533.png">

<br>

그리고 나는 `macOS`에서 `Node`의 `.gitignore` 파일이 필요하다면 위와 같이 입력한 후에 `생성` 버튼을 눌러보자. 

```gitignore
# Created by https://www.toptal.com/developers/gitignore/api/macos,node
# Edit at https://www.toptal.com/developers/gitignore?templates=macos,node

### macOS ###
# General
.DS_Store
.AppleDouble
.LSOverride


# Files that might appear in the root of a volume
.DocumentRevisions-V100
.fseventsd
.Spotlight-V100
.TemporaryItems
.Trashes
.VolumeIcon.icns
.com.apple.timemachine.donotpresent

- 이하 생략 - 
```

<br>

그러면 위와 같은 `.gitignore` 파일을 생성해준다. 만약에 본인이 하는 프로젝트에 `.gitignore` 파일이 필요하다면 이렇게 만드는 것도 하나의 방법인 것 같다.

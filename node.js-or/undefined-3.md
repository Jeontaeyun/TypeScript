# 노드 패키지 매니저

## 노드 패키지 매니저 

{% hint style="info" %}
**패키지를 선택하는 방법**

npm에 패키지를 검색하면 하단에 같이 비교되는 많은 패키지들이 나온다. 이를 통해 사람들이 많이 사용하는 것을 사용하는 것이 러닝 커브나 관련 생태계를 통한 지식 교류가 활발하기에 참고하는 것이 좋다.
{% endhint %}

### 노드 패키지 매니저 주요 커맨드

| 구분  | 설명  |
| :--- | :--- |
| npm audit | npm install 시에 자동으로 취약점을 검사하는 커맨드 |
| npm audit fix | npm이 수정할 수 있는 패키지는 자동으로 수정해주는 커맨드 |
| npm install -g 패키지명 | 패키지를 전역에 설치 |
| npm install -g 패키지명@버전 | 패키지의 특정 버전을 전역에 설 |
| npm install -g 패키지명@latest | 패키지의 최신 버전을 전역에 설치  |
| npm uninstall -g 패키지명 | 젼역에 설치된 패키지를 삭제 |
| npm install 패키지명 -dev | devDependencies에 해당 패키지를 추가\(어플리케이션 개발용\) |
| npm view 패키지명  | 특정 패키지에 대한 관련 정보를 모두 확인 |
| npm view 패키지명 versions | 원격 저장소에 등록된 모든 패키지 버전 확인  |
| npm view 패키지명 version | 원격 저장소에 등록된 최신 패키지 버전 확인 |
| npm outdated -g  | 전역에 설치된 패키지 중 버전이 만료된 모든 패키지 확인 |
| npm outdated -g 패키지명 | 전역에 설치된 패지키 중 특정 패키지의 만료 여부 확인  |


#유닛에서 편집하고 모형 애니메이션 내보내기

###### *version :2.1.1beta   Update:2019-7-27 插件版本：2.1.0*

게임 캐릭터 복피 골격 애니메이션은 3D 게임에서 대량의 운용으로 캐릭터 애니메이션 모형을 유닛 에디션을 편집한 뒤 리야에이어로 내보내는 것이다.

>> 여기 우리가 사용하는 복피 골격 애니메이션 원숭이

####모형 가져오기

유닛 자원 관리자에서 오른쪽 단추를 가져오기 (Import New Assets) FBX 형식 자원, 스티커 자원, 모형 끌어당겨서 재질 스티커를 조정하고 저장하고, 이 예에 저장된 장면은'monkey'라고 합니다.

[] (img/1.png)<br>(1)

####애니메이션 컨트롤러 만들기

유닛 자원 관리자 가운데 오른쪽 버튼 클립 메뉴 만들기 (Create) 애니메이션 컨트롤러 (Animmator Controller) 에 따라 애니메이션 이름을 지명 (LayaMankeyController) 로 이름을 지었다.

[] (img/2.png)<br>(2)

####애니메이션 컨트롤러 편집

애니메이션 컨트롤러를 두 번 누르면 애니메이션 컨트롤러 인터페이스 편집, 가져오는 모형 오른쪽'작은 삼각'파일을 모형 애니메이션 파일로, 기본적으로 'Take 001' 으로 끌어당겨 애니메이션 컨트롤러 인터페이스 (그림 3) 로 저장합니다.

[] (img/3.png)<br>

(그림 3)

####애니메이션 컨트롤러 바인딩

장면 속 캐릭터 모형을 선택하여 캐릭터 애니메이션 컨트롤을 선택한 모형 애니메이션 구성 요소에 부여한다. 애니메이션 구성 요소가 없으면 캐릭터에 묶여 주어야 한다. 그렇지 않으면 내보내는 애니메이션은 틀어지지 않는다.

[] (img/4.png)<br>(4)

이상의 절차를 거쳐 우리는 캐릭터 애니메이션을 유닛의 편집을 완성하고 유닛에서 실행 버튼을 누르면 우리는 애니메이션이 방영되는 것을 볼 수 있다.애니메이션 재생에 문제가 없다면 이전'유닛 플러그인 도구 사용'교정 방법에 따라 Layair의 자원을 내보낼 수 있다.

**Tips: 다른 애니메이션은 유닛 처리 방식도 일치하고, 다음과 같은 절차: 장면 모형에 애니메이션 구성 요소인 애니메이션 컨트롤러 만들기 — 애니메이션 콘솔을 애니메이션 컨트롤러에 넣어 모형 애니메이션 구성 요소를 추가합니다.**

###애니메이션 내보내기 시 주의해야 한다

#####애니메이션 파일 관련

여러 애니메이션 파일이 중명 상태를 가져서는 안 된다.

#####강체 애니메이션 관련

애니메이션 대상 애니메이션 사용 중인 애니메이터 Controller Avatar 추가하지 마세요

#####복피 뼈 애니메이션 관련

1. 골격 절점 관련 대상의 골격에는 동명의 노드가 없다.

2. 애니메이션 타입은 Generic 형식만 지원합니다.

3. Optimize Game Object 옵션 선택

[] (img/6.png)<br>(도 6)

#####애니메이션 컨트롤러 형식

애니메이터 override Controller 애니메이션 컨트롤러를 지원하지 않습니다.

[] (img/7.png)<br>
# RPG-Learn

용어
---
snap -> END키 스냅은 액터를 땅바닥에 붙이는 키

기즈모 위치 변경 -> 마우스 휠 클릭

해당 메시의 디폴트 -> ctrl + e

머테리얼 - 해당 메시에 색깔과 질감을 표현

메시 - 껍데기

피직스 에셋 - 물리적인 효과

스켈레톤 - 움직이는 본

루트 - 스켈레톤의 최상위 본

애니메이션
---
   콘텐츠-캐릭터-플레이어 폴더 만들고 Y-BOT 끌어놓고 스켈레톤-없음 모두 임포트
  
   플레이어-애니메이션-로코 폴더 생성, 모션 FBX 파일을 끌어다 놓고 임포트 옵션에서 스켈레톤을 플레이어 스켈레톤으로 선택
  
   로코 폴더에 우클릭-애니메이션-레거시-블렌드스페이스1D-해당 스켈레톤 선택
  
   애니메이션을 끌어다 놓아 0 1 2으로 설정
  
   애니메이션 폴더에서 우클릭-애니메이션-애니메이션블루프린트-해당 스켈레톤 선택
  
   BP_Player 선택해서 애니메이션에 애닝클래스에 애니메이션블루프린트 선택 -> 애니메이션들 루프로 선택

   움직이는 애니메이션의 경우에는 루트 강제 잠금설정
  
   프로젝트세팅-엔진-입력 축 매핑에 w a s d 추가
  
![image](https://github.com/user-attachments/assets/4446e71a-d6fd-46f6-8afe-3bd1b4be6e42)

  BP_player 이벤트그래프
  
  ![image](https://github.com/user-attachments/assets/73830d78-7730-492d-98eb-046bb25357b5)

플레이어 만들기
---
  플레이어-BP 파일 생성 블루프린트 클래스 생성 -> 캐릭터 더블클릭
  
  스켈레탈 메스 에셋에 Y-Bot 추가, 캡슐과 화살표방향 맞추고 컴파일, 저장
  
  컴포넌트에 추가 - 카메라, 스프링암 -> 카메라암으로 이름 바꾸고 카메라를 카메라암 밑으로 넣기
  
  콘텐츠-레벨-블루프린트클래스 생성 게임모드베이스 더블클릭 디폴트 폰 클래스를 BP_Player로 변경 
  
  프로젝트 세팅에 맵앤 모드에 기본 게임모드를 생성한 게임모드베이스로 변경
  
루트모션 버그수정
---
블랜더의 믹사모 컨버터 마스터를 통해 수정

![image](https://github.com/user-attachments/assets/f71be1b9-9d8c-4d3f-978b-e71eb393d0e3)

버그가 발생하는 이유는 믹사모의 본과 언리얼의 본이 다른경우가 있기 때문.

리타게팅
---
언리얼 엔진으로 캐릭터를 가져올 경우 리타게팅을 통해 애니메이션을 사용할 수 있게 한다.

우클릭-애니메이션-IK 리타게터,IK 릭(베이스),IK 릭(타겟)을 만든다. 

리타게터를 실행시키고 베이스로가서 루트가 아닌 Pevis나 Hips를 리타겟 루트로 설정

spine, neck, leftarm, rightarm, leftleg, rightleg를 체인으로 설정(트위스트는 제외)

입력
---
입력을 받기위해 입력-입력맵컨텍스트

입력액션을 추가 값 타입을 Axix2D로 변경(앞뒤좌우)

IMC컨트롤러에서 매핑을 WSAD는 W (스위즐 입력축값) S (Negate, 스위즐 입력 축 값) A (Negate) D (기본 입력값)

인풋매핑-BP_Player

![image](https://github.com/user-attachments/assets/5424328b-6851-4615-a94c-71a0d2f6dca4)

Move-BP_Player

![image](https://github.com/user-attachments/assets/1fb6c6a6-d291-4dcc-ade6-2c9e6170a48b)

ABP_Player

![image](https://github.com/user-attachments/assets/7d95d3bc-0bcd-48f5-898c-ed1377de6cf3)

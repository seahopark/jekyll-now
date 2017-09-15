---
layout: post
title: 기획에서 개발까지 효과적으로 GA 관리하기
---
<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-105839481-1', 'auto');
  ga('send', 'pageview');
</script>

> 이 글은 Google Analytics를 사용하는 법에 대한 정의가 아닙니다. 개발과 기획간의 Google Analytics를 효율적으로 관리할 수 있는법을 정리한 것이고, GA를 사용하는 법은 저보다 훨씬 많은 분들이 더 잘 설명하고 있으니 그분들의 글을 읽어보세요!

## 우선 알고나 씁시다
### Google Analytics가 뭐할때 쓰는거라구요?
"구글 애널리틱스(앞으론 GA라고 하겠습니다.)"는 이제는 너무나 많은 회사 및 개인들이 사용하는 유저 행동 분석 툴 입니다.
GA를 사용함으로서, 서비스 제공자들은 유저들의 행동(User Behavior)파악을 통해,
1. 지금 구현되어 있는 서비스가 서비스 제공자의 의도에 맞게 맵핑(Mapping)되었는지
2. 혹시나 길을 잃은 ~~어린양들이~~ 고객들이 있는지.
3. 또 어느부분에서 가장 많이 이탈을 하는지.
4. 유저들은 어떤 디바이스를 사용하는지, 또는 어느나이대, 어느 국가에서 해당 서비스를 사용하고 있는지.
5. 커머스 같은 경우엔, 유저가 어떤 물건에 가장 큰 관심을 가지는지.
등 분석을 통해 다양한 정보를 확인할 수 있습니다.

### 이글을 읽으면 GA 짱짱맨이 되는건가요?
아닙니다(단호).
저도 GA를 잘 활용하는 법에 대해선 잘 몰라 열심히 공부하는 중입니다.

### 그럼 이글은 뭔가요?
GA는 기획자 또는 PM분이 잘 하신다고, 100% 효과를 얻을 수 없어요(Google Tag Manager등을 통해서는 어느정도 도움이 되지만,)
제가 알려드리려는 건, GA를 개발자님들과 기획자님들이 효율적으로 관리하고 이해할 수 있도록 하는 일에 대해서 설명드리려고 합니다.

## GA 시작하기
우선 제가 설명드리는 건 무료계정의 케이스 입니다!
하나하나 천천히 설명드릴게요!

### GA 계정 생성하기
GA를 시작하기 위해선, 해당 서비스를 위한 Analytics계정이 필요합니다.
한명의 Google 계정 당 100개의 GA 계정을 제작할 수 있고, "새계정 만들기"를 통해 새 계정을 만들 수 있습니다.

### 계정 ID, 사용자 관리하기
Analytics계정을 생성하고 나면, 9개의 숫자로 되어있는 계정 ID가 생성됩니다.

Google Analytics를 위한 Google Spreadsheet를 제작, 개발과 기획간의 로그에 대한 현황파악 대시보드를 제작합니다.

### 구조
* GA-All.xls: 전체 GA 데이터
* GA-Android update.csv: 기능 추가/ 개선 등의 상황으로 GA 변경 시 적용되는 Android GA 사항 업데이트
* GA-ios update.csv: 기능 추가/ 개선 등의 상황으로 GA 변경 시 적용되는 iOS GA 사항 업데이트

## 프로세스
![음?](https://files.slack.com/files-pri/T02EMF0J1-F6HFL9NRJ/ga_tracking_process.png?pub_secret=259ee686d7)
* Spec Final 전까지 기획에서는 로깅해야 할 이벤트 들을 정의하고 논의합니다.
* 논의가 된 Logging Event는 개발에서는 Task로 관리, 각각의 플랫폼 별로 정리 된 ~.csv파일을 확인하고 적용시킵니다.
* GA 관리자는 해당 부분에 대한 개발 완료 후 테스팅을 자체적으로 진행합니다.

## SDK Documentation
* Android: https://developers.google.com/analytics/devguides/collection/android/v4/
* iOS - Swift : https://developers.google.com/analytics/devguides/collection/ios/v3/?ver=swift

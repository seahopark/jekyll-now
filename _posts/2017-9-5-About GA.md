---
layout: post
title: 기획에서 개발까지 효과으로 GA 관리하기
---
<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-105839481-1', 'auto');
  ga('send', 'pageview');
</script>

## 우선 알고나 씁시다
### Google Alaytics가 뭐할때 스는거라구요?
구글 애널리틱스(앞으론 GA라고 하겠습니다.)는 이제는 너무나 많은 유저분들이 사용하는 유저 행동 분석 툴 입니다.
GA를 통해 서비스 제공자들은 유저들의 행동분석을 통해서
1. 지금 구현되어 있는 페이지가 서비스 제공자들의 의도에 맞게 맵핑(Mapping)되었는지
2. 혹시나 길을 잃은 ~어린양들이~ 고객들이 있는지. 어느부분에서 가장 많이 이탈을 하는지
3. 유저들은 어떤 디바이스를 사용하는지, 또는 어느나이대, 어느 국가에서 해당 서비스를 사용하고 있는지
4. 커머스 같은 경우엔, 유저가 어떤 물건에 가장 큰 관심을 가지는지
등 분석을 통해 다양한 정보를 확인할 수 있습니다.

# GA 적용하기
Google Analytics Test
## 의의
해당 Repo의 의의는, 기획과 개발간에서 Google Analytics를
1. 직군간, 플랫폼간 보다 명확한 커뮤니케이션을 진행하기 위해
2. 보다 정확하게 GA 적용 여부를 파악하기 위해
3. 각자가 필요한 부분만 확인하고 찾아가기 위해
제작된 Repo입니다.

## 구조
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

# KnowledgeBase


1.
- 발생일: 24.06.03 이전
- 현상: 개발/운영 서버 내에서 SPA 페이지 재호출 또는 flutter uri open / javascript window.open 수행 시 whitelabel error 페이지 출력
- 원인: thymeleaf 는 html 별로 view를 맵핑하지만 SPA(하나의 html에서 url에 따른 매핑과 호환하지 못함)
  따라서 정상동작을 위해 매핑되는 html이 제각각 존재해야합니다. 또는
  registry.addViewController("/MAIN_COMMON_001").setViewName("forward:/index.html");
  위와 같이 spring webconfig 단에서 각각의 route에 대해 설정해주어야 합니다.
- 참고 URL: https://happy-coding-day.tistory.com/entry/Springboot-%EC%97%90%EC%84%9C-reactjs-%EC%97%B0%EB%8F%99%EC%8B%9C-%EB%AA%A8%EB%93%A0-view-%EB%A7%B5%ED%95%91%EC%9D%84-indexhtml%EC%9C%BC%EB%A1%9C-forwarding-%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80

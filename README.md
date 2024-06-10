# Spring Security

## SecurityBuilder, SecurityConfigurer
- SecurityBuilder는 빌더 클래스로 웹 보안을 구성하는 빈 객체와 설정클래스들을 생성하는 역할을 한다, 대표적으로 `HttpSecurity`와 `WebSecurity`가 있다.
- SecurityConfigurer는 HTTP 요청과 관련된 보안처리를 담당하는 필터들을 생성하고 여러 초기화 설정에 관여한다.
- SecurityBuilder는 SecurityConfigurer를 참조하고 있으며 인증 및 인가 초기화 작업은 SecurityConfigurer에서 진행한다.

## HttpSecurity
- HttpSecurityConfiguration에서 HttpSecurity를 생성하고 초기화를 진행한다.
- HttpSecurity는 보안에 필요한 각 설정 클래스와 필터들을 생성하고 최종적으로 `SecurityFilterChain` 빈을 생성한다.

## WebSecurity
- WebSecurityConfiguration에서 WebSecurity를 생성하고 초기화를 진행한다.
- WebSecurity는 HttpSecurity에서 생성한 `SecurityFilterChain` 빈을 `SecurityBuilder`에 저장한다.
- WebSecurity가 build()를 실행하면 `SecurityBuilder`에서 `SecurityFilterChain` 빈을 가져와서 `FilterChainProxy` 생성자에게 전달한다.

## HttpSecurity, WebSecurity 결론
- HttpSecurity가 `SecurityFilterChain` 빈을 생성하고 WebSecurity가 `SecurityFilterChain` 빈을 `FilterChainProxy`에 전달한다.[README.md](README.md)
# Spring Security

## HttpSecurity
- HttpSecurityConfiguration에서 HttpSecurity를 생성하고 초기화를 진행한다.
- HttpSecurity는 보안에 필요한 각 설정 클래스와 필터들을 생성하고 최종적으로 `SecurityFilterChain` 빈을 생성한다.

## WebSecurity
- WebSecurityConfiguration에서 WebSecurity를 생성하고 초기화를 진행한다.
- WebSecurity는 HttpSecurity에서 생성한 `SecurityFilterChain` 빈을 `SecurityBuilder`에 저장한다.
- WebSecurity가 build()를 실행하면 `SecurityBuilder`에서 `SecurityFilterChain` 빈을 가져와서 `FilterChainProxy` 생성자에게 전달한다.

## HttpSecurity, WebSecurity 결론
- HttpSecurity가 `SecurityFilterChain` 빈을 생성하고 WebSecurity가 `SecurityFilterChain` 빈을 `FilterChainProxy`에 전달한다.[README.md](README.md)
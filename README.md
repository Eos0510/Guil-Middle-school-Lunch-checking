author : 이현록

이 소스코드는 구일중학교의 급식정보를 구일중학교 공식 사이트에서 크롤링함으로서 동작합니다.

사용 프로그램 : v0.1~v0.2 : Python IDLE, v0.3 : Visual Studio Code

############원리

0. input으로 날짜를 입력받는다.

1. http://guil.sen.ms.kr/65872/subMenu.do 사이트에 requests 모듈을 통해 날짜 정보를 POST 형식으로 보낸다.

2. Beautifulsoup을 통해 파싱을 한 뒤, a태그로 서버에 전송되는 mlsvId값을 찾아낸다.

3. 찾아낸 mlsvId값을 http://guil.sen.ms.kr/65872/subMenu.do 에 POST형식으로 보내서 급식정보를 얻는다.

4. 얻은 급식정보를 파싱 및 정규표현식으로 잘 가공한 뒤, print로 출력한다.

#############

v0.1

최초 출시

버그1 - 급식 정보가 안 나옴

버그2 - 문자열 입력 시 프로그램 종료됨

#############

v0.2

급식 정보가 안 나오는 버그 수정

버그1 - 급식 정보가 없는 날(토요일, 일요일, 공휴일)에는 에러가 출력됨

버그2 - 문자열, 공백 입력 시 아무 출력 없이 프로그램 종료됨

#############

v0.3

코드 관련

 -> 코드 안정화 및 최적화 진행됨

 -> class사용으로 객체화 시킴. 크게 mlsvId 값을 얻는 함수와 mlsvId값을 토대로 최종 급식정보를 얻는 함수가 있음.

기능 관련

 -> 급식 정보가 없는 요일에는 '해당 요일에는 급식이 없습니다.' 출력

 -> 잘못된 값 입력시 '잘못된 값이 입력되었습니다.' 출력 및 다시 날짜 물어봄

버그 수정

v0.2의 버그1, 버그2 해결됨.

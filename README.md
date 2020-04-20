# HTTP&REST
## HTTP(Hypertext Transfer Protocol)  
브라우저(클라이언트)와 서버간 데이터를 주고받기위한 방식(나는 이렇게 줄 테니, 넌 이렇게 받아) HTTP로 데이터를 주고받기 위해서는 Request, Response가 있어야한다.  
### URL을통해 데이터를 요청하는데, 요청하는 데이터에 특정 동작을 수행할 수 있다.  
1. GET : 존재하는 자원에 대한 요청  
2. POST : 새로운 자원을 생성  
3. PUT : 존재하는 자원에 대한 변경
4. DELETE : 존재하는 자원에 대한 삭제
### 기타 요청 method  
1. HEAD : 서버 헤더 정보를 획득. GET과 비슷하나, Response Body를 반환하지 않는다.  
2. OPTIONS : 서버 옵션들을 확인하기 위한 요청. CORS에서 사용    
## REST(REpresentational State Transfer)  
웹을 구성하는 자원(resources)들을 고유한 이름으로 구분하여 해당 자원의 정보를 주고받는 것.  
1. HTTP URL(어쩌면 URI가 맞을수도)을 통해 고유한 이름으로 자원을 명시하고,
2. HTTP Method(POST, GET, DELETE, PUT)을 통해 해당 자원에 대한 CRUD를 적용  
### URL vs URI  
1. URL : 클라이언트가 서버에 요청한 파일!의 디렉토리(위치)  
2. URI : 해당 자원의 고유 식별값  
예시) http://clooo.loooooo.net/lectures.html(URL) vs http://clooo.loooooo.net/lectures/114(URI)
#### URI는 URI을 포함하고있다.  
### RESTful API  
REST한 방식의 API란, 잘 설계된 API를 말한다.  
1. 웹을 근간으로 하는 HTTP 기반이다.  
2. 자원은 URI로 표현하며 말 그대로 고유해야한다.  
3. URI는 단순하고 직관적인 구조여야 한다.  
4. 자원의 상태는 HTTP Methods를 활용해 구분한다.  
### API Design  
1. 복수명사를 사용한다(/movies)  
2. 필요하면 URL에 하위 자원을 표현(/movies/23) => URI  
3. 필터조건을 허용할 수 있다(/movies?state=active) => URI  
### 예제  
|URI|Methods|설명|
|---|---|---|
|/movies|GET|모든 영화리스트 가져오기|
|/movies|POST|영화추가|
|/movies/:title|GET|title 해당영화 가져오기|
|/movies/:title|DELETE|title 해당 영화 삭제|
|/movies/:title|PUT|title 해당영화 업데이트|
|/movies?min=9|GET|평점이 최소 9 이상인 영화|
# [구현할 기능 목록] 1단계 - 상품 API 
## 1. 상품 정보를 담는 Product 클래스 구현
#### - 필드값 : Long id, String name, Long price, String imageurl;
## 2. CRUD 요청을 받고 응답을 반환할 controller 구현
#### - Create : 자바 컬렉션 프레임워크를 사용하여 메모리에 저장하는 메서드 구현
#### - Read : 상품 전부를 조회하는 메서드, URL 경로 변수와 일치하는 id를 가지는 상품을 조회하는 메서드 구현
#### - Update : URL 경로 변수와 일치하는 id를 가진 상품의 필드값들 수정하는 메서드 구현
#### - Delete : URL 경로 변수와 일치하는 id를 가진 상품 삭제하는 메서드 구현


# [구현할 기능 목록] 2단계 - 관리자 화면 
## 1. 의존성 추가
### (1) 의존성 추가 
- implementation 'org.springframework.boot:spring-boot-starter-thymeleaf
- implementation 'org.springframework.boot:spring-boot-starter-data-jpa'
- runtimeOnly 'com.h2database:h2'
### (2) 간단한 웹페이지 구현
- `products.html` : 상품 관리 메인 페이지. 추가된 상품들을 보여줌.
- `creat_product.html` : 사용자 입력을 통해 상품 정보 추가.
- `edit_product.html` : 추가된 상품 정보를 수정 가능
### (3) MVC 구현
- `ProductController` : SSR 이용하여 컨트롤러 구현   
- `ProductService` : CRUD 서비스 구현 
- `ProductRepository` : JPA 활용

# [구현할 기능 목록] 3단계 - 데이터베이스 적용
## 1. 상품 옵션 추가
- [x] create_product.html : 상품 옵션 추가 기능 구현
- [x] 전체적인 웹 페이지 ui 변경

## 2. JdbcTemplate 활용
- [x] application.yml : h2 database 접속 정보 설정
- [x] schema.sql : 데이터베이스의 테이블 설계
- [x] ProducRepository : JdbcTemplate을 활용하여 CRUD 구현 
- [x] DB 사용 로직의 중복 해결 by RowMapper

## 3. ExceptionHandler 구현
- [x] 사용자 정의 exception 구현
  - [x] ProductNotFoundException: 제품을 찾을 수 없을 때 발생하는 예외   
  - [x] ProductAlreadyExistsException: 제품이 이미 존재할 때 발생하는 예외
  - [x] InvalidProductDataException: 입력하는 제품 데이터가 유효하지 않을 때 발생하는 예외
- [x] Global Exception 핸들러 구현 


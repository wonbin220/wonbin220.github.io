# 🐩 pet-mily 
>  반려동물 관련 복합 커뮤니티 

 </br> 

## 1. 제작 기간 & 참여 인원
- 2025년 8월 30일 ~ 10월 25일
- 개인 프로젝트
  
 </br>

## 2. 프로젝트 개요

**pet-mily**는 Spring Boot, Spring Security, MyBatis, Thymeleaf를 기반으로 구축된 커뮤니티형 반려동물 종합 사이트 입니다. 

사용자 인증, 게시판, 댓글 등 커뮤니티의 핵심 기능을 갖추고 있으며, 관리자 페이지를 통해 사용자 및 게시글을 체계적으로 관리할 수 있습니다. 
SmartEditor2 연동을 통해 사용자 편의성을 높였고, AJAX를 적극적으로 활용하여 동적인 웹 환경을 구현했습니다.

## 3. 기술 스택

- **Backend**: 
    - **Java 17** : 장기적인 안정성과 지원을 제공
    - **Spring Boot 3.4.5** : 빠른 개발과 자바 17 이상과 호환성이 좋고 새로운 기능 활용 때문
    - **Gradle** : 뛰어난 성능, 유연성, 그리고 다양한 프로젝트 지원
    - **Spring Security** : 보안 관련 기능을 쉽고 효과적으로 구현할 수 있기 때문
- **Database**: 
    - **MyBatis** : 유연하고 기존 시스템과의 호 환성이 있으며 SQL을 직접 제어하며 복잡한 쿼리를 쉽게 작성할 수 있기 때문
    - **MySQL 8.0** : 웹 애플리케이션에 매우 적합하며 안정적이고 유연한 성능을 제공

- **Libraries**:
  - **Paging**: PageHelper : MyBatis 환경에서 복잡한 페이징 로직을 단순화하고 개발 생산성을 높이기 위해
  - **Editor**: Naver SmartEditor2 : 사용자 친화적인 인터페이스 제공 및 이미지 업로드 기능 지원 
  - **Email**:  Spring Boot Starter Mail (JavaMailSender) : 이메일 발송 기능을 쉽게 구현하기 위해
  

## 4. 주요 기능 및 담당 역할

### 👤 회원 관리 (Member Management)
<img src="https://github.com/user-attachments/assets/cf4d8066-cd4b-46d8-af5c-7b7895e4626b" width="24%">
<img src="https://github.com/user-attachments/assets/3f943095-fcd4-47c5-a840-4334f200f179" width="24%">
<img src="https://github.com/user-attachments/assets/32de0e5b-d3b0-48f3-ae15-645eba21ca60" width="24%">
<img src="https://github.com/user-attachments/assets/4e070d8a-c815-4462-a0e0-59c5036e6847" width="24%">

- **회원 인증 (Authentication & Authorization)**
  - **Spring Security**를 활용하여 안전한 로그인 및 로그아웃 기능을 구현했습니다.
  - `LoginSuccessHandler`를 커스텀하여 로그인 성공 시 사용자 정보를 세션에 저장하고, 이를 통해 인증 상태를 유지합니다.
  - 페이지 접근 권한을 **USER**와 **ADMIN**으로 분리하여 체계적인 접근 제어를 구현했습니다.

- **회원 가입 및 정보 수정 (CRUD)**
  - 회원 가입 시 아이디 중복 검사를 수행하고, `BCryptPasswordEncoder`를 이용해 비밀번호를 **단방향 암호화**하여 DB에 저장합니다.
  - 사용자는 자신의 개인 정보(이메일, 주소 등)를 직접 수정할 수 있습니다.

- **아이디/비밀번호 찾기**
  - **JavaMailSender API**를 연동하여 사용자가 가입 시 입력한 이메일로 인증번호를 발송합니다.
  - 인증번호 검증을 통해 아이디를 화면에 보여주거나, 비밀번호를 안전하게 재설정하는 기능을 구현했습니다.

- **관리자 기능 (Admin-specific)**
  - 관리자는 모든 회원의 목록을 **페이징**하여 조회할 수 있습니다.
  - **AJAX**를 활용하여 각 회원의 등급(예: USER, ADMIN)을 동적으로 변경할 수 있는 기능을 구현했습니다.
  - 특정 회원이 작성한 모든 게시글을 모아보는 기능을 제공하여 사용자 활동을 쉽게 추적할 수 있습니다.



### 📝 게시판 (Board)
![board page](https://github.com/user-attachments/assets/f59ad43e-bd91-44a7-86c5-f3d620dc9970)

- **게시글 CRUD**
  - **SmartEditor2**를 연동하여 사용자가 편리하게 이미지와 텍스트를 포함한 게시글을 작성, 조회, 수정, 삭제할 수 있도록 구현했습니다.
  - MyBatis를 사용하여 데이터베이스와 통신하며, 파일 업로드 시 `FileService`를 통해 서버에 파일을 저장하고 게시글 삭제 시 관련 파일도 함께 삭제하여 **데이터 무결성**을 유지합니다.

- **페이징, 검색, 카테고리**
  - **PageHelper** 라이브러리를 활용하여 효율적인 **서버 사이드 페이징**을 구현했습니다.
  - 게시글을 '일반', '공지' 등 카테고리별로 나누어 볼 수 있습니다.
  - 제목, 내용, 작성자 등 다양한 조건으로 게시글을 **검색**하는 기능을 제공합니다.

- **조회수 및 상위 게시물**
  - **쿠키(Cookie)** 를 이용하여 특정 시간 내 중복 조회수가 증가하지 않도록 방지하는 로직을 구현했습니다.
  - 메인 페이지에 조회수가 높은 __'Top 10 게시글'__ 과 **'최신 공지사항'** 목록을 노출하여 사용자 편의성을 높였습니다.



### 💬 댓글 (Comment)
![comment](https://github.com/user-attachments/assets/042980f6-6b4a-44cb-b94e-0d06a19d22a2)

- **댓글 CRUD (AJAX)**
  - 게시글 상세 페이지에서 페이지 새로고침 없이 댓글을 작성, 수정, 삭제할 수 있도록 모든 댓글 기능을 **AJAX**로 구현했습니다.
  - **RESTful API** 형식(`@RestController`)으로 엔드포인트를 설계하여 클라이언트와의 데이터 통신을 효율적으로 관리합니다.
  - 댓글 수를 실시간으로 카운트하여 게시글 목록에 표시합니다.



### 🖥️ 메인 페이지 및 UI/UX
<img src="https://github.com/user-attachments/assets/8f021e7e-3e61-484a-a426-45bd05900fde" width="65%" height="65%">

- **동적 메인 페이지**
    - 메인 페이지에 최신 공지사항, Top 10 게시글, 최신 일반 게시글 목록을 동적으로 불러와 보여줌으로써 사이트의 활성도를 시각적으로 표현합니다.
- **반응형 UI**
    - Bootstrap을 활용하여 모바일, 태블릿, 데스크톱 등 다양한 디바이스에서 최적화된 화면을 제공합니다.


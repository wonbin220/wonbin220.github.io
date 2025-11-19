# 🐩 pet-mily
>  반려동물 관련 복합 커뮤니티

 </br>

## 1. 퍼블리셔에서 백엔드 개발자로

초기에는 웹 퍼블리셔로 근무하며 아래와 같이 다양한 웹사이트를 제작했습니다.

### 국제장애인기능올림픽_e_역사관 (https://www.kead.or.kr/abilympics/)
- HTML, CSS, JavaScript, JQuery를 활용한 퍼블리싱 개발
<img src="https://github.com/user-attachments/assets/2bfbe9c4-c3ab-4ae7-8e61-ed504419d2a8" width="65%" height="45%">

### 버블몬스터 홈페이지 제작 (https://www.bubblemonster.co.kr/)
- JSP, PHP, HTML, CSS, JavaScript, JQuery를 활용한 퍼블리싱 개발
<img src="https://github.com/user-attachments/assets/73d1c49e-b20a-4dc4-869e-47314c65b00c" width="65%" height="45%">

### 공연예술인노조 홈페이지 제작 (www.artnojo.kr)
- PHP, MYSQL, APACHE, HTML, CSS, JavaScript, JQuery를 활용한 퍼블리싱 개발
- 이런 개발들을 통해 게시판 구조를 알고 있음
<img src="https://github.com/user-attachments/assets/e5e3af5d-446c-4c79-bfde-b9d565861ac6" width="65%" height="45%">

 </br>


### PHP를 활용한 백엔드 개발 경험
- 퍼블리셔로 근무하며 PHP를 활용한 Beck-end 서비스 개발 참여
<img src="https://github.com/user-attachments/assets/4c06f43b-fff1-4e30-9237-f221bea123ad" width="65%" >

</br>

### PHP로 Beck-end 서비스를 조금이나마 만든 경험들을 통해 점차 사용자가 보지 못하는 서버 뒷단에 더 큰 흥미를 느끼게 되었습니다. 데이터베이스, 서버, API 로직 등 애플리케이션의 핵심을 다루는 백엔드 개발에 더 큰 책임감과 매력을 느껴 직무를 전향하게 되었습니다.

</br>

---

</br>

## 2. 개인 프로젝트: pet-mily

### 2-1. 제작 기간 & 참여 인원
- 2025년 8월 30일 ~ 10월 25일
- 개인 프로젝트

 </br>

### 2-2. 프로젝트 개요

**pet-mily**는 Spring Boot, Spring Security, MyBatis, Thymeleaf를 기반으로 구축된 커뮤니티형 반려동물 종합 사이트 입니다.

사용자 인증, 게시판, 댓글 등 커뮤니티의 핵심 기능을 갖추고 있으며, 관리자 페이지를 통해 사용자 및 게시글을 체계적으로 관리할 수 있습니다.
SmartEditor2 연동을 통해 사용자 편의성을 높였고, AJAX를 적극적으로 활용하여 동적인 웹 환경을 구현했습니다.

 </br>


### 2-3. 기술 스택

- **Backend**:
    - **Java 17** : 장기적인 안정성과 지원을 제공
    - **Spring Boot 3.4.5** : 자동 구성(Auto-configuration)과 내장 서버를 통해 초기 설정의 복잡함을 줄여 핵심 비즈니스 로직 개발에 집중할 수 있었습니다. 스타터(starter) 의존성은 라이브러리 버전 관리를 간소화하여 안정성을 높여주었고, Spring Security 등 다른 Spring 프로젝트와의 뛰어난 통합 덕분에 보안과 같은 필수 기능들을 효율적으로 구현할 수 있었습니다.
    - **Gradle** : 뛰어난 성능, 유연성, 그리고 다양한 프로젝트 지원
    - **Spring Security** : 보안 관련 기능을 쉽고 효과적으로 구현할 수 있기 때문
- **Database**:
    - **MyBatis** : 유연하고 기존 시스템과의 호 환성이 있으며 SQL을 직접 제어하며 복잡한 쿼리를 쉽게 작성할 수 있기 때문
    - **MySQL 8.0** : 웹 애플리케이션에 매우 적합하며 안정적이고 유연한 성능을 제공

- **Libraries**:
    - **Paging**: PageHelper : MyBatis 환경에서 복잡한 페이징 로직을 단순화하고 개발 생산성을 높이기 위해
    - **Editor**: Naver SmartEditor2 : 사용자 친화적인 인터페이스 제공 및 이미지 업로드 기능 지원
    - **Email**:  Spring Boot Starter Mail (JavaMailSender) : 이메일 발송 기능을 쉽게 구현하기 위해

 </br>

### 2-4. 주요 기능 및 담당 역할

#### 👤 회원 관리 (Member Management)
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


 </br>

#### 📝 게시판 (Board)
![board page](https://github.com/user-attachments/assets/f59ad43e-bd91-44a7-86c5-f3d620dc9970)

- **구현 내용**
    - **SmartEditor2 연동**: 사용자가 이미지와 텍스트를 손쉽게 편집할 수 있는 WYSIWYG 에디터를 제공하여 콘텐츠 작성의 편의성을 극대화했습니다.
    - **효율적인 데이터 관리**: `PageHelper`를 이용한 **서버 사이드 페이징**으로 대용량 데이터도 클라이언트 부담 없이 빠르게 조회할 수 있습니다. 또한, 게시글 삭제 시 첨부 파일까지 함께 삭제하는 로직을 구현하여 **데이터 무결성**을 확보했습니다.
    - **콘텐츠 접근성 향상**: 카테고리 분류, 다양한 조건의 검색 기능, 메인 페이지의 'Top 10 게시글' 및 '최신 공지' 노출을 통해 사용자가 원하는 정보에 쉽게 접근할 수 있도록 설계했습니다.

- **개발 과정에서의 고민**
    - **게시판 CRUD**: 파일이 포함된 게시글을 어떻게 안정적으로 처리할지 고민했습니다. 사용자가 게시글을 수정하며 파일을 추가하거나 삭제하는 다양한 시나리오를 고려해야 했습니다. 이를 해결하기 위해 게시글 정보와 파일 정보를 별도의 트랜잭션으로 관리하고, `FileService`를 만들어 파일의 업로드, 수정, 삭제 생명주기를 명확히 제어함으로써 데이터 정합성 문제를 방지했습니다.
    - **조회수 중복 방지**: 단순한 DB 업데이트는 사용자가 새로고침할 때마다 조회수가 무한정 오르는 문제가 있었습니다. 이를 해결하기 위해 **쿠키(Cookie)** 를 활용했습니다. 사용자가 특정 게시물을 조회하면, 해당 게시물 ID를 쿠키에 저장하고 정해진 시간(예: 24시간) 내에는 조회수를 올리지 않도록 로직을 구현하여 보다 정확한 인기 게시물 집계가 가능하도록 만들었습니다.


 </br>

#### 💬 댓글 (Comment) - 계층형 구조
![comment](https://github.com/user-attachments/assets/042980f6-6b4a-44cb-b94e-0d06a19d22a2)
![comment](https://github.com/user-attachments/assets/40dbb4b9-9a4b-43ba-a450-cf7d522b75da)

- **계층형 댓글 구조 (Hierarchical Comments)**
    - **대댓글 기능**을 통해 사용자들이 특정 댓글에 직접 답글을 달 수 있는 **계층형 구조**를 구현했습니다. 이는 단순히 시간순으로 나열되는 단일 목록 구조와 달리, 특정 주제에 대한 논의가 집중되고 대화의 흐름을 쉽게 파악할 수 있게 합니다.

    - **구현 내용**:
      - **가독성 향상**: 관련된 대화가 그룹화되어 있어 사용자가 특정 토론을 따라가기 용이합니다.
      - **구현 방식**: DB 테이블에 `parent_id`와 `depth` 컬럼을 두어 부모-자식 관계와 깊이를 정의했습니다. 서버에서는 계층형 쿼리를 사용하여 댓글과 대댓글을 함께 조회하고, 이를 클라이언트에 전달하여 시각적으로 들여쓰기 등으로 표현했습니다.
    


    

- **개발 과정에서의 고민**
    - **댓글 CRUD**: 계층 구조를 어떻게 효율적으로 조회하고 표현할지가 가장 큰 고민이었습니다. DB에서 모든 댓글을 가져와 서비스 로직에서 재귀적으로 구조를 만드는 방식과, DB 자체의 계층형 쿼리(예: `CONNECT BY` 또는 `Recursive CTE`)를 사용하는 방식 사이에서 고민했습니다. 데이터 양이 많아질 경우를 대비해 DB의 부담을 줄이는 방향으로, 가져온 데이터를 서비스단에서 효과적으로 그룹화하여 계층 구조를 만드는 방식을 채택했습니다.
    - **UI/UX 개선**: 대댓글이 무한정 깊어지면 UI가 깨지고 가독성이 떨어지는 문제가 있었습니다. 이를 해결하기 위해 **최대 5개의 대댓글까지만 허용**하고, 5단계를 넘어가는 댓글은 자동으로 최상위 레벨(1단계) 댓글로 등록되도록 정책을 정했습니다. 이를 통해 사용자 경험과 시스템 안정성을 모두 확보할 수 있었습니다.


#### 🖥️ 메인 페이지 및 UI/UX
<img src="https://github.com/user-attachments/assets/8f021e7e-3e61-484a-a426-45bd05900fde" width="65%" height="65%">

- **동적 메인 페이지**
    - 메인 페이지에 최신 공지사항, Top 10 게시글, 최신 일반 게시글 목록을 동적으로 불러와 보여줌으로써 사이트의 활성도를 시각적으로 표현합니다.
- **반응형 UI**
    - Bootstrap을 활용하여 모바일, 태블릿, 데스크톱 등 다양한 디바이스에서 최적화된 화면을 제공합니다.


</br>
</br>

### 프로젝트 한줄 평

    - 기본 게시판 기능에 충실하면서도, 계층형 댓글과 같은 다른 기능을 추가하고 관리자 페이지도 구현한 프로젝트입니다. 추후에 알람, 채팅 등 실시간 기능을 추가하여 더욱 완성도 높은 커뮤니티 사이트로 발전시킬 예정입니다.
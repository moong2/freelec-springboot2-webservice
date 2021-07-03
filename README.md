# 게시판 제작(개인 공부 프로젝트)

## 프로젝트 구성 안내 
Spring을 이용해서 게시판을 제작하고 소셜로그인 접속이나 aws를 이용한 배포를 한 후 CI/CD를 이용한 자동배포화, Nginx를 이용한 무중단배포를 공부한 프로젝트입니다.<br>
무중단 배포까지 진행을 하였지만 현재는 배포 중단 상태입니다. <br>
'스프링 부트와 AWS로 혼자 구현하는 웹 서비스'를 참고하여 진행했습니다. <br>

### 제작 이유
개념으로만 공부한 Spring을 처음 실제 코드에 적용해 본 프로젝트입니다.<br>
백엔드 개발자라면 개발부터 배포까지 실제로 경험해 보아야 한다고 생각을 했습니다. 그래서 공부한 것이 조금 부족하더라도 실제로 코드에 적용해 보자는 생각으로 이 프로젝트를 시작하게 되었습니다.<br>

### 기술 스택
- Spring Framework
- MariaDB
- AWS(EC2, RDS, S3, CodeDeploy)
- Travis CI
- Nginx
- Linux

### 개발, 배포 환경
1. 개발 환경
   - Intellij의 Spring MVC 모듈 사용
   - 자바 1.8 버전 사용
   - TDD를 위한 junit, mock, assertj dependency 사용
   - 점점 많이 쓰이는 기술을 접해보기 위해 Gradle 사용
   - OAuth 2.0 사용을 위한 스프링 시큐리티 관련 의존성 사용

2. 배포 환경
  ![board_deployment_layout](https://user-images.githubusercontent.com/67732143/124348635-ee02e580-dc25-11eb-8ffb-34fc5e02855a.jpg)
  
   - 호스팅을 위한 AWS EC2(+탄력적 ip)사용
   - 클라우드 데이터베이스를 위한 AWS RDS사용
   - S3, Travis CI, CodeDeploy를 연동하여 배포자동화
   - Nginx를 이용하여 무중단배포
   
## 프로젝트 기능
   #### Main 화면
   
      ![board_home](https://user-images.githubusercontent.com/67732143/124348935-ba28bf80-dc27-11eb-949a-faa954ddbdc0.jpg)
      - 게시글의 목록과 로그인/로그아웃 할 수 있는 기능이 있습니다.
      
   #### Login 화면
   
      ![board_login](https://user-images.githubusercontent.com/67732143/124348955-ca409f00-dc27-11eb-9472-f731d921c345.jpg)
      - 네이버/구글 소셜 로그인이 가능합니다.
      
   #### 게시글 작성 화면
   
      ![board_notice](https://user-images.githubusercontent.com/67732143/124348972-d7f62480-dc27-11eb-8393-585ed6056a0d.jpg)
      - 간단하게 글의 제목, 작성자, 내용을 기입하는 칸이 있고 글을 올리는 등록버튼과 취소버튼이 있습니다. 
      - 로그인을 해야만 게시글을 작성할 수 있으며 계정에 권한이 걸려 있어 권한이 있는 사람만 글을 작성할 수 있습니다.
     
   #### 게시글 수정/삭제 화면
   
      ![board_modify_and_delete](https://user-images.githubusercontent.com/67732143/124348983-e7756d80-dc27-11eb-86a7-f7c48e5360e5.jpg)
      - 자신의 게시글을 수정/삭제 할 수 있습니다. 
      - 수정/삭제시 게시글은 읽기 전용으로 글 번호와 작성자는 수정할 수 없고 게시글 제목과 내용만 수정이 가능합니다.
     

## 프로젝트 모듈
   1. PostsApiController
      - **역할** : 게시글 저장 / 업데이트 / 게시글 id로 검색
      - **관련 파일** : PostsService, PostsSaveRequestDto, PostsResponseDto, PostsUpdateRequestDto, Posts
   2. CustomOAuth2UserService
      - **역할** : 유저 정보 / 로그인
      - **관련 파일** : User, Role, UserRepository, OAuthAttributes, 

## 버그
   - 현재 배포가 중단되었습니다.

## 프로젝트 작성자 및 도움을 준 사람
   - 작성자 : moong2
   - 이메일 : pushclap@gmail.com

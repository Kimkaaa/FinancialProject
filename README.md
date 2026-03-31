# Financial Project

![메인](images/main.png)

<br>

**Financial Project**는 금융회사 내부 업무를 지원하기 위한 직원용 웹 서비스를 구현한 팀 프로젝트입니다.

고객 관리, 상품 관리, 금융 상품 설계 및 계산, 일정 관리 등 다양한 업무를 통합 관리할 수 있습니다.

<br>

백엔드는 Spring Boot, 화면은 Thymeleaf 기반으로 구현했습니다.

데이터 접근 계층에서는 MyBatis를 사용해 복잡한 조회 및 조건 검색을 SQL 중심으로 처리했고,

JWT와 Spring Security를 통해 사용자 권한에 따른 접근 제어를 적용했습니다.

<br>

Redis를 활용해 인증번호 관리 및 요청 제한 기능을 구현했고,

문자 발송(CoolSMS)과 금융 지수 및 뉴스 데이터 등 외부 API를 연동하여 기능을 확장했습니다.

<br>

팀원 전원이 기획부터 개발까지 전 과정에 참여했으며

Notion으로 일정과 작업을 관리하고, Figma로 화면을 디자인하며 협업했습니다.

<br>
<br>


## 프로젝트 정보

- **유형**: 팀 프로젝트 (8명)

- **기간**: 2024.11.12 ~ 2024.12.02 (약 3주)

- **주요 기능**

    - 회원가입 및 로그인
 
    - 메인 대시보드
 
    - 고객 관리
 
    - 상품 관리
 
    - 설계 관리

    - 일정 관리

    - 게시판 및 공지사항

    - 직원 관리

    - 시스템 관리

<br>
<br>

## 기술 스택

- **프론트엔드**: HTML, CSS, JavaScript, Thymeleaf

- **백엔드**: Java 17, Spring Boot, Spring Security, JWT, MyBatis

- **데이터베이스**: PostgreSQL

- **인프라 및 배포**: AWS (Elastic Beanstalk, S3, RDS), GitHub Actions

- **기타**: Redis, CoolSMS API

- **협업 도구**: Notion, Figma

<br>
<br>

## 협업 및 설계 문서

프로젝트 진행 전 기능 정의와 일정 계획을 문서로 정리하고, 이를 기반으로 개발을 진행했습니다.

<details>
  <summary>기능 구조도</summary>
  <br>
  <img src="./images/function_structure.png" alt="function_structure" width="600" />
</details>

<details>
  <summary>WBS</summary>
  <br>
  <img src="./images/wbs.png" alt="WBS" />
</details>

<br>
<br>

## UI 설계

![Figma](images/figma_design.png)

🔗 [Figma 바로가기](https://www.figma.com/design/aK2gKNUb8bxkMFCU6ES8Ss/%EA%B8%88%EC%9C%B5-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8?node-id=17-2979&m=dev&t=V1uoZDM5dfp42IBC-1)

<br>
<br>

## DB 설계

<details>
  <summary>ERD</summary>
  <br>
  <img src="./images/erd.png" alt="ERD" />
</details>

<details>
  <summary>테이블 정의서</summary>
  <br>
    🔗 
  <a href="https://docs.google.com/spreadsheets/d/19e_x4LEoJLsBGvr3lKOzUTOLFp19_eG0KBQx1qcyVqU/edit?usp=sharing">
    테이블 정의서 확인하기
  </a>
</details>

<br>
<br>

## 주요 구현 화면

### 메인 대시보드

업무에 필요한 정보를 확인할 수 있는 통합 대시보드입니다.

사용자 권한에 따라 메뉴가 동적으로 구성되며,

즐겨찾기 기능을 통해 자주 사용하는 메뉴를 상단에 고정할 수 있습니다.

![대시보드](images/dashboard_main.png)

<br>

### 고객 목록

고객 정보를 관리하기 위한 페이지로, 조회 및 검색 기능을 제공합니다.

여러 고객을 선택해 문자 메시지를 일괄 발송하거나 인쇄할 수 있습니다.

![고객 목록](images/customer_list.png)

<details>
  <summary>문자 발송 기능</summary>
  <br>
  <img src="./images/customer_sms.png" alt="customer_sms" />
</details>

<details>
  <summary>문자 발송 결과</summary>
  <br>
  <img src="./images/sms_result.png" alt="sms_result" width="400" />
</details>

<br>

### 고객 상세 & 상담

고객의 상세 정보를 조회하고, 고객 정보와 상담 이력을 함께 관리할 수 있는 페이지입니다.

고객 정보 수정 및 담당자 변경이 가능하며,

상담 이력 조회, 등록, 수정, 삭제 기능을 제공합니다.

![고객 상세](images/customer_detail.png)

<details>
  <summary>상담 내역 관리 기능</summary>
  <br>
  <img src="./images/consultation_list.png" alt="consultation_list" />
  <img src="./images/consultation_detail.png" alt="consultation_detail" />
</details>

<br>

### 상품 설계 조회

고객의 상품 설계 현황을 조회하고 관리하기 위한 페이지입니다.

설계 진행 상태(제안중, 만기예정 등)를 기반으로 설계를 관리할 수 있으며,

자동 업데이트와 수동 상태 변경 기능을 제공합니다.

![설계 조회](images/promotion_list.png)

<details>
  <summary>진행상태 수동 업데이트 기능</summary>
  <br>
  <img src="./images/promotion_status_update.gif" alt="promotion_status_update" />
</details>

<details>
  <summary>인쇄 기능</summary>
  <br>
  <img src="./images/promotion_print.gif" alt="promotion_print" />
</details>

<br>

### 금융 계산기

다양한 금융 상품의 설계를 수행하고, 이자 및 수익을 계산하는 페이지입니다.

상품 선택 후 금리 등 조건을 입력하면 계산 결과가 차트와 표 형태로 제공됩니다.

간편설계와 정상설계를 통해 단순 계산과 고객 기반 설계를 할 수 있습니다.

![계산기](images/promotion_calculator.png)

<br>

### 개인 일정 관리

일정을 관리할 수 있는 페이지입니다.

월별 캘린더와 오늘의 일정을 확인할 수 있으며,

일정 등록, 수정, 삭제 및 완료 여부를 관리할 수 있습니다.

![일정](images/schedule.png)

<br>

### 고객 이벤트 관리

고객의 이벤트와 상담 일정을 관리하는 페이지입니다.

캘린더를 통해 고객 생일, 만기일 등의 이벤트를 확인하고, 상담 일정을 조회 및 관리할 수 있습니다.

![이벤트](images/customer_event.png)

<br>

### 게시판

공지사항 및 일반 게시글을 관리할 수 있는 게시판 페이지입니다.

첨부파일 업로드 기능을 제공합니다.

![게시판](images/board.png)

<details>
  <summary>게시글 상세 & 댓글 기능</summary>
  <br>
  <img src="./images/board_detail.png" alt="board_detail" />
</details>

<details>
  <summary>공지사항 관리 기능</summary>
  <br>
  <img src="./images/notice_management.png" alt="notice_management" />
</details>

<br>
<br>

## 담당 역할

### 백엔드 구현

- 상품 설계 관련 테이블 설계

- 고객 상담 CRUD 및 상품·고객 조건 검색 기능

- 설계 진행상태 자동·수동 업데이트 구현

- 금융 상품별 이자 계산 로직 구현

### 프론트엔드 구현

- 고객 목록 및 상세 페이지

- 상품 설계 조회 및 금융 계산기 페이지

### 문제 해결 및 개선

- 계산 불가(null)와 정상 결과(0) 구분 문제 해결

- 데이터 정합성 문제(부모/자식 테이블 불일치) 분석 및 해결

### 프로젝트 기여

- 요구사항 정의서, 테이블 정의서, WBS 등 문서 작성 및 정리

- Figma 디자인 정리 및 일관성 개선

- 전체 UI 정비를 통한 화면 일관성 개선

<br>
<br>

## 관련 글

🔗 [프로젝트 소개 및 회고](https://velog.io/@kimkaaa/Financial-Project-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EC%86%8C%EA%B0%9C-%EB%B0%8F-%ED%9A%8C%EA%B3%A0)

🔗 [설계 조회 페이지 구현 및 트러블슈팅](https://velog.io/@kimkaaa/Financial-Project-%EC%84%A4%EA%B3%84-%EC%A1%B0%ED%9A%8C-%ED%8E%98%EC%9D%B4%EC%A7%80-%EA%B5%AC%ED%98%84-%EB%B0%8F-%ED%8A%B8%EB%9F%AC%EB%B8%94%EC%8A%88%ED%8C%85)

<br>
<br>

## 프로젝트 후기

이번 프로젝트는 기획부터 구현까지 전 과정을 보다 체계적으로 진행하려고 노력했습니다.

<br>

요구사항 정의서와 테이블 정의서 등을 작성해 기능 구조와 데이터 흐름을 정리했고,

이를 개발 과정에서 작업 기준으로 활용했습니다.

다만 문서 작성 이후 변경 사항을 지속적으로 반영하고 공유하는 부분에서는 아쉬움이 있었고,

문서를 협업 도구로 활용하기 위해서는 지속적인 업데이트와 관리가 필요하다고 느꼈습니다.

<br>

설계 조회 기능 구현 과정에서는 계산 결과가 0인 경우와 계산 불가 상태가 동일하게 표시되는 문제를 개선했습니다.

입력값 검증을 통해 null을 반환하도록 수정하고,

서비스 계층에서 "N/A"와 실제 0 값을 구분해 처리함으로써 조회 결과의 의미를 명확하게 표현했습니다.

<br>

또한 부모-자식 테이블로 분리된 설계 데이터 구조에서 데이터 누락으로 조회 값이 정상적으로 출력되지 않는 문제를 확인하고,

검증 쿼리를 통해 원인을 파악해 데이터 정합성을 개선했습니다.

<br>

협업 과정에서는 기능의 의도와 사용 흐름을 충분히 공유하는 것이 중요하다는 점을 느꼈습니다.

UI 스타일을 통일하는 과정에서 체크박스 선택 상태가 페이지 이동 후에도 유지되는 것을 확인했고

이를 오류로 판단해 수정하려 했지만, 여러 페이지에서 선택 항목을 한 번에 인쇄하기 위한 의도된 동작임을 알게 되었습니다.

이를 통해 작은 기능이라도 구현 목적과 동작 방식을 사전에 공유하는 것이 필요하다는 것을 깨달았습니다.

<br>

또한 Figma 기반으로 UI를 설계하고 공통 스타일을 적용해 화면의 일관성을 유지했으며,

검색 UX 개선과 버튼 기반 입력 등 사용자 편의성을 고려한 UI를 보완했습니다.

<br>

이번 프로젝트를 통해 설계 및 구현, UI 개선까지 전반적인 개발 흐름을 경험할 수 있었고,

특히 커뮤니케이션이 개발의 효율과 완성도에 영향을 미친다는 것을 체감할 수 있었습니다.

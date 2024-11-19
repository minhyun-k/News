<div align="center">

<!-- logo -->
<img src="https://github.com/minhyun-k/Book-IEUM/blob/main/public/loading-1.png" width="400" height="400"/>

### IEUM 🖍️

</div> 

## 📝 프로젝트 소개

**News App**은 사용자가 최신 뉴스를 효율적으로 탐색할 수 있도록 설계된 웹 애플리케이션입니다.  
- **목적**: 뉴스 데이터를 실시간으로 제공하여 사용자가 관심 있는 주제의 최신 정보를 빠르게 확인할 수 있도록 지원합니다.  
- **특징**: vue.js를 기반으로 API 통신을 구현했으며, 다양한 카테고리에서 뉴스를 검색할 수 있는 필터링 기능을 제공합니다.  
- **학습 목표**: 
  - API 호출 및 데이터 상태 관리에 대한 이해를 심화.

---

[배포사이트 링크](https://apinews-virid.vercel.app/)  
[GitHub Repository](https://github.com/minhyun-k/News.git)
<br />

## 🗓 프로젝트 일정
**총 일정 2024.06 ~ 2024.08**



<br />
## 🛠 화면 구성

|화면 명|
|:---:|
|로딩 화면|
|<img src="https://github.com/minhyun-k/Book-IEUM/blob/main/public/loading.gif" width="450"/>|
|처음 어플리케이션 실행 시 로딩화면 출력|
|메인 홈|
|:---:|
|<img src="https://github.com/minhyun-k/Book-IEUM/blob/main/public/Home.gif" width="450"/>|
|홈 화면은 서버요청을 통해 베스트셀러, 신간 등 카테고리에 맞는 데이터가 출력되어 사용자가 도서 목록을 확인할 수 있습니다.|
|도서목록|
|:---:|
|<img src="https://github.com/minhyun-k/Book-IEUM/blob/main/public/list.gif" width="450"/>|
|홈 화면에서 각 카테고리별 더보기 클릭시, 혹은 헤더 메뉴 클릭시 각 카테고리에 맞는 도서 목록이 페이지에 출력됩니다.|
|상세페이지|
|:---:|
|<img src="https://github.com/minhyun-k/Book-IEUM/blob/main/public/detail.gif" width="450"/>|
|홈, 도서목록에서 사용자가 관심있는 도서 컨텐츠를 클릭 시, 클릭한 도서의 상세정보가 포함된 페이지가 열립니다. 이 페이지에서는 도서의 상세내용, 북마크, 코멘트 작성이 가능하며, 베스트셀러의 경우 베스트 순위, 신간의 경우 신간도서 표시가 제공됩니다.|
|북마크 등록 및 코멘트 작성|
|:---:|
|<img src="https://github.com/minhyun-k/Book-IEUM/blob/main/public/detail2.gif" width="450"/>|
|북마크 클릭시 '읽는중', '읽고싶어요' 등록 가능, firebase를 통해 각 로그인한 사용자 개인 북마크 기능 활성화, 코멘트 작성 시 별점과 리뷰(댓글형식)가 표시됩니다.|
|마이페이지|
|:---:|
|<img src="https://github.com/minhyun-k/Book-IEUM/blob/main/public/mypage.gif" width="450"/>|
|로그인 시 firebase를 사용하여, 각 사용자가 사용한 북마크와 코멘트가 출력되어 사용자의 경험, 히스토리를 확인할 수 있습니다.|

<br />

## ⚙ 기술 스택

이 프로젝트는 다양한 최신 기술을 활용하여 구현되었습니다.

- **Frontend**: Vue.js, HTML5, CSS3, Sass  
- **API**: [News API](https://newsapi.org/)  
- **Vercel**: 배포 플랫폼 (배포 사이트: [https://apinews-virid.vercel.app/](https://apinews-virid.vercel.app/))
- **GitHub**: 버전 관리 및 협업 도구

<br />

## :wrench: 주요 기능 및 특징

### 1) **실시간 뉴스 제공**
- **설명**: [News API](https://newsapi.org/)를 사용해 실시간 뉴스 데이터를 가져옵니다.
- **사용 방법**: 
  - 페이지 로드 시 기본적으로 주요 헤드라인을 표시.
  - 각 뉴스 아이템은 제목, 설명, 이미지, 출처 링크를 포함.

### 2) **카테고리 필터링**
- **설명**: 사용자는 스포츠, 경제, 기술, 엔터테인먼트 등 다양한 카테고리로 뉴스를 필터링할 수 있습니다.
- **특징**: 선택된 카테고리에 따라 API 요청 URL을 동적으로 변경.

### 3) **상세 뉴스 페이지**
- **설명**: 뉴스 카드 클릭 시 해당 뉴스의 상세 내용을 확인할 수 있는 별도의 페이지로 이동.
- **추가 정보**: 기사 원문 링크 제공으로 출처 명확화.

### 4) **반응형 디자인**
- **설명**: 모바일, 태블릿, 데스크톱 등 다양한 화면 크기에 최적화된 사용자 경험 제공.
- **기술 사용**: CSS Grid 및 Flexbox를 활용한 유연한 레이아웃 구성.

### 5) **로딩 상태 시각화**
- **설명**: API 응답 대기 시간 동안 로딩 인디케이터 표시.
- **사용 이유**: 사용자 경험 개선 및 빈 화면 방지.

---
<br />

## 🤔 기술적 이슈와 해결 과정

### 1) **API 요청 관리**  
- **문제**: News API는 하루 요청 횟수에 제한(무료 플랜 기준)이 있어 반복 요청 시 에러 발생.  
- **해결 방법**: 
  1. **초기 데이터 캐싱**: 동일한 데이터를 반복 요청하지 않도록 React의 상태로 데이터를 관리.
  2. **효율적인 데이터 요청**: 
     - 카테고리 변경 시 필요한 데이터만 요청하도록 설계.
     - 서버 응답이 없을 때 기본 데이터를 표시하여 사용자 경험을 유지.

### 2) **카테고리별 데이터 로드 딜레이**  
- **문제**: API 응답 시간이 길어 페이지 전환 시 지연 발생.  
- **해결 방법**:
  - React의 `useEffect`와 비동기 함수를 활용하여 API 호출 및 데이터 로드를 비동기적으로 처리.
  - 로딩 상태 표시기를 추가하여 사용자에게 진행 상태를 명확히 전달.

### 3) **레이아웃 깨짐 현상**  
- **문제**: 뉴스 카드 레이아웃이 특정 화면 크기에서 깨지는 문제.  
- **해결 방법**:
  - CSS 단위를 고정 값(`px`)에서 상대 단위(`%, rem, vw/vh`)로 변경.
  - 반응형 디자인을 위한 미디어 쿼리(`@media`) 적용으로 모든 디바이스에서 안정적 표시.

---

<br />

##  :file_folder: 폴더 구조
📂 src
 ┣ 📂 components         # 공통 컴포넌트 폴더
 ┃ ┣ 📜 Header.jsx       # 헤더 UI 컴포넌트
 ┃ ┣ 📜 Footer.jsx       # 푸터 UI 컴포넌트
 ┃ ┗ 📜 NewsCard.jsx     # 뉴스 카드 컴포넌트
 ┣ 📂 pages              # 주요 페이지
 ┃ ┣ 📜 Home.jsx         # 메인 페이지
 ┃ ┗ 📜 Detail.jsx       # 뉴스 상세 페이지
 ┣ 📂 assets             # 정적 리소스 (이미지, 아이콘 등)
 ┣ 📂 utils              # 유틸리티 함수
 ┃ ┗ 📜 api.js           # API 호출 함수
 ┣ 📜 App.js             # 메인 애플리케이션 파일
 ┗ 📜 index.js           # React DOM 렌더링

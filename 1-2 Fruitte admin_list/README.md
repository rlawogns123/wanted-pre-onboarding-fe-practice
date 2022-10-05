# wanted-pre-onboarding-fruitte 과제

# 목차

- [실행](#1-실행)
- [폴더구조](#2-폴더구조)
- [과제 달성 사항 및 해결 방법](#3과제-달성-사항-및-해결-방법)

## 팀원


| 이름                                   | 역할                                                                                               |
| -------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [김재훈](https://github.com/rmawogns)  | 관리 페이지 상품 삭제, 노출 여부 조정 기능 구현.                                                   |
| [노기훈](https://github.com/ch4md0m)   | 관리자 상품 등록 페이지 구현, 초기 셋팅.                                                           |
| [유지예](https://github.com/jiye-7)    | 상품 결제 페이지/상품 정보, 배송정보(도로 api 연동), 주문 요약, 결제 수단, 동의 및 결제 기능 구현. |
| [이우윤](https://github.com/EEOOOO)    | 상품 상세 페이지 구현, 상품 옵션 입력 받아 주문 페이지 전달기능 구현.                              |
| [백광현](https://github.com/ghbaekdev) | 상세, 주문 페이지에서 전달된 데이터를 바탕으로 주문 확인 페이지 구현.                              |
| [정진우](https://github.com/jinux127)  | 관리페이지 페이지네이션, 스타일 적용.                                                              |
| [정현준](https://github.com/wjd2676)   | 상품 리스트 페이지 구현, product.json 작성.       


## Tech Stack

<div>
    <img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=white">
    <img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black">
    <img src="https://img.shields.io/badge/styled components-DB7093?style=for-the-badge&logo=styled-components&logoColor=white">
    <img src="https://img.shields.io/badge/MUI-007FFF?style=for-the-badge&logo=mui&logoColor=white">
    <img src="https://img.shields.io/badge/RECOIL-764ABC?style=for-the-badge&logo=recoil&logoColor=white">
</div>

<br/>
<br/>
 
## 1. 실행
### 실행 방법

```sh
npm install

npm run start
```

<br/>

### 데모 링크

### [🚀🚀 fruitte 보러가기](https://bright-longma-5a20b7.netlify.app/)

<br/>
<br/>

## 2. 폴더구조

```
├── package-lock.json
├── package.json
├── public
│   ├── data
│   │   ├── blog_link.json
│   │   └── product.json
│   └── index.html
├── src
│   ├── App.js
│   ├── api
│   │   ├── BlogLinkApi.js
│   │   ├── GetproductApi.js
│   │   ├── adminApi.js
│   │   └── index.js
│   ├── assets
│   │   └── a.img
│   ├── components
│   │   ├── CardContainer
│   │   │   ├── Card
│   │   │   │   └── index.js
│   │   │   ├── CardList
│   │   │   │   └── index.js
│   │   │   ├── CardListButtons
│   │   │   │   └── index.js
│   │   │   ├── CardPrice
│   │   │   │   └── index.js
│   │   │   ├── CardProperty
│   │   │   │   └── index.js
│   │   │   └── index.js
│   │   ├── Footer
│   │   │   ├── index.jsx
│   │   │   └── style.js
│   │   ├── IntroduceLink
│   │   │   └── index.js
│   │   ├── Links
│   │   │   ├── index.jsx
│   │   │   └── style.js
│   │   ├── Navbar
│   │   │   ├── index.jsx
│   │   │   └── style.js
│   │   ├── Pagination
│   │   │   └── index.jsx
│   │   ├── Sidebar
│   │   │   ├── index.jsx
│   │   │   └── style.js
│   │   ├── Table
│   │   │   ├── TableBody
│   │   │   │   ├── index.jsx
│   │   │   │   └── style.js
│   │   │   ├── TableHeader
│   │   │   │   ├── index.jsx
│   │   │   │   └── style.js
│   │   │   ├── index.jsx
│   │   │   └── style.js
│   │   └── introduceContent
│   │       ├── CommentData.js
│   │       └── index.js
│   ├── constants
│   │   └── data
│   │       └── product.json
│   ├── hooks
│   │   └── hooks.js
│   ├── index.js
│   ├── layouts
│   │   └── index.jsx
│   ├── pages
│   │   ├── AddProduct.js
│   │   ├── Admin.js
│   │   ├── AdminProduct.js
│   │   └── List.js
│   ├── store
│   │   └── store.js
│   ├── styles
│   │   ├── globalStyle.js
│   │   └── theme.js
│   └── utils
│       ├── links.js
│       └── utils.js
└── yarn.lock
```

## 3.과제 달성 사항 및 해결 방법

### 3.1.사용자 기능

#### 스토어 상품목록 조회

- 상품 List를 10개단위 페이지네이션으로 구현했습니다.
- 상품을 클릭했을 때, /list ⇒ /detail/${id} 로 넘어가게 params를 구현했습니다.

#### 스토어 상품 상세조회

- 상품 목록에서 클릭된 단일 상품 데이터 송/수신
- 상품에 대한 옵션 선택 기능 : 옵션은 5개까지 선택 가능하도록 우선 설정
- 옵션 별 수량 수정 기능 : 수정된 수량 별로 해당 옵션에 해당하는 금액 업데이트
- 전체 옵션 별 수량, 가격 데이터로 해당 상품 총 가격 계산해 렌더링
- 주문 버튼 클릭 시 상품 데이터와 선택한 옵션 데이터 묶어 전송

#### 스토어 상품 주문

- 주문 상품 정보 리코일에 저장한 상품 값 핸들링
- 주문자 정보를 입력받아 처리
- 배송 정보 중 수령인, 연락처는 주문자 정보와 동일하게 처리 할 수 있도록 구현
- 주소 api 를 통한 주소를 입력
- 배송 메모는 선택, 직접입력 가능
- 결제 수단이 무통장일 때 현금 영수증 신청 가능하도록 처리
- 동의/결제까지 필수 정보들이 다 충족되야만 결제요청을 보내도록 처리

#### 스토어 상품 주문 내역확인

- 주문페이지에서 저장된 상품값 리스트로 구현.
- 뒤로가기 버튼 및 홈으로 가기 버튼 구현

### 3.2.관리자 기능

#### 스토어 상품목록 등록 페이지

#### 스토어 상품목록 관리 페이지

```js
├── Table
│   │   │   ├── TableBody
│   │   │   │   ├── index.jsx
│   │   │   │   └── style.js
│   │   │   ├── TableHeader
│   │   │   │   ├── index.jsx
│   │   │   │   └── style.js
│   │   │   ├── index.jsx
│   │   │   └── style.js\
├── Pagination
│   │   │   └── index.jsx
```

- 재사용을 위해 테이블 컴포넌트와 페이지네이션 컴포넌트로 구현하였습니다.
- 삭제기능: 현재 테이블에서 삭제
- 노출여부 변경: 버튼 토글

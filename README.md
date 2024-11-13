# 전자담배 액상 확인 프로젝트

https://kshpf.netlify.app
<br/><br/>
# 📋 프로젝트 개요

- 전자담배 액상 정보를 정보를 확인할 수 있는 사이트입니다.
- 지속적으로 개선 및 최신 기술을 학습할 수 있는 프로젝트입니다.
<br/><br/>
# 🏗️ 페이지 소개

## 메인페이지
[![mainpage.png](https://i.postimg.cc/MGS5th9V/mainpage.png)](https://postimg.cc/LJxj80K8)
- Sass로 전반적인 레이아웃을 잡았습니다.
- 모바일 유저 고려 모든 페이지를 반응형 웹 페이지로 제작하였습니다.
- context 전역 상태를 이용해 다크모드를 구현하였습니다.

## 상품 리스트 페이지
[![listPage.png](https://i.postimg.cc/SKnCh4Dw/listPage.png)](https://postimg.cc/yJzkmMqP)
- 현재 상품 목록의 카테고리와 일치하는 스와이퍼 부분을 활성화시켜 보여줍니다.
- 카테고리와 일치하는 상품 목록을 네트워크 통신을 통해서 firebase DB에서 가져옵니다.
- 네트워크 통신이 발생 시 사용자 경험을 고려해 react-router-dom의 lazy 기능을 사용해서 로딩 화면을 일시적으로 나타납니다.
- staleTime을 6분으로 설정하여 데이터를 최신 상태로 유지하고 6분 동안은 캐시된 데이터를 사용하도록 구성했습니다

## 제품 상세 페이지
[![detail-Page.png](https://i.postimg.cc/4xZWsY9j/detail-Page.png)](https://postimg.cc/cr9Rc4Tc)
- 상품의 정보와 해당 상품의 맛 분포를 한눈에 보기 쉽게 각각 그래프로 시각화해서 보여줍니다.
- 현재 상품의 카테고리와 일치하는 카테고리 버튼을 활성화시켜 사용자에게 보여줍니다.
- 북마크 버튼 클릭 시 북마크 완료 팝업이 나타나며 해당 아이템의 정보를 localStorage에 저장합니다.

## 북마크 페이지
[![bookmark-Page.png](https://i.postimg.cc/mZHj9Y30/bookmark-Page.png)](https://postimg.cc/z3qTZRcj)
- 북마크 페이지 진입 시 localStorage에 북마크 상품 유무에 따라서 조건부로 화면을 랜더링합니다.
- 북마크 상품 클릭 시 상품 상세 페이지로 이동합니다.
- 북마크 상품 삭제 버튼 클릭 시 localStorage에서 해당 상품을 삭제합니다.
<br/><br/>
# 👷 기능 구현사항
- 반응형
- 다크모드 구현
- 상품 검색 기능
- 상품 북마크 기능
- 스와이퍼 애니매이션 
- 카테고리 필터 기능


<br/>

# ⚙️ 기술스택

### React
### tanstack query, react-router, swiper, firebase
### Sass


<br/>

# 📁 폴더 구조

```
📦src
 ┣ 📂api
 ┃ ┣ 📂crud  # 데이터 통신을 위한 폴더
 ┃ ┃ ┗ 📜crud.js
 ┃ ┣ 📂radarData
 ┃ ┃ ┗ 📜extractRadarData.js
 ┃ ┗ 📂suspense
 ┃ ┃ ┗ 📜suspense.jsx
 ┣ 📂components  # 페이지 구성 컴포넌트 / 공통 컴포넌트 포함
 ┃ ┣ 📂Banner
 ┃ ┃ ┣ 📜Banner.jsx
 ┃ ┃ ┗ 📜Banner.module.scss
 ┃ ┣ 📂BannerSwiper
 ┃ ┃ ┣ 📜Banner__swiper.jsx
 ┃ ┃ ┗ 📜Banner__swiper.module.scss
 ┃ ┣ 📂BarGraph
 ┃ ┃ ┣ 📜Bar__graph.jsx
 ┃ ┃ ┗ 📜Bar__graph.module.scss
 ┃ ┣ 📂FixScroll
 ┃ ┃ ┗ 📜Fix__scroll.jsx
 ┃ ┣ 📂FlavorCategories
 ┃ ┃ ┣ 📜Flavor__categories.jsx
 ┃ ┃ ┗ 📜Flavor__categories.module.scss
 ┃ ┣ 📂FlavorIcon
 ┃ ┃ ┣ 📜Flavor__icon.jsx
 ┃ ┃ ┗ 📜Flavor__icon.module.scss
 ┃ ┣ 📂Header
 ┃ ┃ ┣ 📜Header.jsx
 ┃ ┃ ┗ 📜Header.module.scss
 ┃ ┣ 📂Item
 ┃ ┃ ┣ 📜Item.jsx
 ┃ ┃ ┗ 📜Item.module.scss
 ┃ ┣ 📂ItemImageContainer
 ┃ ┃ ┣ 📜Item__image__container.jsx
 ┃ ┃ ┗ 📜Item__image__container.module.scss
 ┃ ┣ 📂Items
 ┃ ┃ ┣ 📜Items.jsx
 ┃ ┃ ┗ 📜Items.module.scss
 ┃ ┣ 📂List__item
 ┃ ┃ ┣ 📜List__item.jsx
 ┃ ┃ ┗ 📜List__item.module.scss
 ┃ ┣ 📂Loading
 ┃ ┃ ┣ 📜Loading.jsx
 ┃ ┃ ┗ 📜Loading.module.scss
 ┃ ┣ 📂Notice
 ┃ ┃ ┣ 📜Notice.jsx
 ┃ ┃ ┗ 📜Notice.module.scss
 ┃ ┣ 📂Popup
 ┃ ┃ ┣ 📜Popup.jsx
 ┃ ┃ ┗ 📜Popup.module.scss
 ┃ ┣ 📂RadarChart
 ┃ ┃ ┣ 📜Radar__chart.jsx
 ┃ ┃ ┗ 📜Radar__chart.module.scss
 ┃ ┗ 📂Search__bar
 ┃ ┃ ┣ 📜Search__bar.jsx
 ┃ ┃ ┗ 📜Search__bar.module.scss
 ┣ 📂context  # 다크모드 상태 변경 위한 context
 ┃ ┗ 📜Dark__mode__context.jsx
 ┣ 📂data  # 고정 데이터
 ┃ ┗ 📜data.js
 ┣ 📂layout
 ┃ ┣ 📜Root.jsx
 ┃ ┗ 📜Root.module.scss
 ┣ 📂pages
 ┃ ┣ 📜Bookmark__page.jsx
 ┃ ┣ 📜Items__page.jsx
 ┃ ┣ 📜Item__detail__page.jsx
 ┃ ┣ 📜Main.jsx
 ┃ ┗ 📜Search__result__page.jsx
 ┣ 📂styles  # css 관리 폴더
 ┃ ┣ 📂pages
 ┃ ┃ ┣ 📜Bookmark__page.module.scss
 ┃ ┃ ┣ 📜ItemsPage.module.scss
 ┃ ┃ ┣ 📜Item__detail__page.module.scss
 ┃ ┃ ┣ 📜Main.module.scss
 ┃ ┃ ┗ 📜Search__result__page.module.scss
 ┃ ┣ 📂utils
 ┃ ┃ ┣ 📜theme.scss
 ┃ ┃ ┣ 📜_darkMode.scss
 ┃ ┃ ┣ 📜_global.scss
 ┃ ┃ ┣ 📜_index.scss
 ┃ ┃ ┣ 📜_mixins.scss
 ┃ ┃ ┣ 📜_reset.scss
 ┃ ┃ ┗ 📜_variables.scss
 ┃ ┗ 📜index.scss
 ┣ 📜App.jsx
 ┗ 📜router.jsx  # 라우터 구성 파일
```
<br/>

# 🚀 미해결 이슈 & 개선 가능 사항

- 접근성
- 에러 핸들링
- 상품 리뷰 기능 구현
- 로그인 / 회원가입
- 이미지 파일 webp 변환
